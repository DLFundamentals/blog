---
layout: post
title: "The Secret Low-Rank Bias of Regularized SGD"
date: 2026-03-11
author: Tomer Galanti
tags: [deep learning, optimization, SGD, weight decay, theory, low-rank]
excerpt: "A simple view of why mini-batch SGD with weight decay implicitly pushes neural networks toward low-rank weight matrices."
---

Deep networks are often massively overparameterized, yet the solutions found in practice are far from arbitrary. Even when a model has enough capacity to memorize the data in many different ways, stochastic gradient descent tends to land on solutions with structure.

One particularly interesting form of structure is **low rank**.

Across many architectures, learned weight matrices often end up being much more compressible than their ambient dimension would suggest. This shows up in pruning, distillation, and low-rank approximations of trained models. But where does this structure actually come from?

A lot of prior theory has tried to explain low-rank behavior in neural networks, but most existing results only apply under fairly restrictive assumptions: special data geometry, linear networks, special losses, or global optimality conditions. What has been missing is a general explanation that applies to the way deep networks are actually trained in practice: **mini-batch SGD with weight decay**.

> **SGD with weight decay implicitly biases neural networks toward low-rank weight matrices, and this effect becomes stronger with smaller batch size, larger learning rate, and stronger weight decay.**

## The setup

We train a neural network by minimizing the regularized empirical loss

$$
L_S^\lambda(W)
=
\frac{1}{m}\sum_{i=1}^m \ell_i(h_W(x_i)) + \lambda \|W\|_F^2.
$$

To focus on one layer, write the network locally as

$$
h(x) = g(W f(x)).
$$

For this layer, the mini-batch SGD update with weight decay is

$$
W_{t+1}
=
W_t - \mu \nabla_W L_{\tilde S_t}(W_t) - 2\mu\lambda W_t,
$$

or equivalently,

$$
W_{t+1}
=
(1 - 2\mu\lambda) W_t - \mu G_t,
$$

where $G_t := \nabla_W L_{\tilde S_t}(W_t)$ is the stochastic gradient on the current mini-batch.

## The key observation

For a fully connected layer, the gradient for a single sample has the form

$$
\nabla_W \ell(h_W(x))
=
\delta(x) f(x)^\top,
$$

which is rank $1$.

For a mini-batch of size $B$, the stochastic gradient rank scales like

$$
\textnormal{rank}(G_t) \lesssim B \cdot m_\ell.
$$

So every SGD step adds a low-rank update, while weight decay forgets older updates exponentially fast.

## Proof sketch

Starting from

$$
W_{t+1}
=
(1 - 2\mu\lambda) W_t - \mu G_t,
$$

unrolling for $n$ steps gives

$$
W_T
=
(1 - 2\mu\lambda)^n W_{T-n}
-
\mu \sum_{j=1}^n (1 - 2\mu\lambda)^{j-1} G_{T-j}.
$$

The first term is an exponentially damped memory of the distant past. The second term is a sum of only recent low-rank gradients, so it is itself low rank.

Choosing $n$ so that the old-memory term is at most $\varepsilon$ gives

$$
n \approx \frac{\log(1/\varepsilon)}{\mu\lambda},
$$

and therefore an effective-rank bound of the form

$$
\textnormal{rank}_\varepsilon(W_T)
\lesssim
\frac{m_\ell B \log(1/\varepsilon)}{\mu\lambda}.
$$

This explains why:

- smaller batch size gives lower rank,
- larger learning rate gives lower rank,
- larger weight decay gives lower rank.

## Conclusion

SGD plus weight decay does more than optimize the loss. It quietly pushes neural networks toward low-rank structure.

The mechanism is simple:

1. each stochastic gradient is low rank,
2. weight decay exponentially forgets older updates,
3. so the current weights are close to a sum of only recent low-rank updates.
