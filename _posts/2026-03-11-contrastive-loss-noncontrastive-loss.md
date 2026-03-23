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
excerpt: "Self-supervised contrastive learning often produces surprisingly semantic representations. This post argues that the reason is structural: its objective and learned geometry are already much closer to a supervised contrastive counterpart than they first appear."
---

<style>
.figure + .col,
.col-wide + .col {
  margin-top: 0.85rem;
}

.flush-list ul,
.flush-list ol {
  margin-left: 0 !important;
  padding-left: 0 !important;
  list-style-position: inside;
}

.flush-list li {
  margin-left: 0 !important;
  padding-left: 0 !important;
}
</style>

<div class="col" markdown="1">

*Based on:*

<div class="flush-list" markdown="1">

- *A. Luthra, T. Yang, T. Galanti. ["Self-Supervised Contrastive Learning is Approximately Supervised Contrastive Learning"](https://arxiv.org/abs/2506.04411), NeurIPS 2025.*
- *A. Luthra, T. Yang, T. Galanti. ["On the Alignment Between Supervised and Self-Supervised Contrastive Learning"](https://arxiv.org/abs/2510.08852), ICLR 2025.*

</div>

---

## Introduction

Self-supervised contrastive learning is trained without labels, yet the learned representations often display clear semantic structure: same-class samples cluster together, linear probes perform well, and downstream transfer can approach supervised pretraining. This raises a basic question: **why does a label-free objective produce representations that look so class-aware?**

A useful way to think about this phenomenon is that standard contrastive learning is not as far from supervised contrastive learning as it may first appear. In this post, I will argue that this closeness appears at two levels, corresponding to the two papers above.

<div class="key-message">
  <p style="margin: 0;">
    <strong>1. The objectives are close.</strong> The standard self-supervised contrastive loss is close to a supervised variant that excludes same-class negatives, with a gap that shrinks as $O(1/C)$ in the number of classes.
  </p>
  <p style="margin: 1rem 0 0 0;">
    <strong>2. The induced geometry is close.</strong> Under shared training randomness, the learned representations remain strongly aligned throughout training, even when the parameters themselves diverge.
  </p>
  <p style="margin: 1rem 0 0 0;">
    <strong>3. The supervised counterpart is geometrically tractable.</strong> Its global minimizers exhibit augmentation collapse, within-class collapse, and simplex ETF structure.
  </p>
</div>

Taken together, these results suggest a more precise picture of why contrastive learning behaves semantically. Rather than viewing it as a completely separate learning principle that somehow recovers class structure indirectly, it is often more accurate to view it as operating near a specific supervised contrastive objective, both at the level of the loss and at the level of the learned representation geometry.

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
    <strong>Figure 1.</strong> UMAP visualizations on mini-ImageNet across training. <strong>Top row:</strong> DCL (self-supervised) progressively forms semantic clusters without access to labels. <strong>Bottom row:</strong> NSCL (supervised) yields tighter, more separable clusters, despite not explicitly pulling same-class samples together. Both runs start from the same random initialization. The similarity between the two trajectories is one of the central observations of this post.
  </div>
</div>

<div class="col" markdown="1">

<hr class="section-rule">

## Part I: A supervised objective sits very near the self-supervised one

### The setup

Consider a labeled dataset $S = \{(x_i,y_i)\}_{i=1}^N$, but suppose that during self-supervised training we only use the inputs $x_i$, not the labels $y_i$. For each sample $x_i$, we generate $K$ augmentations and map them through an encoder $f$: $z_i^l = f(\alpha_l(x_i))$.

A standard **decoupled contrastive loss** (DCL) takes the form

$$
\mathcal{L}^{\mathrm{DCL}}(f) = -\frac{1}{K^2N}\sum_{l_1,l_2=1}^K\sum_{i=1}^N \log\left(\frac{\exp(\mathrm{sim}(z_i^{l_1},z_i^{l_2}))}{\sum_{l_3=1}^K\sum_{j\neq i}\exp(\mathrm{sim}(z_i^{l_1},z_j^{l_3}))}\right).
$$

This is a purely self-supervised objective. It rewards agreement between two views of the same sample and penalizes similarity to all other samples.

Now compare it with the following supervised variant:

$$
\mathcal{L}^{\mathrm{NSCL}}(f) = -\frac{1}{K^2N}\sum_{l_1,l_2=1}^K\sum_{i=1}^N \log\left(\frac{\exp(\mathrm{sim}(z_i^{l_1},z_i^{l_2}))}{\sum_{l_3=1}^K\sum_{j:y_j\neq y_i}\exp(\mathrm{sim}(z_i^{l_1},z_j^{l_3}))}\right).
$$

We call this **NSCL**, for **negatives-only supervised contrastive learning**.

This comparison is useful because it isolates the precise role of supervision. The numerator is the same in both objectives. The positive pairs are the same. The only difference is in the denominator:

<div class="flush-list">
  <ul>
    <li><strong>DCL</strong> treats every other sample as a negative.</li>
    <li><strong>NSCL</strong> removes same-class samples from the negative set.</li>
  </ul>
</div>

That single change turns out to account for a great deal.

### Why the gap is small

Suppose the dataset is balanced, with $C$ classes and $n$ samples per class, so $N = Cn$. Fix an anchor. In DCL, the denominator sums over all $N-1$ other samples. In NSCL, it sums over only the $N-n = n(C-1)$ different-class samples. The only terms that appear in DCL but not in NSCL are the $n-1$ same-class samples.

So the discrepancy between the two objectives is controlled by a very simple quantity: the fraction of the denominator occupied by same-class samples. In a balanced $C$-class problem, that fraction is roughly $1/C$. As the number of classes grows, the two denominators become increasingly similar.

This can be made precise:

<div class="math-block" markdown="1">

$$
\mathcal{L}^{\mathrm{NSCL}}(f) \le \mathcal{L}^{\mathrm{DCL}}(f) \le \mathcal{L}^{\mathrm{NSCL}}(f) + \frac{e^2}{C-1}.
$$

</div>

The bound is clean and quite general. It holds for any encoder $f$, without assumptions on the data distribution or the model class. The gap shrinks as $O(1/C)$, which means that for problems with many semantic classes, DCL is already very close to NSCL.

So one useful conclusion is the following: for large-$C$ problems, standard self-supervised contrastive learning is optimizing an objective that is already quite near a natural supervised contrastive counterpart.

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
    <strong>Figure 2.</strong> Interactive visualization of the CL-NSCL loss gap. The grid shows what each method's denominator includes: DCL sums over all other samples, including same-class negatives in red, while NSCL excludes them. The chart shows both the gap bound and the same-class fraction shrinking as $C$ grows.
  </div>
</div>

<div class="col" markdown="1">

### Validating the bound during training

To examine this behavior empirically, we train models using SimCLR to minimize the DCL loss and track both losses throughout training, along with the theoretical upper bound
\[
\mathcal{L}^{\mathrm{NSCL}}(f) + \log\left(1+\frac{n_{\max}e^2}{N-n_{\max}}\right).
\]

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
    <strong>Figure 3 (top).</strong> DCL loss, NSCL loss, and the theoretical bound tracked during SimCLR training on train and test sets. All three quantities are highly correlated. The gap between DCL and NSCL becomes tighter as the number of classes increases; compare CIFAR-10 with CIFAR-100.
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
    <strong>Figure 3 (bottom).</strong> Comparing the NSCL loss of two models, one trained with DCL and the other with NSCL. The resulting NSCL losses are comparable regardless of training objective, suggesting that minimizing DCL already brings the NSCL loss close to the value achieved by direct NSCL minimization.
  </div>
</div>

<div class="col" markdown="1">

The DCL loss consistently upper bounds the NSCL loss, and the two become closer for tasks with more classes. When $C$ is large, for example $C = 100$, the bound becomes quite tight. Moreover, the NSCL losses of DCL-trained and NSCL-trained models are comparable at convergence, indicating that optimizing DCL already leads to a representation regime close to the one favored by NSCL.

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

NSCL is useful not only as a supervised comparison point, but also as a tractable bridge for understanding the geometry that contrastive learning is implicitly approaching. Since DCL sits close to NSCL at the level of the loss, it is natural to ask what the global minimizers of NSCL look like.

The answer is remarkably structured. Any global minimizer of the NSCL loss exhibits three properties:

<div class="flush-list">
  <ol>
    <li><strong>Augmentation collapse:</strong> all augmented views of the same sample map to the same point.</li>
    <li><strong>Within-class collapse:</strong> all samples from the same class share a single representation.</li>
    <li><strong>Simplex ETF structure:</strong> the resulting class centers form a simplex equiangular tight frame, a maximally separated symmetric configuration on the unit sphere.</li>
  </ol>
</div>

This matters because it places NSCL within the same broader geometric picture that appears in supervised learning. The supervised problem adjacent to DCL is not arbitrary; it has the same neural-collapse structure familiar from other well-studied supervised objectives.

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
    <strong>Figure 5.</strong> Neural collapse geometry: class centers form a simplex equiangular tight frame on the unit sphere. Drag the epoch slider to watch scattered features collapse into tight clusters at the ETF vertices. This is the same structure that arises at global optima of several supervised objectives, including NSCL.
  </div>
</div>

<div class="col" markdown="1">

<hr class="section-rule">

## Part II: The learned representations stay close

Loss-level closeness is informative, but it does not by itself imply similar learned geometry. Two nearby objectives can still drive optimization in meaningfully different directions. The second paper addresses this point directly.

### Shared-randomness coupling

Consider training DCL and NSCL under shared randomness: same initialization, same mini-batches, same augmentations, and the same hyperparameters. The only difference between the two runs is the objective.

To compare the learned representations, define the cosine similarity matrix

$$
\Sigma(Z)_{ij} = \cos(z_i,z_j),
$$

which directly captures representation geometry. From this matrix, standard alignment metrics such as **CKA** (centered kernel alignment) and **RSA** (representational similarity analysis) follow naturally.

### The similarity matrices stay close

Under this coupled training protocol, the difference between the DCL and NSCL similarity matrices throughout training satisfies a bound of the form

$$
\|\Sigma_T^{\mathrm{CL}}-\Sigma_T^{\mathrm{NS}}\|_F \lesssim \frac{e^{2/\tau}}{\tau C \sqrt{B}} \cdot \exp\left(\frac{1}{2\tau^2 B}\sum_{t=0}^{T-1}\eta_t\right)\cdot \left(\sum_{t=0}^{T-1}\eta_t\right).
$$

The right-hand side becomes smaller when the number of classes $C$ is larger, the batch size $B$ is larger, the temperature $\tau$ is higher, and the cumulative step size $\sum_{t=0}^{T-1}\eta_t$ is more moderate. So the same regimes that make the loss gap small also tend to keep the learned geometries aligned.

This immediately yields lower bounds on CKA and RSA:

<div class="math-block" markdown="1">

$$
\mathrm{CKA}_T \ge \frac{1-\rho_T}{1+\rho_T}, \qquad \mathrm{RSA}_T \ge \frac{1-r_T}{1+r_T}.
$$

</div>

</div>

<div class="col" markdown="1">

### Empirical confirmation: RSA and CKA are consistently high

The theoretical prediction is that representation geometry should remain aligned even when the two objectives are not identical. To test this directly, we train DCL and NSCL models under exactly matched conditions, same initialization, same mini-batches, same augmentations, and same optimizer settings, for 300 epochs, and then measure CKA and RSA between the learned representations. A score of 1.0 would indicate identical geometry; 0 would indicate no alignment.

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
    <strong>Figure 6.</strong> Representation similarity between DCL and NSCL models trained with matched initialization and mini-batch order. RSA and CKA values are consistently above 0.81 across all datasets and both architectures, confirming strong alignment in learned representation geometry despite different objectives.
  </div>
</div>

<div class="col" markdown="1">

Across all three datasets and both architectures, RSA and CKA exceed 0.81, and for CIFAR-100, all four measurements reach 0.91. Two patterns are especially notable.

First, alignment is strongest when the number of classes is largest, as in CIFAR-100 and mini-ImageNet. This matches the theory: more classes imply a smaller loss gap, which in turn keeps the optimization trajectories closer and the learned geometry more aligned.

Second, the scores are nearly identical across ResNet-50 and ViT-Base, indicating that the DCL-NSCL relationship is not an artifact of a particular architecture.

These results are also consistent with the form of the theoretical bound. The divergence scales as $1/(\tau C \sqrt{B})$, so when $C = 100$ and $B = 1024$, the predicted discrepancy is small and the empirical alignment is correspondingly high. The fact that CKA and RSA both stay above 0.8 even for CIFAR-10 suggests that the bound is not tight, but does capture the correct qualitative dependence.

### But weights can still diverge

In contrast, parameter-space coupling is much less stable. A typical bound on parameter divergence takes the form

$$
\|w_T^{\mathrm{CL}}-w_T^{\mathrm{NS}}\| \lesssim \frac{G e^{2/\tau}}{\beta\tau C} \cdot \left(\exp\left(\beta\sum_{t=0}^{T-1}\eta_t\right)-1\right).
$$

Although both bounds grow exponentially, the exponent in the similarity-matrix bound is much milder: it is scaled by $1/B$, whereas the weight-space bound has no analogous batch-size moderation. Thus, representation-level alignment can remain stable even when parameter-space divergence becomes large.

This is not especially surprising. Deep networks have substantial parameter redundancy, so two models can follow very different paths in weight space while still inducing very similar representation geometry.

</div>

<div class="col" markdown="1">

<hr class="section-rule">

## The right mental model

The standard description of contrastive learning is that it is a self-supervised method that nonetheless learns semantic structure. While this is true, it leaves open the question of why this happens so consistently.

The picture that emerges here is more specific. The self-supervised contrastive objective is already close to a supervised contrastive objective that excludes same-class negatives. That supervised objective has global minimizers with the same neural-collapse geometry familiar from supervised learning. And under shared training randomness, the two methods learn highly aligned representations throughout training.

From this perspective, the semantic behavior of contrastive learning is not an isolated phenomenon. It is tied to the fact that the self-supervised objective sits near a structured supervised counterpart, both analytically and geometrically.

This does not mean that self-supervised and supervised learning are identical, nor that labels are irrelevant. But it does suggest that the gap between the two is narrower, and more structured, than the usual informal description implies.

<hr class="section-rule">

<div class="takeaway flush-list">
  <div class="takeaway-label">Takeaway</div>
  <p style="margin-bottom: 1rem;">The main point is not merely that self-supervised and supervised contrastive learning are related. It is that the relation is surprisingly tight and structurally clean.</p>
  <ol>
    <li><strong>The objectives are close.</strong> The standard self-supervised contrastive loss approximates the NSCL loss, with a gap that shrinks as $O(1/C)$.</li>
    <li><strong>The nearby supervised problem has elegant geometry.</strong> NSCL minimizers exhibit augmentation collapse, within-class collapse, and simplex ETF structure.</li>
    <li><strong>The learned representations stay aligned.</strong> Under shared training randomness, DCL and NSCL produce highly similar representation geometry, even when their parameters diverge.</li>
  </ol>
  <p style="margin-top: 1rem; margin-bottom: 0;">A useful way to view contrastive learning, then, is not as a completely separate mechanism that somehow recovers semantics, but as a self-supervised procedure whose objective and learned geometry already lie close to a specific supervised counterpart.</p>
</div>

</div>
