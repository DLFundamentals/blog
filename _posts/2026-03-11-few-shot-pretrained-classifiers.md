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

*Based on: T. Galanti, A. György, M. Hutter. ["Generalization Bounds for Few-Shot Transfer Learning with Pretrained Classifiers"](https://arxiv.org/abs/2212.12532), arXiv 2022.*

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

Deep networks trained on large classification benchmarks such as ImageNet often transfer surprisingly well to new tasks. One trains on a large source dataset, freezes the learned representation, fits a simple head on only a handful of labeled examples from new classes, and the result often works remarkably well. This is a routine practice in modern machine learning.

From a theoretical perspective, however, this is not obvious. A classifier trained on ImageNet is optimized to separate the ImageNet classes. Why should the same representation also make it easy to separate **new** classes that never appeared during training? And why should only a few labeled examples be enough?

The explanation I will focus on here is geometric. If pretraining produces a feature space in which same-class samples form tight clusters and different class means are well separated, then this geometry can generalize beyond the observed source training data. It first extends from source samples to the underlying source-class distributions, and then from the observed source classes to new unseen classes. Once that happens, a nearest-center classifier can learn the target task from only a few labeled examples.

<div class="key-message">
The main idea is that few-shot transfer is not mysterious once the right geometric quantity is identified. What matters is not just that source classes are separated, but that their within-class variability is small relative to the distance between class means. If this geometry generalizes from source samples to source classes, and from source classes to unseen target classes, then few-shot learning becomes possible.
</div>

The argument has three parts:

<div class="flush-list">
  <ol>
    <li><strong>Model classes as i.i.d. random draws</strong> from a common population, so transfer to unseen classes becomes a well-posed question.</li>
    <li><strong>Measure clustering relative to separation</strong> using the class-distance normalized variance (CDNV).</li>
    <li><strong>Show that small source-task CDNV generalizes twice</strong>: first from source training samples to source-class population geometry, and then from source classes to unseen target classes.</li>
  </ol>
</div>

<hr class="section-rule">

## Part I: A formal model for transfer to new classes

### Classes as random objects

To reason about transfer to **new classes**, one needs a model that relates source and target tasks. The key step is to treat classes themselves as random objects.

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
    <strong>Figure 1.</strong> The class-sampling process. Source and target classes are drawn independently from the same population $\mathcal D$. Source classes receive many labeled examples; target classes receive only a few. The question is whether the feature geometry learned from the source task remains favorable enough to support classification on the target task.
  </div>
</div>

<br>

This captures the intended use of pretrained representations. We train on many source classes that are meant to represent a broader population, and then ask whether the learned feature map transfers to fresh classes drawn from that same population.

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

The population quantities describe the true geometry induced by $f$, while the empirical quantities describe what is observed from finitely many source or target samples.

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

This is the quantity of interest: when does a representation learned on $\ell$ source classes support few-shot learning on new classes?

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

Small CDNV is exactly the favorable regime for transfer. Same-class samples remain concentrated around their mean, while different class means stay well separated.

### Why CDNV is the right quantity

Few-shot learning with a nearest-center classifier succeeds only if a small number of labeled examples is enough to estimate each target class center accurately. That requires two things at once:

<div class="flush-list">
  <ol>
    <li><strong>Low within-class variability.</strong> Same-class samples must stay close to their class mean.</li>
    <li><strong>Large between-class separation.</strong> Different class means must be far apart.</li>
  </ol>
</div>

CDNV combines these requirements into a single scale-free quantity. If $V_f(Q_i,Q_j)$ is small, then the within-class noise of $Q_i$ is small relative to its separation from $Q_j$. In that regime, empirical class centers are stable, and nearest-center classification becomes reliable even when only a few labeled examples are available.

This is the key point: **the relevant geometric question is not merely whether the representation separates the source classes, but whether it makes within-class variability small relative to between-class distances.**

### The connection to neural collapse

CDNV is closely connected to the geometry of **neural collapse**. The NC1 component says that features from the same class collapse toward their class mean, which drives the numerator $\operatorname{Var}_f(Q_i)$ downward. The NC2 component says that class means become maximally spread out, ideally approaching a simplex equiangular tight frame, which enlarges the denominator $\|\mu_f(Q_i)-\mu_f(Q_j)\|^2$.

So neural collapse improves CDNV from both sides: it reduces within-class spread and increases between-class separation. This is exactly the geometry one would want for few-shot transfer.

### The two generalization steps

This is the conceptual heart of the story.

During pretraining, we only observe **source training samples** $\tilde S_1,\dots,\tilde S_\ell$. If the empirical source geometry looks favorable, meaning that within-class spread is small and class means are well separated, then with enough samples per source class this reflects the true population geometry of the source classes $\tilde P_1,\dots,\tilde P_\ell$. This is the first generalization step: **from source training samples to source-class population geometry**.

Then comes the second step. The source classes themselves are i.i.d. draws from $\mathcal D$. So if the observed source classes exhibit good population geometry on average, that property extends to new classes $P_1,\dots,P_k$ drawn independently from the same $\mathcal D$. This is the second generalization step: **from observed source classes to unseen target classes**.

That is the logic behind transfer. Clustering on the source training data generalizes first to the underlying source-class distributions, and then, because classes are sampled from a common population, to unseen classes as well.

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
    <strong>Figure 2.</strong> Visualization of the transfer mechanism. As source classes collapse into tight, well-separated clusters, the same learned feature geometry can also organize unseen target classes. Once the clusters are tight enough and the means are sufficiently separated, nearest-center classification succeeds from only a few target examples.
  </div>
</div>

<div class="card-stack">
  <div class="card">
    <div class="card-title">Step 1: source samples cluster</div>
    <p>During pretraining, source training samples concentrate around their class means. This is the empirical geometry that can be observed directly.</p>
  </div>
  <div class="card">
    <div class="card-title">Step 2: source-class geometry generalizes</div>
    <p>With enough samples per source class, this empirical clustering reflects the true geometry of the underlying source-class distributions, not just the finite training set.</p>
  </div>
  <div class="card">
    <div class="card-title">Step 3: unseen classes inherit the geometry</div>
    <p>Because classes themselves are i.i.d. draws from the same population $\mathcal D$, favorable geometry on many source classes extends to new target classes. Then nearest-center classification can succeed in the few-shot regime.</p>
  </div>
</div>

<hr class="section-rule">

## Part III: The transfer bound

### The main result

The paper formalizes this argument by proving that the transfer error $\mathcal{L}_{\mathcal D}(f)$ of a pretrained feature map $f$ is controlled by the average empirical CDNV on the source classes, together with terms that quantify the two generalization steps above. At a high level, the bound takes the form

<div class="math-block">

$$
\mathcal L_{\mathcal D}(f) \;\lesssim\; k\,\operatorname{Avg}_{i\neq j} V_f(\tilde S_i,\tilde S_j) + \frac{k\,\mathcal{C}(f)}{\min_{i\neq j}\|\mu_f(\tilde S_i)-\mu_f(\tilde S_j)\|} \left(\frac{n^2}{\sqrt{m}}+\frac{1}{\sqrt{\ell}}\right),
$$

</div>

where $\mathcal{C}(f)$ is a suitable notion of complexity of the pretrained model $f$.

### What each term means

**The geometric term** $k\,\operatorname{Avg}_{i\neq j} V_f(\tilde S_i,\tilde S_j)$ is small when the source training classes are tightly clustered relative to their separation. This is the observable signature of favorable few-shot transfer geometry.

**The $1/\sqrt{m}$ term** corresponds to the first generalization step. It says that with more samples per source class, the empirical clustering on $\tilde S_i$ better reflects the true geometry of the underlying source-class distributions $\tilde P_i$.

**The $1/\sqrt{\ell}$ term** corresponds to the second generalization step. It says that with more source classes, the average geometry observed on the source task better reflects the geometry of the full population of classes $\mathcal D$. This is the term that lets the argument extend to unseen target classes.

**The minimal class-distance term** $\min_{i\neq j}\|\mu_f(\tilde S_i)-\mu_f(\tilde S_j)\|$ is the minimum pairwise distance between empirical source class means. It captures the worst-case class separation in feature space. The larger this quantity is, the easier it is to distinguish classes by nearest-center classification, and the stronger the guarantee becomes. Under neural collapse, the class means become more uniformly and more maximally separated, which makes this term favorable.

So the theorem mirrors the conceptual picture quite closely: many samples per class allow one to pass from training points to source-class distributions, and many source classes allow one to pass from seen classes to unseen classes.

### Why the bound is meaningful in the few-shot regime

The key point is that the bound remains informative even when $n$, the number of labeled target examples per class, is small. The downstream learner is not required to discover complicated structure from very limited target data. That structure has already been built into the feature space during pretraining.

Once the representation makes unseen classes form tight, well-separated clusters, only a few target examples are needed to estimate their centers and classify by nearest center.

<hr class="section-rule">

## The right mental model

The usual informal explanation for few-shot transfer is that pretrained models learn “good features.” While not wrong, that description leaves open what exactly makes the features good for unseen classes.

The picture here is more specific. Pretraining shapes a feature space in which within-class variability is small relative to between-class distances. This favorable geometry can be observed empirically on the source task, generalized to the underlying source-class distributions, and then generalized again from observed source classes to unseen target classes. Once this happens, few-shot classification no longer needs to solve a difficult learning problem from scratch. It only needs to estimate a few class centers in an already well-structured feature space.

From this perspective, the success of pretrained classifiers in few-shot learning is best understood geometrically. The difficult part is done during pretraining, by constructing a representation whose clustering structure survives both kinds of generalization.

<hr class="section-rule">

## What this does and does not claim

This theory does **not** say that every pretrained classifier transfers well to every target task, or that exact neural collapse must hold perfectly, or that source and target may come from unrelated class populations.

What it *does* say is more precise: if the learned representation exhibits small class-distance normalized variance on many source training classes, then this geometry first generalizes to the underlying source-class distributions and then, because classes are i.i.d. draws from a common population, to unseen target classes. In that regime, few-shot nearest-center classification can succeed.

<hr class="section-rule">

<div class="takeaway flush-list">
  <div class="takeaway-label">Takeaway</div>
  <p style="margin-bottom: 1rem;">Few-shot transfer works because pretraining learns a feature geometry that generalizes twice.</p>
  <ol>
    <li><strong>From source samples to source classes.</strong> If source training points cluster tightly and class means are well separated, then with enough samples per class this reflects the true geometry of the source-class distributions.</li>
    <li><strong>From source classes to unseen classes.</strong> Because classes are i.i.d. draws from a common population, favorable geometry on many source classes extends to new target classes.</li>
    <li><strong>From geometry to few-shot learning.</strong> Once unseen classes also form tight, well-separated clusters, a nearest-center classifier can learn them from only a handful of labeled examples.</li>
  </ol>
  <p style="margin-top: 1rem; margin-bottom: 0;">The hard part of few-shot learning is therefore not done at transfer time. It is done during pretraining, by shaping a representation whose clustering geometry survives both kinds of generalization.</p>
</div>
