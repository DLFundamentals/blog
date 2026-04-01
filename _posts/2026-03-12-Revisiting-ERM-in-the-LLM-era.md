<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.min.css">
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.min.js"></script>
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/contrib/auto-render.min.js"></script>
<link href="https://fonts.googleapis.com/css2?family=Newsreader:ital,wght@0,300;0,400;0,500;0,600;1,400&family=DM+Sans:wght@400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
:root {
  --ink: #1a1714;
  --ink-soft: #4a4640;
  --ink-muted: #8a8680;
  --cream: #faf8f4;
  --paper: #ffffff;
  --rule: #e0dcd6;
  --accent: #c45028;
  --accent-soft: #f0e6df;
  --teal: #1a7a5c;
  --teal-soft: #e4f2ec;
  --purple: #5a4ab8;
  --purple-soft: #eeedfe;
  --amber: #a06810;
  --amber-soft: #faf0da;
  --coral: #d85a30;
  --coral-soft: #faece7;
  --serif: 'Newsreader', Georgia, serif;
  --sans: 'DM Sans', -apple-system, sans-serif;
  --mono: 'JetBrains Mono', monospace;
}

* { margin: 0; padding: 0; box-sizing: border-box; }

body {
  font-family: var(--serif);
  background: var(--cream);
  color: var(--ink);
  line-height: 1.72;
  -webkit-font-smoothing: antialiased;
  width: 100%;
  max-width: 100%;
  overflow-x: clip;
}

.hero {
  max-width: 900px;
  margin: 0 auto;
  padding: 3.4rem 2rem 2.35rem;
  border-bottom: 1px solid var(--rule);
}

.hero-eyebrow {
  font-family: var(--sans);
  font-size: 12px;
  font-weight: 600;
  letter-spacing: 2px;
  text-transform: uppercase;
  color: var(--accent);
  margin-bottom: .95rem;
}

.hero h1 {
  font-family: var(--serif);
  font-size: clamp(2rem, 5vw, 3rem);
  font-weight: 500;
  line-height: 1.2;
  color: var(--ink);
  margin: 0 0 1.2rem 0;
  max-width: 700px;
}

.hero-subtitle {
  font-size: 1.15rem;
  color: var(--ink-soft);
  max-width: 620px;
  line-height: 1.65;
}

.hero-meta {
  margin-top: 1.5rem;
  font-family: var(--sans);
  font-size: 13px;
  color: var(--ink-muted);
  display: flex;
  gap: 1.5rem;
  flex-wrap: wrap;
  align-items: center;
}

.paper-badge {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  background: var(--purple-soft);
  color: var(--purple);
  padding: 4px 12px;
  border-radius: 20px;
  font-weight: 500;
  font-size: 12px;
}

article {
  max-width: 680px;
  margin: 0 auto;
  padding: 1.7rem 2rem 1.35rem;
}

article p { font-size: 1.05rem; margin: 0 0 1.2rem 0; }

article h2 {
  font-family: var(--serif);
  font-size: 1.6rem;
  font-weight: 500;
  margin: 2.2rem 0 .95rem;
  color: var(--ink);
  padding-top: 1.45rem;
  border-top: 1px solid var(--rule);
}

article h3 {
  font-family: var(--sans);
  font-size: 1rem;
  font-weight: 600;
  margin: 1.45rem 0 .6rem;
  color: var(--ink-soft);
  letter-spacing: 0.3px;
}

.key-insight {
  border-left: 3px solid var(--accent);
  padding: 1rem 1.2rem;
  margin: 1.2rem 0;
  background: var(--accent-soft);
  border-radius: 0 8px 8px 0;
  font-style: italic;
  color: var(--ink-soft);
  font-size: 1.05rem;
  line-height: 1.65;
}

.math-display {
  text-align: center;
  padding: 1.1rem .85rem;
  margin: 1.1rem 0;
  background: var(--paper);
  border: 1px solid var(--rule);
  border-radius: 8px;
  overflow-x: auto;
}

.math-display .katex { font-size: 1.1em; }

.eq-highlight {
  background: var(--amber-soft);
  border: 1px solid #e8d5b0;
  border-radius: 8px;
  padding: 1.05rem 1.15rem;
  margin: 1.1rem 0;
  text-align: center;
  overflow-x: auto;
}

.eq-highlight .katex { font-size: 1.15em; }

code {
  font-family: var(--mono);
  font-size: 0.88em;
  background: #f0ede8;
  padding: 2px 6px;
  border-radius: 4px;
  color: var(--accent);
  white-space: nowrap;
}

.paper-note {
  font-family: var(--sans);
  font-size: 12px;
  color: var(--purple);
  background: var(--purple-soft);
  padding: 10px 14px 10px 32px;
  border-radius: 6px;
  margin: 1rem 0 1.5rem;
  line-height: 1.6;
  position: relative;
}

.paper-note::before {
  content: "◆";
  position: absolute;
  left: 14px;
  top: 10px;
  font-size: 10px;
}

.paper-note a { color: var(--purple); font-weight: 500; }
.paper-note code { background: rgba(90,74,184,0.1); color: #3c3489; white-space: normal; }

/* Mechanism cards */
.mechanism-grid {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 10px;
  margin: 1.15rem 0;
}

@media (max-width: 600px) { .mechanism-grid { grid-template-columns: 1fr; } }

.mechanism-card {
  background: var(--paper);
  border: 1px solid var(--rule);
  border-radius: 8px;
  padding: 1rem;
  border-top: 3px solid var(--rule);
}

.mechanism-card .step-num {
  font-family: var(--sans);
  font-size: 11px;
  font-weight: 600;
  letter-spacing: 1px;
  text-transform: uppercase;
  margin-bottom: 6px;
}

.mechanism-card h4 {
  font-family: var(--sans);
  font-size: 14px;
  font-weight: 600;
  margin-bottom: 6px;
  color: var(--ink);
}

.mechanism-card p {
  font-size: 13px;
  color: var(--ink-soft);
  line-height: 1.55;
  margin: 0;
}

.compare-grid {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 10px;
  margin: 1.15rem 0;
}

@media (max-width: 600px) { .compare-grid { grid-template-columns: 1fr; } }

.compare-card {
  background: var(--paper);
  border: 1px solid var(--rule);
  border-radius: 8px;
  padding: .95rem 1.05rem;
}

.compare-card h4 {
  font-family: var(--sans);
  font-size: 13px;
  font-weight: 600;
  margin-bottom: 6px;
}

.compare-card p {
  font-size: 13px;
  color: var(--ink-soft);
  line-height: 1.55;
  margin: 0;
}

/* Results table */
.results-table-wrap {
  margin: 1.2rem 0;
  overflow-x: auto;
  border-radius: 10px;
  border: 1px solid var(--rule);
  background: var(--paper);
}

.results-table {
  width: 100%;
  border-collapse: collapse;
  font-family: var(--sans);
  font-size: 13px;
  background: var(--paper);
}

.results-table th {
  text-align: left;
  font-weight: 600;
  padding: 10px 12px;
  border-bottom: 2px solid var(--rule);
  color: var(--ink-soft);
  font-size: 11px;
  letter-spacing: 0.5px;
  text-transform: uppercase;
  white-space: nowrap;
  position: sticky;
  top: 0;
  background: var(--paper);
}

.results-table td {
  padding: 6px 11px;
  border-bottom: 1px solid var(--rule);
  vertical-align: middle;
  white-space: nowrap;
}

.results-table tr:last-child td { border-bottom: none; }

.results-table td:first-child {
  font-weight: 500;
  color: var(--ink);
}

.results-table .best {
  font-weight: 600;
  color: var(--teal);
}

.results-table .near-chance {
  color: var(--ink-muted);
}

.results-table .col-llmpv {
  background: var(--teal-soft);
}

.figcaption {
  font-family: var(--sans);
  font-size: 13px;
  color: var(--ink-muted);
  line-height: 1.55;
  margin-top: 8px;
}

/* Pipeline viz */
.pipeline {
  background: var(--paper);
  border: 1px solid var(--rule);
  border-radius: 12px;
  padding: 1.25rem;
  margin: 1.55rem 0;
}

.pipeline-title {
  font-family: var(--sans);
  font-size: 14px;
  font-weight: 600;
  color: var(--ink);
  margin-bottom: 4px;
}

.pipeline-subtitle {
  font-family: var(--sans);
  font-size: 13px;
  color: var(--ink-muted);
  margin-bottom: 1.25rem;
}

.pipeline-steps {
  display: flex;
  gap: 0;
  align-items: stretch;
  position: relative;
}

@media (max-width: 600px) {
  .pipeline-steps { flex-direction: column; }
  .pipe-arrow { transform: rotate(90deg); align-self: center; }
}

.pipe-step {
  flex: 1;
  border-radius: 8px;
  padding: .9rem;
  text-align: center;
  cursor: pointer;
  transition: transform 0.15s, box-shadow 0.15s;
  position: relative;
  min-width: 0;
}

.pipe-step:hover { transform: translateY(-2px); box-shadow: 0 4px 12px rgba(0,0,0,0.06); }

.pipe-step.active { box-shadow: 0 4px 16px rgba(0,0,0,0.1); transform: translateY(-3px); }

.pipe-step-num {
  font-family: var(--sans);
  font-size: 11px;
  font-weight: 600;
  letter-spacing: 1px;
  text-transform: uppercase;
  margin-bottom: 6px;
}

.pipe-step-title {
  font-family: var(--sans);
  font-size: 14px;
  font-weight: 600;
  margin-bottom: 4px;
}

.pipe-step-desc {
  font-family: var(--sans);
  font-size: 12px;
  line-height: 1.5;
}

.pipe-arrow {
  display: flex;
  align-items: center;
  font-size: 20px;
  color: var(--ink-muted);
  padding: 0 4px;
  flex-shrink: 0;
}

.pipe-detail {
  margin-top: .9rem;
  padding: .95rem;
  background: var(--cream);
  border-radius: 8px;
  font-family: var(--sans);
  font-size: 13px;
  color: var(--ink-soft);
  line-height: 1.6;
  min-height: 60px;
  transition: opacity 0.2s;
}

.pipe-detail code {
  font-size: 12px;
  background: #eae7e1;
}

/* Tension table */
.tension-table {
  width: 100%;
  border-collapse: collapse;
  font-family: var(--sans);
  font-size: 13px;
  margin: 1.2rem 0;
  background: var(--paper);
  border: 1px solid var(--rule);
  border-radius: 10px;
  overflow: hidden;
}

.tension-table th {
  padding: 10px 14px;
  border-bottom: 2px solid var(--rule);
  font-weight: 600;
  font-size: 12px;
  letter-spacing: 0.5px;
  text-transform: uppercase;
  color: var(--ink-muted);
  text-align: left;
}

.tension-table td {
  padding: 10px 14px;
  border-bottom: 1px solid var(--rule);
  vertical-align: middle;
}

.tension-table tr:last-child td { border-bottom: none; }

.tension-table td:first-child { font-weight: 500; color: var(--ink); }

/* Bar chart */
.bar-chart {
  margin: 1.25rem 0;
  background: var(--paper);
  border: 1px solid var(--rule);
  border-radius: 10px;
  padding: 1rem;
}

.bar-chart-title {
  font-family: var(--sans);
  font-size: 12px;
  font-weight: 600;
  color: var(--ink-muted);
  letter-spacing: 0.5px;
  text-transform: uppercase;
  margin-bottom: 12px;
}

.bar-row {
  display: flex;
  align-items: center;
  margin-bottom: 6px;
  gap: 8px;
}

.bar-label {
  font-family: var(--sans);
  font-size: 12px;
  color: var(--ink-soft);
  width: 100px;
  flex-shrink: 0;
  text-align: right;
}

.bar-track {
  flex: 1;
  height: 20px;
  background: #f0ede8;
  border-radius: 4px;
  overflow: hidden;
  position: relative;
}

.bar-fill {
  height: 100%;
  border-radius: 4px;
  transition: width 0.6s ease;
  display: flex;
  align-items: center;
  justify-content: flex-end;
  padding-right: 6px;
}

.bar-value {
  font-family: var(--mono);
  font-size: 10px;
  font-weight: 500;
  color: white;
}

.bar-value-outside {
  font-family: var(--mono);
  font-size: 10px;
  font-weight: 500;
  color: var(--ink-muted);
  margin-left: 6px;
  flex-shrink: 0;
}

/* Takeaway */
.takeaway {
  background: var(--ink);
  color: var(--cream);
  padding: 2rem 2.25rem;
  border-radius: 12px;
  margin: 2.2rem 0 1.5rem;
}

.takeaway h3 {
  font-family: var(--sans);
  font-size: 12px;
  font-weight: 600;
  letter-spacing: 2px;
  text-transform: uppercase;
  color: var(--accent);
  margin: 0 0 1rem;
}

.takeaway p {
  color: #d0cdc6;
  margin-bottom: .75rem;
  font-size: 1.02rem;
}

.takeaway p:last-child { margin-bottom: 0; }
.takeaway strong { color: var(--cream); }

.post-footer {
  max-width: 680px;
  margin: 0 auto;
  padding: 0 2rem 4rem;
  text-align: center;
}

.post-footer p { font-family: var(--sans); font-size: 13px; color: var(--ink-muted); }
.post-footer a { color: var(--accent); }

.fade-in {
  opacity: 0;
  transform: translateY(16px);
  transition: opacity 0.6s ease, transform 0.6s ease;
}

.fade-in.visible {
  opacity: 1;
  transform: translateY(0);
}

hr.section-rule {
  border: none;
  height: 1px;
  background: var(--rule);
  margin: 1.8rem 0;
}

/* Task filter tabs */
.filter-tabs {
  display: flex;
  gap: 6px;
  margin-bottom: 12px;
  flex-wrap: wrap;
}

.filter-tab {
  font-family: var(--sans);
  font-size: 12px;
  padding: 4px 12px;
  border-radius: 20px;
  border: 0.5px solid var(--rule);
  background: transparent;
  color: var(--ink-muted);
  cursor: pointer;
  transition: all 0.15s;
}

.filter-tab:hover { background: var(--paper); }
.filter-tab.active { background: var(--teal-soft); color: var(--teal); border-color: var(--teal); font-weight: 500; }

/* Trace simulator */
.trace-btn {
  font-family: var(--sans);
  font-size: 13px;
  font-weight: 500;
  padding: 5px 14px;
  border-radius: 6px;
  border: 0.5px solid var(--rule);
  background: transparent;
  color: var(--ink-soft);
  cursor: pointer;
  transition: all .15s;
}

.trace-btn:hover { background: var(--cream); }
.trace-btn.active { background: var(--accent); color: white; border-color: var(--accent); }

.trace-cand {
  background: var(--paper);
  border: 0.5px solid var(--rule);
  border-radius: 8px;
  padding: 10px 12px;
  transition: all .3s;
}

.trace-cand.best { border-color: var(--purple); border-width: 1.5px; }
.trace-cand.eliminated { opacity: .35; }

.trace-cand-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 6px;
}

.trace-cand-label {
  font-family: var(--sans);
  font-size: 12px;
  font-weight: 500;
  color: var(--ink-muted);
}

.trace-badge {
  font-family: var(--sans);
  font-size: 11px;
  padding: 2px 8px;
  border-radius: 10px;
  font-weight: 500;
}

.trace-badge-pass { background: var(--teal-soft); color: var(--teal); }
.trace-badge-fail { background: var(--coral-soft); color: var(--coral); }
.trace-badge-partial { background: var(--amber-soft); color: var(--amber); }
.trace-badge-best { background: var(--purple-soft); color: var(--purple); }

.trace-code {
  font-family: var(--mono);
  font-size: 12px;
  line-height: 1.55;
  color: var(--ink);
  white-space: pre-wrap;
  word-break: break-word;
}

.trace-footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: 8px;
  padding-top: 8px;
  border-top: 0.5px solid var(--rule);
}

.trace-score {
  font-family: var(--mono);
  font-size: 12px;
  color: var(--ink-muted);
}

.trace-bar-track {
  flex: 1;
  height: 4px;
  background: #f0ede8;
  border-radius: 2px;
  margin: 0 12px;
  max-width: 200px;
}

.trace-bar-fill {
  height: 100%;
  border-radius: 2px;
  transition: width .5s ease;
}

.explorer {
  background: var(--paper);
  border: 1px solid var(--rule);
  border-radius: 12px;
  padding: 1.25rem;
  margin: 1.55rem 0;
}

.explorer-title {
  font-family: var(--sans);
  font-size: 14px;
  font-weight: 600;
  color: var(--ink);
  margin-bottom: 4px;
}

.explorer-subtitle {
  font-family: var(--sans);
  font-size: 13px;
  color: var(--ink-muted);
  margin-bottom: 1rem;
}


.mechanism-grid > *,
.compare-grid > *,
.pipeline-steps > *,
.results-table-wrap,
.pipeline,
.explorer,
.bar-chart,
.key-insight,
.math-display,
.eq-highlight,
.tension-table {
  width: 100%;
  border-collapse: collapse;
  font-family: var(--sans);
  font-size: 13px;
  margin: 1.2rem 0;
  background: var(--paper);
  border: 1px solid var(--rule);
  border-radius: 10px;
  overflow: hidden;
}

select,
button,
input {
  max-width: 100%;
}

@media (max-width: 768px) {
  .hero {
  max-width: 900px;
  margin: 0 auto;
  padding: 3.4rem 2rem 2.35rem;
  border-bottom: 1px solid var(--rule);
}
  article {
  max-width: 680px;
  margin: 0 auto;
  padding: 1.7rem 2rem 1.35rem;
}
  .hero h1 {
  font-family: var(--serif);
  font-size: clamp(2rem, 5vw, 3rem);
  font-weight: 500;
  line-height: 1.2;
  color: var(--ink);
  margin: 0 0 1.2rem 0;
  max-width: 700px;
}
  .pipeline-steps { gap: 6px; }
}

@media (max-width: 700px) {
  .hero { padding: 3rem 1rem 2rem; }
  article { padding: 1.45rem 1rem 1rem; }
  .post-footer { padding: 0 1rem 3rem; }
}

@media (max-width: 480px) {
  .hero h1 { font-size: 1.7rem; }
  .hero-meta { gap: .6rem; }
  .takeaway { padding: 1.45rem 1.15rem; }
}

  .bar-label { width: 82px; }
  .pipe-step { padding: .8rem; }
  .explorer,
  .pipeline,
  .bar-chart,
  .takeaway {
  background: var(--ink);
  color: var(--cream);
  padding: 2rem 2.25rem;
  border-radius: 12px;
  margin: 2.2rem 0 1.5rem;
}
}
</style>

<!-- HERO -->
<div class="hero">
  <div class="hero-eyebrow">Learning Theory &middot; Program Synthesis &middot; LLMs</div>
  <h1>Revisiting ERM in the LLM Era</h1>
  <p class="hero-subtitle">How pretrained LLMs can serve as search priors for empirical risk minimization over programs, recovering exact algorithmic rules from just a handful of examples — while SGD-trained models remain at chance.</p>
  <div class="hero-meta">
    <span>By Tomer Galanti</span>
    <span>&middot;</span>
    <span>March 20, 2026</span>
    <span>&middot;</span>
    <span>14 min read</span>
    <span>&middot;</span>
    <span class="paper-badge">◆ Based on Singhal, Mishra, Malach, Galanti — arXiv 2025</span>
  </div>
</div>

<!-- ARTICLE -->
<article>

<h2 style="border-top:none; padding-top:0; margin-top:0;">Introduction</h2>

<p>Deep learning works extraordinarily well in vision, language, and audio. But outside these regimes there are many simple tasks that standard training methods still do not handle well: primality testing, parity, Boolean circuits, graph connectivity, and other rule-based problems. One can cast them as supervised learning tasks and train a large model on labeled examples. In practice, the model often fits the training data and still fails to recover the underlying rule.</p>

<p>A natural alternative is to use the fact that many such tasks admit short exact implementations — often just a few lines of Python. Instead of training a model to imitate the input-output map, we can search directly for a <strong>program</strong> that explains the data. This is empirical risk minimization (ERM) over a discrete class of programs, and classical learning theory tells us that such an approach can generalize from surprisingly little data.</p>

<p>The difficulty is computational. Exhaustive search over all Python programs is clearly infeasible. The number of candidates grows exponentially with program length, so even when the correct hypothesis is very short, brute-force ERM is usually not practical.</p>

<div class="key-insight">
Pretrained LLMs can serve as search priors for empirical risk minimization over short programs. This makes classical program-based ERM practically searchable while preserving its strong sample-efficiency advantages.
</div>

<p>The story has four parts:</p>

<div class="mechanism-grid fade-in">
  <div class="mechanism-card" style="border-top-color: var(--coral);">
    <div class="step-num" style="color: var(--coral);">Part I</div>
    <h4>SGD is the wrong search</h4>
    <p>SGD-trained networks fit the training data and still fail to recover algorithmic rules. The failure is fundamental on SQ-hard tasks, not a tuning issue.</p>
  </div>
  <div class="mechanism-card" style="border-top-color: var(--teal);">
    <div class="step-num" style="color: var(--teal);">Part II</div>
    <h4>Program ERM is sample-efficient</h4>
    <p>PAC-style guarantees scale with description length $L$, not input dimension $n$. A compact parity program generalizes from $O(k \log n)$ examples.</p>
  </div>
  <div class="mechanism-card" style="border-top-color: var(--amber);">
    <div class="step-num" style="color: var(--amber);">Part III</div>
    <h4>LLM-PV makes ERM feasible</h4>
    <p>A pretrained LLM replaces uniform search with a structured proposal distribution. Verification still comes from held-out data — the ERM principle is preserved.</p>
  </div>
  <div class="mechanism-card" style="border-top-color: var(--purple);">
    <div class="step-num" style="color: var(--purple);">Part IV</div>
    <h4>Exact rules from few examples</h4>
    <p>LLM-PV recovers perfect accuracy on 10 of 13 algorithmic tasks from only 200 examples, while all neural baselines remain near chance.</p>
  </div>
</div>

<div class="paper-note">
Based on: S. Singhal, P. Mishra, E. Malach, T. Galanti. <a href="https://arxiv.org/abs/2506.xxxxx">"LLM Priors for ERM over Programs"</a>, arXiv, 2025.
</div>

<h2>Part I: Deep learning can be the wrong search procedure</h2>

<h3>Where our usual intuition comes from</h3>

<p>Most of our intuitions about sample efficiency come from settings where deep learning is well matched to the structure of the problem. In images, language, and speech, expressive models trained with SGD often generalize reliably from finite data. Algorithmic tasks are different.</p>

<div class="compare-grid fade-in">
  <div class="compare-card" style="border-left: 3px solid var(--coral);">
    <h4 style="color: var(--coral);">Parity</h4>
    <p>Decide whether $\langle s, x \rangle \bmod 2 = 1$ for an unknown sparse vector $s$. A one-line program — but gradient methods cannot efficiently learn it.</p>
  </div>
  <div class="compare-card" style="border-left: 3px solid var(--coral);">
    <h4 style="color: var(--coral);">Primality</h4>
    <p>Decide whether a large integer is prime. A short algorithm exists (trial division, Miller-Rabin), but SGD has no efficient gradient signal toward it.</p>
  </div>
  <div class="compare-card" style="border-left: 3px solid var(--coral);">
    <h4 style="color: var(--coral);">Balanced parentheses</h4>
    <p>Decide whether a bracket string is a valid Dyck-2 word. A stack-based check — compact as code, opaque to gradient descent.</p>
  </div>
  <div class="compare-card" style="border-left: 3px solid var(--coral);">
    <h4 style="color: var(--coral);">Pattern matching</h4>
    <p>Determine whether a fixed motif appears in a binary string. A simple scan — but the target function has no smooth gradient landscape for SGD to follow.</p>
  </div>
</div>

<h3>The failure mode</h3>

<p>Across several 1B-scale language models, training on a few hundred labeled examples yields near-perfect <em>training</em> accuracy on tasks such as parity, Dyck-2, and cellular automata parity. <em>Test</em> accuracy, however, often remains near chance. This behavior persists even when the amount of training data is increased substantially — the same qualitative pattern appears across different backbones, broad hyperparameter sweeps, and strong fine-tuning or in-context learning baselines.</p>

<h3>Why SGD struggles</h3>

<p>The statistical query perspective gives a clean explanation. Gradient-based methods access the data distribution only through aggregate statistics, and for families such as sparse parity this creates an inherent bottleneck. For planted $k$-parity over $n$ variables, mini-batch coordinate SGD requires at least:</p>

<div class="eq-highlight">
$$q = \Omega\!\left(\frac{\sqrt{\binom{n}{k}}}{2^b}\right)$$
</div>

<p>fresh examples to achieve nontrivial population error. The target rule is simple as a program, but <strong>SGD is the wrong search procedure for this hypothesis class</strong>.</p>

<h2>Part II: ERM over short programs is statistically attractive</h2>

<h3>Think of the target as code</h3>

<p>Suppose the target rule can be expressed as a program of length $L$ over an alphabet $\Sigma$. The relevant hypothesis class is the set of valid programs of length at most $L$, with $|\mathcal{H}_L| \le |\Sigma|^L$. This immediately yields a classical PAC-style guarantee:</p>

<div class="eq-highlight">
$$\text{test error} \;\le\; \frac{L \log|\Sigma| + \log(2L^2/\delta)}{m}$$
</div>

<p>The sample complexity depends on <strong>description length</strong>, not on raw input dimension. A compact parity program can therefore generalize from surprisingly few examples.</p>

<h3>The central tension</h3>

<p>When learning $k$-parity functions, this yields a sharp distinction between statistical and computational efficiency:</p>

<table class="tension-table fade-in">
  <thead>
    <tr><th></th><th>SGD</th><th>Length-first ERM</th></tr>
  </thead>
  <tbody>
    <tr>
      <td>Samples for low error</td>
      <td style="color: var(--coral);">$\Omega(n^{k/2})$</td>
      <td style="color: var(--teal);">$O(k \log n)$</td>
    </tr>
    <tr>
      <td>Per-sample compute</td>
      <td style="color: var(--teal);">$O(1)$</td>
      <td style="color: var(--coral);">$\Omega(n^{\Theta(k)})$</td>
    </tr>
  </tbody>
</table>

<p>SGD is computationally cheap but statistically wasteful on these tasks. Program ERM is statistically efficient but computationally intractable. So the real question is: can one keep ERM's statistical advantages while replacing uniform search with something more structured?</p>

<h2>Part III: LLM-PV makes ERM searchable</h2>

<h3>From uniform search to proposal priors</h3>

<p>The real bottleneck in program ERM is not verification — given a candidate program, checking whether it fits the data is easy. The difficult part is <strong>proposing promising candidates</strong> in the first place. Uniform search over programs of length $L$ assigns probability roughly $|\Sigma|^{-L}$ to any fixed target. A pretrained LLM changes this proposal distribution: conditioned on labeled examples, it places probability mass on short, structured, plausible rules suggested by the data.</p>

<h3>The LLM-PV pipeline</h3>

<p>LLM-PV — propose-and-verify — is simple. Click each stage to see details:</p>

<div class="pipeline fade-in" id="pipeline">
  <div class="pipeline-title">LLM-PV: propose-and-verify</div>
  <div class="pipeline-subtitle">The LLM proposes, the data verifies, the selection rule remains ERM</div>

  <div class="pipeline-steps">
    <div class="pipe-step" style="background: var(--accent-soft);" onclick="showPipe(0)" id="ps0">
      <div class="pipe-step-num" style="color: var(--accent);">Step 1</div>
      <div class="pipe-step-title" style="color: var(--accent);">Prompt</div>
      <div class="pipe-step-desc" style="color: var(--ink-soft);">Format examples as input-output pairs</div>
    </div>
    <div class="pipe-arrow">→</div>
    <div class="pipe-step" style="background: var(--purple-soft);" onclick="showPipe(1)" id="ps1">
      <div class="pipe-step-num" style="color: var(--purple);">Step 2</div>
      <div class="pipe-step-title" style="color: var(--purple);">Sample</div>
      <div class="pipe-step-desc" style="color: var(--ink-soft);">Draw $k$ candidate programs from LLM</div>
    </div>
    <div class="pipe-arrow">→</div>
    <div class="pipe-step" style="background: var(--amber-soft);" onclick="showPipe(2)" id="ps2">
      <div class="pipe-step-num" style="color: var(--amber);">Step 3</div>
      <div class="pipe-step-title" style="color: var(--amber);">Execute</div>
      <div class="pipe-step-desc" style="color: var(--ink-soft);">Compile and run in sandbox</div>
    </div>
    <div class="pipe-arrow">→</div>
    <div class="pipe-step" style="background: var(--teal-soft);" onclick="showPipe(3)" id="ps3">
      <div class="pipe-step-num" style="color: var(--teal);">Step 4</div>
      <div class="pipe-step-title" style="color: var(--teal);">Select</div>
      <div class="pipe-step-desc" style="color: var(--ink-soft);">Pick lowest validation error</div>
    </div>
  </div>

  <div class="pipe-detail" id="pipe-detail">
    <strong>Step 1 — Prompt construction.</strong> The training examples $S_{\text{tr}}$ are formatted as input-output pairs and placed into a prompt that asks the LLM to write a Python function implementing the underlying rule. No gradient updates are used.
  </div>
</div>

<h3>The formal guarantee</h3>

<p>The guarantee cleanly separates the statistical role of validation from the search role of the LLM. Let $p_\epsilon(S_{\text{tr}})$ denote the probability that a fresh LLM proposal has population error at most $\epsilon$. Then after $k$ trials:</p>

<div class="eq-highlight">
$$\text{err}_D(h^\star) \;\le\; \epsilon \;+\; 2\sqrt{\frac{\log(4k/\delta)}{2m_{\text{val}}}}$$
</div>

<p>The LLM enters only through $p_\epsilon$ — the probability that it proposes a good program. It does not need to be trusted as the final predictor. It only needs to assign enough mass to good hypotheses so that one appears within a manageable number of trials. The effective search size becomes roughly $1/p_\epsilon(S_{\text{tr}})$ instead of $|\Sigma|^L$.</p>

<h3>Inside the search: watching candidates evolve</h3>

<p>What does the LLM-PV search look like from the inside? The reasoning trace reveals how candidate programs evolve across sampling rounds — from naive heuristics toward correct algorithms. Select a task and step through the rounds:</p>

<div class="explorer fade-in" id="trace-sim">
  <div style="display:flex;justify-content:space-between;align-items:flex-start;flex-wrap:wrap;gap:8px;margin-bottom:16px">
    <div>
      <div class="explorer-title" style="margin:0">Reasoning trace simulator</div>
      <div class="explorer-subtitle" style="margin:0">Candidate programs sharpen from heuristics to correct solutions</div>
    </div>
    <div style="display:flex;flex-direction:column;gap:6px;align-items:flex-end">
      <div style="display:flex;gap:6px;align-items:center">
        <span style="font-family:var(--sans);font-size:12px;color:var(--ink-muted)">Task:</span>
        <select id="trace-task" onchange="traceReset()" style="font-family:var(--sans);font-size:13px;padding:4px 8px;border-radius:6px;border:0.5px solid var(--rule);background:transparent;color:var(--ink);cursor:pointer">
          <option value="prime">IsPrime</option>
          <option value="parity">Parity</option>
          <option value="palindrome">IsPalindrome</option>
          <option value="dyck">Dyck-2</option>
        </select>
      </div>
      <div style="display:flex;gap:6px;align-items:center">
        <button class="trace-btn" id="trace-play-btn" onclick="traceTogglePlay()">Play</button>
        <button class="trace-btn" onclick="traceStep()">Next round</button>
        <button class="trace-btn" onclick="traceReset()">Reset</button>
        <span id="trace-round-label" style="font-family:var(--mono);font-size:13px;color:var(--ink-muted);min-width:80px;text-align:right">Round 0 / 2</span>
      </div>
    </div>
  </div>

  <div id="trace-candidates" style="display:flex;flex-direction:column;gap:8px;margin-bottom:12px">
    <div style="text-align:center;padding:2rem;color:var(--ink-muted);font-family:var(--sans);font-size:13px">Press <strong>Play</strong> or <strong>Next round</strong> to begin</div>
  </div>

  <div style="background:var(--cream);border-radius:8px;padding:12px 14px">
    <div style="font-family:var(--sans);font-size:12px;font-weight:600;color:var(--ink-muted);letter-spacing:.3px;text-transform:uppercase;margin-bottom:8px">Best validation accuracy over rounds</div>
    <div id="trace-evo"></div>
  </div>

  <div id="trace-insight" style="display:none;margin-top:12px;font-family:var(--sans);font-size:13px;line-height:1.55;padding:10px 14px;background:var(--purple-soft);border-radius:8px;color:var(--purple)"></div>
</div>

<div class="figcaption" style="margin-top:-0.5rem;margin-bottom:2rem">
  <strong>Figure 2.</strong> Simulated reasoning trace for LLM-PV. On IsPrime, the LLM's proposals evolve from "check if odd" (58%) to trial division with √n bound (100%) in just two rounds. On parity, the correct solution appears in round 1. The key insight: the LLM does not need to be perfect — it only needs to assign enough mass to the right program for ERM verification to find it.
</div>

<h2>Part IV: Results</h2>

<h3>Recovering exact rules from a handful of examples</h3>

<p>Across 13 algorithmic tasks at input length $n = 100$, LLM-PV recovers exact or near-exact rules from only 200 labeled examples. The pattern is striking — and informative about when the method works and when it does not:</p>

<div class="bar-chart fade-in" id="results-chart">
  <div class="bar-chart-title">Test accuracy (%) — 200 training examples, $n = 100$</div>
  <div class="filter-tabs">
    <button class="filter-tab active" onclick="filterBars('all', this)">All tasks</button>
    <button class="filter-tab" onclick="filterBars('perfect', this)">LLM-PV perfect</button>
    <button class="filter-tab" onclick="filterBars('hard', this)">Challenging</button>
  </div>
  <div id="bars-container"></div>
</div>

<div class="figcaption" style="margin-top: -0.5rem; margin-bottom: 1.5rem;">
  <strong>Figure 1.</strong> LLM-PV achieves perfect accuracy on 10 of 13 tasks. On SHA-256 parity — intentionally pseudorandom with no exploitable short structure — it fails, confirming the method's dependency on compressible hypotheses.
</div>

<p>The full comparison with baselines:</p>

<div class="results-table-wrap fade-in">
  <table class="results-table">
    <thead>
      <tr><th>Task</th><th>XGBoost</th><th>SGD (1B)</th><th>Fine-tune</th><th>ICL (30B)</th><th>TabPFN</th><th class="col-llmpv">LLM-PV</th></tr>
    </thead>
    <tbody>
      <tr><td>Full parity</td><td class="near-chance">49.9</td><td class="near-chance">49.3</td><td class="near-chance">50.4</td><td class="near-chance">53.0</td><td class="near-chance">50.1</td><td class="col-llmpv best">100</td></tr>
      <tr><td>First-half parity</td><td class="near-chance">50.0</td><td class="near-chance">50.6</td><td class="near-chance">51.3</td><td class="near-chance">54.0</td><td class="near-chance">50.5</td><td class="col-llmpv best">100</td></tr>
      <tr><td>Pattern 1</td><td class="near-chance">50.6</td><td class="near-chance">51.5</td><td>61.5</td><td class="near-chance">56.0</td><td class="near-chance">49.2</td><td class="col-llmpv best">100</td></tr>
      <tr><td>Pattern 2</td><td class="near-chance">52.3</td><td class="near-chance">53.6</td><td>57.6</td><td class="near-chance">51.0</td><td class="near-chance">51.2</td><td class="col-llmpv best">100</td></tr>
      <tr><td>3-parity</td><td class="near-chance">49.9</td><td class="near-chance">49.7</td><td class="near-chance">51.0</td><td class="near-chance">50.0</td><td class="near-chance">49.3</td><td class="col-llmpv best">100</td></tr>
      <tr><td>10-parity</td><td class="near-chance">49.3</td><td class="near-chance">50.3</td><td class="near-chance">50.5</td><td class="near-chance">50.0</td><td class="near-chance">50.5</td><td class="col-llmpv best">100</td></tr>
      <tr><td>IsPalindrome</td><td>83.6</td><td class="near-chance">49.2</td><td class="near-chance">49.6</td><td class="near-chance">47.0</td><td class="near-chance">49.4</td><td class="col-llmpv best">100</td></tr>
      <tr><td>Dyck-2</td><td class="near-chance">49.7</td><td class="near-chance">51.4</td><td class="near-chance">52.7</td><td class="near-chance">48.0</td><td class="near-chance">50.5</td><td class="col-llmpv best">100</td></tr>
      <tr><td>CA parity</td><td class="near-chance">50.4</td><td class="near-chance">49.4</td><td class="near-chance">50.7</td><td class="near-chance">49.0</td><td class="near-chance">48.0</td><td class="col-llmpv best">100</td></tr>
      <tr><td>IsPrime</td><td>61.8</td><td>58.8</td><td>57.2</td><td class="near-chance">50.0</td><td>57.1</td><td class="col-llmpv best">100</td></tr>
      <tr><td>IsPrime+47</td><td>59.3</td><td class="near-chance">53.6</td><td>58.7</td><td>58.0</td><td>65.4</td><td class="col-llmpv best">80.6</td></tr>
      <tr><td>CycleCount</td><td class="near-chance">51.1</td><td class="near-chance">53.5</td><td>65.7</td><td class="near-chance">46.0</td><td class="near-chance">51.3</td><td class="col-llmpv best">96.9</td></tr>
      <tr><td>SHA-256</td><td class="near-chance">50.3</td><td class="near-chance">49.8</td><td class="near-chance">50.8</td><td class="near-chance best">54.0</td><td class="near-chance">50.6</td><td class="col-llmpv near-chance">50.1</td></tr>
    </tbody>
  </table>
</div>

<h3>More data does not rescue SGD</h3>

<p>A natural objection is that neural baselines may simply need more examples. But even with up to 100,000 training examples, SGD-trained models can remain near chance on parity-style tasks while fitting the training data perfectly. These tasks are not difficult because they require huge datasets — they are difficult because the search procedure is poorly matched to the hypothesis class.</p>

<h3>Length generalization emerges naturally</h3>

<p>A particularly striking property of LLM-PV is that it often synthesizes <strong>dimension-invariant programs</strong>. When trained on short inputs ($n = 10$) and tested on much longer ones ($n = 100$), it can maintain perfect accuracy. This follows naturally from representing the hypothesis as code rather than as a fixed-dimensional parametric map — a loop, recursion, or invariant-checking procedure extends cleanly beyond the training input size.</p>

<div class="compare-grid fade-in">
  <div class="compare-card" style="border-left: 3px solid var(--teal);">
    <h4 style="color: var(--teal);">Auditable output</h4>
    <p>The output is executable code and the search trace is logged. The learned hypothesis can be read, tested, modified, and verified directly — a major conceptual difference from opaque neural predictors.</p>
  </div>
  <div class="compare-card" style="border-left: 3px solid var(--purple);">
    <h4 style="color: var(--purple);">Beyond algorithmic tasks</h4>
    <p>On standard tabular datasets with only 100 training samples, LLM-PV is competitive with XGBoost, Random Forest, and TabPFN — the propose-and-verify view extends beyond exact program recovery.</p>
  </div>
</div>

<h2>The right mental model</h2>

<p>The most useful way to view this method is not as "LLMs solve program synthesis," and not as a replacement for standard deep learning on perception tasks. The picture is narrower and cleaner:</p>

<p>Classical ERM over programs is <strong>statistically attractive but computationally inaccessible</strong> because uniform search is too expensive. A pretrained LLM changes the proposal distribution. It makes some short, structured hypotheses much easier to find. Verification and final selection still come from the data.</p>

<p>So the role of the LLM is not to replace ERM, but to <strong>make a previously impractical ERM procedure searchable</strong>.</p>

<p>This perspective also explains the limitations. If the target does not admit a short exploitable program, or if the LLM assigns negligible mass to useful candidates, the method will fail. The SHA-256 result is an example of exactly this regime — there is no short compressible structure for the proposal prior to exploit.</p>

<h2>What this does and does not say</h2>

<p>This argument does <strong>not</strong> say that LLM-PV replaces deep learning on standard vision, language, or audio tasks. In those domains, the usual pipeline remains extremely effective.</p>

<p>What it <em>does</em> show is that classical ERM over programs becomes practically relevant again when a pretrained LLM provides a strong search prior. The LLM does not replace verification, and it does not change the learning objective. It changes only the proposal mechanism.</p>

<div class="compare-grid fade-in">
  <div class="compare-card">
    <h4 style="color: var(--accent);">The LLM proposes</h4>
    <p>Conditioned on examples, it generates candidate programs from a structured distribution over code — vastly more efficient than uniform enumeration.</p>
  </div>
  <div class="compare-card">
    <h4 style="color: var(--teal);">The data verifies</h4>
    <p>Held-out validation selects the best candidate. The LLM is not trusted as the final predictor — it is a search engine, and ERM is the selection rule.</p>
  </div>
</div>

<div class="takeaway">
  <h3>Takeaway</h3>
  <p>Pretrained LLMs can make program-based ERM practical by replacing brute-force search with guided search. The mechanism has four parts:</p>
  <p><strong>Short programs generalize.</strong> If the target has a length-$L$ description, ERM needs only $O(L \log|\Sigma|)$ samples.</p>
  <p><strong>SGD can still fail badly.</strong> On SQ-hard families such as parity, gradient-based learners may require exponentially many samples even when the target is simple as code.</p>
  <p><strong>Brute-force ERM is computationally intractable.</strong> Uniform search over programs scales like $|\Sigma|^L$.</p>
  <p><strong>LLM-PV changes the search distribution.</strong> A pretrained LLM proposes plausible candidate programs, and held-out verification selects the best one — preserving the ERM principle while making the search feasible.</p>
  <p>The resulting paradigm recovers exact algorithmic rules from a handful of examples, generalizes beyond the training distribution, and produces executable hypotheses that can be inspected and verified directly.</p>
</div>

</article>

<div class="post-footer">
  <p>Originally published on <a href="https://dlfundamentals.github.io/blog/">Theory/Simplified</a> &middot; Based on <a href="https://arxiv.org/abs/2506.xxxxx">Singhal, Mishra, Malach, Galanti — arXiv 2025</a></p>
</div>

<script>
// KaTeX auto-render
var katexCheck = setInterval(function() {
  if (typeof renderMathInElement !== 'undefined') {
    clearInterval(katexCheck);
    renderMathInElement(document.body, {
      delimiters: [
        {left: '$$', right: '$$', display: true},
        {left: '$', right: '$', display: false}
      ],
      throwOnError: false
    });
  }
}, 100);

// Pipeline interaction
var pipeDetails = [
  '<strong>Step 1 — Prompt construction.</strong> The training examples $S_{\\text{tr}}$ are formatted as input-output pairs and placed into a prompt asking the LLM to write a Python function implementing the underlying rule. No gradient updates, no fine-tuning — just prompting.',
  '<strong>Step 2 — Sampling.</strong> The LLM generates $k$ candidate programs (typically $k = 64$ to $256$). Each is a complete, executable Python function. The LLM acts purely as a proposal distribution — it does not optimize the learning objective.',
  '<strong>Step 3 — Sandbox execution.</strong> Each candidate program is compiled and executed against both training and validation examples in an isolated sandbox. Programs that crash, time out, or produce malformed output are discarded automatically.',
  '<strong>Step 4 — ERM selection.</strong> The program with the lowest error on held-out validation data $S_{\\text{val}}$ is selected. This is classical empirical risk minimization — the LLM proposes, the data decides.'
];

function showPipe(i) {
  document.querySelectorAll('.pipe-step').forEach(function(el) { el.classList.remove('active'); });
  document.getElementById('ps' + i).classList.add('active');
  var detail = document.getElementById('pipe-detail');
  detail.innerHTML = pipeDetails[i];
  if (typeof renderMathInElement !== 'undefined') {
    renderMathInElement(detail, {
      delimiters: [{left: '$', right: '$', display: false}],
      throwOnError: false
    });
  }
}

// Bar chart
var tasks = [
  { name: 'Full parity', llmpv: 100, best_base: 53.0, cat: 'perfect' },
  { name: 'First-half parity', llmpv: 100, best_base: 54.0, cat: 'perfect' },
  { name: 'Pattern 1', llmpv: 100, best_base: 61.5, cat: 'perfect' },
  { name: 'Pattern 2', llmpv: 100, best_base: 57.6, cat: 'perfect' },
  { name: '3-parity', llmpv: 100, best_base: 51.0, cat: 'perfect' },
  { name: '10-parity', llmpv: 100, best_base: 50.5, cat: 'perfect' },
  { name: 'IsPalindrome', llmpv: 100, best_base: 83.6, cat: 'perfect' },
  { name: 'Dyck-2', llmpv: 100, best_base: 52.7, cat: 'perfect' },
  { name: 'CA parity', llmpv: 100, best_base: 50.7, cat: 'perfect' },
  { name: 'IsPrime', llmpv: 100, best_base: 61.8, cat: 'perfect' },
  { name: 'IsPrime+47', llmpv: 80.6, best_base: 65.4, cat: 'hard' },
  { name: 'CycleCount', llmpv: 96.9, best_base: 65.7, cat: 'hard' },
  { name: 'SHA-256', llmpv: 50.1, best_base: 54.0, cat: 'hard' }
];

var currentFilter = 'all';

function renderBars(filter) {
  currentFilter = filter;
  var container = document.getElementById('bars-container');
  container.innerHTML = '';
  var filtered = filter === 'all' ? tasks : tasks.filter(function(t) { return t.cat === filter; });

  filtered.forEach(function(task) {
    // LLM-PV bar
    var row1 = document.createElement('div');
    row1.className = 'bar-row';
    row1.innerHTML = '<div class="bar-label">' + task.name + '</div>' +
      '<div class="bar-track"><div class="bar-fill" style="width:' + task.llmpv + '%; background: var(--teal);">' +
      (task.llmpv > 15 ? '<span class="bar-value">' + task.llmpv + '</span>' : '') +
      '</div></div>' +
      (task.llmpv <= 15 ? '<span class="bar-value-outside">' + task.llmpv + '</span>' : '');

    // Best baseline bar
    var row2 = document.createElement('div');
    row2.className = 'bar-row';
    row2.style.marginBottom = '14px';
    row2.innerHTML = '<div class="bar-label" style="font-size:11px; color: var(--ink-muted);">best baseline</div>' +
      '<div class="bar-track"><div class="bar-fill" style="width:' + task.best_base + '%; background: var(--ink-muted); opacity: 0.5;">' +
      (task.best_base > 15 ? '<span class="bar-value">' + task.best_base + '</span>' : '') +
      '</div></div>' +
      (task.best_base <= 15 ? '<span class="bar-value-outside">' + task.best_base + '</span>' : '');

    container.appendChild(row1);
    container.appendChild(row2);
  });
}

function filterBars(filter, el) {
  document.querySelectorAll('.filter-tab').forEach(function(t) { t.classList.remove('active'); });
  if (el) el.classList.add('active');
  renderBars(filter);
}

renderBars('all');

// Fade-in observer
var observer = new IntersectionObserver(function(entries) {
  entries.forEach(function(entry) {
    if (entry.isIntersecting) entry.target.classList.add('visible');
  });
}, { threshold: 0.15 });
document.querySelectorAll('.fade-in').forEach(function(el) { observer.observe(el); });

// ===== TRACE SIMULATOR =====
var traceTasks = {
  prime: {
    name: 'IsPrime',
    rounds: [
      {
        candidates: [
          {code:'def predict(x):\n  return x % 2 != 0', score:58, label:'Check if odd', status:'partial'},
          {code:'def predict(x):\n  return len(str(x)) > 1', score:52, label:'Digit count heuristic', status:'fail'},
          {code:'def predict(x):\n  s = sum(int(d) for d in str(x))\n  return s % 3 != 0', score:55, label:'Digit sum rule', status:'partial'},
          {code:'def predict(x):\n  return x > 1 and x % 2 != 0\\\n    and x % 3 != 0', score:72, label:'Check 2 and 3', status:'partial'}
        ],
        best: 3, insight: 'Round 1: The LLM proposes simple heuristics. Checking divisibility by 2 and 3 is the best so far — but it wrongly classifies composites like 25 and 35 as prime.'
      },
      {
        candidates: [
          {code:'def predict(x):\n  if x < 2: return False\n  for d in [2,3,5,7,11,13]:\n    if x > d and x % d == 0:\n      return False\n  return True', score:88, label:'Check small primes', status:'partial'},
          {code:'def predict(x):\n  return x in [2,3,5,7,11,13,17,\\\n    19,23,29,31,37,41,43,47]', score:61, label:'Hardcoded list', status:'fail'},
          {code:'def predict(x):\n  if x < 2: return False\n  for i in range(2, min(x, 20)):\n    if x % i == 0: return False\n  return True', score:91, label:'Trial division (cap 20)', status:'partial'},
          {code:'def predict(x):\n  return x > 1 and all(\n    x % i != 0\n    for i in range(2, int(x**.5)+1))', score:100, label:'Trial division (√n)', status:'pass'}
        ],
        best: 3, insight: 'Round 2: Candidates sharpen. The LLM now proposes trial division — but with different bounds. Only the √n version is correct for all inputs. Validation selects it immediately.'
      }
    ]
  },
  parity: {
    name: 'Parity',
    rounds: [
      {
        candidates: [
          {code:'def predict(x):\n  return x[0] ^ x[1]', score:52, label:'XOR first two bits', status:'fail'},
          {code:'def predict(x):\n  return sum(x) % 2', score:100, label:'Sum mod 2', status:'pass'},
          {code:'def predict(x):\n  return x[-1]', score:51, label:'Last bit', status:'fail'},
          {code:'def predict(x):\n  c = 0\n  for b in x: c += b\n  return c > len(x)//2', score:54, label:'Majority vote', status:'fail'}
        ],
        best: 1, insight: 'Round 1: Full parity has a one-line solution: sum all bits mod 2. The LLM finds it on the first round — ERM verification confirms 100% accuracy immediately.'
      }
    ]
  },
  palindrome: {
    name: 'IsPalindrome',
    rounds: [
      {
        candidates: [
          {code:'def predict(x):\n  return x[0] == x[-1]', score:68, label:'Match first/last', status:'partial'},
          {code:'def predict(x):\n  return len(set(x)) < len(x)//2', score:55, label:'Low unique count', status:'fail'},
          {code:'def predict(x):\n  n = len(x)\n  return all(x[i]==x[n-1-i]\n    for i in range(n//2))', score:100, label:'Full palindrome check', status:'pass'},
          {code:'def predict(x):\n  return x[:3] == x[-3:][::-1]', score:72, label:'Match first/last 3', status:'partial'}
        ],
        best: 2, insight: 'Round 1: The correct solution — comparing characters from both ends — appears alongside partial heuristics. Validation picks the 100% candidate immediately.'
      }
    ]
  },
  dyck: {
    name: 'Dyck-2',
    rounds: [
      {
        candidates: [
          {code:'def predict(x):\n  return x.count("(")==x.count(")")', score:62, label:'Count parens only', status:'partial'},
          {code:'def predict(x):\n  return len(x) % 2 == 0', score:53, label:'Even length', status:'fail'},
          {code:'def predict(x):\n  s = []\n  for c in x:\n    if c in "([": s.append(c)\n    elif not s: return False\n    elif c==")" and s[-1]!="(":\n      return False\n    elif c=="]" and s[-1]!="[":\n      return False\n    else: s.pop()\n  return len(s)==0', score:95, label:'Stack-based check', status:'partial'},
          {code:'def predict(x):\n  d = 0\n  for c in x:\n    d += 1 if c=="(" else -1\n    if d < 0: return False\n  return d == 0', score:74, label:'Depth counter (1 type)', status:'partial'}
        ],
        best: 2, insight: 'Round 1: Dyck-2 requires tracking two bracket types. The stack-based solution reaches 95% but has an edge case on mixed nesting.'
      },
      {
        candidates: [
          {code:'def predict(x):\n  m = {"(":")", "[":"]"}\n  s = []\n  for c in x:\n    if c in m: s.append(m[c])\n    elif not s or s.pop()!=c:\n      return False\n  return not s', score:100, label:'Stack with map', status:'pass'},
          {code:'def predict(x):\n  s = []\n  for c in x:\n    if c in "([": s.append(c)\n    elif not s: return False\n    elif c==")" and s[-1]=="(":\n      s.pop()\n    elif c=="]" and s[-1]=="[":\n      s.pop()\n    else: return False\n  return len(s)==0', score:100, label:'Explicit stack match', status:'pass'},
          {code:'def predict(x):\n  while "()" in x or "[]" in x:\n    x = x.replace("()","").\\\n      replace("[]","")\n  return x == ""', score:100, label:'Reduction method', status:'pass'},
          {code:'def predict(x):\n  d1=d2=0\n  for c in x:\n    if c=="(": d1+=1\n    elif c==")": d1-=1\n    elif c=="[": d2+=1\n    else: d2-=1\n    if d1<0 or d2<0: return 0\n  return d1==0 and d2==0', score:82, label:'Dual counters', status:'partial'}
        ],
        best: 0, insight: 'Round 2: Three candidates achieve 100% — the stack-with-map, explicit matching, and reduction approaches all solve Dyck-2. The dual-counter fails on interleaved brackets like "([)]".'
      }
    ]
  }
};

var traceRound = 0;
var traceTask = 'prime';
var tracePlaying = false;
var traceTimer = null;
var traceBestHistory = [];

function traceReset() {
  if (tracePlaying) traceTogglePlay();
  traceTask = document.getElementById('trace-task').value;
  traceRound = 0;
  traceBestHistory = [];
  document.getElementById('trace-candidates').innerHTML = '<div style="text-align:center;padding:2rem;color:var(--ink-muted);font-family:var(--sans);font-size:13px">Press <strong>Play</strong> or <strong>Next round</strong> to begin</div>';
  document.getElementById('trace-evo').innerHTML = '';
  document.getElementById('trace-insight').style.display = 'none';
  traceUpdateLabel();
}

function traceUpdateLabel() {
  var total = traceTasks[traceTask].rounds.length;
  document.getElementById('trace-round-label').textContent = 'Round ' + traceRound + ' / ' + total;
}

function traceStep() {
  var t = traceTasks[traceTask];
  if (traceRound >= t.rounds.length) return;
  var round = t.rounds[traceRound];
  traceRound++;

  var container = document.getElementById('trace-candidates');
  container.innerHTML = '';

  round.candidates.forEach(function(c, i) {
    var div = document.createElement('div');
    div.className = 'trace-cand' + (i === round.best ? ' best' : (c.status === 'fail' ? ' eliminated' : ''));
    div.style.opacity = '0';
    div.style.transform = 'translateY(8px)';

    var badgeClass = c.status === 'pass' ? 'trace-badge-pass' : (c.status === 'fail' ? 'trace-badge-fail' : 'trace-badge-partial');
    var badgeText = c.status === 'pass' ? '100% — selected' : (c.status === 'fail' ? 'eliminated' : c.score + '%');
    if (i === round.best && c.status !== 'pass') { badgeText = c.score + '% — best so far'; badgeClass = 'trace-badge-best'; }
    if (i === round.best && c.status === 'pass') badgeClass = 'trace-badge-pass';

    var barColor = c.status === 'pass' ? 'var(--teal)' : (c.status === 'fail' ? 'var(--coral)' : 'var(--amber)');
    if (i === round.best) barColor = c.status === 'pass' ? 'var(--teal)' : 'var(--purple)';

    div.innerHTML =
      '<div class="trace-cand-header">' +
        '<span class="trace-cand-label">Candidate ' + (i+1) + ' — ' + c.label + '</span>' +
        '<span class="trace-badge ' + badgeClass + '">' + badgeText + '</span>' +
      '</div>' +
      '<div class="trace-code">' + c.code + '</div>' +
      '<div class="trace-footer">' +
        '<span class="trace-score">Validation: ' + c.score + '%</span>' +
        '<div class="trace-bar-track"><div class="trace-bar-fill" style="width:0%;background:' + barColor + '"></div></div>' +
      '</div>';

    container.appendChild(div);

    setTimeout(function() {
      div.style.transition = 'opacity .4s ease, transform .4s ease';
      div.style.opacity = '1';
      div.style.transform = 'translateY(0)';
      var fill = div.querySelector('.trace-bar-fill');
      if (fill) fill.style.width = c.score + '%';
    }, i * 150 + 50);
  });

  traceBestHistory.push(round.candidates[round.best].score);

  var evoContainer = document.getElementById('trace-evo');
  evoContainer.innerHTML = '';
  traceBestHistory.forEach(function(score, i) {
    var row = document.createElement('div');
    row.style.cssText = 'display:flex;align-items:center;gap:8px;margin-bottom:4px';
    var barColor = score >= 100 ? 'var(--teal)' : (score >= 80 ? 'var(--purple)' : 'var(--amber)');
    row.innerHTML =
      '<span style="font-family:var(--mono);font-size:11px;color:var(--ink-muted);min-width:28px">R' + (i+1) + '</span>' +
      '<div style="flex:1;height:6px;background:var(--paper);border-radius:3px"><div style="height:100%;border-radius:3px;width:' + score + '%;background:' + barColor + ';transition:width .6s ease"></div></div>' +
      '<span style="font-family:var(--mono);font-size:11px;color:var(--ink-muted);min-width:36px;text-align:right">' + score + '%</span>';
    evoContainer.appendChild(row);
  });

  var insightEl = document.getElementById('trace-insight');
  insightEl.style.display = 'block';
  insightEl.textContent = round.insight;

  traceUpdateLabel();
  if (traceRound >= t.rounds.length && tracePlaying) traceTogglePlay();
}

function traceTogglePlay() {
  tracePlaying = !tracePlaying;
  var btn = document.getElementById('trace-play-btn');
  if (tracePlaying) {
    btn.textContent = 'Pause';
    btn.classList.add('active');
    if (traceRound === 0 || traceRound >= traceTasks[traceTask].rounds.length) traceReset();
    traceStep();
    traceTimer = setInterval(function() {
      if (traceRound >= traceTasks[traceTask].rounds.length) { traceTogglePlay(); return; }
      traceStep();
    }, 3500);
  } else {
    btn.textContent = 'Play';
    btn.classList.remove('active');
    clearInterval(traceTimer);
  }
}

traceReset();
</script>
