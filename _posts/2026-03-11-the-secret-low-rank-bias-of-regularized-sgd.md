---
layout: post
title: "Why SGD Prefers Low-Rank Neural Networks"
date: 2026-03-11
author: Tomer Galanti
tags:
  - deep-learning
  - optimization
  - stochastic-gradient-descent
  - weight-decay
  - theory
  - low-rank
excerpt: "Why mini-batch SGD with weight decay implicitly pushes neural networks toward low-rank weight matrices."
---

Deep networks are heavily overparameterized, yet the solutions found in practice are far from arbitrary. Even when a model has enough capacity to fit the data in many different ways, stochastic gradient descent often lands on highly structured solutions.

One especially striking form of structure is **low rank**.

Across many architectures, learned weight matrices are often much more compressible than their ambient dimension would suggest. This shows up in pruning, distillation, and post-hoc low-rank approximations of trained models. But where does this structure come from?

A lot of prior theory explains low-rank behavior only under restrictive assumptions: linear models, special losses, strong symmetry, or global optimality conditions. What is still missing is a simple explanation for the setting practitioners actually use every day:

> **mini-batch SGD with weight decay.**

The main message of this post is:

> **SGD with weight decay implicitly biases each layer toward low-rank structure, and this effect becomes stronger with smaller batch size, larger learning rate, and stronger weight decay.**

This is not a convergence theorem. It is a structural explanation for why low-rank layers naturally emerge during training.

## The setup

We train a network by minimizing the regularized empirical loss

$$
L_S^\lambda(W) = \frac{1}{m}\sum_{i=1}^m \ell_i(h_W(x_i)) + \lambda \|W\|_F^2.
$$

To study one layer, fix all other parameters and focus on a single trainable matrix \(W\).

For now, assume that this matrix is used once on each input. Then the network can be written locally as

$$
h_W(x) = g(Wf(x)).
$$

Here:

- $f(x)$ is the input representation entering the layer,
- $W$ is the matrix of that layer,
- $g$ collects everything that happens after this layer.

This is the cleanest case, and it already reveals the whole mechanism.

Later we will return to residual blocks, convolutions, and self-attention, where the same matrix may be reused several times within one example.

## The SGD update

For this layer, mini-batch SGD with weight decay takes the form

$$
W_{t+1} = W_t - \mu \nabla_W L_{\tilde S_t}(W_t) - 2\mu\lambda W_t,
$$

where:

- $\mu$ is the learning rate,
- $\lambda$ is the weight decay coefficient,
- $\tilde S_t$ is the current mini-batch.

Equivalently,

$$
W_{t+1} = (1 - 2\mu\lambda)W_t - \mu G_t,
$$

where

$$
G_t := \nabla_W L_{\tilde S_t}(W_t).
$$

This decomposition is already suggestive:

- the factor $(1-2\mu\lambda)$ shrinks the current weight matrix,
- the stochastic gradient $G_t$ injects a new update.

The key question is: **what structure does \(G_t\) have?**

## The key observation: one sample gives a rank-1 update

Consider a single training example \(x\). Since

$$
h_W(x)=g(Wf(x)),
$$

the chain rule gives

$$
\nabla_W \ell(h_W(x))
=
\Big(J_g(Wf(x))^\top \nabla_h \ell(h_W(x))\Big)\, f(x)^\top.
$$

Define

$$
\delta(x) := J_g(Wf(x))^\top \nabla_h \ell(h_W(x)).
$$

Then

$$
\nabla_W \ell(h_W(x)) = \delta(x) f(x)^\top.
$$

This is the outer product of two vectors. Therefore,

$$
\textnormal{rank}\big(\nabla_W \ell(h_W(x))\big) \le 1.
$$

So a **single-sample gradient is rank 1**.

That is the basic reason low rank appears.

## From one sample to a mini-batch

If the mini-batch has size \(B\), then the stochastic gradient is the average of \(B\) such outer products:

$$
G_t = \frac{1}{B}\sum_{i=1}^B \delta_i f_i^\top.
$$

A sum of \(B\) rank-1 matrices has rank at most \(B\), so

$$
\textnormal{rank}(G_t) \le B.
$$

Thus, every SGD step adds a matrix of rank at most the batch size.

This is already interesting:

- **small batch** means lower-rank updates,
- **large batch** means higher-rank updates.

But this is only half the story. The other half is weight decay.

## Weight decay forgets the distant past

Starting from

$$
W_{t+1} = (1 - 2\mu\lambda)W_t - \mu G_t,
$$

we can unroll the recursion for \(n\) steps:

$$
W_T
=
(1-2\mu\lambda)^n W_{T-n}
-
\mu \sum_{j=1}^n (1-2\mu\lambda)^{j-1} G_{T-j}.
$$

This identity is the heart of the argument.

It says that the current matrix \(W_T\) is made of two parts:

1. an exponentially decayed memory of the distant past,
2. a weighted sum of the most recent stochastic gradients.

The first term becomes small when \(n\) is moderately large, because it is multiplied by \((1-2\mu\lambda)^n\).

The second term is a sum of recent low-rank matrices.

So, after enough time, the current weight matrix is well approximated by a sum of only **recent low-rank updates**.

That is why SGD with weight decay tends to produce low-rank structure.

## An effective-rank bound

Suppose we choose \(n\) large enough so that the old-memory term is at most \(\varepsilon\) in norm:

$$
\|(1-2\mu\lambda)^n W_{T-n}\| \le \varepsilon.
$$

Since \((1-2\mu\lambda)^n \approx e^{-2\mu\lambda n}\), this happens for

$$
n \approx \frac{\log(1/\varepsilon)}{\mu\lambda}.
$$

Now the second term is a sum of \(n\) mini-batch gradients, each of rank at most \(B\). Therefore its rank is at most \(nB\). This gives the heuristic effective-rank bound

$$
\textnormal{rank}_\varepsilon(W_T)
\;\lesssim\;
\frac{B \log(1/\varepsilon)}{\mu\lambda}.
$$

The notation \(\textnormal{rank}_\varepsilon\) means the minimum rank of a matrix that approximates \(W_T\) up to error \(\varepsilon\).

This bound is not meant to be sharp. Its value is conceptual. It shows the correct qualitative dependencies:

- smaller batch size \(\Rightarrow\) lower effective rank,
- larger learning rate \(\Rightarrow\) shorter memory \(\Rightarrow\) lower effective rank,
- larger weight decay \(\Rightarrow\) shorter memory \(\Rightarrow\) lower effective rank.

## What this means intuitively

Each stochastic gradient step writes only a few directions into the matrix.

Weight decay prevents the matrix from remembering too many old directions at once.

So instead of accumulating an unrestricted full-rank history, the layer mostly remembers a short window of recent low-rank updates.

That is exactly the kind of mechanism that produces compressible matrices.

## Why the local form \(h_W(x)=g(Wf(x))\) is natural

At first glance, writing the network as

$$
h_W(x)=g(Wf(x))
$$

may look restrictive. But it is actually the correct local view for a very broad class of layers.

The idea is simple: fix all parameters except one matrix \(W\), and isolate the place in the computation where \(W\) acts.

- $f(x)$ is whatever enters that linear map,
- $Wf(x)$ is the output of that map,
- $g$ absorbs everything downstream.

For a standard fully connected layer, this is immediate.

For a residual block, it is still true locally: the skip connection is simply absorbed into \(g\).

For example, if the block output is

$$
u(x) + \tilde g(Wf(x)),
$$

then we can define

$$
g(z) := u(x) + \tilde g(z),
$$

and again write

$$
h_W(x)=g(Wf(x)).
$$

So the simple one-use model already covers dense layers and matrices inside residual architectures.

## Extension: when the same matrix is used many times

The only place where the rank-1 statement needs to be modified is when the same matrix \(W\) is reused multiple times within a single example.

This happens in:

- convolutions, where the same kernel is applied across many spatial locations,
- self-attention projections \(W_Q, W_K, W_V\), where the same matrix is applied to every token,
- other shared linear operators.

In that case, the correct local form is slightly more general.

Instead of a single vector \(f(x)\), collect all local inputs into a matrix

$$
F(x) = [f_1(x),\dots,f_R(x)],
$$

where \(R\) is the number of locations, patches, or tokens on which \(W\) acts.

Then we write

$$
h_W(x)=g(WF(x)).
$$

Now the chain rule gives

$$
\nabla_W \ell(h_W(x))
=
\Delta(x) F(x)^\top,
$$

where \(\Delta(x)\) collects the backpropagated error vectors for those \(R\) uses of the matrix.

Equivalently,

$$
\nabla_W \ell(h_W(x))
=
\sum_{r=1}^R \delta_r(x) f_r(x)^\top.
$$

Therefore,

$$
\textnormal{rank}\big(\nabla_W \ell(h_W(x))\big) \le R.
$$

So the single-sample gradient is no longer necessarily rank \(1\), but it is still low rank: its rank is at most the number of local applications of \(W\) within that example.

### Convolution

For a convolutional kernel reshaped as a matrix \(W\), the same kernel is applied at many spatial locations. If the extracted local patches are \(f_1(x),\dots,f_R(x)\), then

$$
\nabla_W \ell(h_W(x))
=
\sum_{r=1}^R \delta_r(x) f_r(x)^\top,
$$

so

$$
\textnormal{rank}\big(\nabla_W \ell(h_W(x))\big) \le R.
$$

Here \(R\) is the number of spatial positions.

### Self-attention projections

For a transformer projection matrix such as \(W_Q\), \(W_K\), or \(W_V\), the same matrix is applied to every token.

If the token representations are \(f_1(x),\dots,f_T(x)\), then

$$
\nabla_W \ell(h_W(x))
=
\sum_{t=1}^T \delta_t(x) f_t(x)^\top,
$$

so

$$
\textnormal{rank}\big(\nabla_W \ell(h_W(x))\big) \le T,
$$

where \(T\) is the sequence length.

Again, this is not rank \(1\), but it is still much smaller than the ambient matrix dimension in many modern models.

## The general principle

The cleanest statement is this:

> **A stochastic gradient update for a given matrix \(W\) has rank at most the number of times that \(W\) is used across the current mini-batch.**

So if:

- \(B\) is the batch size,
- \(R\) is the number of local uses of \(W\) per example,

then

$$
\textnormal{rank}(G_t) \le BR.
$$

The rest of the argument is unchanged.

Weight decay still exponentially forgets old updates, so the current matrix remains close to a sum of only recent low-rank gradients. The one-use case \(R=1\) is simply the sharpest and cleanest special case.

## Takeaway

SGD with weight decay does more than optimize the loss.

It quietly pushes each layer toward low-rank structure.

The mechanism is simple:

1. each stochastic gradient is low rank,
2. weight decay exponentially forgets old updates,
3. so the current weights are close to a sum of only recent low-rank updates.

For layers used once per example, the single-sample gradient is rank \(1\).

For layers reused across tokens or spatial locations, the same idea still holds, with rank controlled by the number of local uses.

That gives a simple and very general picture for why low-rank structure appears so often in trained neural networks.
