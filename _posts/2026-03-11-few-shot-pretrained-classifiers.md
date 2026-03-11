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

Deep networks trained on ordinary classification tasks often transfer remarkably well to new classes.

This is especially striking in the **few-shot** regime. We pretrain a model on many source classes, freeze its representation, and then fit a very simple classifier on top of only one or a few examples from each new class. Empirically, this often works much better than one might expect.

Why?

A common answer is that pretraining learns "good features." That is true, but it does not yet explain what geometric property of the feature space makes few-shot transfer possible.

The main message of this post is the following:

> <span style="color:#1e6bd6; font-weight:600;">
> Supervised pretraining can organize the feature space so that each class becomes a tight cluster around its mean, while different classes stay far apart. Once this happens, a new class can often be learned from only a few labeled examples.
> </span>

This is closely tied to a central part of **neural collapse**.

<div style="margin: 2rem 0;">
  <div style="display: grid; grid-template-columns: repeat(4, 1fr); gap: 16px; align-items: stretch;">

    <div style="padding: 14px; border: 1px solid #d8e2f1; border-radius: 12px; background: #f8fbff; text-align: center;">
      <strong>Pretraining</strong><br>
      Learn a feature map on many source classes
    </div>

    <div style="padding: 14px; border: 1px solid #d8e2f1; border-radius: 12px; background: #f8fbff; text-align: center;">
      <strong>Geometry</strong><br>
      Same-class features collapse around their mean
    </div>

    <div style="padding: 14px; border: 1px solid #d8e2f1; border-radius: 12px; background: #f8fbff; text-align: center;">
      <strong>Transfer</strong><br>
      Unseen classes inherit a similar geometry
    </div>

    <div style="padding: 14px; border: 1px solid #d8e2f1; border-radius: 12px; background: #f8fbff; text-align: center;">
      <strong>Few-shot adaptation</strong><br>
      A few samples are enough to estimate each new class center
    </div>

  </div>
</div>

<div style="margin-top: 1rem; font-size: 1.02rem; line-height: 1.5; text-align: left;">
  <strong>Figure 1.</strong>
  <strong>The basic picture.</strong>
  The source task shapes the feature space. If each class forms a tight cluster relative to the distance between class means, then simple classifiers built from only a few target examples can already work well.
</div>

<br>

## The setup

Let $f(x)$ be the pretrained feature map. On a new few-shot task, the simplest thing we can do is estimate the mean feature vector of each class from the few labeled examples we have, and classify by nearest center.

That gives the classifier

$$
h(x) = \arg\min_c \|f(x)-\mu_f(S_c)\|,
$$

where $S_c$ is the small labeled sample from target class $c$, and $\mu_f(S_c)$ is the empirical feature mean of that class.

This rule is almost embarrassingly simple.

So the real question is:

> **When should nearest-class-center classification work well on unseen classes?**

## The key geometric quantity

For two classes $Q_i$ and $Q_j$, define

$$
V_f(Q_i,Q_j) = \frac{\operatorname{Var}_f(Q_i)}{\|\mu_f(Q_i)-\mu_f(Q_j)\|^2}.
$$

This quantity compares two things:

- how spread out class $i$ is in feature space,
- how far its mean is from the mean of class $j$.

If $V_f(Q_i,Q_j)$ is small, then class $i$ is tight relative to the distance between the two class centers.

This is exactly the geometry we want. Small within-class variation and large between-class separation make the class structure stable.

In the language of neural collapse, this is a form of **class-feature variability collapse**.

## Why a few examples can be enough

Suppose a new target class really does form a compact cluster in feature space.

Then even if we only observe a few examples from that class, their empirical mean is already a decent estimate of the true class center. The classifier does not need to learn a complicated decision boundary from scratch. It mostly needs to locate where each new class sits.

That is why few-shot transfer becomes plausible.

The hard part is not the small classifier fitted on top. The hard part is learning a representation where classes already look like tight, separated clouds.

Once that geometry is in place, the downstream task becomes much easier.

## The main theoretical point

The theory studies a setting where source classes and target classes are both drawn from a broader population of classes. Under that model, one can define the transfer error of the feature map $f$ as the expected few-shot classification error on a new target task.

The high-level result is that this transfer error can be bounded by three ingredients:

$$
\text{transfer error}
\;\lesssim\;
\text{collapse on source classes}
+
\text{sample generalization term}
+
\text{class generalization term}.
$$

Very roughly:

- the first term measures how clustered the source classes are in feature space,
- the second term shrinks as the number of source samples per class grows,
- the third term shrinks as the number of source classes grows.

So the picture is:

1. many source samples stabilize the geometry within each source class,
2. many source classes make that geometry generalize to unseen classes,
3. collapse is what turns the pretrained representation into a good few-shot feature map.

## A slightly more concrete version

The full paper proves bounds of the form

$$
\mathcal{L}_{\mathcal D}(f)
\;\lesssim\;
(k-1)\,\operatorname{Avg}_{i\neq j} V_f(\tilde S_i,\tilde S_j)
+
\frac{k\,\mathrm{complexity}(f)}{\Lambda}\left(\frac{n^2}{\sqrt{m}}+\frac{1}{\sqrt{l}}\right),
$$

up to logarithmic factors.

Here:

- $\mathcal{L}_{\mathcal D}(f)$ is the expected few-shot transfer error,
- $l$ is the number of source classes,
- $m$ is the number of source samples per class,
- $n$ is the number of target samples per class,
- $\Lambda$ is the minimum distance between source class means in feature space.

Do not focus too much on the constants. The important part is the structure.

The bound says that transfer becomes good when:

- the source classes collapse,
- the class means remain separated,
- the pretrained representation is learned from many classes and many samples.

Most importantly, the guarantee is meaningful even in the few-shot regime where $n$ stays small.

## Why this is nontrivial

A lot of classical theory becomes informative only when the downstream task itself has many samples.

That is not the regime we care about here.

In few-shot learning, the target task may have only one or five examples per class. So we need a different explanation. The theory here says that the target task can still be easy, not because we have enough target data, but because pretraining has already built the right geometry into the feature space.

That is the central idea.

## Why nearest-center appears naturally

If classes collapse around their means, then nearest-center classification is no longer an arbitrary choice. It becomes the natural rule.

Indeed, once the representation is well clustered, the exact shape of a complicated classifier matters less. The main information is already contained in the class means.

This also explains why simple top-layer methods such as nearest-center, ridge regression, or logistic regression on frozen features often perform surprisingly well.

They are not doing the heavy lifting.

The geometry is.

## What the experiments support

Empirically, the same pattern appears across standard few-shot benchmarks:

- during supervised training on source classes, the collapse quantity decreases,
- the same geometry generalizes to held-out examples from the source classes,
- as the number of source classes grows, the target geometry improves too,
- and few-shot target accuracy rises along with it.

So the collapse is not just a training artifact. It tracks actual transfer performance on unseen classes.

That is exactly what one would want from a useful explanation.

## What this does and does not say

This does **not** say that every pretrained classifier will transfer well to every target task.

It does **not** say that exact neural collapse must literally occur.

And it does **not** remove the need for the source and target classes to come from a related family.

What it does say is more precise:

- there is a concrete geometric property of learned representations,
- that property emerges during ordinary supervised training,
- and that property is enough to explain why few-shot transfer can work.

So this is not just a vague story about "good representations." It is a specific mechanism.

## Takeaway

The success of few-shot transfer is not magic.

A pretrained classifier can work well on new classes because supervised training organizes the feature space in a highly favorable way:

1. each source class becomes concentrated around its mean,
2. different classes stay well separated,
3. this geometry generalizes to new classes,
4. so a few target examples are enough to estimate the new class centers.

In other words, pretraining does not need to solve the future task in advance.

It only needs to create a feature space where new classes are already easy to place.

That is why ordinary supervised pretraining can be such a strong few-shot learner.
