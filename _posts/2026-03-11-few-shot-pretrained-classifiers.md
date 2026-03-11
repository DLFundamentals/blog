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

Deep networks trained on large classification benchmarks such as **ImageNet** often transfer remarkably well to new tasks.

This is one of the most common recipes in modern machine learning. We train a classifier on a large source dataset, keep its learned representation, and then adapt it to a new set of classes using only a small amount of labeled data, often with nothing more than a simple linear head.

Practitioners use this all the time because it works.

But from a theoretical point of view, that only sharpens the puzzle.

A classifier trained on ImageNet is trained to separate the ImageNet classes. Why should the same representation also make it easy to separate **new** classes that were never seen during training? And why should only a few labeled examples be enough to fit a simple classifier on top?

A common answer is that pretraining learns "good features." That is certainly true, but it still leaves open the main question:

> **What property of the learned feature space makes adaptation to new classes possible with so little data?**

The main message of this post is the following:

> <span style="color:#1e6bd6; font-weight:600;">
> If supervised pretraining makes each class form a tight cluster in feature space, while keeping different class means well separated, then new classes can often be learned from only a few labeled examples using a simple linear or nearest-center classifier.
> </span>

So the story is not just that ImageNet pretraining produces a useful representation. The deeper point is that, under the right conditions, it produces a representation with a very particular **geometry**: samples from the same class are concentrated, and different classes are separated at the level of their means.

That is the geometric reason few-shot adaptation can work.

To formalize this, we need a setting in which the source classes and the target classes are not arbitrary unrelated labels, but are both drawn from a common population of possible classes. That is where the class-conditional setup comes in.

<div style="margin: 2rem 0;">
  <div style="display: grid; grid-template-columns: repeat(4, 1fr); gap: 16px; align-items: stretch;">

    <div style="padding: 14px; border: 1px solid #d8e2f1; border-radius: 12px; background: #f8fbff; text-align: center;">
      <strong>Pretrain on a large source task</strong><br>
      e.g. ImageNet classification
    </div>

    <div style="padding: 14px; border: 1px solid #d8e2f1; border-radius: 12px; background: #f8fbff; text-align: center;">
      <strong>Learn a feature map</strong><br>
      The network organizes classes geometrically
    </div>

    <div style="padding: 14px; border: 1px solid #d8e2f1; border-radius: 12px; background: #f8fbff; text-align: center;">
      <strong>Move to new classes</strong><br>
      Draw unseen target classes from the same population
    </div>

    <div style="padding: 14px; border: 1px solid #d8e2f1; border-radius: 12px; background: #f8fbff; text-align: center;">
      <strong>Adapt with little data</strong><br>
      Fit a simple head from a few examples
    </div>

  </div>
</div>

<div style="margin-top: 1rem; font-size: 1.02rem; line-height: 1.5; text-align: left;">
  <strong>Figure 1.</strong>
  <strong>The motivating picture.</strong>
  A classifier pretrained on a large source task such as ImageNet is often reused as a representation for new classes. The goal of the theory is to explain when this common practice should work, and why only a few labeled examples can already be enough.
</div>

% Requires:
% \usepackage{tikz}
% \usetikzlibrary{positioning,calc,fit,arrows.meta,decorations.pathreplacing}

\newcommand{\lrupdate}[4]{%
% #1 = x, #2 = y, #3 = opacity, #4 = label
\begin{scope}[shift={(#1,#2)}]
    \foreach \i in {0,...,3} {
        \foreach \j in {0,...,3} {
            \draw[gray!45, line width=0.3pt] (0.18*\j,0.18*\i) rectangle +(0.18,0.18);
        }
    }
    % stylized low-rank pattern: one column + one row
    \fill[blue!70!black, opacity=#3] (0.18,0.00) rectangle +(0.18,0.72);
    \fill[blue!70!black, opacity=#3] (0.00,0.36) rectangle +(0.72,0.18);
    \node[font=\scriptsize] at (0.36,-0.20) {$#4$};
\end{scope}
}

\newcommand{\finalweight}[2]{%
% #1 = x, #2 = y
\begin{scope}[shift={(#1,#2)}]
    \foreach \i in {0,...,5} {
        \foreach \j in {0,...,5} {
            \draw[gray!45, line width=0.3pt] (0.20*\j,0.20*\i) rectangle +(0.20,0.20);
        }
    }
    % overlay a few recent low-rank corrections
    \fill[blue!70!black, opacity=.70] (0.20,0.00) rectangle +(0.20,1.20);
    \fill[blue!70!black, opacity=.70] (0.00,0.60) rectangle +(1.20,0.20);

    \fill[blue!70!black, opacity=.40] (0.60,0.00) rectangle +(0.20,1.20);
    \fill[blue!70!black, opacity=.40] (0.00,0.20) rectangle +(1.20,0.20);

    \fill[blue!70!black, opacity=.22] (1.00,0.00) rectangle +(0.20,1.20);
    \fill[blue!70!black, opacity=.22] (0.00,1.00) rectangle +(1.20,0.20);

    \node[font=\small] at (0.60,-0.30) {$W_T$};
\end{scope}
}

\begin{figure}[t]
\centering
\begin{tikzpicture}[
    >=Latex,
    panel/.style={draw=black!70, rounded corners=4pt, fill=gray!3},
    note/.style={font=\small, align=center},
    title/.style={font=\bfseries},
    every node/.style={inner sep=2pt}
]

% --- Panel boxes ---
\draw[panel] (0,0) rectangle (5.9,4.7);
\draw[panel] (6.3,0) rectangle (12.2,4.7);
\draw[panel] (12.6,0) rectangle (19.3,4.7);

% --- Panel titles ---
\node[title] at (2.95,4.35) {(a) each step writes a low-rank update};
\node[title] at (9.25,4.35) {(b) weight decay forgets the distant past};
\node[title] at (15.95,4.35) {(c) recent low-rank updates dominate};

% =========================
% Panel (a)
% =========================
\begin{scope}[shift={(0.25,0.2)}]
    \lrupdate{0.20}{2.10}{0.95}{G_{T-5}}
    \lrupdate{1.20}{2.10}{0.95}{G_{T-4}}
    \lrupdate{2.20}{2.10}{0.95}{G_{T-3}}
    \lrupdate{3.20}{2.10}{0.95}{G_{T-2}}
    \lrupdate{4.20}{2.10}{0.95}{G_{T-1}}

    \draw[->, thick, black!70] (0.35,1.35) -- (4.95,1.35);
    \node[note] at (2.65,0.90) {SGD writes only a few directions per step};
    \node[note] at (2.65,0.35) {$\operatorname{rank}(G_t)\le B$};
\end{scope}

% =========================
% Panel (b)
% =========================
\begin{scope}[shift={(6.55,0.2)}]
    \node[note] at (2.80,3.75) {$\times(1-2\mu\lambda)^4$ \hspace{0.45cm} $\times(1-2\mu\lambda)^3$ \hspace{0.45cm} $\times(1-2\mu\lambda)^2$ \hspace{0.45cm} $\times(1-2\mu\lambda)$};

    \lrupdate{0.20}{2.10}{0.18}{G_{T-5}}
    \lrupdate{1.20}{2.10}{0.30}{G_{T-4}}
    \lrupdate{2.20}{2.10}{0.45}{G_{T-3}}
    \lrupdate{3.20}{2.10}{0.65}{G_{T-2}}
    \lrupdate{4.20}{2.10}{0.95}{G_{T-1}}

    \draw[decorate, decoration={brace, amplitude=6pt}, black!65] (0.15,1.25) -- (4.95,1.25);
    \node[note] at (2.55,0.75) {older updates are exponentially suppressed};
    \node[note] at (2.55,0.20) {$W_{t+1}=(1-2\mu\lambda)W_t-\mu G_t$};
\end{scope}

% =========================
% Panel (c)
% =========================
\begin{scope}[shift={(12.85,0.15)}]
    % recent weighted updates
    \lrupdate{0.20}{2.55}{0.35}{(1-2\mu\lambda)^2G_{T-3}}
    \lrupdate{0.20}{1.60}{0.62}{(1-2\mu\lambda)G_{T-2}}
    \lrupdate{0.20}{0.65}{0.95}{G_{T-1}}

    % arrows into final matrix
    \draw[->, thick, black!70] (1.20,2.95) -- (2.55,2.45);
    \draw[->, thick, black!70] (1.20,2.00) -- (2.55,2.05);
    \draw[->, thick, black!70] (1.20,1.05) -- (2.55,1.65);

    % final matrix
    \finalweight{3.10}{1.15}

    \node[note] at (3.25,0.25) {$W_T \approx -\mu\sum_{j=1}^{n}(1-2\mu\lambda)^{j-1}G_{T-j}$};
\end{scope}

\end{tikzpicture}
\caption{\textbf{Why SGD with weight decay favors low-rank structure.} \textbf{(a)} Each stochastic gradient step adds a low-rank correction to the layer matrix. \textbf{(b)} Weight decay exponentially suppresses older updates, so the distant past contributes little to the current layer. \textbf{(c)} As a result, the current matrix is dominated by a short weighted history of low-rank corrections, which biases the layer toward low effective rank.}
\label{fig:sgd_low_rank_mechanism}
\end{figure}

<br>

## The right setting: classes are random objects

To talk about transfer to **new classes**, we need a model in which classes themselves are random.

The setup is this.

There is an unknown distribution $\mathcal D$ over a set $\mathcal E$ of class-conditional distributions. Each element of $\mathcal E$ is one possible class. So instead of saying "the model trains on one fixed dataset and then tests on another," we say:

- a **class** is itself a distribution over inputs,
- source classes are sampled from $\mathcal D$,
- target classes are also sampled from $\mathcal D$.

Concretely, the source task is built from class-conditionals

$$
\tilde P_1,\dots,\tilde P_l \sim \mathcal D
$$

and the target task is built from new class-conditionals

$$
P_1,\dots,P_k \sim \mathcal D,
$$

independently of the source draw.

This is the key modeling move.

It formalizes the intended use of pretrained representations: we train on many source classes that are representative of some broader family, and then we want to transfer to new classes from the same family.

## Source and target classification problems

Once the classes are sampled, they induce balanced classification problems.

The source task is the balanced $l$-class distribution

$$
\tilde P(x,y)
\quad\text{with}\quad
\tilde P(y=c)=\frac{1}{l},
\qquad
x \mid y=c \sim \tilde P_c.
$$

The target task is the balanced $k$-class distribution

$$
P(x,y)
\quad\text{with}\quad
P(y=c)=\frac{1}{k},
\qquad
x \mid y=c \sim P_c.
$$

From these class-conditionals we draw data.

For the source task, we observe many labeled samples per class:

$$
\tilde S_c=\{\tilde x_{c1},\dots,\tilde x_{cm}\},
\qquad
\tilde x_{ci} \sim \tilde P_c.
$$

For the target task, we only get a few labeled samples per class:

$$
S_c=\{x_{c1},\dots,x_{cn}\},
\qquad
x_{ci} \sim P_c.
$$

Here $m$ is large, while $n$ is small. That is the few-shot regime.

## What the pretrained model is supposed to learn

We train a classifier on the source task, but the real object we care about is the feature map

$$
f:\mathcal X \to \mathbb R^p.
$$

This is the pretrained representation, usually the penultimate layer of a neural network.

Once $f$ is learned, we freeze it and solve the target problem using only the few target samples. The simplest classifier is the nearest-class-center rule

$$
h(x)=\arg\min_{c\in[k]} \|f(x)-\mu_f(S_c)\|,
$$

where

$$
\mu_f(S_c)=\frac{1}{n}\sum_{i=1}^n f(x_{ci})
$$

is the empirical feature mean of class $c$.

So the target task becomes:

> Use a few examples from each new class to estimate its center in feature space, then classify by whichever center is closest.

This is simple enough that if it works well, the explanation must lie in the geometry of the feature map itself.

## What does it mean for a feature map to transfer well?

Since the target classes are random, the right object is not the error on one fixed target task, but the **expected few-shot transfer error** over new target classes and their few-shot samples.

That is,

$$
\mathcal L_{\mathcal D}(f)
=
\mathbb E_{P_1,\dots,P_k \sim \mathcal D}
\;
\mathbb E_{S_c \sim P_c^n}
\left[
L_P(h)
\right],
$$

where $h$ is the nearest-class-center classifier built on top of $f$.

So $\mathcal L_{\mathcal D}(f)$ asks a clean question:

> If I draw a fresh target task from the same population of classes, and only get $n$ examples per class, how well does the pretrained representation perform on average?

That is the quantity the theory controls.

## The geometric quantity that matters

For two classes $Q_i$ and $Q_j$, define

$$
V_f(Q_i,Q_j)
=
\frac{\operatorname{Var}_f(Q_i)}{\|\mu_f(Q_i)-\mu_f(Q_j)\|^2}.
$$

Here

$$
\mu_f(Q)=\mathbb E_{x\sim Q}[f(x)]
$$

is the class mean in feature space, and

$$
\operatorname{Var}_f(Q)
=
\mathbb E_{x\sim Q}\|f(x)-\mu_f(Q)\|^2
$$

is the within-class variance.

So $V_f(Q_i,Q_j)$ compares:

- how spread out class $i$ is,
- how far apart the two class means are.

If this quantity is small, then class $i$ is tightly clustered relative to its separation from class $j$.

This is the basic form of **class-feature variability collapse**.

## Why this quantity is exactly the right one

If a new target class is very diffuse in feature space, then a few labeled samples are not enough to locate it reliably.

But if the feature map makes each class form a tight cluster, then even a few samples already give a decent estimate of the class center.

So small $V_f(Q_i,Q_j)$ means:

- low within-class noise,
- stable class centers,
- easier few-shot estimation,
- more reliable nearest-center classification.

This is why collapse is not just an aesthetic geometric property. It directly supports few-shot transfer.

## The high-level theorem

The full paper proves upper bounds on the transfer error $\mathcal L_{\mathcal D}(f)$ of the pretrained feature map $f$.

At a high level, the result has the form

$$
\mathcal L_{\mathcal D}(f) \;\lesssim\; (k-1)\,\operatorname{Avg}_{i\neq j} V_f(\tilde S_i,\tilde S_j) + \frac{k\,\mathrm{complexity}(f)}{\min_{i\neq j}\|\mu_f(\tilde S_i)-\mu_f(\tilde S_j)\|} \left(\frac{n^2}{\sqrt{m}}+\frac{1}{\sqrt{l}}\right),
$$

up to logarithmic factors.

Here:

- $l$ is the number of source classes,
- $m$ is the number of source samples per source class,
- $n$ is the number of target samples per target class,
- $k$ is the number of target classes,
- $\mu_f(\tilde S_i)$ is the empirical mean of source class $i$ in feature space.

This bound is worth unpacking carefully.

The first term,

$$
(k-1)\,\operatorname{Avg}_{i\neq j} V_f(\tilde S_i,\tilde S_j),
$$

is the geometric term. It is small when the source classes are tightly clustered relative to the distances between their feature means. This is exactly the kind of class-wise organization that neural collapse predicts. So this term says that if pretraining produces strong class collapse on the source task, then few-shot transfer should become easier.

The second part is the generalization error. Its structure is also very natural. It becomes smaller when:

- $m$ is large, meaning we have many samples from each source class, and
- $l$ is large, meaning we train on many different source classes.

These two roles are different.

The $1/\sqrt{m}$ term is a standard sample effect: with more examples from each source class, we can estimate the geometry of that class more accurately.

The $1/\sqrt{l}$ term is more interesting. It reflects generalization to **new classes**. Since the target classes are not seen during pretraining, the representation must generalize not only across new examples, but across new class-conditionals. So having many source classes is essential in its own right.

The denominator

$$
\min_{i\neq j}\|\mu_f(\tilde S_i)-\mu_f(\tilde S_j)\|
$$

is equally important. It measures the minimal separation between source class means in feature space. If two source class centers are extremely close, then even small within-class fluctuations may cause confusion, and the transfer guarantee deteriorates. By contrast, if all class means stay well separated, then the same amount of within-class variance is much less harmful.

So the bound is expressing a very simple principle:

> Few-shot transfer is good when the pretrained representation makes classes tight, keeps their means apart, and is learned from many samples and many source classes.

There is also an important conceptual point here. The guarantee remains meaningful in the true few-shot regime, where $n$ is small and may even stay fixed while $m$ and $l$ grow. This is exactly the setting we care about. The goal is not to say that transfer works because eventually we get lots of target data. The goal is to explain why transfer can already work when the target task has only a handful of labeled examples.

The bound above does exactly that. It says that the burden of learning is shifted to pretraining: if the source task is rich enough and the learned feature geometry is sufficiently collapsed and separated, then the downstream target task can be solved from very little data.

## Why the number of source classes matters

One subtle point in the theory is that there are **two** kinds of generalization happening.

The first is standard sample generalization: with more samples per source class, the empirical geometry of each source class better reflects its true geometry.

The second is more interesting: **generalization across classes**.

Even if every source class is well learned, that alone does not guarantee transfer to unseen target classes. To get that, we need many source classes sampled from the population $\mathcal D$.

That is why the bound has a term of order $1/\sqrt{l}$.

This is not an artifact. If we want to generalize to new classes, the number of training classes matters in its own right.

## Why nearest-class-center appears naturally

Once classes collapse around their means, nearest-center classification is no longer an arbitrary rule. It becomes the natural one.

The downstream learner does not need to discover a complicated separator from a tiny amount of data. It mainly needs to estimate where each new class center lies.

That is why simple top-layer methods such as nearest-center, ridge regression, or logistic regression on frozen features often work so well in practice. The difficult part has already been done by the representation.

The geometry is doing the real work.

## What the experiments show

Empirically, the same story appears across standard few-shot benchmarks.

As source training proceeds:

- the collapse quantity decreases on the source training classes,
- similar geometry appears on held-out samples from the same classes,
- and, importantly, geometry on new target classes improves as well.

At the same time, few-shot target accuracy rises.

So collapse is not merely a source-training artifact. It tracks actual transfer performance on unseen classes.

That is what makes it a compelling explanation.

## What this does and does not claim

This theory does **not** say that every pretrained classifier transfers well to every target task.

It does **not** say that exact neural collapse must hold perfectly.

And it does **not** remove the need for source and target classes to come from a related population.

What it does say is more precise:

- there is a clear probabilistic model for transfer to unseen classes,
- there is a concrete geometric quantity that can be measured,
- and that quantity explains why supervised pretraining can make few-shot adaptation easy.

So this is not just a vague claim about "good features." It is a specific mechanism with a clean mathematical setting behind it.

## Takeaway

The right way to think about few-shot transfer is not that pretraining somehow memorizes every future task.

It is that pretraining learns a feature space with the right geometry.

In the formal setting:

- source classes $\tilde P_1,\dots,\tilde P_l$ are sampled from a distribution $\mathcal D$ over class-conditionals,
- target classes $P_1,\dots,P_k$ are new draws from the same $\mathcal D$,
- the pretrained feature map $f$ is evaluated by the expected few-shot transfer error $\mathcal L_{\mathcal D}(f)$,
- and this transfer error is small when class-feature variability collapse happens on the source classes and generalizes across classes.

In simple words:

1. each class becomes concentrated around its mean,
2. different classes stay far apart,
3. this geometry extends to new classes,
4. so a few labeled examples are enough to estimate the new centers.

That is why ordinary supervised pretraining can be such a strong few-shot learner.
