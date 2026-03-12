---
layout: post
title: "Can LLMs Make ERM Practical Again?"
date: 2026-03-11
author: Tomer Galanti
tags:
  - machine-learning
  - theory
  - empirical-risk-minimization
  - large-language-models
  - program-synthesis
  - algorithmic-reasoning
excerpt: "Short programs should be learnable from few examples, but classical ERM is computationally intractable and gradient-based learning can be statistically inefficient. LLM-PV uses a pretrained LLM as a search prior to make ERM over programs practical."
---

*This post is based on our paper on learning short programs with LLM-guided propose-and-verify.*

A lot of modern machine learning is built around one dominant recipe:

1. choose a large parametric model,
2. train it with gradient descent,
3. hope the learned predictor generalizes.

This recipe has been spectacularly successful in vision, speech, and language. But it is not the only way to think about learning.

There is an older and very clean perspective from classical learning theory:

> If the target rule is *simple*, then it should be learnable from *few examples*.

For example, suppose the target is not just an arbitrary classifier, but a short program. Maybe it computes parity of a hidden subset of bits. Maybe it checks whether a string contains a pattern. Maybe it tests whether a large number is prime. Maybe it verifies whether a bracket string is balanced.

From the viewpoint of statistical learning theory, such targets should often be easy. If the correct rule can be described by a short program, then the effective hypothesis class is small enough that empirical risk minimization (ERM) should need only a modest number of labeled examples.

So what is the problem?

The problem is computation.

The classical ERM solution is to search over all short programs and return one that fits the data. This is statistically attractive, but computationally brutal. The modern deep-learning alternative avoids exhaustive search, but can be a very poor match to discrete algorithmic structure.

This post is about a simple question:

> **Can we recover the sample efficiency of ERM over short programs without paying the full cost of exhaustive enumeration?**

Our answer is a simple recipe we call **LLM-PV**:

> Use a pretrained LLM as a **proposal distribution** over candidate programs, then **verify** candidates by execution and select the best one by held-out error.

The LLM is not trusted as the final predictor. It is used as a search prior. The selection rule remains executable and empirical.

That turns out to matter a lot.

## The old promise of ERM

Let us start from the clean classical picture.

Suppose the target rule can be implemented by a program of length $L$ over an alphabet $\Sigma$. Then the number of candidate programs is at most $|\Sigma|^L$. Standard finite-class learning theory tells us that ERM over this class needs only on the order of

$$
O(L \log |\Sigma|)
$$

examples to generalize.

This is the usual Occam-style story: short descriptions imply small effective hypothesis classes, and small hypothesis classes imply sample efficiency.

So from a purely statistical point of view, short-program learning is favorable.

But there is a catch. To actually implement ERM, the naive procedure is:

1. enumerate candidate programs,
2. run each one on the data,
3. return a program with low empirical error.

That immediately introduces an exponential search cost in the description length:

$$
|\mathcal{L}_{\le L}| = \Theta(|\Sigma|^L).
$$

So ERM has a beautiful sample-complexity guarantee, but brute-force search is usually hopeless.

This is the first tension:

> **ERM over programs is sample-efficient but computationally expensive.**

## Why gradient-based learning is not the answer

A natural reaction is: fine, do not search over programs explicitly. Train a neural network instead.

This is the modern default. It is often computationally attractive per step, and it avoids explicit combinatorial search.

But for many algorithmic tasks, this only swaps one problem for another.

There is a long line of theory showing that broad classes of gradient-based procedures are poorly matched to certain discrete targets. A canonical example is parity. A parity function can be represented by a very short program, yet learning it through gradient-based access can require exponentially many samples in the relevant problem parameters.

This is not because parity is complicated in a description-length sense. It is because the *interface* used by SGD is poorly aligned with the target structure.

That is the second tension:

> **Gradient-based learning is computationally convenient per step, but can be statistically inefficient on short, discrete, algorithmic rules.**

So now we have two unsatisfying extremes:

- **ERM:** statistically efficient, computationally intractable
- **SGD:** computationally convenient, statistically inefficient on many short-program families

This is the gap we want to close.

## A new lens: ERM with a learned search prior

If brute-force search is too expensive, and SGD is often the wrong inductive bias, then the real bottleneck is not generalization theory and not verification.

The bottleneck is **search**.

That suggests a different question:

> Instead of enumerating all short programs, can we search the program space *non-uniformly*?

Uniform random sampling does not help. If the correct length-$L$ program has probability about $|\Sigma|^{-L}$ under a uniform distribution, then the expected number of trials is still exponential.

So the real object we need is a **proposal distribution** that places much more mass on plausible programs than uniform search does.

This is where pretrained LLMs enter.

A strong pretrained LLM has absorbed enormous amounts of code, patterns, heuristics, and reusable program templates. Conditioned on a few labeled examples, it does not sample uniformly from the space of all strings that happen to be Python. It tends to concentrate on concise, recognizable rules.

That motivates the following recipe.

## LLM-PV: propose and verify

LLM-PV is deliberately simple.

We split the labeled data into a training set $S_{\mathrm{tr}}$ and a validation set $S_{\mathrm{val}}$.

Then we repeat:

1. prompt the LLM with $S_{\mathrm{tr}}$ and ask it to output a candidate program,
2. compile and run the program,
3. discard invalid or duplicate candidates,
4. score the candidate on $S_{\mathrm{val}}$,
5. keep the best one seen so far.

After $k$ trials, we return the candidate with lowest validation error.

That is all.

There are two important aspects of this design.

First, the LLM is used **only as a proposer**. It is not doing gradient updates, and it is not trusted as the final classifier.

Second, selection is still grounded in **execution and held-out error**. A candidate does not win because it sounds plausible. It wins because it works.

In pseudocode, the procedure looks like this:

1. initialize the best validation error to 1
2. for $t=1,\dots,k$:
   - sample a candidate program from the LLM
   - compile and execute it
   - if it is valid, compute its validation error
   - update the best-so-far candidate if needed
3. return the best candidate found

Conceptually, this is ERM-style selection over a discrete program class, but with an LLM replacing exhaustive enumeration by a much more concentrated proposal distribution.

## The theory behind the method

The theory is simple and clean.

Let

$$
p_\epsilon(S_{\mathrm{tr}})
=
\Pr_{h \sim q(\cdot \mid S_{\mathrm{tr}})}
\big[\mathrm{err}_D(h) \le \epsilon \big]
$$

denote the probability that a fresh proposal from the LLM-induced distribution has population error at most $\epsilon$.

Then two things matter:

1. **Proposal quality:** how much mass the proposal distribution puts on good programs
2. **Validation selection:** how much penalty we pay for choosing the best among $k$ candidates

If $k$ is large enough that a good candidate appears with high probability, and if the validation set is large enough to compare the $k$ candidates reliably, then the returned program has population error close to the best proposal error.

In other words, the LLM only needs to do one thing:

> put enough probability mass on low-error programs so that a good candidate appears in a small number of trials.

Once that happens, held-out execution-based selection takes over.

This perspective is important. It clarifies the role of the pretrained model:

- the LLM is **not** the final learner in the usual black-box sense,
- it is a **search prior** over a discrete hypothesis class.

That is a very different use of pretrained knowledge.

## What we test

We evaluate this idea on a suite of algorithmic classification tasks where short executable rules exist, but gradient-based learners often struggle to recover them from few examples.

These include:

- parity variants,
- pattern matching,
- palindrome detection,
- Dyck-2 membership,
- primality testing,
- a shifted primality task,
- cellular automata parity,
- graph cycle counting,
- SHA-256 parity.

These tasks are designed to stress different kinds of structure:

- sparse global dependencies,
- position-invariant search,
- symmetry,
- context-free constraints,
- arithmetic reasoning,
- pseudorandom or avalanche-like behavior.

For most experiments, we use only **200 labeled examples**, split into 100 for training and 100 for validation.

That is the regime where short-program ERM should be attractive, but where brute-force search is impractical and gradient training often fails.

## The main empirical picture

The headline result is simple:

> **LLM-PV often recovers the exact underlying rule from a very small labeled set and generalizes far beyond the training regime.**

At input length $n=100$, LLM-PV reaches:

- **100%** on full parity,
- **100%** on first-half parity,
- **100%** on random 3-parity,
- **100%** on random 10-parity,
- **100%** on both pattern-matching tasks,
- **100%** on palindrome detection,
- **100%** on Dyck-2,
- **100%** on cellular automata parity,
- **100%** on primality,
- **80.6%** on the shifted primality task,
- **96.9%** on cycle counting,

while remaining near chance on SHA-256 parity.

That last failure is actually informative. SHA is intended as a true stress test: if the label behaves pseudorandomly and no short recoverable program is discoverable from the data, then propose-and-verify should fail too. And it does.

### What about the baselines?

We compare against several families of baselines:

- classic ML methods such as SVM, Random Forest, XGBoost, and genetic algorithms,
- TabPFN,
- transformers trained from scratch with SGD,
- fine-tuned pretrained LMs,
- in-context learning with larger instruction-tuned models.

Across the algorithmic tasks, most of these baselines stay near chance once the problems become truly structural.

For example:

- parity variants remain near chance for SGD, FT, ICL, and tabular baselines,
- cellular automata parity remains near chance,
- even when training accuracy becomes very high, test accuracy often does not improve.

This is exactly the failure mode one would expect when a model memorizes the training distribution without recovering the underlying rule.

## More data does not automatically fix SGD

A natural objection is that 200 examples might simply be too small for the gradient-based baselines.

So we also scale up training for an SGD baseline to **100k labeled examples**.

The result is striking: the model can fit the training data extremely well, but still remains near chance on several key tasks such as random 10-parity and cellular automata parity.

This is the point where the old ERM perspective becomes very useful again.

These tasks admit short programs. So from a description-length viewpoint, they should be learnable from relatively few examples. If an SGD-trained model still fails after seeing orders of magnitude more data, that is not just a small-data issue. It is a mismatch between the learner and the structure of the task.

## Length generalization is the clearest difference

One of the strongest empirical differences appears in out-of-distribution length generalization.

We train at a short input length, such as $n=10$, and then evaluate at much larger lengths.

The gradient-based baselines often achieve strong performance at the training length, but collapse toward chance as the input length grows.

LLM-PV behaves very differently.

Because it often outputs an explicit program that is independent of the input dimension, it can generalize almost perfectly across lengths. This is especially clear on tasks like pattern matching and random 3-parity.

That is exactly what one would hope for from true rule recovery.

## Why reasoning traces matter

A particularly nice byproduct of the approach is that it is auditable.

The output is executable code, but the *search process* can also be inspected.

For example, on primality, the model often starts with weak heuristics such as digit-sum tests, then shifts toward modular structure, and eventually lands on an explicit primality-testing procedure such as Miller-Rabin.

On parity tasks, the trace often moves from superficial checks to linear-algebraic reasoning over $\mathbb{F}_2$ before recovering the correct support.

This matters because it gives us something rare in modern learning systems:

> not only an interpretable final hypothesis, but also an interpretable learning trajectory.

That makes debugging much easier. Failures can be inspected. Successes can be validated mechanistically. The final program can be stress-tested out of distribution.

## What the results mean

I do not think the right takeaway is “LLMs solve program learning.”

The more interesting takeaway is this:

> **Pretrained LLMs can make an old idea, ERM over short programs, computationally viable again.**

That is a different claim.

The LLM is not replacing generalization theory. It is not replacing verification. It is not even replacing model selection.

It is replacing **uniform search** by a much better proposal mechanism.

This gives a very different picture of what pretrained models may be useful for:

- not only as predictors,
- not only as in-context reasoners,
- but as **search priors** over structured discrete hypothesis spaces.

## Takeaway

There is a classical lesson in learning theory:

> If the target has a short description, then it should be learnable from few examples.

For program learning, this leads naturally to ERM over short programs. The problem is that brute-force ERM is computationally infeasible, while gradient-based learning can be statistically inefficient on exactly the structured tasks where short-program descriptions are most meaningful.

LLM-PV offers a simple middle ground:

1. use a pretrained LLM to propose candidate programs,
2. verify them by execution,
3. select by held-out error.

Across a wide range of algorithmic tasks, this is enough to recover exact or near-exact rules from very small labeled datasets, often with strong out-of-distribution generalization.

So perhaps the right way to think about this is not that LLMs replace ERM.

It is that they may finally give us a practical way to use it.
