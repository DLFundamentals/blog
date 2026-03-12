---
layout: post
title: "Why SGD Prefers Low-Rank Neural Networks"
date: 2026-03-11
author: Tomer Galanti
tags:
  - deep-learning
  - optimization
  - stochastic-gradient-descent
  - weight-decay
  - theory
  - low-rank
excerpt: "Why mini-batch SGD with weight decay implicitly pushes neural networks toward low-rank weight matrices."
---

Deep networks are massively overparameterized, yet the solutions found in practice are far from arbitrary. Even when a model has enough capacity to fit the data in many different ways, stochastic gradient methods often converge to highly structured solutions.

One especially striking form of structure is **low rank**.

Across architectures, trained weight matrices are often far more compressible than their ambient dimension would suggest. This phenomenon shows up in pruning, distillation, and post-hoc low-rank approximations of trained networks. Empirically, low-rank structure is everywhere. But why should training produce it in the first place?

A good deal of prior theory explains low-rank behavior only in settings much cleaner than modern practice: linear models, very special losses, exact symmetries, or global optimality conditions. What is still missing is a simple structural explanation for the regime practitioners actually use every day: **mini-batch SGD with weight decay.**

The main message of this post is the following:

> <span style="color:#1e6bd6; font-weight:600;">
> SGD with weight decay implicitly biases each layer toward low-rank structure, and this effect becomes stronger with smaller batch size, larger learning rate, and stronger weight decay.
> </span>

<div style="margin: 2rem 0;">
  <div style="display: grid; grid-template-columns: repeat(4, 1fr); gap: 20px; align-items: start;">

    <div style="text-align: center;">
      <img src="{{ '/assets/figures/low-rank-bias/contour_resnet_bs_8.png' | relative_url }}" style="width:100%; max-width:220px;">
      <div><strong>(a)</strong> \(B = 8\)</div>
    </div>

    <div style="text-align: center;">
      <img src="{{ '/assets/figures/low-rank-bias/contour_resnet_bs_16.png' | relative_url }}" style="width:100%; max-width:220px;">
      <div><strong>(b)</strong> \(B = 16\)</div>
    </div>

    <div style="text-align: center;">
      <img src="{{ '/assets/figures/low-rank-bias/contour_resnet_lr_5.png' | relative_url }}" style="width:100%; max-width:220px;">
      <div><strong>(c)</strong> \(\mu = 0.5\)</div>
    </div>

    <div style="text-align: center;">
      <img src="{{ '/assets/figures/low-rank-bias/contour_resnet_wd_6e-3.png' | relative_url }}" style="width:100%; max-width:220px;">
      <div><strong>(d)</strong> \(\lambda = 6 \times 10^{-3}\)</div>
    </div>

  </div>
</div>

  <div style="margin-top: 1rem; font-size: 1.02rem; line-height: 1.5; text-align: left;">
    <strong>Figure 1.</strong>
    <strong>Higher weight decay (\(\lambda\)) and learning rate (\(\mu\)), or smaller batch sizes (\(B\)), lead to a lower average rank across the network layers.</strong>
    We plot the average rank at the end of training for ResNet-18 trained on CIFAR-10 while varying a pair of hyperparameters.
  </div>

<br>

The mechanism is simple:

1. each stochastic gradient step adds only a low-rank update,
2. weight decay prevents the layer from remembering too much of the distant past,
3. so the current matrix is dominated by a relatively short history of low-rank corrections.

That is the whole story. Everything below just makes this precise.

## The local view of one layer

To isolate the mechanism, fix all parameters except one trainable matrix $W$. We look at the network locally around that layer.

In the simplest case, the network can be written as

$$
h_W(x) = g(Wf(x)).
$$

Here:
- $f(x)$ is the representation entering the layer,
- $W$ is the matrix we want to study,
- $g$ collects everything that happens after this layer.

This is the cleanest setting, and it already reveals the essential phenomenon.

Later we will return to residual blocks, convolutions, and self-attention, where the same matrix may be reused multiple times within a single example. But it is worth emphasizing that the basic decomposition above is not artificial. It is exactly the right local view whenever a matrix is used once along the computation path.

We train with regularized empirical loss

$$
L_S^\lambda(W) = \frac{1}{m}\sum_{i=1}^m \ell_i(h_W(x_i)) + \lambda \|W\|_F^2.
$$

Under mini-batch SGD with weight decay, the layer update is

$$
W_{t+1} = W_t - \mu \nabla_W L_{\tilde S_t}(W_t) - 2\mu\lambda W_t,
$$

where $\mu$ is the learning rate, $\lambda$ is the weight decay coefficient, and $\tilde S_t$ is the mini-batch at step $t$.

Equivalently,

$$
W_{t+1} = (1 - 2\mu\lambda)W_t - \mu G_t,
$$

where

$$
G_t := \nabla_W L_{\tilde S_t}(W_t).
$$

This decomposition already suggests the answer. The previous weight matrix is shrunk by the factor $1-2\mu\lambda$, and then a fresh stochastic gradient update is injected. So the main question becomes:

> **What kind of matrix is $G_t$?**

## Step 1: one example gives a rank-1 gradient

Consider a single training example $x$. Since

$$
h_W(x) = g(Wf(x)),
$$

the chain rule gives

$$
\nabla_W \ell(h_W(x)) = \Big(J_g(Wf(x))^\top \nabla_h \ell(h_W(x))\Big) f(x)^\top.
$$

Define

$$
\delta(x) := J_g(Wf(x))^\top \nabla_h \ell(h_W(x)).
$$

Then

$$
\nabla_W \ell(h_W(x)) = \delta(x) f(x)^\top.
$$

This is an outer product of two vectors. Therefore,

$$
\operatorname{rank}\big(\nabla_W \ell(h_W(x))\big) \le 1.
$$

So a **single-example gradient is rank 1**.

This is the key observation. The gradient of the loss with respect to a layer matrix is not an arbitrary full-rank matrix. For one example, it has the simplest possible structure: one left direction times one right direction.

## Step 2: a mini-batch still gives a low-rank update

Now suppose the mini-batch size is $B$. The stochastic gradient is the average of $B$ single-example gradients:

$$
G_t = \frac{1}{B}\sum_{i=1}^B \delta_i f_i^\top.
$$

Since each term is rank 1, the whole mini-batch gradient satisfies

$$
\operatorname{rank}(G_t) \le B.
$$

So every SGD step adds a matrix whose rank is at most the batch size.

This is already informative:
- **smaller batch size** means lower-rank updates,
- **larger batch size** allows higher-rank updates.

At this stage, one can already see why SGD is different from a generic optimization procedure. It does not update a layer with an arbitrary matrix. It writes only a small number of directions at each step.

But this alone is not enough. If we kept accumulating low-rank updates forever with no forgetting, the sum could eventually become high rank. The second half of the story is what prevents that.

## Step 3: weight decay limits memory

Return to the recursion

$$
W_{t+1} = (1 - 2\mu\lambda)W_t - \mu G_t.
$$

Unrolling this recursion for $n$ steps gives

$$
W_T = (1-2\mu\lambda)^n W_{T-n} - \mu \sum_{j=1}^n (1-2\mu\lambda)^{j-1} G_{T-j}.
$$

This identity is the heart of the argument.

It says that the current matrix $W_T$ is made of two parts:

1. a decayed memory of the older past,
2. a weighted sum of recent stochastic gradients.

The first term,

$$
(1-2\mu\lambda)^n W_{T-n},
$$

shrinks exponentially with $n$. So if we look back far enough, the contribution of old history becomes negligible.

The second term is a sum of recent mini-batch gradients. But each one of those gradients is low rank.

So after enough training, the current matrix is well approximated by a weighted sum of only **recent low-rank updates**.

That is exactly the mechanism that produces low-rank structure.

Another way to say it is this:
- SGD writes only a few directions per step,
- weight decay stops the layer from keeping too many old directions alive at once.

The matrix therefore behaves less like a full memory of the entire training trajectory, and more like a short moving window of recent low-rank corrections.

<div style="text-align:center; margin: 2rem 0;">
  <img src="{{ '/assets/figures/low-rank-bias/sgd_low_rank_mechanism.png' | relative_url }}" style="width:100%; max-width:950px;">
</div>

## An effective-rank interpretation

The previous argument can be turned into a crude but useful effective-rank bound.

Choose $n$ so that the old-memory term is at most $\varepsilon$ in norm:

$$
\|(1-2\mu\lambda)^n W_{T-n}\| \le \varepsilon \|W_T\|.
$$

Since

$$
(1-2\mu\lambda)^n \approx e^{-2\mu\lambda n},
$$

this happens for

$$
n \approx \frac{\log(1/\varepsilon)}{\mu\lambda}.
$$

Now the recent-history term is a sum of $n$ gradients, each with rank at most $B$. Therefore its rank is at most $nB$. This gives the heuristic effective-rank estimate

$$
\operatorname{rank}_\varepsilon(W_T) \lesssim \frac{B\log(1/\varepsilon)}{\mu\lambda}.
$$

Here $\operatorname{rank}_\varepsilon$ denotes the minimum rank of a matrix that approximates $\frac{W_T}{\lVert W_T \rVert}$ up to error $\varepsilon$.

This bound is not meant to be sharp. Its value is conceptual. It captures the correct qualitative dependencies:
- smaller batch size $\Rightarrow$ lower effective rank,
- larger learning rate $\Rightarrow$ shorter memory $\Rightarrow$ lower effective rank,
- larger weight decay $\Rightarrow$ shorter memory $\Rightarrow$ lower effective rank.

This is exactly the trend often seen in practice.

## Why the decomposition is natural

At first glance, the representation

$$
h_W(x)=g(Wf(x))
$$

may look like a special case. In fact, it is the correct local view for a very broad family of layers.

The idea is simple: fix all parameters except one matrix $W$, and isolate the place in the computation where that matrix acts. Then:
- $f(x)$ is whatever enters that linear map,
- $Wf(x)$ is the output of that linear map,
- $g$ absorbs everything that happens afterward.

For a standard fully connected layer, this is immediate.

For a residual architecture, the same local picture still applies. If the block has the form

$$
u(x) + \tilde g(Wf(x)),
$$

then we simply absorb the skip path into the downstream function and define

$$
g(z) := u(x) + \tilde g(z).
$$

So again,

$$
h_W(x)=g(Wf(x)).
$$

Thus the one-use model already covers dense layers and matrices inside residual blocks. It is not an artificial simplification. It is the basic local geometry of backpropagation through a single matrix.

## When the same matrix is used many times

The only point where the rank-1 statement changes is when the same matrix $W$ is reused multiple times within one example.

This happens in several important settings:
- convolutions, where the same kernel is applied at many spatial locations,
- self-attention projections $W_Q$, $W_K$, $W_V$, where the same matrix is applied to every token,
- more generally, any shared linear operator.

In that case, the right local description is

$$
h_W(x)=g(WF(x)),
$$

where

$$
F(x) = [f_1(x),\dots,f_R(x)]
$$

collects all $R$ local inputs on which the same matrix acts.

The chain rule then gives

$$
\nabla_W \ell(h_W(x)) = \Delta(x) F(x)^\top,
$$

where $\Delta(x)$ collects the corresponding backpropagated error vectors.

Equivalently,

$$
\nabla_W \ell(h_W(x)) = \sum_{r=1}^R \delta_r(x) f_r(x)^\top.
$$

Therefore,

$$
\operatorname{rank}\big(\nabla_W \ell(h_W(x))\big) \le R.
$$

So the single-example gradient is no longer necessarily rank 1, but it is still low rank: its rank is controlled by the number of times that $W$ is used within that example.

The one-use setting is simply the cleanest special case $R=1$.

## Convolution

For a convolutional kernel reshaped as a matrix $W$, the same operator is applied across many spatial positions. If the extracted local patches are $f_1(x),\dots,f_R(x)$, then the single-example gradient takes the form

$$
\nabla_W \ell(h_W(x)) = \sum_{r=1}^R \delta_r(x) f_r(x)^\top.
$$

Hence

$$
\operatorname{rank}\big(\nabla_W \ell(h_W(x))\big) \le R,
$$

where $R$ is the number of spatial locations.

So even though the gradient is not rank 1, it is still far from arbitrary. Its rank is limited by the number of local applications of the kernel.

## Self-attention projections

Exactly the same principle applies to transformer projection matrices such as $W_Q$, $W_K$, and $W_V$. These matrices are shared across tokens. If the token representations are $f_1(x),\dots,f_T(x)$, then

$$
\nabla_W \ell(h_W(x)) = \sum_{t=1}^T \delta_t(x) f_t(x)^\top,
$$

and therefore

$$
\operatorname{rank}\big(\nabla_W \ell(h_W(x))\big) \le T,
$$

where $T$ is the sequence length.

Again, the gradient is not full rank in any generic sense. Its rank is controlled by the number of token-wise uses of the shared projection matrix.

In many modern models, this is still much smaller than the ambient dimension of the weight matrix.

## The general principle

The cleanest general statement is the following:

> **A stochastic gradient update for a given matrix $W$ has rank at most the number of times that $W$ is used across the current mini-batch.**

If:
- $B$ is the batch size,
- $R$ is the number of local uses of $W$ per example,

then

$$
\operatorname{rank}(G_t) \le BR.
$$

The rest of the argument is unchanged.

Weight decay still exponentially suppresses old updates, so the current matrix remains close to a weighted sum of only recent low-rank gradients. The one-use case $R=1$ is simply the sharpest and easiest version of the phenomenon.

## What this explanation does and does not say

It is worth being precise about the scope of the claim.

This argument does **not** say that every trained layer must become exactly low rank. It does not prove a universal convergence theorem, nor does it rule out settings where optimization, architecture, normalization, or data geometry complicate the picture.

What it does say is something structural:
- the updates written by SGD are intrinsically low rank,
- weight decay gives the layer a finite effective memory,
- therefore low-rank structure is not mysterious or accidental.

It is a natural byproduct of how training writes and forgets directions over time.

This perspective also helps explain why low-rank compression often works surprisingly well after training. In many cases, compression is not discovering structure that was absent. It is recovering structure that SGD and weight decay were already building into the model.

## Takeaway

SGD with weight decay does more than optimize the loss.

It quietly biases each layer toward low-rank structure.

The mechanism is simple and very general:

1. each stochastic gradient is low rank,
2. weight decay exponentially forgets old updates,
3. so the current weight matrix is dominated by a short history of low-rank corrections.

For layers used once per example, a single-example gradient is rank 1.

For shared operators, such as convolutions and attention projections, the same idea still holds, with rank controlled by the number of local uses of the matrix.

So low-rank structure in trained neural networks is not just an empirical curiosity. It is a natural consequence of the way SGD with weight decay writes information into a model.
