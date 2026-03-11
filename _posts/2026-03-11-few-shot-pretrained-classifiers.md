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

Few-shot learning sounds like it should require a special-purpose algorithm.

After all, if you only get one or five labeled examples from each new class, why should a standard classifier trained on old classes be enough?

And yet, in practice, this is exactly what often happens.

A large model is pretrained on an ordinary supervised classification task, we freeze its representation, fit a simple classifier on top of the new task, and the result is surprisingly strong. In many benchmarks, this simple pipeline is competitive with methods designed specifically for few-shot learning.

So why does this work?

A common answer is that pretraining learns "good features." That is true, but it is also vague. What geometric property of the representation actually makes few-shot transfer possible?

The main message of this post is the following:

> <span style="color:#1e6bd6; font-weight:600;">
> When supervised pretraining makes each class collapse into a tight cluster in feature space, and keeps different class means well separated, new classes can often be learned from only a few examples.
> </span>

This connects the success of few-shot transfer to a concrete and measurable geometric phenomenon: **class-feature variability collapse**, one of the central components of **neural collapse**.

<div style="margin: 2rem 0;">
  <div style="display: grid; grid-template-columns: repeat(4, 1fr); gap: 16px; align-items: stretch;">

    <div style="padding: 14px; border: 1px solid #d8e2f1; border-radius: 12px; background: #f8fbff; text-align: center;">
      <strong>Source training</strong><br>
      Many labeled classes
    </div>

    <div style="padding: 14px; border: 1px solid #d8e2f1; border-radius: 12px; background: #f8fbff; text-align: center;">
      <strong>Feature geometry</strong><br>
      Each class forms a tight cluster
    </div>

    <div style="padding: 14px; border: 1px solid #d8e2f1; border-radius: 12px; background: #f8fbff; text-align: center;">
      <strong>New classes</strong><br>
      Their features are also separated
    </div>

    <div style="padding: 14px; border: 1px solid #d8e2f1; border-radius: 12px; background: #f8fbff; text-align: center;">
      <strong>Few-shot adaptation</strong><br>
      A few samples estimate the new class centers
    </div>

  </div>
</div>

<div style="margin-top: 1rem; font-size: 1.02rem; line-height: 1.5; text-align: left;">
  <strong>Figure 1.</strong>
  <strong>The picture behind the theory.</strong>
  Pretraining does not just improve accuracy on the source task. It can organize the feature space so that unseen classes are already geometrically easy to separate. Then a nearest-class-center or ridge/logistic classifier only needs a handful of labeled examples to localize each new class.
</div>

<br>

## The puzzle

Suppose we pretrain a network on a large classification problem with many source classes.

Later, we want to solve a new target task with different classes and very little data. The usual recipe is simple:

1. learn a feature map $f$ on the source task,
2. freeze $f$,
3. fit a lightweight classifier on top of the features $f(x)$ for the new task.

Empirically, this works extremely well.

What makes this surprising is that the downstream classes were **not known during pretraining**. The model never saw them. So any explanation has to say more than "the source task was learned well." It must explain why a representation trained on old classes should already be suitable for new ones.

The theory here adopts a natural viewpoint:

> The source and target classes are both sampled from a broader population of possible classes.

That assumption matters. If the new classes have nothing to do with the old ones, transfer should not be expected to work. But if both come from the same underlying family, then the geometry learned from many source classes can generalize to unseen target classes.

## The geometric phenomenon: collapse within each class

The key quantity is very simple.

For two classes $Q_i$ and $Q_j$, define

$$
V_f(Q_i,Q_j) = \frac{\operatorname{Var}_f(Q_i)}{\|\mu_f(Q_i)-\mu_f(Q_j)\|^2}.
$$

Here:

- $\mu_f(Q_i)$ is the mean feature vector of class $i$,
- $\operatorname{Var}_f(Q_i)$ is the within-class feature variance,
- the denominator is the squared distance between the class means.

So $V_f(Q_i,Q_j)$ measures a basic ratio:

> **How wide is class $i$ compared to how far it sits from class $j$?**

If this ratio is small, then class $i$ is tightly clustered relative to the distance between the two classes.

This is exactly the right notion for few-shot transfer. If each class forms a compact cloud and different class means are far apart, then the classes are easy to separate geometrically.

This is one of the central signatures of neural collapse.

The important point is that we do **not** need exact collapse. We only need enough clustering that the representation becomes stable at the class level.

## Why this helps few-shot learning

Imagine a new class at test time.

You only get $n$ examples from it. If the class is diffuse in feature space, those $n$ samples may tell you almost nothing. The empirical center will be noisy, and different classes may overlap badly.

But if the feature map has already learned to make classes concentrate, then even a tiny sample gives a reasonable estimate of the class mean.

That is the whole mechanism.

Few-shot learning becomes easy when two things hold:

1. each class has low within-class variability in feature space,
2. different class means are well separated.

Then the classifier does not need many examples to learn a complicated boundary. It mostly needs to estimate where each new class lives.

This is why nearest-class-center rules become so natural here. If classes look like tight clouds around their means, the right classifier is almost forced on us:

$$
h(x) = \arg\min_c \|f(x)-\mu_f(S_c)\|,
$$

where $S_c$ is the small labeled sample from target class $c$.

In words, classify a point by whichever empirical class center is closest to it.

## What the theory actually shows

The full paper proves a nontrivial statement:

> Under a distribution-over-classes model, if pretraining produces collapse on many source classes, then the transfer error on new classes can be small even when the number of target examples per class stays fixed.

That last part is the striking one.

Most classical generalization guarantees become meaningful only when the number of target examples grows. Here the goal is different. We want a guarantee that still makes sense in the true few-shot regime, where $n$ may be $1$, $5$, or some other small constant.

The proof has three main ideas.

### 1. Reduce transfer error to pairwise class comparisons

A $k$-class error can be upper bounded by asking a simpler question:

> For a random example from class $i$, how often does it look closer to class $j$ than to its own class?

So the multiclass problem reduces to many two-class comparisons. This is useful because geometric separation is much easier to analyze pairwise.

### 2. Show that pairwise few-shot behavior generalizes to new classes

The next step is subtle. We do not just want good geometry on the source classes. We want the **average pairwise few-shot error** on source classes to predict the corresponding error on unseen classes.

This is where the random-classes assumption enters. Since source and target classes are both drawn from the same population, good average behavior over many source classes can generalize to new target classes.

So the theory moves from:

- "these particular training classes are clustered"

to

- "a randomly drawn new class pair is also likely to be easy."

### 3. Control pairwise few-shot error by collapse

Finally, the paper shows that the relevant pairwise few-shot error can be bounded using the collapse quantity $V_f(Q_i,Q_j)$ and related margin-based quantities.

Very roughly, the transfer risk takes the form

$$
\text{transfer error}
\;\lesssim\;
\text{collapse on source classes}
+
\text{sample generalization term}
+
\text{class generalization term}.
$$

The last two terms shrink as the number of source samples per class $m$ and the number of source classes $l$ increase.

So the message is:

- more source samples help the geometry stabilize within each source class,
- more source classes help that geometry generalize to unseen classes,
- collapse is the bridge that turns supervised pretraining into few-shot transfer.

## A useful informal takeaway

The easiest way to remember the result is this:

> Pretraining does not need to memorize how to classify every future class. It only needs to learn a representation in which classes naturally look like tight, separated clusters.

Once that happens, a new class is not hard to learn. A few labeled points are enough to locate its center.

That is a much weaker requirement than learning the full target task in advance, and it is exactly why transfer learning can work so well.

## What the experiments support

The empirical results line up with this picture.

Across datasets such as Mini-ImageNet, CIFAR-FS, FC-100, and EMNIST, the same pattern appears:

- during source training, the collapse metric decreases,
- this behavior generalizes to held-out examples from the source classes,
- as the number of source classes grows, collapse on target classes improves,
- few-shot target accuracy rises along with it.

So the geometry is not just becoming cleaner on the training data. It is becoming more useful for transfer.

This is the most important empirical point. The theory would be much less interesting if collapse were only a training-set artifact. But it is not. It tracks few-shot performance on new classes.

## What this does and does not claim

It is worth being precise here.

This theory does **not** say that every pretrained model will succeed on every downstream task. It does not remove the need for source and target classes to come from a related population. And it does not claim that exact neural collapse literally occurs in practice.

What it does say is more structural:

- there is a measurable geometric property of representations,
- that property emerges during ordinary supervised training,
- and that property is enough to explain why few-shot transfer can work.

So this is not just a post-hoc story about "good features." It is a concrete mechanism.

## Why this matters

A lot of the excitement around foundation models comes from their ability to adapt quickly to new tasks. But that success often seems mysterious.

This work gives a clean explanation for one important part of that story.

A classifier trained on many source classes can become a strong few-shot learner not because it has seen the future task, but because it has learned the right **geometry**:

- low within-class variability,
- large between-class separation,
- stable class-level structure that generalizes to new classes.

Once that geometry is in place, a few labels go a long way.

## Takeaway

The central lesson is simple:

1. supervised pretraining can make features from the same class collapse around their mean,
2. this collapse can generalize beyond the source training data,
3. then new classes can be learned from only a few examples by estimating their centers in feature space.

So the success of few-shot transfer is not magic, and it is not necessarily evidence that we need a very specialized meta-learning algorithm.

Sometimes, an ordinary classifier trained on many classes is already doing the hard part.

It is learning a feature space where new classes are easy to place.

---

The goal of the full theory is not to prove that few-shot transfer is always easy. The point is to identify a concrete geometric reason that it can be easy, and to show that this reason is exactly the kind of structure that modern deep networks often learn during pretraining.
