---
layout: post
title: "Why SGD Prefers Low-Rank Neural Networks"
date: 2026-03-11
author: Tomer Galanti
tags:
  - deep-learning
  - low-rank-bias
  - sgd
  - compression
  - theory
  - foundation-models
excerpt: "Why do trained neural networks often end up low rank? Mini-batch SGD and weight decay together create a built-in pressure toward compressible layers."
---

*Based on: T. Galanti, Z. Siegel, A. Gupte, T. Poggio. ["SGD and Weight Decay Secretly Minimize the Rank of Your Neural Network"](https://openreview.net/forum?id=xhW2WyPhRP), CPAL 2025.*

<style>
  .flush-list ul,
  .flush-list ol {
    margin-left: 0;
    padding-left: 0;
    list-style-position: inside;
  }

  .flush-list li {
    margin-left: 0;
    padding-left: 0;
  }
</style>

---

## Introduction

Deep networks are heavily overparameterized, yet the solutions found in practice are far from arbitrary. Even when many parameter settings can fit the training data, stochastic gradient methods often converge to highly structured models. One particularly striking form of structure is **low rank**: across many architectures, trained weight matrices are often far more compressible than their full dimension would suggest.

Much of the existing theory explains low-rank behavior only in cleaner settings than those used in modern practice: linear models, specialized losses, exact symmetries, or global optimality arguments. What is still missing is a structural explanation for the regime practitioners actually use, namely **training practical neural networks with mini-batch SGD and weight decay**.

<div class="key-message">
  Mini-batch SGD with weight decay creates a strong pressure toward low-rank layers.
  This pressure becomes stronger with smaller batch size $B$, larger learning rate $\mu$, and
  stronger weight decay $\lambda$.
</div>

<div class="figure col-wide">
  <div class="figure-grid">
    <div class="figure-grid-item">
      <img src="{{ '/assets/figures/low-rank-bias/contour_resnet_bs_8.png' | relative_url }}" alt="Batch size 8">
      <div class="label"><strong>(a)</strong> $B = 8$</div>
    </div>
    <div class="figure-grid-item">
      <img src="{{ '/assets/figures/low-rank-bias/contour_resnet_bs_16.png' | relative_url }}" alt="Batch size 16">
      <div class="label"><strong>(b)</strong> $B = 16$</div>
    </div>
    <div class="figure-grid-item">
      <img src="{{ '/assets/figures/low-rank-bias/contour_resnet_lr_5.png' | relative_url }}" alt="Learning rate 0.5">
      <div class="label"><strong>(c)</strong> $\mu = 0.5$</div>
    </div>
    <div class="figure-grid-item">
      <img src="{{ '/assets/figures/low-rank-bias/contour_resnet_wd_6e-3.png' | relative_url }}" alt="Weight decay 6e-3">
      <div class="label"><strong>(d)</strong> $\lambda = 6 \times 10^{-3}$</div>
    </div>
  </div>
  <div class="figcaption">
    <strong>Figure 1.</strong> Average rank across network layers at the end of training for ResNet-18 on CIFAR-10. Smaller batch size, larger learning rate, and stronger weight decay are associated with lower final rank.
  </div>
</div>

The mechanism has three parts, each developed in a section below:

<div class="flush-list">
  <ol>
    <li><strong>Each stochastic gradient is low rank.</strong> A single-example gradient is rank 1, so a mini-batch gradient has rank at most $B$.</li>
    <li><strong>Weight decay limits memory.</strong> It exponentially suppresses old updates, so only a short window of past gradients contributes meaningfully to the current weight matrix.</li>
    <li><strong>The combination produces low-rank layers.</strong> The current matrix is dominated by a short history of low-rank corrections, yielding an effective rank of roughly $B / (\mu\lambda)$.</li>
  </ol>
</div>

<div class="figure col-wide">
  <img src="{{ '/assets/figures/low-rank-bias/sgd_low_rank_mechanism.png' | relative_url }}" alt="Low-rank mechanism">
  <div class="figcaption">
    <strong>Figure 2.</strong> Each mini-batch gradient $G_t$ has rank $\le B$. Weight decay exponentially suppresses older updates (shown as fading blocks). The current matrix $W_T$ is dominated by a short effective memory window of recent low-rank corrections.
  </div>
</div>

## Interactive explorer

Here is a live simulation of the mechanism. A $14 \times 14$ weight matrix is built step by step from rank-$B$ stochastic gradient updates under weight decay. Press **Play** to watch the dynamics unfold, or **Step** to advance one iteration at a time.

<div class="col-wide">
  <div class="embed-wrap">
    <iframe
      src="{{ '/assets/figures/low-rank-bias/sgd_low_rank_bias_stable.html' | relative_url }}"
      height="540"
      loading="lazy"
      title="Interactive low-rank bias explorer">
    </iframe>
  </div>
  <div class="figcaption">
    <strong>Figure 3.</strong> Interactive simulation of the low-rank mechanism. The heatmap shows $W_T$ (warm = positive, cool = negative). Singular value bars reveal the rank structure. The memory window at the bottom shows how weight decay fades old gradient contributions. The sliders control batch size $B$, learning rate $\mu$, and weight decay $\lambda$.
  </div>
</div>

<div class="card-stack">
  <div class="card">
    <div class="card-title">Low-rank updates</div>
    <p>Set $B = 1$ and step through the dynamics. Each gradient is a single outer product, so the matrix grows in structured stripe-like patterns. Increase $B$ to 8 or more and watch the updates become richer as more singular values light up.</p>
  </div>
  <div class="card">
    <div class="card-title">Weight decay limits memory</div>
    <p>With small $\lambda$ (say 0.01), the timeline blocks stay bright for many steps and the effective rank climbs. Increase $\lambda$ toward 0.10 and watch old blocks fade rapidly, the memory window shrink, and the rank drop.</p>
  </div>
  <div class="card">
    <div class="card-title">The interaction</div>
    <p>Try $B = 1$, $\mu = 0.10$, $\lambda = 0.10$ for very low rank (around 1-2), then try $B = 8$, $\mu = 0.02$, $\lambda = 0.01$ for higher rank. The badge next to the equation shows the decay factor $1 - 2\mu\lambda$, constrained to remain positive.</p>
  </div>
</div>

<hr class="section-rule">

## Part I: Stochastic gradients are low rank

### A local view of one layer

Fix all parameters except one trainable matrix $W$. Locally around that layer, the network can be written as

$$
h(x) = g(Wf(x)),
$$

where $f(x)$ is the representation entering the layer and $g$ collects everything that comes afterward. We train with the regularized loss

$$
L_S^\lambda(W) = \frac{1}{m}\sum_{i=1}^m \ell_i(h(x_i)) + \lambda \|W\|_F^2.
$$

Under mini-batch SGD with weight decay, the update is

$$
W_{t+1} = (1 - 2\mu\lambda)W_t - \mu G_t,
$$

where $G_t := \nabla_W L_{\tilde S_t}(W_t)$ is the mini-batch gradient. The previous matrix is shrunk by the factor $1 - 2\mu\lambda$, and a fresh stochastic gradient is added. So the key question is: **what kind of matrix is $G_t$?**

### One example gives a rank-1 gradient

For a single training example $x$, the chain rule gives

$$
\nabla_W \ell(h(x)) = \delta(x) f(x)^\top,
$$

where $\delta(x) := J_g(Wf(x))^\top \nabla_h \ell(h(x))$. This is an outer product of two vectors, so

$$
\textnormal{rank}\big(\nabla_W \ell(h(x))\big) \le 1.
$$

A single-example gradient is not an arbitrary full-rank matrix. It has the simplest possible structure: one left direction times one right direction.

### A mini-batch gives an update of rank at most $B$

The mini-batch gradient is the average of $B$ rank-1 terms:

$$
G_t = \frac{1}{B}\sum_{i=1}^B \delta_i f_i^\top,
\qquad
\textnormal{rank}(G_t) \le \min(d_{\mathrm{out}}, d_{\mathrm{in}}, B).
$$

So every SGD step writes only a low-rank correction. Smaller batch sizes make this restriction stronger; larger batch sizes relax it.

But low-rank updates alone are not enough. If we accumulate them forever with no forgetting, their sum can eventually become high rank. The second ingredient is weight decay.

<hr class="section-rule">

## Part II: Weight decay limits memory

Unrolling the recursion
$$
W_{t+1} = (1 - 2\mu\lambda)W_t - \mu G_t
$$
for $n$ steps gives the identity at the heart of the argument:

$$
W_T
=
\underbrace{(1 - 2\mu\lambda)^n W_{T-n}}_{\text{decayed past}}
-
\mu
\underbrace{\sum_{j=1}^n (1 - 2\mu\lambda)^{j-1} G_{T-j}}_{\text{recent low-rank updates}}.
$$

The first term shrinks exponentially in $n$. The second is a weighted sum of recent mini-batch gradients, each of rank at most $B$. So after enough training, the current matrix is well approximated by a **short moving memory of low-rank corrections**. That is the mechanism:

<div class="flush-list">
  <ul>
    <li>SGD writes only a few directions per step.</li>
    <li>Weight decay prevents too many old directions from remaining active.</li>
    <li>The layer behaves like a sliding window of low-rank updates.</li>
  </ul>
</div>

### A simple effective-rank heuristic

Choose $n$ so that the old-memory term is negligible:
$(1 - 2\mu\lambda)^n \approx e^{-2\mu\lambda n} \le \varepsilon$,
which gives
$n \approx \frac{\log(1/\varepsilon)}{\mu\lambda}$.

The recent term is a sum of $n$ gradients of rank at most $B$, so

<div class="math-block">
$$
\textnormal{rank}_\varepsilon(W_T) \lesssim \frac{B \log(1/\varepsilon)}{\mu\lambda}.
$$
</div>

This bound captures the correct qualitative dependencies: smaller batch size, larger learning rate, or larger weight decay all shorten the effective memory and produce lower effective rank.

<hr class="section-rule">

## Part III: Shared operators

The rank-1 statement changes when the same matrix $W$ is reused multiple times within a single example. This happens in convolutions, where the same kernel is applied at many spatial locations; in self-attention projections, where $W_Q$, $W_K$, and $W_V$ are applied to many tokens; and in any other shared linear operator. In that case,

$$
h(x) = g(Wf_1(x), \dots, Wf_R(x)),
$$

and the chain rule gives

$$
\nabla_W \ell(h(x))
=
\sum_{r=1}^R \delta_r(x) f_r(x)^\top,
\qquad
\textnormal{rank}\big(\nabla_W \ell(h(x))\big) \le R.
$$

For a mini-batch,
$\textnormal{rank}(G_t) \le \min(d_{\mathrm{out}}, d_{\mathrm{in}}, BR)$.

The rest of the argument is unchanged. Weight decay still exponentially suppresses old updates, so the current matrix remains close to a weighted sum of recent low-rank gradients. The one-use setting $R = 1$ is simply the cleanest case.

### Why the local view is natural

The representation $h(x) = g(Wf(x))$ is not an artificial simplification. It is the natural local view of any layer: fix all other parameters, isolate the point where $W$ acts, and absorb everything before it into $f$ and everything after it into $g$. For fully connected layers this is immediate. For residual blocks, the dependence on $W$ still enters through $Wf(x)$, so the outer-product structure of the gradient is preserved.

<hr class="section-rule">

## What this does and does not say

This argument does **not** imply that every trained layer must be exactly low rank. Nor does it eliminate the influence of architecture, normalization, or data geometry.

What it *does* provide is a broad structural reason that low-rank behavior should often appear in practice. Low rank is not an accident, and it is not merely a pattern discovered afterward by compression. It is built into the training dynamics through the interaction of stochastic gradients and weight decay.

This also helps explain why **post-training low-rank compression** is often so effective: in many cases, it is not inventing structure but extracting structure that training had already encouraged.

<hr class="section-rule">

<div class="takeaway flush-list">
  <div class="takeaway-label">Takeaway</div>
  <p style="margin-bottom: 1rem;">SGD with weight decay does more than optimize the loss. It quietly pushes layers toward low-rank structure. The mechanism operates in three parts:</p>
  <ol>
    <li><strong>Low-rank updates.</strong> Each stochastic gradient is low rank: rank 1 per example, rank $B$ per mini-batch, and rank $BR$ for shared operators.</li>
    <li><strong>Finite memory.</strong> Weight decay exponentially forgets old updates, limiting the effective memory to roughly $1/(\mu\lambda)$ steps.</li>
    <li><strong>Low-rank layers.</strong> The current weight matrix is dominated by a short history of low-rank corrections, yielding an effective rank of roughly $B\log(1/\varepsilon)/(\mu\lambda)$.</li>
  </ol>
  <p style="margin-top: 1rem; margin-bottom: 0;">Low-rank structure in trained neural networks is not just an empirical curiosity. It is a natural consequence of how SGD with weight decay writes and forgets directions over time.</p>
</div>
