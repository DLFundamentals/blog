---
layout: post
title: "Why Contrastive Learning Is More Supervised Than It Looks"
date: 2026-03-11
author: Tomer Galanti
tags:
  - deep-learning
  - self-supervised-learning
  - contrastive-learning
  - supervised-learning
  - representation-learning
  - theory
excerpt: "Contrastive learning is often much closer to supervised contrastive learning than it first appears, not only at the level of the loss, but often also in the geometry of the learned representations."
---

Self-supervised contrastive learning has become one of the central ideas in modern representation learning.

It trains on unlabeled data, yet the features it learns often look strikingly semantic. Samples from the same class cluster together, linear probes work well, and downstream transfer can get surprisingly close to supervised pre-training.

That is the puzzle.

How can a method that never sees class labels end up learning representations that look so class-aware?

The main message of this post is the following:

> <span style="color:#1e6bd6; font-weight:600;">
> Contrastive learning is often much closer to supervised contrastive learning than it first appears.  
> This is true first at the level of the loss, and often also at the level of the learned representation geometry.
> </span>

The story has two parts.

First, the standard self-supervised contrastive loss is close to a supervised variant that simply removes same-class negatives.

Second, when the two models are trained under the same randomness, their learned representations can remain highly aligned even when their parameters drift apart.

That combination gives a much clearer explanation for why contrastive learning so often behaves like a supervised method.

<div style="margin: 2rem 0;">
  <div style="display: grid; grid-template-columns: repeat(3, 1fr); gap: 20px; align-items: start;">

    <div style="text-align: center;">
      <img src="{{ '/assets/figures/cl-nscl/weight_space_angle.png' | relative_url }}" style="width:100%; max-width:240px;">
      <div><strong>(a)</strong> Weight space</div>
    </div>

    <div style="text-align: center;">
      <img src="{{ '/assets/figures/cl-nscl/rep_space_angle.png' | relative_url }}" style="width:100%; max-width:240px;">
      <div><strong>(b)</strong> Representation space</div>
    </div>

    <div style="text-align: center;">
      <img src="{{ '/assets/figures/cl-nscl/cka_rsa_gap.png' | relative_url }}" style="width:100%; max-width:240px;">
      <div><strong>(c)</strong> CKA / RSA / weight gap</div>
    </div>

  </div>
</div>

<div style="margin-top: 1rem; font-size: 1.02rem; line-height: 1.5; text-align: left;">
  <strong>Figure 1.</strong>
  <strong>CL and NSCL can drift apart in weight space while staying closely aligned in representation space.</strong>
  This is the core phenomenon: the objectives are related, the learned geometry stays similar, but the parameter trajectories do not have to match.
</div>

<br>

## The basic setup

We start from a labeled dataset

$$
S = \{(x_i,y_i)\}_{i=1}^N,
$$

but during self-supervised training the algorithm only sees the inputs \(x_i\), not the labels \(y_i\).

For each sample \(x_i\), we generate \(K\) augmentations and map them through an encoder \(f\):

$$
z_i^l = f(\alpha_l(x_i)).
$$

The standard decoupled contrastive loss (DCL) is

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

This is a standard self-supervised contrastive objective. It pulls together two views of the same sample and pushes the anchor away from all other samples.

Now compare it to a supervised variant that excludes same-class negatives from the denominator:

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

We call this objective **NSCL**, for **negatives-only supervised contrastive learning**.

So the only difference between the two objectives is simple:

- **DCL** treats every other sample as a negative
- **NSCL** removes same-class samples from the denominator

That is it.

## Why the loss gap is small

Fix an anchor \(x_i\). The denominator of DCL includes all other samples, while the denominator of NSCL excludes samples with the same class label.

If each class contains at most \(n_{\max}\) examples, then for a given anchor:

- the number of extra same-class terms is at most \(n_{\max}-1\)
- the number of different-class terms is at least \(N-n_{\max}\)

So when the number of classes is large, the fraction of same-class negatives is small.

This leads to a clean theorem.

## The first theorem

For any encoder \(f\),

$$
\mathcal{L}^{\mathrm{NSCL}}(f)
\le
\mathcal{L}^{\mathrm{DCL}}(f)
\le
\mathcal{L}^{\mathrm{NSCL}}(f)
+
\log\left(1+\frac{n_{\max}e^2}{N-n_{\max}}\right).
$$

Using \(\log(1+x)\le x\), this implies

$$
\mathcal{L}^{\mathrm{DCL}}(f)
\le
\mathcal{L}^{\mathrm{NSCL}}(f)
+
\frac{n_{\max}e^2}{N-n_{\max}}.
$$

In a balanced dataset with \(C\) classes,

$$
\frac{n_{\max}}{N-n_{\max}} = \frac{1}{C-1},
$$

so the gap shrinks like

$$
\mathcal{O}\left(\frac{1}{C}\right).
$$

This is the first key point.

> **The self-supervised contrastive loss is already close to a supervised contrastive loss when the number of classes is large.**

That does not prove the models themselves are close. But it does mean that the objective is much more supervised than it first looks.

## Why this is conceptually useful

This theorem is simple, but it changes the right mental model.

The usual picture of contrastive learning is:

- pull together two augmentations of the same sample
- push away all other samples

That is true, but incomplete.

A better view is:

- pull together two augmentations of the same sample
- push away mostly different-class samples
- accidentally penalize same-class samples only through a relatively small correction

So in many-class regimes, CL is already optimizing something very close to a supervised contrastive objective.

That helps explain why semantic clustering can emerge at all.

But there is an important caveat.

## Loss similarity is not enough

A small loss gap does **not** automatically imply:

- similar parameters
- similar optimization trajectories
- similar representations

Two nearby objectives can still drive training in rather different directions.

So the next natural question is:

> **Does the CL-NSCL similarity persist only at the level of the loss, or does it also show up in the learned representation geometry?**

This is where the second part of the story begins.

## Looking at representations instead of weights

Suppose we train CL and NSCL under shared randomness:

- same initialization
- same mini-batches
- same augmentations

Then the only real difference between the two runs is the objective itself.

To compare the resulting representations, we look at their similarity matrices. If \(Z\) denotes a collection of embeddings, define the pairwise similarity matrix

$$
\Sigma(Z)_{ij} = \cos(z_i,z_j).
$$

This matrix captures the geometry of the representation space much more directly than the raw parameters do.

From these similarity matrices, one can compute standard alignment metrics such as:

- **CKA**, which compares centered similarity structure
- **RSA**, which compares pairwise dissimilarity structure

These are natural tools for asking whether two models learn the same geometry.

## The second theorem, informally

Under a coupled training protocol, one can bound the gap between the CL and NSCL similarity matrices throughout training.

A simplified version of the bound looks like

$$
\|\Sigma_T^{\mathrm{CL}}-\Sigma_T^{\mathrm{NS}}\|_F
\le
\exp\left(\frac{1}{2\tau^2 B}\sum_{t=0}^{T-1}\eta_t\right)
\cdot
\frac{1}{\tau\sqrt{B}}
\left(\sum_{t=0}^{T-1}\eta_t\right)
\Delta_{\pi,\delta}(B;\tau),
$$

where:

- \(B\) is the batch size
- \(\tau\) is the temperature
- \(\eta_t\) are the step sizes
- \(\Delta_{\pi,\delta}(B;\tau)\) captures the batch-composition mismatch between CL and NSCL

You do not need every detail of this formula to see the main message. What matters is how it scales.

The bound gets **smaller** when:

- the number of classes is larger
- the batch size is larger
- the temperature is higher
- the total step size is more moderate

So the theory predicts that CL and NSCL should become more aligned in representation space precisely in the regimes where the loss-level difference is also mild.

## What this gives for CKA and RSA

Once the similarity matrices are close, standard comparison arguments give lower bounds on CKA and RSA.

In simplified form, the guarantees look like

$$
\mathrm{CKA}_T \ge \frac{1-\rho_T}{1+\rho_T},
\qquad
\mathrm{RSA}_T \ge \frac{1-r_T}{1+r_T},
$$

where \(\rho_T\) and \(r_T\) are normalized versions of the similarity-matrix gap.

So the second key point is:

> **the CL-NSCL connection is not only about the objective values. It often persists at the level of representation geometry.**

That is a much stronger statement.

## The surprising twist: weights can still diverge

At the same time, there is an important contrast.

In parameter space, the gap can grow much less benignly. A typical bound takes the form

$$
\|w_T^{\mathrm{CL}}-w_T^{\mathrm{NS}}\|
\lesssim
\frac{G}{\beta\tau}\,\Delta_{\pi,\delta}(B;\tau)
\left(
\exp\left(\beta\sum_{t=0}^{T-1}\eta_t\right)-1
\right),
$$

which can grow exponentially with training time.

So weight-space coupling is fragile.

Representation-space coupling is much more stable.

This is not a contradiction. It is exactly what one should expect in deep learning: parameters can move very differently while still producing similar relational geometry over the data.

That is why representation-space alignment is the more meaningful notion here.

## What the experiments show

Empirically, this is exactly what appears.

Across datasets such as CIFAR-10/100, Tiny-ImageNet, mini-ImageNet, and ImageNet-1K, one finds:

- **CL and NSCL stay much more aligned than CL and standard supervised baselines**
- **alignment improves with the number of classes**
- **alignment improves with higher temperature**
- **weights drift apart much more than representations do**

So the theory is not just abstract. It matches the qualitative training behavior.

The strongest empirical takeaway is that **NSCL is the supervised objective most tightly coupled to CL**, much more so than cross-entropy or even standard supervised contrastive learning.

## Why this changes the big picture

Putting the two pieces together gives a more useful conceptual view of contrastive learning.

### First:
the self-supervised contrastive objective is already close to a supervised contrastive one.

### Second:
the learned representations can remain closely aligned with that supervised proxy throughout training.

That means NSCL is not just a technical variation. It is a natural bridge between self-supervised and supervised learning.

If we want to understand what CL is doing, NSCL is a much better supervised reference point than generic classification objectives.

## What this does and does not claim

It is worth being precise.

This line of work does **not** say that CL is secretly supervised learning.

It does **not** say that CL and NSCL must have identical minimizers.

And it does **not** say that their parameter trajectories should stay close.

What it does say is more structural:

- CL differs from NSCL in one specific way
- that difference becomes small in many-class regimes
- and despite parameter drift, the learned representation geometry can remain highly aligned

That is already a strong and useful connection.

## Takeaway

Contrastive learning is more supervised than it looks.

Mathematically, this appears in two layers:

1. the standard self-supervised contrastive loss is close to a supervised contrastive loss that excludes same-class negatives
2. under shared training randomness, the learned representation geometry can remain closely aligned as well

So the semantic behavior of self-supervised contrastive learning is not as mysterious as it first seems.

The objective is already closer to supervised learning than the name suggests, and the learned geometry often reflects that closeness throughout training.
