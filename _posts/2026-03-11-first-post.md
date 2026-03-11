---
layout: post
title: "The Secret Low-Rank Bias of Regularized SGD"
date: 2026-03-11
author: Tomer Galanti
tags: [deep learning, optimization, SGD, weight decay, theory, low-rank]
excerpt: "A simple view of why mini-batch SGD with weight decay implicitly pushes neural networks toward low-rank weight matrices."
---

Deep networks are often massively overparameterized, yet the solutions found in practice are far from arbitrary. Even when a model has enough capacity to memorize the data in many different ways, stochastic gradient descent tends to land on solutions with structure.

One particularly interesting form of structure is **low rank**.

Across many architectures, learned weight matrices often end up being much more compressible than their ambient dimension would suggest. This shows up in pruning, distillation, and low-rank approximations of trained models. But where does this structure actually come from?

A lot of prior theory has tried to explain low-rank behavior in neural networks, but most existing results only apply under fairly restrictive assumptions: special data geometry, linear networks, special losses, or global optimality conditions. What has been missing is a general explanation that applies to the way deep networks are actually trained in practice: **mini-batch SGD with weight decay**.

This is the main point of our work:

> **SGD with weight decay implicitly biases neural networks toward low-rank weight matrices, and this effect becomes stronger with smaller batch size, larger learning rate, and stronger weight decay.**

The nice part is that this is not a statement about a special dataset or a special optimum. It comes directly from the training dynamics.

## Related work and the gap

There is already a rich literature showing that neural networks often become highly compressible after training. Many weights can be pruned, large models can be distilled, and in many cases trained weight matrices can be approximated well by low-rank factors.

There is also theoretical work on low-rank bias in optimization. But those results usually focus on narrow settings, such as:

- linear or nearly linear models,
- linearly separable data,
- special losses like exponential or logistic loss,
- global minimizers of regularized objectives,
- only particular layers in the network.

Those results are valuable, but they do not quite explain the broader empirical pattern seen in modern deep learning.

Our goal is different. We ask:

**Can standard mini-batch SGD with weight decay, by itself, induce a general low-rank bias across a broad class of architectures?**

Our answer is yes.

## The setup

We train a neural network by minimizing the regularized empirical loss

\[
L_S^\lambda(W)
=
\frac{1}{m}\sum_{i=1}^m \ell_i(h_W(x_i)) + \lambda \|W\|_F^2.
\]

To focus on one layer, write the network locally as

\[
h(x) = g(W f(x)).
\]

Here:

- `f(x)` is the feature vector entering the layer,
- `W` is the weight matrix of that layer,
- `g` represents everything that happens after that layer.

For this layer, the mini-batch SGD update with weight decay is

\[
W_{t+1}
=
W_t - \mu \nabla_W L_{\tilde S_t}(W_t) - 2\mu\lambda W_t,
\]

or equivalently,

\[
W_{t+1}
=
(1 - 2\mu\lambda) W_t - \mu G_t,
\]

where \(G_t := \nabla_W L_{\tilde S_t}(W_t)\) is the stochastic gradient on the current mini-batch.

This formula already contains the whole story.

## The key observation

The key point is simple:

> **Each stochastic gradient is low rank.**

For a fully connected layer, the gradient of the loss with respect to \(W\) for a single sample has the form

\[
\nabla_W \ell(h_W(x))
=
\delta(x) f(x)^\top,
\]

which is an outer product, hence rank 1.

For more general layers such as convolutions, the gradient is still a sum of a small number of outer products, so its rank is bounded by a layer-dependent constant. For a mini-batch of size \(B\), the stochastic gradient is then a sum over the samples in the batch, so its rank scales like

\[
\operatorname{rank}(G_t) \lesssim B \cdot m_\ell,
\]

where \(m_\ell\) depends on the layer.

So every SGD step adds a **low-rank update**.

Now combine that with weight decay. The factor \((1 - 2\mu\lambda)\) shrinks the previous iterate at every step. Older contributions are exponentially forgotten, while recent low-rank stochastic gradients keep getting added.

That means the current weight matrix is mostly a mixture of **recent low-rank updates**.

And a mixture of only a limited number of low-rank updates is itself low rank, or at least close to low rank.

## Proof sketch

The proof is short and quite intuitive.

Starting from the SGD + weight decay update,

\[
W_{t+1}
=
(1 - 2\mu\lambda) W_t - \mu G_t,
\]

we can unroll the recursion for \(n\) steps:

\[
W_T
=
(1 - 2\mu\lambda)^n W_{T-n}
-
\mu \sum_{j=1}^n (1 - 2\mu\lambda)^{j-1} G_{T-j}.
\]

This decomposition has two parts.

### 1. An old-memory term

The term

\[
(1 - 2\mu\lambda)^n W_{T-n}
\]

is the contribution of the distant past. Because of weight decay, it gets exponentially damped as \(n\) grows.

### 2. A recent-update term

The sum

\[
\sum_{j=1}^n (1 - 2\mu\lambda)^{j-1} G_{T-j}
\]

contains only the last \(n\) stochastic gradients. Each one has rank at most on the order of \(m_\ell B\), so the whole sum has rank at most on the order of

\[
m_\ell B n.
\]

So the final weight matrix \(W_T\) can be written as:

- an exponentially small leftover from the distant past, plus
- a matrix of rank at most about \(m_\ell B n\).

This immediately implies that \(W_T\) is close to a low-rank matrix.

Now choose \(n\) so that the exponentially decayed old-memory term is at most \(\varepsilon\). Since the decay is exponential, this gives

\[
n \approx \frac{\log(1/\varepsilon)}{\mu\lambda}.
\]

Plugging this into the rank bound yields an effective-rank estimate of the form

\[
\operatorname{rank}_\varepsilon(W_T)
\lesssim
\frac{m_\ell B \log(1/\varepsilon)}{\mu\lambda}.
\]

This already explains the hyperparameter dependence:

- **smaller batch size \(B\)** leads to lower rank,
- **larger learning rate \(\mu\)** leads to lower rank,
- **larger weight decay \(\lambda\)** leads to lower rank.

It also explains why **weight decay is essential**. Without weight decay, there is no exponential forgetting, so the weights are not forced to stay close to a sum of only recent low-rank updates.

## What the experiments show

The empirical results match the theory quite well.

Across a range of architectures, including MLPs, ResNets, VGG, and ViTs, the effective rank of the learned weight matrices decreases when:

- the batch size gets smaller,
- the learning rate gets larger,
- the weight decay gets stronger.

One especially revealing observation is that when weight decay is removed, the effect of batch size on rank becomes much weaker. This is exactly what the theory predicts. Batch size controls the rank of the stochastic gradients, but weight decay is what creates the forgetting mechanism that turns those low-rank updates into a persistent low-rank bias.

We also looked at generalization. Lower-rank solutions often showed slightly better test performance when comparing models that all fit the training data well, but the effect was modest. So low rank does not seem to be the whole story behind generalization. Still, it does appear to be one meaningful structural bias induced by the optimizer.

## Why this perspective is useful

I think there are three nice takeaways here.

First, it gives a concrete interpretation of weight decay beyond just norm shrinkage. Weight decay does not merely keep parameters small. In combination with SGD, it creates a kind of **short-term memory** in the optimization dynamics: old updates are forgotten exponentially fast, and recent low-rank updates dominate the current weights.

Second, it explains why common hyperparameters affect compressibility. Smaller batch size, larger learning rate, and stronger weight decay do not just change optimization speed or gradient noise. They directly change the effective rank profile of the learned matrices.

Third, it suggests that low-rank structure may be a fairly universal byproduct of standard training, rather than a curiosity tied to a few special models or datasets.

## A simple mental picture

A useful way to think about the result is this:

At every step, SGD writes a low-rank note into the weights. Weight decay slowly erases the old notes. After long training, what remains is mostly a superposition of the most recent few notes. That naturally limits the effective rank.

Without weight decay, the notebook never forgets. The notes just accumulate, and the low-rank bias becomes much weaker.

## Insights and conclusions

The main message is simple:

> **SGD plus weight decay does more than optimize the loss. It quietly pushes neural networks toward low-rank structure.**

And the mechanism is surprisingly clean:

1. each stochastic gradient is low rank,  
2. weight decay exponentially forgets older updates,  
3. so the current weights are close to a sum of only recent low-rank updates.

This gives a direct explanation for why lower batch size, larger learning rate, and stronger weight decay all encourage lower-rank weight matrices.

That does **not** mean every trained network becomes genuinely low rank, nor that low rank alone explains generalization. But it does mean that one of the most common optimization recipes in deep learning carries a very specific structural bias, and that bias is strong enough to show up clearly both in theory and in experiments.

Understanding these hidden biases matters. They help explain not only why deep networks fit data, but what kinds of solutions they prefer while doing so.
