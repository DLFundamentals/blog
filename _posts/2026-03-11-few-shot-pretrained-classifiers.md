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

*Based on: T. Galanti, A. Gyorgy, M. Hutter. ["Generalization Bounds for Few-Shot Transfer Learning with Pretrained Classifiers"](https://arxiv.org/abs/2212.12532), arXiv 2022.*

---

## Introduction

Deep networks trained on large classification benchmarks such as ImageNet often transfer surprisingly well to new tasks. Train a classifier on a large source dataset, keep the learned representation, fit a simple head on a handful of labeled examples from new classes, and it works. Practitioners rely on this all the time.

But from a theoretical perspective, the phenomenon is puzzling. A classifier trained on ImageNet is optimized to separate the ImageNet classes. Why should the same representation also make it easy to separate **new** classes that never appeared during training? And why should only a handful of labeled examples be enough?

<div class="key-message">
The key idea is geometric. If pretraining makes same-class features tightly clustered and different class means well separated on the source task, then this geometry first generalizes to fresh samples from those source classes, and then it also extends to new unseen classes. Once that happens, a nearest-center classifier can learn the new classes from only a few examples.
</div>

The explanation has three steps:

1. **Model classes as i.i.d. random draws** from a common population, so transfer to unseen classes becomes a well-posed question.
2. **Measure clustering relative to separation** using the class-distance normalized variance (CDNV).
3. **Show that small CDNV on the source task generalizes twice**: first from source training samples to source-class population geometry, and then from source classes to unseen target classes.

<hr class="section-rule">

## Part I: A formal model for transfer to new classes

### Classes as random objects

To reason about transfer to **new classes**, we need a model that relates source and target tasks. The key idea is to treat classes themselves as random objects.

There is an unknown distribution $\mathcal D$ over a collection $\mathcal E$ of class-conditional distributions. Each element of $\mathcal E$ represents one possible class. The source task is built from i.i.d. draws

$$
\tilde P_1,\dots,\tilde P_\ell \sim \mathcal D,
$$

and the target task is built from new, independent i.i.d. draws

$$
P_1,\dots,P_k \sim \mathcal D.
$$

So source and target classes are different, but they come from the same underlying population of classes.

<div class="col-wide">
  <div class="embed-wrap">
    <iframe
      src="{{ '/assets/figures/pretrained-classifiers/sampling_process.html' | relative_url }}"
      height="440"
      loading="lazy"
      title="Class sampling process">
    </iframe>
  </div>
  <div class="figcaption">
    <strong>Figure 1.</strong> The class-sampling process. Click through to watch source and target classes drawn independently from the population $\mathcal{D}$. Source classes receive $m = 18$ samples each (dense clusters); target classes receive only $n = 4$ (sparse, outlined dots). The representation learned from the source must generalize to classify the target from these few examples alone.
  </div>
</div>

<br>

This captures the intended use of pretrained representations: we train on many source classes that are representative of a broader population, then ask whether the learned features transfer to new classes drawn from that same population.

### Notation for feature means and variances

Let $f:\mathcal X \to \mathbb R^p$ be the learned feature map.

For any class-conditional distribution $Q \in \mathcal E$, define its **population feature mean**

$$
\mu_f(Q) := \mathbb E_{x\sim Q}[f(x)]
$$

and its **population within-class variance**

$$
\operatorname{Var}_f(Q) := \mathbb E_{x\sim Q}\|f(x)-\mu_f(Q)\|^2.
$$

For a finite sample $S=\{x_1,\dots,x_n\}$ from one class, define the **empirical feature mean**

$$
\mu_f(S) := \frac{1}{n}\sum_{i=1}^n f(x_i).
$$

We will use population quantities to describe the true geometry induced by $f$, and empirical quantities to describe what we observe from finitely many source or target samples.

### Source pretraining and target adaptation

For each source class $\tilde P_i$, we observe a training set $\tilde S_i$ of size $m$, with $\tilde S_i \sim \tilde P_i^m$. Using these source classes and labels, we train a classifier and obtain a feature map $f$.

At transfer time, we freeze $f$. For each new target class $P_c$, we observe only a few labeled examples $S_c \sim P_c^n$, where $n$ is small. We then classify by nearest empirical class center:

$$
h(x)=\arg\min_{c\in[k]} \|f(x)-\mu_f(S_c)\|.
$$

The **transfer error** is the expected few-shot error over newly sampled target tasks:

$$
\mathcal L_{\mathcal D}(f) = \mathbb E_{P_1,\dots,P_k \sim \mathcal D} \; \mathbb E_{S_c \sim P_c^n} \left[L_P(h)\right].
$$

This is the quantity we want to understand: when does a representation learned on $\ell$ source classes support few-shot learning on new classes?

<hr class="section-rule">

## Part II: The geometric quantity that controls transfer

### Class-distance normalized variance

For two class-conditionals $Q_i$ and $Q_j$, define the **class-distance normalized variance** (CDNV):

<div class="math-block">

$$
V_f(Q_i,Q_j) = \frac{\operatorname{Var}_f(Q_i)}{\|\mu_f(Q_i)-\mu_f(Q_j)\|^2}.
$$

</div>

This quantity compares two competing effects in feature space: the within-class spread of $Q_i$ and the separation between the class means of $Q_i$ and $Q_j$.

Small CDNV is exactly the favorable regime for transfer: samples from the same class form a tight cluster, while different classes remain well separated.

### Why CDNV is the right quantity

Few-shot learning with a nearest-center classifier succeeds only if a small number of labeled samples is enough to estimate each target class center accurately. That requires two things at once:

1. **Low within-class variability**: same-class samples must stay close to their class mean.
2. **Large between-class separation**: different class means must be far apart.

CDNV combines these two requirements into a single scale-free quantity. If $V_f(Q_i,Q_j)$ is small, then the noise within class $Q_i$ is small relative to its separation from class $Q_j$. In that regime, empirical class centers are stable, and nearest-center classification becomes reliable even from a few labeled examples.

This is why **class-feature variability collapse** is not just a qualitative geometric pattern. It directly measures whether the representation makes few-shot transfer possible.

### The connection to neural collapse

CDNV is closely tied to the geometry of **neural collapse**. The NC1 component says that features from the same class collapse toward their class mean, which drives the numerator $\operatorname{Var}_f(Q_i)$ downward. The NC2 component says that class means become maximally spread out, ideally approaching a simplex equiangular tight frame, which enlarges the denominator $\|\mu_f(Q_i)-\mu_f(Q_j)\|^2$.

So neural collapse improves CDNV from both sides: it shrinks within-class spread and enlarges between-class separation. That is exactly why it creates the right geometry for few-shot transfer.

### The two generalization steps

This is the conceptual heart of the story.

First, during pretraining we only observe **source training samples** $\tilde S_1,\dots,\tilde S_\ell$. If the empirical source geometry looks good — small within-class spread and large separation between class means — then with enough samples per class, this reflects the true population geometry of the source classes $\tilde P_1,\dots,\tilde P_\ell$. This is the first generalization step: **from source training samples to source-class population geometry**.

Second, the source classes themselves are i.i.d. draws from $\mathcal D$. So if the source classes exhibit good population geometry on average, then this property extends to new classes $P_1,\dots,P_k$ drawn from the same $\mathcal D$. This is the second generalization step: **from observed source classes to unseen target classes**.

That is the logic behind transfer: clustering on source training data generalizes to clustering for the underlying source classes, and because classes are i.i.d., extends to unseen classes too.

<div class="col-wide">
  <div class="embed-wrap">
    <iframe
      src="{{ '/assets/figures/pretrained-classifiers/fewshot_transfer_visualization.html' | relative_url }}"
      height="450"
      loading="lazy"
      title="Few-shot transfer visualization">
    </iframe>
  </div>
  <div class="figcaption">
    <strong>Figure 2.</strong> Interactive simulation of the transfer mechanism. As source classes collapse into tight, well-separated clusters, the same learned feature geometry also organizes unseen target classes. Once the clusters are tight enough and the means are far enough apart, nearest-center classification succeeds from just a few target examples. Drag to rotate.
  </div>
</div>

<div class="card-stack">
  <div class="card">
    <div class="card-title">Step 1: source samples cluster</div>
    <p>As training proceeds, source training samples concentrate around their class means. This is the empirical geometry you can see directly during pretraining.</p>
  </div>
  <div class="card">
    <div class="card-title">Step 2: source-class geometry generalizes</div>
    <p>With enough samples per source class, this empirical clustering reflects the true geometry of the underlying source-class distributions, not just the finite training set.</p>
  </div>
  <div class="card">
    <div class="card-title">Step 3: unseen classes inherit the geometry</div>
    <p>Because the classes themselves are i.i.d. draws from the same population $\mathcal D$, good geometry on many source classes implies good geometry on new target classes as well. Then nearest-center classification works in the few-shot regime.</p>
  </div>
</div>

<hr class="section-rule">

## Part III: The transfer bound

### The main result

To formalize the argument, the paper proves that the transfer error $\mathcal{L}_{\mathcal D}(f)$ of a pretrained feature map $f$ is controlled by the average empirical CDNV on the source classes plus generalization terms. At a high level, the bound has the form

<div class="math-block">

$$
\mathcal L_{\mathcal D}(f) \;\lesssim\; (k-1)\,\operatorname{Avg}_{i\neq j} V_f(\tilde S_i,\tilde S_j) + \frac{k\,\mathcal{C}(f)}{\min_{i\neq j}\|\mu_f(\tilde S_i)-\mu_f(\tilde S_j)\|} \left(\frac{n^2}{\sqrt{m}}+\frac{1}{\sqrt{\ell}}\right),
$$

</div>

where $\mathcal{C}(f)$ is some notion of complexity of the pre-trained model $f$.

### What each term means

**The geometric term** $(k-1)\,\operatorname{Avg}_{i\neq j} V_f(\tilde S_i,\tilde S_j)$ is small when the source training classes are tightly clustered relative to their separation. This is the observable signature of good few-shot transfer geometry.

**The $1/\sqrt{m}$ term** is the first generalization step. It says that with more samples per source class, the empirical clustering on $\tilde S_i$ better reflects the true geometry of the underlying source-class distributions $\tilde P_i$.

**The $1/\sqrt{\ell}$ term** is the second generalization step. It says that with more source classes, the average geometry seen on the observed source classes better reflects the geometry of the full population of classes $\mathcal D$. This is exactly the term that lets the argument extend to unseen target classes.

**The $\min_{i\neq j}|\mu_f(\tilde S_i)-\mu_f(\tilde S_j)|$ term** is the minimum pairwise distance between the empirical source class means in feature space. It captures the worst-case separation between classes: the larger this quantity is, the easier it is to distinguish classes by nearest-center classification, and the stronger the transfer guarantee becomes. Under neural collapse, the class means become more uniformly and maximally separated, which makes this term large.

So the theorem mirrors the conceptual story: many samples per class let you generalize from training points to the source-class distributions, and many source classes let you generalize from seen classes to unseen classes.

### Why neural collapse helps

Neural collapse improves both parts of the geometry. It shrinks within-class variability, which reduces the CDNV numerator. And under NC2, the class means become maximally separated, which enlarges the denominator. In the ideal ETF geometry, the class centers are as far apart as possible given their norm. So neural collapse is not merely correlated with transfer. It improves exactly the quantity that appears in the bound.

### Why this works in the true few-shot regime

The bound remains meaningful when $n$ is a small constant while $m$ and $\ell$ grow. This is the key point: the downstream learner does not need to discover complex structure from tiny data. Pretraining has already shaped the feature space so that new classes also look clusterable.

Once the representation has that geometry, a few target examples are enough to estimate the new class centers and classify by proximity to them.

<hr class="section-rule">

## What this does and does not claim

This theory does **not** say that every pretrained classifier transfers well to every target task, or that exact neural collapse must hold perfectly, or that source and target can come from unrelated populations.

What it does say is precise: if the learned representation exhibits small class-distance normalized variance on many source training classes, then this geometry first generalizes to the underlying source-class distributions and then, because classes are i.i.d. draws from a common population, to unseen target classes. That is why few-shot nearest-center classification can succeed.

<hr class="section-rule">

<div class="takeaway">
  <div class="takeaway-label">Takeaway</div>
  <p style="margin-bottom: 1rem;">Few-shot transfer works because pretraining learns a feature space whose geometry generalizes twice:</p>
  <ol>
    <li><strong>From source samples to source classes.</strong> If source training points cluster tightly and class means are well separated, then with enough samples per class this reflects the true geometry of the source-class distributions.</li>
    <li><strong>From source classes to unseen classes.</strong> Because classes are i.i.d. draws from a common population, good geometry on many source classes extends to new target classes.</li>
    <li><strong>From geometry to few-shot learning.</strong> Once unseen classes also form tight, well-separated clusters, a nearest-center classifier can learn them from only a handful of labeled examples.</li>
  </ol>
  <p style="margin-top: 1rem; margin-bottom: 0;">The hard part of few-shot learning is not done at transfer time. It is done during pretraining, by shaping a representation whose clustering geometry survives both kinds of generalization.</p>
</div>
