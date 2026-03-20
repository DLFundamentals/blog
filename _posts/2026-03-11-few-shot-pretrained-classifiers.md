---
layout: post
title: "Why Pretrained Classifiers Work So Well in Few-Shot Learning"
date: 2026-03-11
author: Tomer Galanti
tags:
  - deep-learning
  - few-shot-learning
  - transfer-learning
  - neural-collapse
  - theory
  - foundation-models
excerpt: "A geometric explanation for why ordinary supervised pretraining can transfer remarkably well to new classes with only a few labeled examples."
---

*Based on: T. Galanti, A. Gyorgy, M. Hutter. ["Generalization Bounds for Few-Shot Transfer Learning with Pretrained Classifiers"](https://arxiv.org/abs/2212.12532), Arxiv 2022.*

---

## Introduction

Deep networks trained on large classification benchmarks such as ImageNet often transfer surprisingly well to new tasks. Train a classifier on a large source dataset, keep the learned representation, fit a simple linear head on a handful of labeled examples from new classes, and it works. Practitioners rely on this all the time.

But from a theoretical perspective, the phenomenon is puzzling. A classifier trained on ImageNet is optimized to separate the ImageNet classes. Why should the same representation also make it easy to separate **new** classes that never appeared during training? And why should only a handful of labeled examples be enough?

<div class="key-message">
If supervised pretraining makes each class form a tight cluster in feature space while keeping different class means well separated, then new classes can be learned from only a few labeled examples using a nearest-center classifier. This geometric property — class-feature variability collapse — is what makes few-shot adaptation possible.
</div>

The explanation has three parts:

1. **A formal model for transfer to new classes** — source and target classes are both drawn from a common population, making the transfer question precise.
2. **A geometric quantity that controls transfer** — the class-distance normalized variance (CDNV) measures how tight each class cluster is relative to class separation.
3. **A bound that connects geometry to few-shot error** — the transfer error is small when CDNV is small on the source classes, with generalization terms that shrink as the number of source classes and samples grow.

<hr class="section-rule">

## Part I: A formal model for transfer to new classes

### Classes as random objects

Transfer learning should not be expected to work equally well for every possible downstream task. To reason about transfer to **new classes**, we need a model that relates source and target. The key idea is to treat classes themselves as random objects.

There is an unknown distribution $\mathcal D$ over a collection $\mathcal E$ of class-conditional distributions. Each element of $\mathcal E$ represents one possible class. The source task is built from class-conditionals $\tilde P_1,\dots,\tilde P_\ell \sim \mathcal D$, and the target task from new, independent draws $P_1,\dots,P_k \sim \mathcal D$.

<div class="figure col-wide">
  <div class="figure-grid" style="grid-template-columns: repeat(2, 1fr);">
    <div class="figure-grid-item">
      <img src="{{ '/assets/figures/pretrained-classifiers/source_classes.png' | relative_url }}" alt="Source classes">
      <div class="label">Source classes ($\ell$ draws from $\mathcal{D}$)</div>
    </div>
    <div class="figure-grid-item">
      <img src="{{ '/assets/figures/pretrained-classifiers/target_classes.png' | relative_url }}" alt="Target classes">
      <div class="label">Target classes ($k$ new draws from $\mathcal{D}$)</div>
    </div>
  </div>
  <div class="figcaption">
    <strong>Figure 1.</strong> Source and target classes are both drawn from the same population $\mathcal{D}$. The representation learned from the source classes must generalize to new target classes.
  </div>
</div>

This captures the intended use of pretrained representations: we train on many source classes that are representative of a broader population, then ask whether the learned features transfer to new classes drawn from that same population.

### The downstream procedure

We train on the source task with many samples per class ($m$ large), learn a feature map $f: \mathcal{X} \to \mathbb{R}^p$, then freeze it. For the target task, we observe only $n$ samples per class ($n$ small) and classify by nearest class center:

$$
h(x)=\arg\min_{c\in[k]} \|f(x)-\mu_f(S_c)\|, \qquad \mu_f(S_c)=\frac{1}{n}\sum_{i=1}^n f(x_{ci}).
$$

The **transfer error** is the expected few-shot error over newly sampled target tasks:

$$
\mathcal L_{\mathcal D}(f) = \mathbb E_{P_1,\dots,P_k \sim \mathcal D} \; \mathbb E_{S_c \sim P_c^n} \left[L_P(h)\right].
$$

<hr class="section-rule">

## Part II: The geometric quantity that controls transfer

### Class-distance normalized variance

For two class-conditional distributions $Q_i$ and $Q_j$, define the **class-distance normalized variance** (CDNV):

<div class="math-block">

$$
V_f(Q_i,Q_j) = \frac{\operatorname{Var}_f(Q_i)}{\|\mu_f(Q_i)-\mu_f(Q_j)\|^2},
$$

</div>

where $\mu_f(Q) = \mathbb{E}_{x\sim Q}[f(x)]$ is the class mean and $\operatorname{Var}_f(Q) = \mathbb{E}_{x\sim Q}\|f(x)-\mu_f(Q)\|^2$ is the within-class variance in feature space.

This ratio compares how spread out a class is to how far apart the two class means are. Small CDNV means that each class forms a tight cluster relative to the distance between classes.

### Why this is the right quantity

If a new target class is diffuse in feature space, then a few labeled samples are not enough to locate its center reliably. But if the feature map makes each class tightly clustered, then even a few samples give a good estimate of the center. Small CDNV means low within-class noise, stable center estimates, and more reliable nearest-center classification. This is why **class-feature variability collapse** — the tendency of CDNV to decrease during training — is not just an aesthetic geometric property. It directly supports few-shot transfer.

### The connection to neural collapse

The CDNV is closely related to the NC1 property of **neural collapse**: during training, the features of same-class samples tend to concentrate around their class means. Under the additional NC2 property — that the class means form a maximally separated simplex equiangular tight frame — the minimum pairwise distance between class means is maximized, which pushes CDNV even lower. So neural collapse, when it occurs, creates precisely the geometric conditions that make few-shot transfer work.

<div class="col-wide">
  <div class="embed-wrap">
    <iframe
      src="{{ '/assets/figures/pretrained-classifiers/fewshot_transfer_visualization.html' | relative_url }}"
      height="420"
      loading="lazy"
      title="Few-shot transfer visualization">
    </iframe>
  </div>
  <div class="figcaption">
    <strong>Figure 2.</strong> Interactive simulation of the transfer mechanism. Drag the epoch slider to watch source classes (left) collapse into tight, well-separated clusters via neural collapse. Simultaneously, unseen target classes (right) also concentrate in the same feature space, even though they were never trained on. Once collapse is strong, the NCC decision boundaries (red dashed lines) emerge and classify target samples accurately from just 5 examples per class.
  </div>
</div>

<div class="card-stack">
  <div class="card">
    <div class="card-title">Watch source collapse</div>
    <p>Drag the epoch slider from 0 to 200. The source classes in the left panel start scattered, then cluster tightly around their means. This is NC1, or within-class variability collapse. The class means simultaneously spread apart. This is NC2.</p>
  </div>
  <div class="card">
    <div class="card-title">Target classes follow</div>
    <p>The right panel shows unseen target classes with only 5 samples each. As the feature map improves from source training, these target samples also concentrate, even though the representation was never optimized for them. This is the transfer.</p>
  </div>
  <div class="card">
    <div class="card-title">NCC boundaries appear</div>
    <p>Past epoch 160, the red dashed NCC decision boundaries emerge. With tight clusters and well-separated means, the nearest-center classifier achieves high accuracy from just a handful of target examples. Watch the CDNV values drop as the classifier accuracy rises.</p>
  </div>
</div>

<hr class="section-rule">

## Part III: The transfer bound

### The main result

The paper proves that the transfer error $\mathcal{L}_{\mathcal D}(f)$ of a pretrained feature map $f$ is controlled by the average CDNV on the source classes plus generalization terms. At a high level, the bound has the form

$$
\mathcal L_{\mathcal D}(f) \;\lesssim\; (k-1)\,\operatorname{Avg}_{i\neq j} V_f(\tilde S_i,\tilde S_j) + \frac{k\,\mathrm{complexity}(f)}{\Lambda} \left(\frac{n^2}{\sqrt{m}}+\frac{1}{\sqrt{l}}\right),
$$

up to logarithmic factors, where $\Lambda = \min_{i\neq j}\|\mu_f(\tilde S_i)-\mu_f(\tilde S_j)\|$ is the minimum pairwise distance between source class means.

### What each term means

**The geometric term** $(k-1)\operatorname{Avg}_{i\neq j} V_f(\tilde S_i,\tilde S_j)$ is small when the source classes are tightly clustered relative to their separation. This is the neural-collapse-driven quantity: if pretraining produces strong class-feature variability collapse, this term becomes small.

**The $1/\sqrt{m}$ term** is a standard sample-complexity term. With more examples from each source class, the empirical geometry of each class better reflects its true geometry.

**The $1/\sqrt{l}$ term** is more interesting: it captures **generalization across classes**. Since the target classes are unseen during pretraining, the representation must generalize not only across new examples, but across new class-conditionals. Having many source classes is essential in its own right. This is not reducible to having more total data.

**The denominator** $\Lambda$ measures the minimum separation between source class means. Under neural collapse (NC2), the class means form an equiangular tight frame, and $\Lambda$ is maximized: $\Lambda = \sqrt{2}\|\mu_f(\tilde S_i)\|$. So neural collapse simultaneously makes the numerator small (tight clusters) and the denominator large (well-separated means).

### Why this works in the true few-shot regime

The bound remains meaningful when $n$ is a small constant while $m$ and $l$ grow. This is the key point: the burden of learning is shifted entirely to pretraining. If the source task is rich enough (many classes, many samples per class) and the learned feature geometry is sufficiently collapsed and separated, then the downstream target task can be solved from very little data.

<hr class="section-rule">

## What this does and does not claim

This theory does **not** say that every pretrained classifier transfers well to every target task, or that exact neural collapse must hold perfectly, or that source and target can come from unrelated populations.

What it does say is precise: there is a concrete geometric quantity (CDNV) that can be measured during training, and when that quantity is small on the source classes and the source task is rich enough, the pretrained representation provably supports few-shot adaptation to new classes. This is the first generalization guarantee for transfer learning that remains meaningful in the true few-shot regime.

<hr class="section-rule">

<div class="takeaway">
  <div class="takeaway-label">Takeaway</div>
  <p style="margin-bottom: 1rem;">Few-shot transfer works because pretraining learns a feature space with the right geometry. This operates in three layers:</p>
  <ol>
    <li><strong>Tight clusters.</strong> Class-feature variability collapse makes each class concentrated around its mean, so a few samples suffice to estimate the center.</li>
    <li><strong>Well-separated means.</strong> Neural collapse maximizes the distance between class centers, making the CDNV small and the denominator $\Lambda$ large.</li>
    <li><strong>Geometry that generalizes.</strong> With many source classes, the collapsed geometry extends to unseen target classes. The $1/\sqrt{l}$ term ensures that the representation learned on $l$ source classes transfers to new classes from the same population.</li>
  </ol>
  <p style="margin-top: 1rem; margin-bottom: 0;">The result is that few-shot adaptation does not require the downstream learner to discover complex structure from tiny data. The hard work has already been done by pretraining: the geometry of the feature space is doing the real work.</p>
</div>
