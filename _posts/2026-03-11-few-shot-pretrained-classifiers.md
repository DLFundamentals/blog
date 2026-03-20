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

*This post is based on: T. Galanti, A. György, M. Hutter. ["Generalization Bounds for Few-Shot Transfer Learning with Pretrained Classifiers"](https://arxiv.org/abs/2212.12532), JMLR 2023.*

---

Deep networks trained on large classification benchmarks such as ImageNet often transfer surprisingly well to new tasks. Train a classifier on a large source dataset, keep the learned representation, fit a simple linear head on a handful of labeled examples from new classes — and it works. Practitioners rely on this all the time.

But from a theoretical perspective, the phenomenon is puzzling. A classifier trained on ImageNet is optimized to separate the ImageNet classes. Why should the same representation also make it easy to separate **new** classes that never appeared during training? And why should only a handful of labeled examples be enough?

The main message of this post is:

> <span style="color:#1e6bd6; font-weight:600;">
> If supervised pretraining makes each class form a tight cluster in feature space while keeping different class means well separated, then new classes can be learned from only a few labeled examples using a nearest-center classifier. This geometric property — class-feature variability collapse — is what makes few-shot adaptation possible.
> </span>

The explanation has three parts, each developed in a section below:

1. **A formal model for transfer to new classes** — source and target classes are both drawn from a common population, making the transfer question precise.
2. **A geometric quantity that controls transfer** — the class-distance normalized variance (CDNV) measures how tight each class cluster is relative to class separation.
3. **A bound that connects geometry to few-shot error** — the transfer error is small when CDNV is small on the source classes, with generalization terms that shrink as the number of source classes and samples grow.

<style>
.task-block {
  margin: 2rem 0;
}
.task-title {
  font-weight: 700;
  font-size: 1.05rem;
  margin: 1.2rem 0 0.6rem 0;
}
.task-grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 12px;
  margin-bottom: 1.2rem;
}
.task-grid figure {
  margin: 0;
  text-align: center;
}
.task-grid img {
  width: 100%;
  aspect-ratio: 1 / 1;
  object-fit: cover;
  border-radius: 10px;
  display: block;
}
.task-grid figcaption {
  margin-top: 0.45rem;
  font-size: 0.95rem;
  color: #555;
}
@media (max-width: 700px) {
  .task-grid {
    grid-template-columns: 1fr;
  }
}
</style>

## Part I: A formal model for transfer to new classes

### Classes as random objects

Transfer learning should not be expected to work equally well for every possible downstream task. To reason about transfer to **new classes**, we need a model that relates source and target. The key idea is to treat classes themselves as random objects.

There is an unknown distribution $\mathcal D$ over a collection $\mathcal E$ of class-conditional distributions. Each element of $\mathcal E$ represents one possible class. The source task is built from class-conditionals $\tilde P_1,\dots,\tilde P_\ell \sim \mathcal D$, and the target task from new, independent draws $P_1,\dots,P_k \sim \mathcal D$.

<div class="task-block">
  <div class="task-title">Source task</div>
  <div class="task-grid">
    <figure>
      <img src="{{ site.baseurl }}/assets/figures/pretrained-classifiers/source_classes.png" alt="Source classes">
    </figure>
  </div>

  <div class="task-title">Target task</div>
  <div class="task-grid">
    <figure>
      <img src="{{ site.baseurl }}/assets/figures/pretrained-classifiers/target_classes.png" alt="Target classes">
    </figure>
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

This is the quantity the theory controls.

## Part II: The geometric quantity that controls transfer

### Class-distance normalized variance

For two class-conditional distributions $Q_i$ and $Q_j$, define the **class-distance normalized variance** (CDNV):

$$
V_f(Q_i,Q_j) = \frac{\operatorname{Var}_f(Q_i)}{\|\mu_f(Q_i)-\mu_f(Q_j)\|^2},
$$

where $\mu_f(Q) = \mathbb{E}_{x\sim Q}[f(x)]$ is the class mean and $\operatorname{Var}_f(Q) = \mathbb{E}_{x\sim Q}\|f(x)-\mu_f(Q)\|^2$ is the within-class variance in feature space.

This ratio compares how spread out a class is to how far apart the two class means are. Small CDNV means that each class forms a tight cluster relative to the distance between classes.

### Why this is the right quantity

If a new target class is diffuse in feature space, then a few labeled samples are not enough to locate its center reliably. But if the feature map makes each class tightly clustered, then even a few samples give a good estimate of the center. Small CDNV means low within-class noise, stable center estimates, and more reliable nearest-center classification. This is why **class-feature variability collapse** — the tendency of CDNV to decrease during training — is not just an aesthetic geometric property. It directly supports few-shot transfer.

### The connection to neural collapse

The CDNV is closely related to the NC1 property of **neural collapse**: during training, the features of same-class samples tend to concentrate around their class means. Under the additional NC2 property — that the class means form a maximally separated simplex equiangular tight frame — the minimum pairwise distance between class means is maximized, which pushes CDNV even lower. So neural collapse, when it occurs, creates precisely the geometric conditions that make few-shot transfer work.

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

**The $1/\sqrt{l}$ term** is more interesting: it captures **generalization across classes**. Since the target classes are unseen during pretraining, the representation must generalize not only across new examples, but across new class-conditionals. Having many source classes is essential in its own right — this is not reducible to having more total data.

**The denominator** $\Lambda$ measures the minimum separation between source class means. Under neural collapse (NC2), the class means form an equiangular tight frame, and $\Lambda$ is maximized: $\Lambda = \sqrt{2}\|\mu_f(\tilde S_i)\|$. So neural collapse simultaneously makes the numerator small (tight clusters) and the denominator large (well-separated means).

### Why this works in the true few-shot regime

The bound remains meaningful when $n$ is a small constant while $m$ and $l$ grow. This is the key point: the burden of learning is shifted entirely to pretraining. If the source task is rich enough (many classes, many samples per class) and the learned feature geometry is sufficiently collapsed and separated, then the downstream target task can be solved from very little data. The transfer error converges to zero even with a fixed, small number of target samples — a property that distinguishes this result from standard generalization bounds that require the number of target samples to grow.

## What this does and does not claim

This theory does **not** say that every pretrained classifier transfers well to every target task, or that exact neural collapse must hold perfectly, or that source and target can come from unrelated populations.

What it does say is precise: there is a concrete geometric quantity (CDNV) that can be measured during training, and when that quantity is small on the source classes and the source task is rich enough, the pretrained representation provably supports few-shot adaptation to new classes. This is the first generalization guarantee for transfer learning that remains meaningful in the true few-shot regime.

## Takeaway

Few-shot transfer works because pretraining learns a feature space with the right geometry. This operates in three layers:

1. **Tight clusters.** Class-feature variability collapse makes each class concentrated around its mean, so a few samples suffice to estimate the center.

2. **Well-separated means.** Neural collapse maximizes the distance between class centers, making the CDNV small and the denominator $\Lambda$ large.

3. **Geometry that generalizes.** With many source classes, the collapsed geometry extends to unseen target classes — the $1/\sqrt{l}$ term ensures that the representation learned on $l$ source classes transfers to new classes from the same population.

The result is that few-shot adaptation does not require the downstream learner to discover complex structure from tiny data. The hard work has already been done by pretraining: the geometry of the feature space is doing the real work.
