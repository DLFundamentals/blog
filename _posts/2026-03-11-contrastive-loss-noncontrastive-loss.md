---
layout: post
title: "Self-Supervised Learning ≈ Supervised Learning"
date: 2026-03-11
author: Tomer Galanti
tags:
  - deep-learning
  - self-supervised-learning
  - contrastive-learning
  - supervised-learning
  - representation-learning
  - theory
excerpt: "Contrastive learning is often much closer to supervised contrastive learning than it first appears, both at the level of the objective and at the level of the learned representation geometry."
---

*This post is based on two papers:*

- *A. Luthra, T. Yang, T. Galanti. ["Self-Supervised Contrastive Learning is Approximately Supervised Contrastive Learning"](https://arxiv.org/abs/2506.04411), NeurIPS 2025.*
- *A. Luthra, T. Yang, T. Galanti. ["On the Alignment Between Supervised and Self-Supervised Contrastive Learning"](https://arxiv.org/abs/2510.08852), ICLR 2025.*

---

## Introduction

Self-supervised contrastive learning trains on unlabeled data, yet the learned features often look remarkably semantic: same-class samples cluster together, linear probes perform well, and downstream transfer can approach supervised pre-training. That raises a basic question: **how can a method that never sees labels learn representations that look so class-aware?**

In this post, we argue that contrastive learning is much closer to supervised contrastive learning than its name suggests. This closeness operates at two levels, each addressed by one of the papers above.

<div class="key-message">
  <p style="margin: 0;">
    1. The self-supervised contrastive loss is close to a supervised variant that removes same-class negatives. The gap shrinks as $O(1/C)$ with the number of classes.
  </p>
  <p style="margin: 1rem 0 0 0;">
    2. Under shared training randomness, the learned representations of the two methods remain closely aligned throughout training, even as their parameters diverge.
  </p>
</div>

<div class="figure col-wide">
  <div class="figure-grid" style="grid-template-columns: repeat(3, 1fr);">
    <div class="figure-grid-item">
      <img src="{{ '/assets/figures/cl-nscl/weight_space_angle.png' | relative_url }}" alt="Weight space alignment">
      <div class="label"><strong>(a)</strong> Weight space</div>
    </div>
    <div class="figure-grid-item">
      <img src="{{ '/assets/figures/cl-nscl/rep_space_angle.png' | relative_url }}" alt="Representation space alignment">
      <div class="label"><strong>(b)</strong> Representation space</div>
    </div>
    <div class="figure-grid-item">
      <img src="{{ '/assets/figures/cl-nscl/cka_rsa_gap.png' | relative_url }}" alt="CKA RSA gap">
      <div class="label"><strong>(c)</strong> CKA / RSA / weight gap</div>
    </div>
  </div>
  <div class="figcaption">
    <strong>Figure 1.</strong> CL and NSCL can separate in weight space while remaining closely aligned in representation space. The objectives are related, the learned geometry stays similar, but the parameter trajectories need not coincide.
  </div>
</div>

<hr class="section-rule">

## Part I: The losses are close

### The setup

Consider a labeled dataset $S = \{(x_i,y_i)\}_{i=1}^N$, but assume that during self-supervised training we only use the inputs $x_i$, not the labels $y_i$. For each sample $x_i$, we generate $K$ augmentations and map them through an encoder $f$: $z_i^l = f(\alpha_l(x_i))$.

A standard **decoupled contrastive loss** (DCL) takes the form

$$
\mathcal{L}^{\mathrm{DCL}}(f) = -\frac{1}{K^2N}\sum_{l_1,l_2=1}^K\sum_{i=1}^N \log\left(\frac{\exp(\mathrm{sim}(z_i^{l_1},z_i^{l_2}))}{\sum_{l_3=1}^K\sum_{j\neq i}\exp(\mathrm{sim}(z_i^{l_1},z_j^{l_3}))}\right).
$$

This is a purely self-supervised objective. It rewards two views of the same sample for being similar and penalizes similarity to all other samples.

Now compare it with a supervised variant that excludes same-class negatives from the denominator:

$$
\mathcal{L}^{\mathrm{NSCL}}(f) = -\frac{1}{K^2N}\sum_{l_1,l_2=1}^K\sum_{i=1}^N \log\left(\frac{\exp(\mathrm{sim}(z_i^{l_1},z_i^{l_2}))}{\sum_{l_3=1}^K\sum_{j:y_j\neq y_i}\exp(\mathrm{sim}(z_i^{l_1},z_j^{l_3}))}\right).
$$

We call this **NSCL**, for **negatives-only supervised contrastive learning**. The two losses differ in exactly one place: DCL treats every other sample as a negative, while NSCL removes same-class samples from the denominator.

### Why the gap is small

Suppose the dataset is balanced, with $C$ classes and $n$ samples per class, so $N = Cn$. Fix an anchor. In DCL, the denominator sums over all $N-1$ other samples. In NSCL, it sums over only the $N-n = n(C-1)$ different-class samples. The same-class terms that appear in DCL but not in NSCL number exactly $n-1$, a fraction roughly $1/C$ of the total. So when $C$ is large, the two denominators are nearly the same.

This can be made precise:

<div class="math-block">

$$
\mathcal{L}^{\mathrm{NSCL}}(f) \le \mathcal{L}^{\mathrm{DCL}}(f) \le \mathcal{L}^{\mathrm{NSCL}}(f) + \frac{e^2}{C-1}.
$$

</div>

The bound is both label-agnostic and architecture-independent: it holds for any encoder $f$, without assumptions on the data distribution or the model class. The gap shrinks as $O(1/C)$, which means that for problems with many semantic classes, DCL is already almost NSCL.

<div class="col-wide">
  <div class="embed-wrap">
    <iframe
      src="{{ '/assets/figures/cl-nscl/cl_nscl_loss_gap_explorer.html' | relative_url }}"
      height="400"
      loading="lazy"
      title="CL-NSCL loss gap explorer">
    </iframe>
  </div>
  <div class="figcaption">
    <strong>Figure 2.</strong> Interactive visualization of the CL-NSCL loss gap. The grid shows what each method's denominator includes: DCL sums over all other samples, including same-class negatives in red, while NSCL excludes them. The chart shows both the gap bound and the same-class fraction shrinking as $C$ grows. Drag the sliders to explore.
  </div>
</div>

### What NSCL minimizers look like

Since NSCL is the supervised bridge, it is natural to ask what its optimal solutions look like. Any global minimizer of the NSCL loss exhibits three structural properties:

1. **Augmentation collapse:** all augmented views of the same sample map to the same point.
2. **Within-class collapse:** all samples from the same class share a single representation.
3. **Simplex ETF structure:** the resulting class centers form a simplex equiangular tight frame, a maximally separated, symmetric configuration on the unit sphere.

<div class="col-wide">
  <div class="embed-wrap">
    <iframe
      src="{{ '/assets/figures/cl-nscl/neural_collapse_3d_visualization.html' | relative_url }}"
      height="380"
      loading="lazy"
      title="3D visualization of neural collapse"
      style="transform: scale(0.85); transform-origin: top center; height: 440px;">
    </iframe>
  </div>
  <div class="figcaption">
    <strong>Figure 3.</strong> Neural collapse geometry: class centers form a simplex equiangular tight frame on the unit sphere. This is the same structure that arises at global optima of supervised losses such as cross-entropy. The fact that NSCL shares these optimal solutions reflects the tight connection between the self-supervised and supervised objectives.
  </div>
</div>

<hr class="section-rule">

## Part II: The representations are close

Loss-level closeness is useful, but it does not by itself imply similar learned geometry. A small objective gap could still drive optimization in different directions. The second paper addresses this directly.

### Shared-randomness coupling

Consider training CL and NSCL under shared randomness: same initialization, same mini-batches, same augmentations. The only difference between the two runs is the objective.

To compare the learned representations, define the cosine similarity matrix

$$
\Sigma(Z)_{ij} = \cos(z_i,z_j),
$$

which captures the geometry of the representation directly. From it, standard alignment metrics follow: **CKA** (centered kernel alignment) and **RSA** (representational similarity analysis).

### The similarity matrices stay close

Under the coupled training protocol, the difference between the CL and NSCL similarity matrices throughout training satisfies a bound of the form

$$
\|\Sigma_T^{\mathrm{CL}}-\Sigma_T^{\mathrm{NS}}\|_F \lesssim \frac{e^{2/\tau}}{\tau C \sqrt{B}} \cdot \exp\left(\frac{1}{2\tau^2 B}\sum_{t=0}^{T-1}\eta_t\right)\cdot \left(\sum_{t=0}^{T-1}\eta_t\right).
$$

The right-hand side gets smaller when the number of classes $C$ is larger, the batch size $B$ is larger, the temperature $\tau$ is higher, and the cumulative step size $\sum_{t=0}^{T-1}\eta_t$ is more moderate. The same regimes that make the loss gap small also keep the representations aligned.

This immediately yields lower bounds on CKA and RSA:

<div class="math-block">

$$
\mathrm{CKA}_T \ge \frac{1-\rho_T}{1+\rho_T}, \qquad \mathrm{RSA}_T \ge \frac{1-r_T}{1+r_T},
$$

</div>

where $\rho_T$ and $r_T$ are normalized versions of the similarity-matrix discrepancy.

### But weights can still diverge

In contrast, parameter-space coupling is far less stable. A typical bound on parameter divergence takes the form

$$
\|w_T^{\mathrm{CL}}-w_T^{\mathrm{NS}}\| \lesssim \frac{G e^{2/\tau}}{\beta\tau C} \cdot \left(\exp\left(\beta\sum_{t=0}^{T-1}\eta_t\right)-1\right).
$$

Although both bounds grow exponentially, the exponent in the similarity-matrix bound is much milder: it is scaled by $1/B$, whereas the weight-space bound has no analogous batch-size moderation. Thus, representation-level alignment can remain stable even when parameter-space divergence becomes large.

This is not paradoxical. In deep networks, parameter space is highly redundant. Two models can follow very different paths in weight space and still induce very similar representation geometry.

<hr class="section-rule">

## The right mental model

Putting the two pieces together gives a sharper picture of why contrastive learning works.

The standard story is that contrastive learning is a *self-supervised* method that *somehow* discovers semantic structure. The picture here is more precise: the self-supervised objective is already close to a specific supervised contrastive objective, namely NSCL; that objective's optimal solutions exhibit the same neural-collapse geometry as supervised training; and the learned representations of the two methods remain aligned throughout training.

So rather than thinking of CL as a completely different form of learning that mysteriously recovers semantics, it is more accurate to think of it as a self-supervised procedure whose objective and learned geometry sit near a very specific supervised counterpart. Not cross-entropy, not generic supervised learning, but a supervised contrastive objective that differs from CL in only one controlled way: whether same-class samples are excluded from the denominator.

<hr class="section-rule">

<div class="takeaway">
  <div class="takeaway-label">Takeaway</div>
  <p style="margin-bottom: 1rem;">Contrastive learning is more supervised than it looks. This appears in three layers:</p>
  <ol>
    <li><strong>The losses are close.</strong> The standard self-supervised contrastive loss approximates the NSCL loss, with a gap that shrinks as $O(1/C)$.</li>
    <li><strong>The geometry is the same.</strong> NSCL minimizers exhibit the same simplex ETF structure as supervised losses: augmentation collapse, within-class collapse, and maximally separated class centers.</li>
    <li><strong>The representations stay aligned.</strong> Under shared training randomness, the learned representations of CL and NSCL remain closely aligned, even as their parameters diverge.</li>
  </ol>
  <p style="margin-top: 1rem; margin-bottom: 0;">The semantic behavior of self-supervised contrastive learning is not as mysterious as it first seems. The objective is already close to supervised learning, its optimal geometry matches supervised learning, and the learned representations track supervised learning throughout training.</p>
</div>
