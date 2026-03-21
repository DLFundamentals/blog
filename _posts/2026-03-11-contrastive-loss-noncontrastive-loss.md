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

<div class="col" markdown="1">

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
  <p style="margin: 1rem 0 0 0;">
    3. Minimizing the supervised variant leads to complete neural collapse at global optimum.
  </p>
</div>

</div>

<!-- UMAP progression: DCL vs NSCL across training epochs -->
<div class="figure col-wide">

  <div style="font-family:var(--font-ui,'DM Sans',sans-serif);font-size:0.78rem;color:#6b7280;margin-bottom:0.3rem;padding-left:0.2rem"><strong>DCL</strong> (self-supervised)</div>
  <div class="figure-grid" style="grid-template-columns: repeat(6, 1fr); gap: 8px; margin-bottom: 0.6rem;">
    <div class="figure-grid-item">
      <img src="{{ '/assets/figures/cl-nscl/umap_imagenet_random.png' | relative_url }}" alt="Random initialization">
      <div class="label">Init</div>
    </div>
    <div class="figure-grid-item">
      <img src="{{ '/assets/figures/cl-nscl/umap_imagenet_dcl_epoch10.png' | relative_url }}" alt="DCL at epoch 10">
      <div class="label">Epoch 10</div>
    </div>
    <div class="figure-grid-item">
      <img src="{{ '/assets/figures/cl-nscl/umap_imagenet_dcl_epoch100.png' | relative_url }}" alt="DCL at epoch 100">
      <div class="label">Epoch 100</div>
    </div>
    <div class="figure-grid-item">
      <img src="{{ '/assets/figures/cl-nscl/umap_imagenet_dcl_epoch500.png' | relative_url }}" alt="DCL at epoch 500">
      <div class="label">Epoch 500</div>
    </div>
    <div class="figure-grid-item">
      <img src="{{ '/assets/figures/cl-nscl/umap_imagenet_dcl_epoch1000.png' | relative_url }}" alt="DCL at epoch 1000">
      <div class="label">Epoch 1000</div>
    </div>
    <div class="figure-grid-item">
      <img src="{{ '/assets/figures/cl-nscl/umap_imagenet_dcl_epoch1900.png' | relative_url }}" alt="DCL at epoch 2000">
      <div class="label">Epoch 2000</div>
    </div>
  </div>

  <div style="font-family:var(--font-ui,'DM Sans',sans-serif);font-size:0.78rem;color:#6b7280;margin-bottom:0.3rem;padding-left:0.2rem"><strong>NSCL</strong> (supervised)</div>
  <div class="figure-grid" style="grid-template-columns: repeat(6, 1fr); gap: 8px;">
    <div class="figure-grid-item">
      <img src="{{ '/assets/figures/cl-nscl/umap_imagenet_random.png' | relative_url }}" alt="Random initialization">
      <div class="label">Init</div>
    </div>
    <div class="figure-grid-item">
      <img src="{{ '/assets/figures/cl-nscl/umap_imagenet_nscl_epoch10.png' | relative_url }}" alt="NSCL at epoch 10">
      <div class="label">Epoch 10</div>
    </div>
    <div class="figure-grid-item">
      <img src="{{ '/assets/figures/cl-nscl/umap_imagenet_nscl_epoch100.png' | relative_url }}" alt="NSCL at epoch 100">
      <div class="label">Epoch 100</div>
    </div>
    <div class="figure-grid-item">
      <img src="{{ '/assets/figures/cl-nscl/umap_imagenet_nscl_epoch500.png' | relative_url }}" alt="NSCL at epoch 500">
      <div class="label">Epoch 500</div>
    </div>
    <div class="figure-grid-item">
      <img src="{{ '/assets/figures/cl-nscl/umap_imagenet_nscl_epoch1000.png' | relative_url }}" alt="NSCL at epoch 1000">
      <div class="label">Epoch 1000</div>
    </div>
    <div class="figure-grid-item">
      <img src="{{ '/assets/figures/cl-nscl/umap_imagenet_nscl_epoch1900.png' | relative_url }}" alt="NSCL at epoch 2000">
      <div class="label">Epoch 2000</div>
    </div>
  </div>

  <div class="figcaption">
    <strong>Figure 1.</strong> UMAP visualizations on mini-ImageNet across training. <strong>Top row:</strong> DCL (self-supervised) progressively forms semantic clusters without ever seeing labels. <strong>Bottom row:</strong> NSCL (supervised) yields tighter, more separable clusters, despite not explicitly pulling same-class samples together. Both start from the same random initialization. The resemblance between the two rows is a central observation of this post.
  </div>
</div>

<div class="col" markdown="1">

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

<div class="math-block" markdown="1">

$$
\mathcal{L}^{\mathrm{NSCL}}(f) \le \mathcal{L}^{\mathrm{DCL}}(f) \le \mathcal{L}^{\mathrm{NSCL}}(f) + \frac{e^2}{C-1}.
$$

</div>

The bound is both label-agnostic and architecture-independent: it holds for any encoder $f$, without assumptions on the data distribution or the model class. The gap shrinks as $O(1/C)$, which means that for problems with many semantic classes, DCL is already almost NSCL.

</div>

<!-- Interactive loss gap visualization -->
<div class="col-wide">
  <div class="embed-wrap">
    <iframe
      src="{{ '/assets/figures/cl-nscl/cl_nscl_loss_gap.html' | relative_url }}"
      height="400"
      loading="lazy"
      title="CL-NSCL loss gap explorer">
    </iframe>
  </div>
  <div class="figcaption">
    <strong>Figure 2.</strong> Interactive visualization of the CL-NSCL loss gap. The grid shows what each method's denominator includes: DCL sums over all other samples, including same-class negatives in red, while NSCL excludes them. The chart shows both the gap bound and the same-class fraction shrinking as $C$ grows. Drag the sliders to explore.
  </div>
</div>

<div class="col" markdown="1">

### Validating the bound during training

We train models using SimCLR to minimize the DCL loss and track both losses throughout training, along with the theoretical upper bound $\mathcal{L}^{\mathrm{NSCL}}(f) + \log(1+\tfrac{n_{\max}\mathrm{e}^2}{N-n_{\max}})$.

</div>

<!-- Losses during training: SimCLR -->
<div class="figure col-wide">
  <div class="figure-grid" style="grid-template-columns: repeat(4, 1fr);">
    <div class="figure-grid-item">
      <img src="{{ '/assets/figures/cl-nscl/svhn_simclr_losses.png' | relative_url }}" alt="SVHN losses">
      <div class="label"><strong>(a)</strong> SVHN</div>
    </div>
    <div class="figure-grid-item">
      <img src="{{ '/assets/figures/cl-nscl/cifar10_simclr_losses.png' | relative_url }}" alt="CIFAR-10 losses">
      <div class="label"><strong>(b)</strong> CIFAR-10</div>
    </div>
    <div class="figure-grid-item">
      <img src="{{ '/assets/figures/cl-nscl/cifar100_simclr_losses.png' | relative_url }}" alt="CIFAR-100 losses">
      <div class="label"><strong>(c)</strong> CIFAR-100</div>
    </div>
    <div class="figure-grid-item">
      <img src="{{ '/assets/figures/cl-nscl/imagenet_simclr_losses.png' | relative_url }}" alt="mini-ImageNet losses">
      <div class="label"><strong>(d)</strong> mini-ImageNet</div>
    </div>
  </div>
  <div class="figcaption">
    <strong>Figure 3 (top).</strong> DCL loss, NSCL loss, and the theoretical bound tracked during SimCLR training on train and test sets. All three quantities are highly correlated. The gap between DCL and NSCL becomes tighter as the number of classes increases, compare CIFAR-10 with CIFAR-100.
  </div>
</div>

<!-- NSCL corollary: DCL-trained vs NSCL-trained -->
<div class="figure col-wide">
  <div class="figure-grid" style="grid-template-columns: repeat(4, 1fr);">
    <div class="figure-grid-item">
      <img src="{{ '/assets/figures/cl-nscl/svhn_simclr_nscl_corollary.png' | relative_url }}" alt="SVHN corollary">
      <div class="label"><strong>(a)</strong> SVHN</div>
    </div>
    <div class="figure-grid-item">
      <img src="{{ '/assets/figures/cl-nscl/cifar10_simclr_nscl_corollary.png' | relative_url }}" alt="CIFAR-10 corollary">
      <div class="label"><strong>(b)</strong> CIFAR-10</div>
    </div>
    <div class="figure-grid-item">
      <img src="{{ '/assets/figures/cl-nscl/cifar100_simclr_nscl_corollary.png' | relative_url }}" alt="CIFAR-100 corollary">
      <div class="label"><strong>(c)</strong> CIFAR-100</div>
    </div>
    <div class="figure-grid-item">
      <img src="{{ '/assets/figures/cl-nscl/imagenet_simclr_nscl_corollary.png' | relative_url }}" alt="mini-ImageNet corollary">
      <div class="label"><strong>(d)</strong> mini-ImageNet</div>
    </div>
  </div>
  <div class="figcaption">
    <strong>Figure 3 (bottom).</strong> Comparing the NSCL loss of two models, one trained with DCL and the other with NSCL. The resulting NSCL losses are comparable regardless of training objective, suggesting that minimizing DCL implicitly brings the NSCL loss close to the value achieved by direct NSCL minimization.
  </div>
</div>

<div class="col" markdown="1">

The DCL loss consistently upper bounds the NSCL loss, and the two become closer for tasks with more classes. When $C$ is large, for example $C=100$, the bound is very tight. Moreover, the NSCL losses of DCL-trained and NSCL-trained models are comparable at convergence, indicating that optimizing DCL leads to representations that are similarly clustered.

### The gap scales as predicted with $C$

</div>

<!-- Gap vs number of classes -->
<div class="figure col-wide">
  <div class="figure-grid" style="grid-template-columns: repeat(3, 1fr);">
    <div class="figure-grid-item">
      <img src="{{ '/assets/figures/cl-nscl/th1_exp2_cifar10.png' | relative_url }}" alt="CIFAR-10 gap versus C">
      <div class="label"><strong>(a)</strong> CIFAR-10</div>
    </div>
    <div class="figure-grid-item">
      <img src="{{ '/assets/figures/cl-nscl/th1_exp2_cifar100.png' | relative_url }}" alt="CIFAR-100 gap versus C">
      <div class="label"><strong>(b)</strong> CIFAR-100</div>
    </div>
    <div class="figure-grid-item">
      <img src="{{ '/assets/figures/cl-nscl/th1_exp2_imagenet.png' | relative_url }}" alt="mini-ImageNet gap versus C">
      <div class="label"><strong>(c)</strong> mini-ImageNet</div>
    </div>
  </div>
  <div class="figcaption">
    <strong>Figure 4.</strong> The gap $\mathcal{L}^{\mathrm{DCL}} - \mathcal{L}^{\mathrm{NSCL}}$ as a function of the number of classes $C$, compared with the theoretical bound $\log(1 + e^2/(C-1))$. The gap shrinks with $C$ and is highly correlated with the bound at all training epochs. Models were trained from scratch for each value of $C$ using randomly sampled class subsets.
  </div>
</div>

<div class="col" markdown="1">

### What NSCL minimizers look like

Beyond simply being a supervised loss, NSCL gives us a tractable bridge for understanding the geometry induced by contrastive learning. This raises a natural question: what kind of representations are learned by minimizing NSCL? Since NSCL serves as the supervised counterpart of DCL, understanding its global minimizers helps reveal the structure that self-supervised contrastive learning is implicitly approaching. In particular, any global minimizer of the NSCL loss exhibits three striking properties:

1. **Augmentation collapse:** all augmented views of the same sample map to the same point.
2. **Within-class collapse:** all samples from the same class share a single representation.
3. **Simplex ETF structure:** the resulting class centers form a simplex equiangular tight frame, a maximally separated, symmetric configuration on the unit sphere.

</div>

<!-- Neural collapse 3D visualization -->
<div class="col-wide">
  <div class="embed-wrap">
    <iframe
      src="{{ '/assets/figures/cl-nscl/neural_collapse_3d_visualization.html' | relative_url }}"
      height="350"
      loading="lazy"
      title="3D visualization of neural collapse">
    </iframe>
  </div>
  <div class="figcaption">
    <strong>Figure 5.</strong> Neural collapse geometry: class centers form a simplex equiangular tight frame on the unit sphere. Drag the epoch slider to watch scattered features collapse into tight clusters at the ETF vertices. This is the same structure that arises at global optima of supervised losses such as cross-entropy. The fact that NSCL shares these optimal solutions reflects the tight connection between the self-supervised and supervised objectives.
  </div>
</div>

<div class="col" markdown="1">

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

<div class="math-block" markdown="1">

$$
\mathrm{CKA}_T \ge \frac{1-\rho_T}{1+\rho_T}, \qquad \mathrm{RSA}_T \ge \frac{1-r_T}{1+r_T},
$$

</div>

where $\rho_T$ and $r_T$ are normalized versions of the similarity-matrix discrepancy.

</div>

<div class="col" markdown="1">

### Empirical confirmation: RSA and CKA are consistently high

The theoretical bounds predict that representation geometry should remain aligned even as parameters diverge. To test this directly, we train DCL and NSCL models under exactly matched conditions, same initialization, same mini-batches, same augmentations, and same hyperparameters, for 300 epochs, then measure CKA and RSA between the two learned representations. A score of 1.0 would mean identical geometry; 0 would mean no alignment.

</div>

<div class="col-wide">
  <div class="embed-wrap">
    <iframe
      src="{{ '/assets/figures/cl-nscl/rsa_cka_alignment.html' | relative_url }}"
      height="220"
      loading="lazy"
      title="RSA and CKA alignment between DCL and NSCL">
    </iframe>
  </div>
  <div class="figcaption">
    <strong>Figure 6.</strong> Representation similarity between DCL and NSCL models trained with matched initialization and mini-batch order. RSA and CKA values are consistently above 0.81 across all datasets and both architectures, confirming near-identical representation geometry despite training with different objectives.
  </div>
</div>

<div class="col" markdown="1">

Across all three datasets and both architectures, RSA and CKA exceed 0.81, and for CIFAR-100, all four measurements reach 0.91. Two patterns stand out. First, alignment is strongest when the number of classes is largest, as in CIFAR-100 and mini-ImageNet. This is exactly what the theory predicts: more classes means a smaller loss gap, which in turn keeps the optimization trajectories closer and the learned geometry more aligned. Second, the scores are nearly identical across ResNet-50 and ViT-Base, confirming that the DCL-NSCL duality is not an artifact of a particular architecture.

These numbers should be read alongside the theoretical prediction. The bound on representation divergence scales as $1/(\tau C \sqrt{B})$, so with $C = 100$ classes and batch size $B = 1024$, the predicted divergence is small and the empirical alignment is correspondingly high. The fact that CKA and RSA both stay above 0.8 even for CIFAR-10 ($C = 10$) suggests that the bound, while not tight, captures the correct qualitative dependence.

### But weights can still diverge

In contrast, parameter-space coupling is far less stable. A typical bound on parameter divergence takes the form

$$
\|w_T^{\mathrm{CL}}-w_T^{\mathrm{NS}}\| \lesssim \frac{G e^{2/\tau}}{\beta\tau C} \cdot \left(\exp\left(\beta\sum_{t=0}^{T-1}\eta_t\right)-1\right).
$$

Although both bounds grow exponentially, the exponent in the similarity-matrix bound is much milder: it is scaled by $1/B$, whereas the weight-space bound has no analogous batch-size moderation. Thus, representation-level alignment can remain stable even when parameter-space divergence becomes large.

This is not paradoxical. In deep networks, parameter space is highly redundant. Two models can follow very different paths in weight space and still induce very similar representation geometry.

</div>

<div class="col" markdown="1">

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
    <li><strong>Elegant geometry.</strong> NSCL minimizers exhibit the same simplex ETF structure as supervised losses: augmentation collapse, within-class collapse, and maximally separated class centers.</li>
    <li><strong>The representations stay aligned.</strong> Under shared training randomness, the learned representations of CL and NSCL remain closely aligned, even as their parameters diverge.</li>
  </ol>
  <p style="margin-top: 1rem; margin-bottom: 0;">The semantic behavior of self-supervised contrastive learning is not as mysterious as it first seems. The objective is already close to supervised learning, its optimal geometry matches supervised learning, and the learned representations track supervised learning throughout training.</p>
</div>

</div>
