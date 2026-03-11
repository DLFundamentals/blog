---
layout: post
title: "Why Self-Supervised Contrastive Learning Looks Surprisingly Supervised"
date: 2026-03-11
author: Tomer Galanti
tags:
  - deep-learning
  - self-supervised-learning
  - contrastive-learning
  - supervised-learning
  - theory
  - representation-learning
excerpt: "Why a standard self-supervised contrastive loss is often very close to a supervised contrastive loss that excludes same-class negatives."
---

Self-supervised contrastive learning is one of the main success stories of modern representation learning.

It trains on unlabeled data, yet the features it learns often look strikingly semantic. Samples from the same class cluster together, simple linear probes work well, and downstream transfer is often surprisingly strong.

That raises a basic question:

> **Why should a loss that never sees labels end up behaving as if it cares about them?**

The main message of this post is the following:

> <span style="color:#1e6bd6; font-weight:600;">
> In many-class problems, the standard self-supervised contrastive loss is close to a supervised contrastive loss that excludes same-class negatives.  
> So even without labels, the optimization objective is already much closer to a label-aware one than it may first appear.
> </span>

This is the key point.

The usual story says that self-supervised contrastive learning pulls together two augmentations of the same sample and pushes away everything else. That is true. But when the number of semantic classes is large, "everything else" is overwhelmingly made of samples from *different* classes anyway. The accidental penalty on same-class examples becomes relatively small.

So the self-supervised loss is not as far from supervised learning as it looks.

## The setup

Suppose we have a dataset

$$
S = \{(x_i,y_i)\}_{i=1}^N,
$$

with $C$ hidden semantic classes, but during training we only use the inputs $x_i$, not the labels $y_i$.

For each sample $x_i$, we generate $K$ augmentations

$$
x_i^1, x_i^2, \dots, x_i^K,
$$

and map them through an encoder $f$ to embeddings

$$
z_i^l = f(x_i^l).
$$

We consider the decoupled contrastive loss (DCL), which has the form

$$
\mathcal{L}^{\mathrm{DCL}}(f)
=
-\frac{1}{K^2N}
\sum_{l_1,l_2=1}^K
\sum_{i=1}^N
\log\left(
\frac{\exp(\mathrm{sim}(z_i^{l_1},z_i^{l_2}))}
{\sum_{l_3=1}^K\sum_{j\neq i}\exp(\mathrm{sim}(z_i^{l_1},z_j^{l_3}))}
\right).
$$

This is a standard self-supervised contrastive objective. The numerator rewards two views of the same sample for being similar. The denominator pushes the anchor away from all other samples.

Notice what is missing:

> **the denominator does not know which samples share the same class.**

It treats all other samples as negatives, even if some of them actually belong to the same semantic category.

That seems very different from supervised contrastive learning. But the gap is smaller than it looks.

## A supervised version that removes same-class negatives

Now imagine a supervised variant of the same loss, where we exclude same-class samples from the denominator.

Call this the **negatives-only supervised contrastive loss** (NSCL). It is the same formula as DCL, except that in the denominator we sum only over samples with different labels:

$$
\mathcal{L}^{\mathrm{NSCL}}(f)
=
-\frac{1}{K^2N}
\sum_{l_1,l_2=1}^K
\sum_{i=1}^N
\log\left(
\frac{\exp(\mathrm{sim}(z_i^{l_1},z_i^{l_2}))}
{\sum_{l_3=1}^K\sum_{j:y_j\neq y_i}\exp(\mathrm{sim}(z_i^{l_1},z_j^{l_3}))}
\right).
$$

This objective is label-aware. It still pushes away different classes, but it no longer punishes same-class points for being close.

So the difference between DCL and NSCL is completely localized:

- **DCL** includes same-class samples in the denominator,
- **NSCL** removes them.

Everything hinges on how much those extra same-class terms matter.

## Why the gap is small

Fix one anchor sample $x_i$.

In the DCL denominator, we sum over all other samples. In the NSCL denominator, we sum only over samples from different classes.

So the only extra terms in DCL are the same-class examples.

If each class contains at most $n_{\max}$ samples, then for a given anchor there are at most

$$
K(n_{\max}-1)
$$

extra same-class terms in the DCL denominator.

But the number of different-class terms is at least

$$
K(N-n_{\max}).
$$

So when the dataset has many classes, the number of accidental same-class negatives is small relative to the total number of negatives.

That is the whole intuition.

If the denominator is dominated by different-class samples anyway, then removing the same-class ones should not change the loss very much.

## A back-of-the-envelope calculation

To see this cleanly, imagine for a moment that all cross-sample similarity terms are roughly the same, so that

$$
\exp(\mathrm{sim}(z_i,z_j)) \approx \gamma
\qquad \text{for all } i\neq j.
$$

Then the DCL denominator is approximately

$$
K(N-1)\gamma,
$$

while the NSCL denominator is approximately

$$
K(N-n_{\max})\gamma.
$$

So the difference between the two losses is roughly

$$
\log\left(\frac{K(N-1)\gamma}{K(N-n_{\max})\gamma}\right)
=
\log\left(1+\frac{n_{\max}-1}{N-n_{\max}}\right).
$$

Ignoring lower-order details, this is on the scale of

$$
\frac{n_{\max}}{N-n_{\max}}.
$$

For a balanced dataset with $C$ classes, we have

$$
n_{\max} = \frac{N}{C},
$$

so this becomes

$$
\frac{n_{\max}}{N-n_{\max}} = \frac{1}{C-1}.
$$

That means:

> **the loss gap shrinks like $1/C$.**

So as the number of classes grows, the self-supervised loss and the supervised loss become close.

Already this explains a lot. If the objective itself is nearly supervised, then it is much less mysterious that the learned representation starts to look supervised too.

## The formal statement

The real theorem does not need the crude assumption that all similarities are approximately constant.

For any encoder $f$, one can prove

$$
\mathcal{L}^{\mathrm{NSCL}}(f)
\le
\mathcal{L}^{\mathrm{DCL}}(f)
\le
\mathcal{L}^{\mathrm{NSCL}}(f)
+
\log\left(1+\frac{n_{\max}e^2}{N-n_{\max}}\right).
$$

Using $\log(1+x)\le x$, this gives

$$
\mathcal{L}^{\mathrm{DCL}}(f)
\le
\mathcal{L}^{\mathrm{NSCL}}(f)
+
\frac{n_{\max}e^2}{N-n_{\max}}.
$$

And in the balanced case,

$$
\frac{n_{\max}}{N-n_{\max}} = \frac{1}{C-1},
$$

so the gap is bounded by a term of order

$$
\mathcal{O}\left(\frac{1}{C}\right).
$$

This bound is nice for two reasons.

First, it is **architecture-independent**. It does not rely on the model being linear, overparameterized, or close to optimal.

Second, it is **label-agnostic in form**. The bound depends only on the class sizes, not on any special geometric assumptions about the representation.

So the phenomenon is not a fragile artifact of a special setting. It is built directly into the combinatorics of the loss.

## What this means conceptually

The usual picture of contrastive learning is:

- pull together two views of the same sample,
- push away all other samples.

But in a many-class problem, "all other samples" are mostly from different classes.

So DCL is already doing something very close to:

- pull together two views of the same sample,
- push away different-class samples.

That second description is much more supervised in spirit.

This does **not** mean self-supervised contrastive learning has access to labels. It does not.

And it does **not** mean DCL and NSCL have identical minimizers. They need not.

But it does mean something important:

> **the optimization objective of self-supervised contrastive learning is often numerically and structurally close to a supervised contrastive objective.**

That helps explain why semantic clusters can emerge even though the loss never explicitly uses class labels.

## Why more classes help

The theorem also makes a concrete prediction:

> **the larger the number of semantic classes, the smaller the gap between DCL and NSCL.**

This is exactly what one would expect from the denominator logic.

If there are only a few classes, then when the anchor looks at other samples, a nontrivial fraction of them may belong to the same class. Treating those as negatives is a noticeable distortion.

But if there are many classes, then almost every other sample belongs to a different class anyway. The distortion becomes small.

So the self-supervised loss becomes a better approximation to the supervised one as $C$ grows.

This gives a simple theoretical reason why contrastive learning can look particularly natural in rich, many-category datasets.

## The punchline

The surprising part of contrastive learning is not that it learns invariance to augmentation. That is built directly into the objective.

The surprising part is that it often learns **semantic** structure.

This result offers a simple explanation:

1. the self-supervised denominator includes all other samples,
2. but most of those samples are from different classes,
3. so the loss is already close to one that explicitly contrasts against different classes only.

In other words, the gap between self-supervised and supervised contrastive learning is often much smaller than the names suggest.

## What this does and does not say

It is worth being precise here.

This argument does **not** say that self-supervised contrastive learning is literally supervised learning in disguise.

It does **not** say that labels are unnecessary in every regime.

And it does **not** prove that two models trained with DCL and NSCL must learn exactly the same representation.

What it does say is more structural:

- the two objectives differ only through same-class terms in the denominator,
- the contribution of those terms becomes small when classes are numerous,
- therefore the self-supervised objective can behave much more like a supervised one than expected.

That already goes a long way toward demystifying why contrastive self-supervision often produces class-aware embeddings.

## Takeaway

Self-supervised contrastive learning looks label-free, but in many-class settings its loss is already very close to a label-aware supervised contrastive loss.

The mechanism is simple:

1. DCL differs from supervised contrastive learning only by including same-class negatives,
2. the number of such terms is small relative to the total number of negatives,
3. so the loss gap shrinks like $\mathcal{O}(1/C)$.

So the semantic behavior of contrastive self-supervision is not a mystery.

It is partly a consequence of the fact that, once the number of classes is large, the self-supervised objective is already approximately supervised.
