---
layout: post
title: "Why SGD Prefers Low-Rank Neural Networks"
date: 2026-03-11
---

<div class="col">

*Based on: T. Galanti, Z. Siegel, A. Gupte, T. Poggio. ["SGD and Weight Decay Secretly Minimize the Rank of Your Neural Network"](https://openreview.net/forum?id=xhW2WyPhRP), CPAL 2025.*

---

Deep networks are heavily overparameterized, yet the solutions found in practice are far from arbitrary. Even when many parameter settings can fit the training data, stochastic gradient methods often converge to highly structured models. One particularly striking form of structure is **low rank**: across many architectures, trained weight matrices are far more compressible than their full dimension would suggest.

Much of the existing theory explains low-rank behavior only in cleaner settings than modern practice: linear models, specialized losses, exact symmetries, or global optimality arguments. What is missing is a structural explanation for the regime practitioners actually use: **training practical neural networks with mini-batch SGD and weight decay.**

<div class="key-message">
Mini-batch SGD with weight decay creates a strong pressure toward low-rank layers. This pressure becomes stronger with smaller batch size, larger learning rate, and stronger weight decay.
</div>

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
    <strong>Figure 1.</strong> Average rank across network layers at the end of training for ResNet-18 on CIFAR-10. Lower batch size, larger learning rate, and stronger weight decay are associated with lower final rank.
  </div>
</div>

<div class="col">

The mechanism has three parts, each developed in a section below:

1. **Each stochastic gradient is low rank** — a single-example gradient is rank 1, so a mini-batch gradient has rank at most $B$.
2. **Weight decay limits memory** — it exponentially suppresses old updates, so only a short window of past gradients contributes to the current weight matrix.
3. **The combination produces low-rank layers** — the current matrix is dominated by a short history of low-rank corrections, yielding an effective rank of roughly $B / (\mu\lambda)$.

</div>

<div class="figure col-wide">
  <img src="{{ '/assets/figures/low-rank-bias/sgd_low_rank_mechanism.png' | relative_url }}" alt="Low-rank mechanism">
  <div class="figcaption">
    <strong>Figure 2.</strong> Each mini-batch gradient $G_t$ has rank $\le B$. Weight decay exponentially suppresses older updates (fading blocks). The current matrix $W_T$ is dominated by a short effective memory window of recent low-rank corrections.
  </div>
</div>

<div class="col">

## Interactive explorer

Here is a live simulation of the mechanism. A $14 \times 14$ weight matrix is built up step by step from rank-$B$ stochastic gradient updates under weight decay. Press **Play** to watch the dynamics unfold, or **Step** to advance one iteration at a time.

</div>

<div class="col-wide">
  <div class="embed-wrap">
    <iframe
      src="{{ '/assets/figures/low-rank-bias/sgd_low_rank_bias_stable.html' | relative_url }}"
      height="560"
      loading="lazy"
      title="Interactive low-rank bias explorer">
    </iframe>
  </div>
  <div class="figcaption">
    <strong>Figure 3.</strong> Interactive simulation of the low-rank mechanism. The heatmap shows $W_T$ (warm = positive, cool = negative). Singular value bars reveal rank structure. The memory window at the bottom shows how weight decay fades old gradient contributions. The sliders control batch size $B$, learning rate $\mu$, and weight decay $\lambda$.
  </div>
</div>

<div class="col">

<div class="card-stack">
  <div class="card">
    <div class="card-title">Low-rank updates</div>
    <p>Set $B = 1$ and step through. Each gradient is a single outer product, so the matrix grows in structured stripe-like patterns. Increase $B$ to 8+ and watch the updates become richer — more singular values light up.</p>
  </div>
  <div class="card">
    <div class="card-title">Weight decay limits memory</div>
    <p>With small $\lambda$ (say 0.01), the timeline blocks stay bright for many steps and effective rank climbs. Increase $\lambda$ toward 0.10 and watch old blocks fade rapidly, the memory window shrinks, and rank drops.</p>
  </div>
  <div class="card">
    <div class="card-title">The interaction</div>
    <p>Try $B = 1$, $\mu = 0.10$, $\lambda = 0.10$ for very low rank (1–2), then $B = 8$, $\mu = 0.02$, $\lambda = 0.01$ for higher rank. The badge next to the equation shows the decay factor $1 - 2\mu\lambda$, constrained to stay positive.</p>
  </div>
</div>

<hr class="section-rule">

## Part I: Stochastic gradients are low rank

### A local view of one layer

Fix all parameters except one trainable matrix $W$. Locally around that layer, the network can be written as

$$h(x) = g(Wf(x)),$$

where $f(x)$ is the representation entering the layer and $g$ collects everything afterward. We train with the regularized loss

$$L_S^\lambda(W) = \frac{1}{m}\sum_{i=1}^m \ell_i(h(x_i)) + \lambda \|W\|_F^2.$$

Under mini-batch SGD with weight decay, the update is

$$W_{t+1} = (1 - 2\mu\lambda)W_t - \mu G_t,$$

where $G_t := \nabla_W L_{\tilde S_t}(W_t)$ is the mini-batch gradient. The previous matrix is shrunk by $1 - 2\mu\lambda$, and a fresh stochastic gradient is added. So the key question is: **what kind of matrix is $G_t$?**

### One example gives a rank-1 gradient

For a single training example $x$, the chain rule gives

$$\nabla_W \ell(h(x)) = \delta(x) f(x)^\top,$$

where $\delta(x) := J_g(Wf(x))^\top \nabla_h \ell(h(x))$. This is an outer product of two vectors, so

$$\operatorname{rank}\big(\nabla_W \ell(h(x))\big) \le 1.$$

A single-example gradient is not an arbitrary full-rank matrix. It has the simplest possible form: one left direction times one right direction.

### A mini-batch gives an update of rank at most $B$

The mini-batch gradient is the average of $B$ rank-1 terms:

$$G_t = \frac{1}{B}\sum_{i=1}^B \delta_i f_i^\top, \qquad \operatorname{rank}(G_t) \le \min(d_{\mathrm{out}}, d_{\mathrm{in}}, B).$$

So every SGD step writes only a low-rank correction. Smaller batch sizes make this restriction stronger; larger batch sizes relax it.

But low-rank updates alone are not enough. If we accumulated them forever with no forgetting, their sum could become high rank. The second ingredient is weight decay.

<hr class="section-rule">

## Part II: Weight decay limits memory

Unrolling the recursion $W_{t+1} = (1 - 2\mu\lambda)W_t - \mu G_t$ for $n$ steps gives the identity at the heart of the argument:

$$W_T = \underbrace{(1 - 2\mu\lambda)^n W_{T-n}}_{\text{decayed past}} - \mu \underbrace{\sum_{j=1}^n (1 - 2\mu\lambda)^{j-1} G_{T-j}}_{\text{recent low-rank updates}}.$$

The first term shrinks exponentially in $n$. The second is a weighted sum of recent mini-batch gradients, each of rank at most $B$. So after enough training, the current matrix is well approximated by a **short moving memory of low-rank corrections**. That is the mechanism:

- SGD writes only a few directions per step,
- weight decay prevents too many old directions from remaining active,
- so the layer behaves like a sliding window of low-rank updates.

### A simple effective-rank heuristic

Choose $n$ so the old-memory term is negligible: $(1-2\mu\lambda)^n \approx e^{-2\mu\lambda n} \le \varepsilon$, giving $n \approx \frac{\log(1/\varepsilon)}{\mu\lambda}$. The recent term is a sum of $n$ gradients of rank at most $B$, so

<div class="math-block">

$$\operatorname{rank}_\varepsilon(W_T) \lesssim \frac{B \log(1/\varepsilon)}{\mu\lambda}.$$

</div>

This bound captures the right qualitative dependencies: smaller batch size, larger learning rate, or larger weight decay all shorten the effective memory and produce lower effective rank.

<hr class="section-rule">

## Part III: Shared operators

The rank-1 statement changes when the same matrix $W$ is reused multiple times within a single example. This happens in convolutions (same kernel at many spatial locations), self-attention projections ($W_Q$, $W_K$, $W_V$ applied to many tokens), and any shared linear operator. In that case,

$$h(x) = g(Wf_1(x), \dots, Wf_R(x)),$$

and the chain rule gives

$$\nabla_W \ell(h(x)) = \sum_{r=1}^R \delta_r(x) f_r(x)^\top, \qquad \operatorname{rank}\big(\nabla_W \ell(h(x))\big) \le R.$$

For a mini-batch, $\operatorname{rank}(G_t) \le \min(d_{\mathrm{out}}, d_{\mathrm{in}}, BR)$. The rest of the argument is unchanged: weight decay still exponentially suppresses old updates, so the current matrix remains close to a weighted sum of recent low-rank gradients. The one-use setting $R = 1$ is simply the cleanest case.

### Why the local view is natural

The representation $h(x) = g(Wf(x))$ is not an artificial simplification. It is the natural local view of any layer: fix all other parameters, isolate the place where $W$ acts, and absorb everything before it into $f$ and everything after it into $g$. For fully connected layers this is immediate. For residual blocks, the dependence on $W$ still enters through $Wf(x)$, so the outer-product structure of the gradient is preserved.

<hr class="section-rule">

## What this does and does not say

This argument does **not** imply that every trained layer must be exactly low rank. It does not bypass the influence of architecture, normalization, or data geometry.

What it *does* give is a broad structural reason that low-rank behavior should often appear in practice. Low rank is not an accident, and it is not merely a pattern discovered afterward by compression — it is built into the model during training by the interaction of stochastic gradients and weight decay.

This also clarifies why **post-training low-rank compression** is so effective: in many cases, it is not inventing structure but extracting structure that the training dynamics had already encouraged.

<hr class="section-rule">

<div class="takeaway">
  <div class="takeaway-label">Takeaway</div>
  <p style="margin-bottom: 1rem;">SGD with weight decay does more than optimize the loss. It quietly pushes layers toward low-rank structure. The mechanism operates in three parts:</p>
  <ol>
    <li><strong>Low-rank updates.</strong> Each stochastic gradient is low rank — rank 1 per example, rank $B$ per mini-batch, rank $BR$ for shared operators.</li>
    <li><strong>Finite memory.</strong> Weight decay exponentially forgets old updates, limiting the effective memory to roughly $1/(\mu\lambda)$ steps.</li>
    <li><strong>Low-rank layers.</strong> The current weight matrix is dominated by a short history of low-rank corrections, yielding an effective rank of roughly $B\log(1/\varepsilon)/(\mu\lambda)$.</li>
  </ol>
  <p style="margin-top: 1rem; margin-bottom: 0;">Low-rank structure in trained neural networks is not just an empirical curiosity. It is a natural consequence of how SGD with weight decay writes and forgets directions over time.</p>
</div>

</div>
