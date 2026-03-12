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
excerpt: "Why mini-batch SGD with weight decay naturally pushes neural networks toward low-rank structure."
---

*This post is based on: T. Galanti, Z. Siegel, A. Gupte, T. Poggio. "SGD and Weight Decay Secretly Minimize the Rank of Your Neural Network", CPAL 2025.*

Deep networks are heavily overparameterized, yet the solutions found in practice are far from arbitrary. Even when many parameter settings can fit the training data, stochastic gradient methods often converge to highly structured models.

One particularly striking form of structure is **low rank**.

Across many architectures, trained weight matrices are far more compressible than their ambient dimension would suggest. This appears in pruning, distillation, and post-hoc low-rank approximations of trained networks. Empirically, low-rank structure is everywhere. But why should training produce it in the first place?

Much of the existing theory explains low-rank behavior only in cleaner settings than modern practice: linear models, highly specialized losses, exact symmetries, or global optimality arguments. What is still missing is a simple structural explanation for the regime practitioners actually use every day:

**mini-batch SGD with weight decay.**

The main message of this post is the following:

> <span style="color:#1e6bd6; font-weight:600;">
> Mini-batch SGD with weight decay creates a strong pressure toward low-rank layers. This pressure becomes stronger with smaller batch size, larger learning rate, and stronger weight decay.
> </span>

<div style="margin: 2rem 0;">
  <div style="display: grid; grid-template-columns: repeat(4, 1fr); gap: 20px; align-items: start;">

    <div style="text-align: center;">
      <img src="{{ '/assets/figures/low-rank-bias/contour_resnet_bs_8.png' | relative_url }}" style="width:100%; max-width:220px;">
      <div><strong>(a)</strong> $B = 8$</div>
    </div>

    <div style="text-align: center;">
      <img src="{{ '/assets/figures/low-rank-bias/contour_resnet_bs_16.png' | relative_url }}" style="width:100%; max-width:220px;">
      <div><strong>(b)</strong> $B = 16$</div>
    </div>

    <div style="text-align: center;">
      <img src="{{ '/assets/figures/low-rank-bias/contour_resnet_lr_5.png' | relative_url }}" style="width:100%; max-width:220px;">
      <div><strong>(c)</strong> $\mu = 0.5$</div>
    </div>

    <div style="text-align: center;">
      <img src="{{ '/assets/figures/low-rank-bias/contour_resnet_wd_6e-3.png' | relative_url }}" style="width:100%; max-width:220px;">
      <div><strong>(d)</strong> $\lambda = 6 \times 10^{-3}$</div>
    </div>

  </div>
</div>

<div style="margin-top: 1rem; font-size: 1.02rem; line-height: 1.5; text-align: left;">
  <strong>Figure 1.</strong>
  <strong>Average rank across network layers at the end of training for ResNet-18 on CIFAR-10.</strong>
  Lower batch size, larger learning rate, and stronger weight decay are associated with lower final rank.
</div>

<br>

The mechanism is simple:

1. each stochastic gradient step writes only a low-rank update,
2. weight decay prevents the layer from retaining too much of the distant past,
3. so the current weight matrix is dominated by a relatively short history of low-rank corrections.

That is the core mechanism. The rest of the post just makes it precise.

## A local view of one layer

To isolate the idea, fix all parameters except one trainable matrix $W$. Locally around that layer, the network can be written as

$$
h_W(x) = g(Wf(x)).
$$

Here, $f(x)$ is the representation entering the layer, $W$ is the matrix we want to study, and $g$ collects everything that happens afterward.

This is the simplest setting, and it already reveals the essential phenomenon. Later we will return to shared operators such as convolutions and attention, where the same matrix is reused multiple times within a single example.

We train with the regularized empirical loss

$$
L_S^\lambda(W) = \frac{1}{m}\sum_{i=1}^m \ell_i(h_W(x_i)) + \lambda \|W\|_F^2.
$$

Under mini-batch SGD with weight decay, the update is

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

This already points to the answer. The previous weight matrix is shrunk by the factor $1 - 2\mu\lambda$, and then a fresh stochastic gradient is added. So the key question becomes:

> **What kind of matrix is $G_t$?**

## One example gives a rank-1 gradient

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

So for a layer that is used once along the computation path, the gradient contributed by a single example is rank $1$.

This is the key structural fact. A single-example gradient is not an arbitrary full-rank matrix. It has the simplest possible form: one left direction times one right direction.

## A mini-batch still gives a low-rank update

Now let the mini-batch size be $B$. The stochastic gradient is the average of $B$ single-example gradients:

$$
G_t = \frac{1}{B}\sum_{i=1}^B \delta_i f_i^\top.
$$

Since each term has rank at most $1$, we get

$$
\operatorname{rank}(G_t) \le B.
$$

More precisely, if $W \in \mathbb{R}^{d_{\mathrm{out}} \times d_{\mathrm{in}}}$, then

$$
\operatorname{rank}(G_t) \le \min(d_{\mathrm{out}}, d_{\mathrm{in}}, B).
$$

So every SGD step writes only a low-rank correction.

This already explains why mini-batch SGD is special. It does not update a layer with an arbitrary matrix. At each step, it can only write a small number of directions. Smaller batch sizes make this restriction stronger, while larger batch sizes relax it.

But this is only half of the story. If we kept accumulating low-rank updates forever with no forgetting, their sum could still become high rank. The second half of the mechanism is weight decay.

## Weight decay limits memory

Return to the recursion

$$
W_{t+1} = (1 - 2\mu\lambda)W_t - \mu G_t.
$$

Unrolling it for $n$ steps gives

$$
W_T = (1 - 2\mu\lambda)^n W_{T-n} - \mu \sum_{j=1}^n (1 - 2\mu\lambda)^{j-1} G_{T-j}.
$$

This identity is the heart of the argument.

It shows that the current matrix $W_T$ is made of two pieces:

1. a decayed memory of the distant past,
2. a weighted sum of recent stochastic gradients.

The first term,

$$
(1 - 2\mu\lambda)^n W_{T-n},
$$

shrinks exponentially in $n$. So if we look far enough into the past, its contribution becomes negligible.

The second term is a sum of recent mini-batch gradients, each of which is low rank.

So after enough training, the current matrix is well approximated by a weighted sum of only **recent low-rank updates**.

That is the mechanism.

Another way to say it is:

- SGD writes only a few directions per step,
- weight decay prevents too many old directions from remaining active,
- so the layer behaves like a short moving memory of low-rank corrections.

<div style="text-align:center; margin: 2rem 0;">
  <img src="{{ '/assets/figures/low-rank-bias/sgd_low_rank_mechanism.png' | relative_url }}" style="width:100%; max-width:950px;">
</div>

## A simple effective-rank heuristic

The previous identity suggests a crude but useful effective-rank estimate.

Choose $n$ so that the old-memory term is at most an $\varepsilon$-fraction of the current matrix:

$$
\|(1 - 2\mu\lambda)^n W_{T-n}\| \le \varepsilon \|W_T\|.
$$

Since $(1 - 2\mu\lambda)^n \approx e^{-2\mu\lambda n}$, this happens for $n \approx \frac{\log(1/\varepsilon)}{\mu\lambda}$.

Now the recent-history term is a sum of $n$ gradients, each with rank at most $B$. Therefore its rank is at most $nB$. This suggests the heuristic bound

$$
\operatorname{rank}_\varepsilon(W_T) \lesssim \frac{B \log(1/\varepsilon)}{\mu\lambda}.
$$

Here $\operatorname{rank}_\varepsilon(A)$ denotes the minimum rank of a matrix that approximates $\frac{A}{\|A\|}$ up to error $\varepsilon$.

This bound is not meant to be sharp. Its value is conceptual. It captures the right qualitative dependencies:

- smaller batch size $\Rightarrow$ lower effective rank,
- larger learning rate $\Rightarrow$ shorter memory $\Rightarrow$ lower effective rank,
- larger weight decay $\Rightarrow$ shorter memory $\Rightarrow$ lower effective rank.

These trends should be interpreted within a regime where training remains stable and achieves comparable optimization quality.

## Why this local decomposition is natural

The representation

$$
h_W(x) = g(Wf(x))
$$

may look specialized at first, but it is the natural local view of a broad family of layers.

The idea is simple: fix all parameters except one matrix $W$, and isolate the place in the computation where that matrix acts. Then $f(x)$ is whatever enters that linear map, $Wf(x)$ is its output, and everything after that can be absorbed into a downstream function.

For a standard fully connected layer, this is immediate.

For a residual block, the same local picture still applies. Even if the full block includes a skip connection, the dependence on $W$ still enters through the term $Wf(x)$. For a fixed example $x$, the gradient with respect to $W$ therefore has the same outer-product structure.

So the one-use model is not an artificial simplification. It is the basic local geometry of backpropagation through a single matrix.

## Shared operators: convolutions and attention

The rank-$1$ statement changes only when the same matrix $W$ is reused multiple times within a single example.

This happens in several important settings:

- convolutions, where the same kernel is applied at many spatial locations,
- self-attention projections ($W_Q$, $W_K$, and $W_V$), where the same matrix is applied to many tokens,
- more generally, any shared linear operator.

In that case, the right local description is

$$
h_W(x) = g(Wf_1(x), \dots, Wf_{R}(x)).
$$

The chain rule then gives

$$
\nabla_W \ell(h_W(x)) = \sum_{r=1}^R \delta_r(x) f_r(x)^\top.
$$

Therefore,

$$
\operatorname{rank}\big(\nabla_W \ell(h_W(x))\big) \le R.
$$

So a single-example gradient is no longer necessarily rank $1$, but it is still low rank. Its rank is controlled by the number of times that $W$ is used within that example.

For a mini-batch of size $B$, this becomes

$$
\operatorname{rank}(G_t) \le BR,
$$

or more precisely,

$$
\operatorname{rank}(G_t) \le \min(d_{\mathrm{out}}, d_{\mathrm{in}}, BR).
$$

The rest of the argument is unchanged. Weight decay still exponentially suppresses old updates, so the current matrix remains close to a weighted sum of only recent low-rank gradients.

The one-use setting $R = 1$ is simply the cleanest case.

## What this explanation does and does not say

It is worth being clear about what has and has not been shown.

This argument does **not** imply that every trained layer must be exactly low rank. It is not a universal convergence theorem, and it does not bypass the influence of architecture, normalization, data geometry, or other aspects of optimization.

What it *does* give is a broad structural reason that low-rank behavior should often appear in practice:

- SGD writes low-rank updates,
- weight decay gives the layer only finite effective memory,
- so the current matrix is governed primarily by a short window of low-rank corrections.

Seen this way, low rank is not an accident, and it is not merely a pattern discovered afterward by compression. It is often already being built into the model during training.

This perspective also clarifies why post-training low-rank compression is so effective: in many cases, it is not inventing structure, but extracting structure that the training dynamics had already encouraged.

## Takeaway

SGD with weight decay does more than optimize the loss. It quietly pushes layers toward low-rank structure.

The mechanism is simple and very general:

1. each stochastic gradient is low rank,
2. weight decay exponentially forgets old updates,
3. so the current weight matrix is dominated by a short history of low-rank corrections.

For layers used once per example, a single-example gradient is rank $1$.

For shared operators such as convolutions and attention projections, the same idea still holds, with the rank controlled by the number of local uses of the matrix.

So low-rank structure in trained neural networks is not just an empirical curiosity. It is a natural consequence of how SGD with weight decay writes and forgets directions over time.
