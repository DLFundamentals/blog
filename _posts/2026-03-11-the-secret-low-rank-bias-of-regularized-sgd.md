<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Why SGD Prefers Low-Rank Neural Networks</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Newsreader:ital,opsz,wght@0,6..72,400;0,6..72,500;1,6..72,400;1,6..72,500&family=DM+Sans:ital,wght@0,400;0,500;0,700;1,400&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.min.css">
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.min.js"></script>
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/contrib/auto-render.min.js" onload="renderMathInElement(document.body,{delimiters:[{left:'$$',right:'$$',display:true},{left:'$',right:'$',display:false}],throwOnError:false})"></script>
<style>
:root {
  --navy: #0a1628;
  --navy-soft: #1a2a4a;
  --ink: #1d2939;
  --body: #374151;
  --muted: #6b7280;
  --faint: #9ca3af;
  --border: #e5e7eb;
  --border-light: #f1f3f5;
  --surface: #f8f9fb;
  --bg: #ffffff;
  --accent: #2563eb;
  --accent-light: #dbeafe;
  --accent-wash: #eff6ff;
  --warm: #d97706;
  --warm-light: #fef3c7;
  --teal: #0d9488;
  --teal-light: #ccfbf1;
  --col-width: 680px;
  --wide-width: 860px;
}

* { margin: 0; padding: 0; box-sizing: border-box; }

html {
  font-size: 17px;
  scroll-behavior: smooth;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

body {
  font-family: 'Newsreader', Georgia, 'Times New Roman', serif;
  color: var(--body);
  background: var(--bg);
  line-height: 1.78;
}

::selection {
  background: var(--accent-light);
  color: var(--navy);
}

/* ── Header ── */
.site-header {
  border-bottom: 1px solid var(--border);
  padding: 1rem 0;
  position: sticky;
  top: 0;
  background: rgba(255,255,255,0.92);
  backdrop-filter: blur(12px);
  z-index: 100;
}
.site-header-inner {
  max-width: var(--wide-width);
  margin: 0 auto;
  padding: 0 2rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.site-logo {
  font-family: 'DM Sans', sans-serif;
  font-weight: 700;
  font-size: 0.85rem;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: var(--navy);
  text-decoration: none;
}
.site-nav {
  display: flex;
  gap: 1.5rem;
}
.site-nav a {
  font-family: 'DM Sans', sans-serif;
  font-size: 0.8rem;
  color: var(--muted);
  text-decoration: none;
  letter-spacing: 0.02em;
  transition: color 0.2s;
}
.site-nav a:hover { color: var(--navy); }

/* ── Article Container ── */
.article-container {
  max-width: var(--col-width);
  margin: 0 auto;
  padding: 0 2rem;
}
.article-wide {
  max-width: var(--wide-width);
  margin: 0 auto;
  padding: 0 2rem;
}

/* ── Hero ── */
.hero {
  padding: 5rem 0 3rem;
  max-width: var(--col-width);
  margin: 0 auto;
  padding-left: 2rem;
  padding-right: 2rem;
}
.hero-tags {
  display: flex;
  gap: 0.5rem;
  flex-wrap: wrap;
  margin-bottom: 1.5rem;
}
.hero-tag {
  font-family: 'DM Sans', sans-serif;
  font-size: 0.7rem;
  font-weight: 500;
  letter-spacing: 0.06em;
  text-transform: uppercase;
  padding: 0.25rem 0.7rem;
  border-radius: 100px;
  background: var(--surface);
  color: var(--muted);
  border: 1px solid var(--border);
}
.hero h1 {
  font-family: 'Newsreader', Georgia, serif;
  font-weight: 500;
  font-size: 2.8rem;
  line-height: 1.18;
  color: var(--navy);
  letter-spacing: -0.025em;
  margin-bottom: 1.25rem;
}
.hero-meta {
  font-family: 'DM Sans', sans-serif;
  font-size: 0.85rem;
  color: var(--muted);
  display: flex;
  align-items: center;
  gap: 0.5rem;
}
.hero-meta .dot { color: var(--border); }
.hero-cite {
  margin-top: 2rem;
  font-size: 0.88rem;
  font-style: italic;
  color: var(--muted);
  padding: 1rem 1.25rem;
  border-left: 3px solid var(--border);
  background: var(--surface);
  border-radius: 0 8px 8px 0;
}
.hero-cite a {
  color: var(--accent);
  text-decoration: none;
  border-bottom: 1px solid var(--accent-light);
  transition: border-color 0.2s;
}
.hero-cite a:hover { border-bottom-color: var(--accent); }

/* ── Prose ── */
article p {
  margin-bottom: 1.4rem;
}
article a {
  color: var(--accent);
  text-decoration: none;
  border-bottom: 1px solid transparent;
  transition: border-color 0.2s;
}
article a:hover { border-bottom-color: var(--accent); }

/* ── Key Message ── */
.key-message {
  margin: 2.5rem 0;
  padding: 1.5rem 1.75rem;
  border-left: 4px solid var(--accent);
  background: linear-gradient(135deg, var(--accent-wash), #fff);
  border-radius: 0 12px 12px 0;
  font-size: 1.02rem;
  line-height: 1.7;
  color: var(--navy-soft);
  font-weight: 400;
}

/* ── Headings ── */
article h2 {
  font-family: 'DM Sans', sans-serif;
  font-weight: 700;
  font-size: 1.55rem;
  color: var(--navy);
  margin-top: 3.5rem;
  margin-bottom: 1rem;
  letter-spacing: -0.01em;
  line-height: 1.3;
  padding-bottom: 0.5rem;
  border-bottom: 1px solid var(--border-light);
}
article h3 {
  font-family: 'DM Sans', sans-serif;
  font-weight: 700;
  font-size: 1.1rem;
  color: var(--ink);
  margin-top: 2.25rem;
  margin-bottom: 0.75rem;
  letter-spacing: -0.005em;
}

/* ── Lists ── */
article ol, article ul {
  padding-left: 1.5rem;
  margin-bottom: 1.4rem;
}
article li {
  margin-bottom: 0.5rem;
}
article li strong {
  color: var(--ink);
}

/* ── Math ── */
.katex-display {
  margin: 1.5rem 0;
  overflow-x: auto;
  padding: 0.5rem 0;
}
.math-block {
  margin: 1.75rem 0;
  padding: 1.25rem 1.5rem;
  background: var(--surface);
  border-radius: 10px;
  border: 1px solid var(--border-light);
  overflow-x: auto;
}

/* ── Figures ── */
.figure {
  margin: 2.5rem 0;
}
.figure-wide {
  max-width: var(--wide-width);
  margin-left: auto;
  margin-right: auto;
  padding: 0 2rem;
}
.figure img {
  width: 100%;
  border-radius: 10px;
}
.figure-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 16px;
  align-items: start;
}
.figure-grid-item {
  text-align: center;
}
.figure-grid-item img {
  width: 100%;
  border-radius: 8px;
  border: 1px solid var(--border-light);
}
.figure-grid-item .label {
  font-family: 'DM Sans', sans-serif;
  font-size: 0.78rem;
  color: var(--muted);
  margin-top: 0.4rem;
}
figcaption, .figcaption {
  font-family: 'DM Sans', sans-serif;
  font-size: 0.82rem;
  color: var(--muted);
  line-height: 1.55;
  margin-top: 0.8rem;
}
figcaption strong, .figcaption strong {
  color: var(--ink);
  font-weight: 500;
}

/* ── Interactive Embed ── */
.embed-wrap {
  margin: 2rem 0;
  border-radius: 14px;
  overflow: hidden;
  border: 1px solid var(--border);
  background: var(--surface);
}
.embed-wrap iframe {
  width: 100%;
  border: none;
  display: block;
}

/* ── Experiment Cards ── */
.experiments {
  margin: 2rem 0;
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}
.experiment-card {
  padding: 1rem 1.25rem;
  border-radius: 10px;
  border: 1px solid var(--border-light);
  background: var(--bg);
  transition: border-color 0.2s, box-shadow 0.2s;
}
.experiment-card:hover {
  border-color: var(--border);
  box-shadow: 0 2px 12px rgba(0,0,0,0.04);
}
.experiment-card .exp-title {
  font-family: 'DM Sans', sans-serif;
  font-weight: 700;
  font-size: 0.85rem;
  color: var(--navy);
  margin-bottom: 0.35rem;
}
.experiment-card p {
  font-size: 0.9rem;
  color: var(--body);
  margin: 0;
  line-height: 1.6;
}

/* ── Divider ── */
.section-rule {
  border: none;
  height: 1px;
  background: var(--border);
  margin: 3rem 0;
}

/* ── Takeaway Box ── */
.takeaway {
  margin: 2.5rem 0;
  padding: 1.75rem;
  background: var(--surface);
  border-radius: 14px;
  border: 1px solid var(--border);
}
.takeaway h3 {
  font-family: 'DM Sans', sans-serif;
  font-size: 0.75rem;
  font-weight: 700;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--muted);
  margin-top: 0;
  margin-bottom: 1rem;
}
.takeaway ol {
  padding-left: 1.25rem;
}
.takeaway li {
  margin-bottom: 0.75rem;
  line-height: 1.65;
}
.takeaway li:last-child {
  margin-bottom: 0;
}

/* ── Footer ── */
.site-footer {
  border-top: 1px solid var(--border);
  margin-top: 4rem;
  padding: 2rem 0;
  text-align: center;
  font-family: 'DM Sans', sans-serif;
  font-size: 0.78rem;
  color: var(--faint);
}

/* ── Responsive ── */
@media (max-width: 768px) {
  html { font-size: 16px; }
  .hero h1 { font-size: 2rem; }
  .figure-grid { grid-template-columns: repeat(2, 1fr); }
  .article-container, .article-wide, .hero, .figure-wide { padding: 0 1.25rem; }
}

/* ── Fade-in animation ── */
@keyframes fadeUp {
  from { opacity: 0; transform: translateY(20px); }
  to { opacity: 1; transform: translateY(0); }
}
.fade-in {
  animation: fadeUp 0.6s ease-out both;
}
.fade-in-d1 { animation-delay: 0.1s; }
.fade-in-d2 { animation-delay: 0.2s; }
.fade-in-d3 { animation-delay: 0.3s; }
</style>
</head>
<body>

<!-- ── Header ── -->
<header class="site-header">
  <div class="site-header-inner">
    <a href="#" class="site-logo">Tomer Galanti</a>
    <nav class="site-nav">
      <a href="#">Research</a>
      <a href="#">Blog</a>
      <a href="#">About</a>
    </nav>
  </div>
</header>

<!-- ── Hero ── -->
<div class="hero">
  <div class="hero-tags fade-in">
    <span class="hero-tag">Deep Learning</span>
    <span class="hero-tag">Optimization</span>
    <span class="hero-tag">Theory</span>
  </div>
  <h1 class="fade-in fade-in-d1">Why SGD Prefers Low-Rank Neural Networks</h1>
  <div class="hero-meta fade-in fade-in-d2">
    <span>Tomer Galanti</span>
    <span class="dot">&middot;</span>
    <span>March 11, 2026</span>
    <span class="dot">&middot;</span>
    <span>10 min read</span>
  </div>
  <div class="hero-cite fade-in fade-in-d3">
    Based on: T. Galanti, Z. Siegel, A. Gupte, T. Poggio.
    <a href="https://openreview.net/forum?id=xhW2WyPhRP">"SGD and Weight Decay Secretly Minimize the Rank of Your Neural Network"</a>, CPAL 2025.
  </div>
</div>

<!-- ── Article ── -->
<article>
<div class="article-container">

<p>Deep networks are heavily overparameterized, yet the solutions found in practice are far from arbitrary. Even when many parameter settings can fit the training data, stochastic gradient methods often converge to highly structured models. One particularly striking form of structure is <strong>low rank</strong>: across many architectures, trained weight matrices are far more compressible than their full dimension would suggest.</p>

<p>Much of the existing theory explains low-rank behavior only in cleaner settings than modern practice: linear models, specialized losses, exact symmetries, or global optimality arguments. What is missing is a structural explanation for the regime practitioners actually use: <strong>training practical neural networks with mini-batch SGD and weight decay.</strong></p>

<div class="key-message">
  Mini-batch SGD with weight decay creates a strong pressure toward low-rank layers. This pressure becomes stronger with smaller batch size, larger learning rate, and stronger weight decay.
</div>

</div>

<!-- Figure 1: Wide grid -->
<div class="figure figure-wide">
  <div class="figure-grid">
    <div class="figure-grid-item">
      <img src="assets/figures/low-rank-bias/contour_resnet_bs_8.png" alt="Batch size 8 contour">
      <div class="label"><strong>(a)</strong> $B = 8$</div>
    </div>
    <div class="figure-grid-item">
      <img src="assets/figures/low-rank-bias/contour_resnet_bs_16.png" alt="Batch size 16 contour">
      <div class="label"><strong>(b)</strong> $B = 16$</div>
    </div>
    <div class="figure-grid-item">
      <img src="assets/figures/low-rank-bias/contour_resnet_lr_5.png" alt="Learning rate 0.5 contour">
      <div class="label"><strong>(c)</strong> $\mu = 0.5$</div>
    </div>
    <div class="figure-grid-item">
      <img src="assets/figures/low-rank-bias/contour_resnet_wd_6e-3.png" alt="Weight decay 6e-3 contour">
      <div class="label"><strong>(d)</strong> $\lambda = 6 \times 10^{-3}$</div>
    </div>
  </div>
  <div class="figcaption">
    <strong>Figure 1.</strong> Average rank across network layers at the end of training for ResNet-18 on CIFAR-10. Lower batch size, larger learning rate, and stronger weight decay are associated with lower final rank.
  </div>
</div>

<div class="article-container">

<p>The mechanism has three parts, each developed in a section below:</p>

<ol>
  <li><strong>Each stochastic gradient is low rank</strong> — a single-example gradient is rank 1, so a mini-batch gradient has rank at most $B$.</li>
  <li><strong>Weight decay limits memory</strong> — it exponentially suppresses old updates, so only a short window of past gradients contributes to the current weight matrix.</li>
  <li><strong>The combination produces low-rank layers</strong> — the current matrix is dominated by a short history of low-rank corrections, yielding an effective rank of roughly $B / (\mu\lambda)$.</li>
</ol>

</div>

<!-- Figure 2: Mechanism diagram -->
<div class="figure figure-wide">
  <img src="assets/figures/low-rank-bias/sgd_low_rank_mechanism.png" alt="Low-rank mechanism diagram" style="max-width: 100%;">
  <div class="figcaption">
    <strong>Figure 2.</strong> Each mini-batch gradient $G_t$ has rank $\le B$. Weight decay exponentially suppresses older updates (fading blocks). The current matrix $W_T$ is dominated by a short effective memory window of recent low-rank corrections.
  </div>
</div>

<div class="article-container">

<!-- ── Interactive Section ── -->
<h2>Interactive explorer</h2>

<p>Before diving into the math, here is a live simulation of the mechanism. A $14 \times 14$ weight matrix is built up step by step from rank-$B$ stochastic gradient updates under weight decay. Press <strong>Play</strong> to watch the dynamics unfold, or <strong>Step</strong> to advance one iteration at a time.</p>

</div>

<div class="article-wide">
<div class="embed-wrap">
  <iframe
    src="assets/figures/low-rank-bias/sgd_low_rank_bias_stable.html"
    height="560"
    loading="lazy"
    title="Interactive low-rank bias explorer">
  </iframe>
</div>
<div class="figcaption" style="padding: 0 2rem;">
  <strong>Figure 3.</strong> Interactive simulation of the low-rank mechanism. The heatmap shows $W_T$ (warm = positive, cool = negative). Singular value bars reveal rank structure. The memory window at the bottom shows how weight decay fades old gradient contributions. The sliders control batch size $B$, learning rate $\mu$, and weight decay $\lambda$.
</div>
</div>

<div class="article-container">

<div class="experiments">
  <div class="experiment-card">
    <div class="exp-title">Low-rank updates</div>
    <p>Set $B = 1$ and step through. Each gradient is a single outer product, so the matrix grows in structured stripe-like patterns. Increase $B$ to 8+ and watch the updates become richer — more singular values light up.</p>
  </div>
  <div class="experiment-card">
    <div class="exp-title">Weight decay limits memory</div>
    <p>With small $\lambda$ (say 0.01), the timeline blocks stay bright for many steps and effective rank climbs. Increase $\lambda$ toward 0.10 and watch old blocks fade rapidly, the memory window shrinks, and rank drops.</p>
  </div>
  <div class="experiment-card">
    <div class="exp-title">The interaction</div>
    <p>Try $B = 1$, $\mu = 0.10$, $\lambda = 0.10$ for very low rank (1–2), then $B = 8$, $\mu = 0.02$, $\lambda = 0.01$ for higher rank. The badge next to the equation shows the decay factor $1 - 2\mu\lambda$, constrained to stay positive.</p>
  </div>
</div>

<hr class="section-rule">

<!-- ── Part I ── -->
<h2>Part I: Stochastic gradients are low rank</h2>

<h3>A local view of one layer</h3>

<p>Fix all parameters except one trainable matrix $W$. Locally around that layer, the network can be written as</p>

$$h(x) = g(Wf(x)),$$

<p>where $f(x)$ is the representation entering the layer and $g$ collects everything afterward. We train with the regularized loss</p>

$$L_S^\lambda(W) = \frac{1}{m}\sum_{i=1}^m \ell_i(h(x_i)) + \lambda \|W\|_F^2.$$

<p>Under mini-batch SGD with weight decay, the update is</p>

$$W_{t+1} = (1 - 2\mu\lambda)W_t - \mu G_t,$$

<p>where $G_t := \nabla_W L_{\tilde S_t}(W_t)$ is the mini-batch gradient. The previous matrix is shrunk by $1 - 2\mu\lambda$, and a fresh stochastic gradient is added. So the key question is: <strong>what kind of matrix is $G_t$?</strong></p>

<h3>One example gives a rank-1 gradient</h3>

<p>For a single training example $x$, the chain rule gives</p>

$$\nabla_W \ell(h(x)) = \delta(x) f(x)^\top,$$

<p>where $\delta(x) := J_g(Wf(x))^\top \nabla_h \ell(h(x))$. This is an outer product of two vectors, so</p>

$$\operatorname{rank}\big(\nabla_W \ell(h(x))\big) \le 1.$$

<p>A single-example gradient is not an arbitrary full-rank matrix. It has the simplest possible form: one left direction times one right direction.</p>

<h3>A mini-batch gives an update of rank at most $B$</h3>

<p>The mini-batch gradient is the average of $B$ rank-1 terms:</p>

$$G_t = \frac{1}{B}\sum_{i=1}^B \delta_i f_i^\top, \qquad \operatorname{rank}(G_t) \le \min(d_{\mathrm{out}}, d_{\mathrm{in}}, B).$$

<p>So every SGD step writes only a low-rank correction. Smaller batch sizes make this restriction stronger; larger batch sizes relax it.</p>

<p>But low-rank updates alone are not enough. If we accumulated them forever with no forgetting, their sum could become high rank. The second ingredient is weight decay.</p>

<hr class="section-rule">

<!-- ── Part II ── -->
<h2>Part II: Weight decay limits memory</h2>

<p>Unrolling the recursion $W_{t+1} = (1 - 2\mu\lambda)W_t - \mu G_t$ for $n$ steps gives the identity at the heart of the argument:</p>

$$W_T = \underbrace{(1 - 2\mu\lambda)^n W_{T-n}}_{\text{decayed past}} - \mu \underbrace{\sum_{j=1}^n (1 - 2\mu\lambda)^{j-1} G_{T-j}}_{\text{recent low-rank updates}}.$$

<p>The first term shrinks exponentially in $n$. The second is a weighted sum of recent mini-batch gradients, each of rank at most $B$. So after enough training, the current matrix is well approximated by a <strong>short moving memory of low-rank corrections</strong>. That is the mechanism:</p>

<ul>
  <li>SGD writes only a few directions per step,</li>
  <li>weight decay prevents too many old directions from remaining active,</li>
  <li>so the layer behaves like a sliding window of low-rank updates.</li>
</ul>

<h3>A simple effective-rank heuristic</h3>

<p>Choose $n$ so the old-memory term is negligible: $(1-2\mu\lambda)^n \approx e^{-2\mu\lambda n} \le \varepsilon$, giving $n \approx \frac{\log(1/\varepsilon)}{\mu\lambda}$. The recent term is a sum of $n$ gradients of rank at most $B$, so</p>

<div class="math-block">
$$\operatorname{rank}_\varepsilon(W_T) \lesssim \frac{B \log(1/\varepsilon)}{\mu\lambda}.$$
</div>

<p>This bound captures the right qualitative dependencies: smaller batch size, larger learning rate, or larger weight decay all shorten the effective memory and produce lower effective rank. These trends should be interpreted within a regime where training remains stable.</p>

<hr class="section-rule">

<!-- ── Part III ── -->
<h2>Part III: Shared operators</h2>

<p>The rank-1 statement changes when the same matrix $W$ is reused multiple times within a single example. This happens in convolutions (same kernel at many spatial locations), self-attention projections ($W_Q$, $W_K$, $W_V$ applied to many tokens), and any shared linear operator. In that case,</p>

$$h(x) = g(Wf_1(x), \dots, Wf_R(x)),$$

<p>and the chain rule gives</p>

$$\nabla_W \ell(h(x)) = \sum_{r=1}^R \delta_r(x) f_r(x)^\top, \qquad \operatorname{rank}\big(\nabla_W \ell(h(x))\big) \le R.$$

<p>For a mini-batch, $\operatorname{rank}(G_t) \le \min(d_{\mathrm{out}}, d_{\mathrm{in}}, BR)$. The rest of the argument is unchanged: weight decay still exponentially suppresses old updates, so the current matrix remains close to a weighted sum of recent low-rank gradients. The one-use setting $R = 1$ is simply the cleanest case.</p>

<h3>Why the local view is natural</h3>

<p>The representation $h(x) = g(Wf(x))$ is not an artificial simplification. It is the natural local view of any layer: fix all other parameters, isolate the place where $W$ acts, and absorb everything before it into $f$ and everything after it into $g$. For fully connected layers this is immediate. For residual blocks, the dependence on $W$ still enters through $Wf(x)$, so the outer-product structure of the gradient is preserved.</p>

<hr class="section-rule">

<!-- ── What this does and does not say ── -->
<h2>What this does and does not say</h2>

<p>This argument does <strong>not</strong> imply that every trained layer must be exactly low rank. It does not bypass the influence of architecture, normalization, or data geometry.</p>

<p>What it <em>does</em> give is a broad structural reason that low-rank behavior should often appear in practice. Low rank is not an accident, and it is not merely a pattern discovered afterward by compression — it is built into the model during training by the interaction of stochastic gradients and weight decay.</p>

<p>This also clarifies why <strong>post-training low-rank compression</strong> is so effective: in many cases, it is not inventing structure but extracting structure that the training dynamics had already encouraged.</p>

<hr class="section-rule">

<!-- ── Takeaway ── -->
<div class="takeaway">
  <h3>Takeaway</h3>
  <p style="margin-bottom: 1rem;">SGD with weight decay does more than optimize the loss. It quietly pushes layers toward low-rank structure. The mechanism operates in three parts:</p>
  <ol>
    <li><strong>Low-rank updates.</strong> Each stochastic gradient is low rank — rank 1 per example, rank $B$ per mini-batch, rank $BR$ for shared operators.</li>
    <li><strong>Finite memory.</strong> Weight decay exponentially forgets old updates, limiting the effective memory to roughly $1/(\mu\lambda)$ steps.</li>
    <li><strong>Low-rank layers.</strong> The current weight matrix is dominated by a short history of low-rank corrections, yielding an effective rank of roughly $B\log(1/\varepsilon)/(\mu\lambda)$.</li>
  </ol>
  <p style="margin-top: 1rem; margin-bottom: 0;">Low-rank structure in trained neural networks is not just an empirical curiosity. It is a natural consequence of how SGD with weight decay writes and forgets directions over time.</p>
</div>

</div><!-- /article-container -->
</article>

<footer class="site-footer">
  <div class="article-container">
    &copy; 2026 Tomer Galanti &middot; Texas A&M University
  </div>
</footer>

</body>
</html>
