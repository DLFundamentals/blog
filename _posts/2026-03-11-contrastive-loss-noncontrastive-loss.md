---
layout: post
title: "Self-Supervised (Contrastive) Learning $\approx$ Supervised (Contrastive) Learning"
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

Self-supervised contrastive learning is one of the most successful paradigms in modern representation learning. It trains on unlabeled data, yet the learned features often look remarkably semantic: same-class samples cluster together, linear probes perform well, and downstream transfer can approach supervised pre-training.

That raises a basic question:

> How can a method that never sees labels learn representations that look so class-aware?

The main message of this post is that contrastive learning is often much closer to supervised contrastive learning than it first appears. This closeness shows up in two layers. First, the standard self-supervised contrastive objective is close to a supervised variant that removes same-class negatives. Second, when the two models are trained under shared randomness, their learned representations can remain highly aligned even when their parameters drift apart.

This gives a cleaner way to think about why contrastive learning so often behaves like a supervised method.

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
  <strong>CL and NSCL can separate in weight space while remaining closely aligned in representation space.</strong>
  This is the central phenomenon: the objectives are related, the learned geometry remains similar, but the parameter trajectories need not coincide.
</div>

<br>

## The setup

Consider a labeled dataset

$$
S = \{(x_i,y_i)\}_{i=1}^N,
$$

but assume that during self-supervised training we only use the inputs $x_i$, not the labels $y_i$. For each sample $x_i$, we generate $K$ augmentations and map them through an encoder $f$:

$$
z_i^l = f(\alpha_l(x_i)).
$$

A standard decoupled contrastive loss (DCL) takes the form

$$
\mathcal{L}^{\mathrm{DCL}}(f) = -\frac{1}{K^2N}\sum_{l_1,l_2=1}^K\sum_{i=1}^N \log\left(\frac{\exp(\mathrm{sim}(z_i^{l_1},z_i^{l_2}))}{\sum_{l_3=1}^K\sum_{j\neq i}\exp(\mathrm{sim}(z_i^{l_1},z_j^{l_3}))}\right).
$$

This is a purely self-supervised objective. It rewards two views of the same sample for being similar and penalizes similarity to all other samples.

Now compare it with a supervised variant that excludes same-class negatives from the denominator:

$$
\mathcal{L}^{\mathrm{NSCL}}(f) = -\frac{1}{K^2N}\sum_{l_1,l_2=1}^K\sum_{i=1}^N \log\left(\frac{\exp(\mathrm{sim}(z_i^{l_1},z_i^{l_2}))}{\sum_{l_3=1}^K\sum_{j:y_j\neq y_i}\exp(\mathrm{sim}(z_i^{l_1},z_j^{l_3}))}\right).
$$

We call this objective **NSCL**, for **negatives-only supervised contrastive learning**.

The two losses differ in exactly one place:

- DCL treats every other sample as a negative.
- NSCL removes same-class samples from the denominator.

So the only mismatch between the two comes from the fact that self-supervised contrastive learning accidentally treats some same-class samples as negatives.

## Why the loss gap is small

This difference looks important, but in many-class problems it is often quite mild.

Suppose for simplicity that the dataset is balanced, with $C$ classes and exactly $n$ samples per class, so $N = Cn$.

Fix an anchor. In DCL, the denominator includes all other samples. In NSCL, it excludes samples from the same class. Therefore:
- the number of same-class terms that appear in DCL but not in NSCL is exactly $n-1$,
- the number of different-class terms is exactly $N-n = n(C-1)$.

So when $C$ is large, the same-class terms form only a small fraction of the denominator. This already suggests that the two losses should be close.

That intuition can be made precise. For any encoder $f$,

$$
\mathcal{L}^{\mathrm{NSCL}}(f) \le \mathcal{L}^{\mathrm{DCL}}(f) \le \mathcal{L}^{\mathrm{NSCL}}(f) + \log\left(1+\frac{e^2}{C-1}\right) \le \mathcal{L}^{\mathrm{NSCL}}(f) + \frac{e^2}{C-1}.
$$

So in the balanced setting, the gap between DCL and NSCL shrinks like $O(1/C)$.

This is the first structural point:

> In many-class regimes, the standard self-supervised contrastive loss is already close to a supervised contrastive loss.

This does not mean CL is literally supervised learning in disguise. It does mean that the objective is much more supervised-like than the name suggests.

## What this explains, and what it does not

This theorem is conceptually useful because it identifies the exact source of the CL-NSCL gap. The self-supervised loss differs from the supervised one only because it includes same-class samples in the denominator, and that contribution becomes small when the number of classes is large.

Still, loss-level closeness is not the whole story. A small objective gap does not by itself imply similar parameters, similar trajectories, or similar learned geometry. Two nearby losses can still drive optimization in rather different directions.

So the real follow-up question is not just whether the losses are close, but whether the learned representations are close as well.

## From losses to geometry

To study this, consider training CL and NSCL under shared randomness:

- same initialization,
- same mini-batches,
- same augmentations.

Then the only real difference between the two runs is the objective.

To compare the learned representations, it is more useful to look at their similarity structure than at their raw parameters. If $Z$ denotes a collection of embeddings, define the similarity matrix

$$
\Sigma(Z)_{ij} = \cos(z_i,z_j).
$$

This matrix captures the geometry of the representation space directly. From it one can compute standard alignment measures such as:

- **CKA**, which compares centered similarity structure,
- **RSA**, which compares pairwise dissimilarity structure.

These are natural metrics for asking whether two models learn the same relational geometry over the data.

## The second result

Under a coupled training protocol, one can bound the difference between the CL and NSCL similarity matrices throughout training. A representative bound has the form

$$
\|\Sigma_T^{\mathrm{CL}}-\Sigma_T^{\mathrm{NS}}\|_F \lesssim \frac{e^{2/\tau}}{\tau C \sqrt{B}} \cdot \exp\left(\frac{1}{2\tau^2 B}\sum_{t=0}^{T-1}\eta_t\right)\cdot \left(\sum_{t=0}^{T-1}\eta_t\right),
$$

where:

- $B$ is the batch size,
- $\tau$ is the temperature,
- $\eta_t$ are the step sizes.

The exact form matters less here than the scaling. The right-hand side gets smaller when:

- the number of classes is larger,
- the batch size is larger,
- the temperature is higher,
- the cumulative step size is more moderate.

So the same regimes that make the loss-level CL-NSCL gap small also make the learned representation geometry more tightly coupled.

This is the second structural point:

> The CL-NSCL connection persists beyond the objective. It often appears directly in the geometry of the learned representations.

## Consequences for CKA and RSA

Once the similarity matrices are close, one immediately gets lower bounds on standard representation-alignment metrics. In simplified form, these bounds look like

$$
\mathrm{CKA}_T \ge \frac{1-\rho_T}{1+\rho_T}, \qquad \mathrm{RSA}_T \ge \frac{1-r_T}{1+r_T},
$$

where $\rho_T$ and $r_T$ are normalized versions of the similarity-matrix discrepancy.

So the theory does not merely say that CL and NSCL have nearby objective values. It says that, under shared randomness, their internal geometry can remain meaningfully aligned throughout training.

That is a substantially stronger statement.

## Why weights can still diverge

At the same time, weight-space coupling is far less stable.

A typical parameter-space bound takes the form

$$
\|w_T^{\mathrm{CL}}-w_T^{\mathrm{NS}}\| \lesssim \frac{G e^{2/\tau}}{\beta\tau C} \cdot \left(\exp\left(\beta\sum_{t=0}^{T-1}\eta_t\right)-1\right),
$$

which can grow exponentially with training time.

So while the similarity matrices remain controlled, the parameters themselves may drift quite far apart.

This is not paradoxical. In deep networks, parameter space is highly redundant and unstable. Two models can take very different routes through weight space and still induce very similar representation geometry. In this setting, representation-space alignment is the more meaningful notion of closeness.

That is exactly what the experiments show.

## What the experiments say

Across datasets such as CIFAR-10, CIFAR-100, Tiny-ImageNet, mini-ImageNet, and ImageNet-1K, the empirical picture is consistent:

- CL and NSCL remain much more aligned than CL and standard supervised baselines,
- alignment improves as the number of classes increases,
- alignment improves as the temperature increases,
- weight-space divergence is much larger than representation-space divergence.

So the theoretical picture matches the observed one. NSCL is not merely a convenient supervised comparison. It is the supervised objective whose learned geometry most closely tracks CL.

That is exactly why it is a useful conceptual bridge.

## The right way to think about CL

Putting the two pieces together gives a much better mental model of contrastive learning.

The first piece says that the self-supervised objective is already close to a supervised contrastive objective. The second says that, under shared training randomness, the learned representations often remain close as well.

So rather than thinking of CL as a completely different type of learning that somehow mysteriously recovers semantics, it is more accurate to think of it as a self-supervised procedure whose objective and learned geometry often sit near a very specific supervised counterpart.

Not cross-entropy.

Not generic supervised learning.

But a supervised contrastive objective that differs from CL in only one controlled way: whether same-class samples are excluded from the denominator.

That is a much sharper and more useful comparison.

## Takeaway

Contrastive learning is more supervised than it looks.

Mathematically, this appears in two layers:

1. the standard self-supervised contrastive loss is close to a supervised contrastive loss that excludes same-class negatives,
2. and under shared training randomness, the learned representation geometry can remain closely aligned as well, even if the parameters diverge.

So the semantic behavior of self-supervised contrastive learning is not as mysterious as it first seems. The objective is already closer to supervised learning than the label “self-supervised” suggests, and the learned geometry often reflects that closeness throughout training.
