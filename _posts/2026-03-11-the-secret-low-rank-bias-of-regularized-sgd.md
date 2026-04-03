<link rel="preconnect" href="https://cdn.jsdelivr.net" crossorigin>
<link rel="preconnect" href="https://fonts.googleapis.com" crossorigin>
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.min.css">
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.min.js"></script>
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/contrib/auto-render.min.js"></script>
<link href="https://fonts.googleapis.com/css2?family=Lora:ital,wght@0,400;0,500;0,600;1,400;1,500&family=IBM+Plex+Mono:wght@400;500&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&display=swap" rel="stylesheet">

<style>
.ps { /* post-scope */
  --bg:          #f6f3ee;
  --bg-warm:     #f0ece4;
  --surface:     #ede9e0;
  --surface-2:   #e8e3d8;
  --border:      #d8d2c6;
  --border-lt:   #e4dfd4;
  --text:        #18160f;
  --text-soft:   #3a3628;
  --muted:       #7a7060;
  --muted-lt:    #a09880;
  --accent:      #1e4f7a;
  --accent-mid:  #2a6199;
  --accent-soft: #d4e6f5;
  --accent-xs:   #ebf4fc;
  --gold:        #b8860b;
  --gold-soft:   #fdf4d8;
  --gold-bd:     #d4a820;
  --green:       #2a6645;
  --green-soft:  #e4f0ea;
  --red:         #8f2a2a;
  --red-soft:    #f5e8e8;
  --serif:       'Lora', Georgia, serif;
  --sans:        'DM Sans', -apple-system, sans-serif;
  --mono:        'IBM Plex Mono', monospace;
}

.ps, .ps *, .ps *::before, .ps *::after { box-sizing: border-box; }

.ps {
  width: 100%; max-width: 100%;
  background: var(--bg);
  color: var(--text);
  font-family: var(--sans);
  font-weight: 300;
  font-size: 17px;
  line-height: 1.78;
  -webkit-font-smoothing: antialiased;
  overflow-x: clip;
}

.ps ::selection { background: var(--accent-soft); color: var(--text); }
.ps a { color: var(--accent-mid); text-decoration: none; }
.ps a:hover { text-decoration: underline; }

/* ── TOP BAR ── */
.ps .top-bar {
  height: 3px;
  background: linear-gradient(90deg, #1e4f7a 0%, #2a6199 55%, #b8860b 100%);
}

/* ── HERO ── */
.ps .hero {
  max-width: 820px;
  margin: 0 auto;
  padding: 3.5rem 2.5rem 2.5rem;
  border-bottom: 1px solid var(--border);
}

.ps .hero-eyebrow {
  font-family: var(--mono);
  font-size: 10.5px;
  font-weight: 500;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: var(--muted);
  margin-bottom: 1.1rem;
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.ps .hero-eyebrow::before {
  content: '';
  display: inline-block;
  width: 18px; height: 2px;
  background: var(--gold);
  flex-shrink: 0;
}

.ps .hero h1 {
  font-family: var(--serif);
  font-size: clamp(1.9rem, 4.5vw, 2.9rem);
  font-weight: 600;
  line-height: 1.13;
  letter-spacing: -0.025em;
  color: var(--text);
  margin: 0 0 1.3rem;
  max-width: 680px;
}

.ps .hero h1 em { font-style: italic; font-weight: 400; color: var(--accent); }

.ps .hero-subtitle {
  font-size: 1.08rem;
  color: var(--muted);
  font-style: italic;
  font-weight: 300;
  max-width: 600px;
  line-height: 1.68;
  border-left: 2px solid var(--border);
  padding-left: 1.1rem;
  margin: 0 0 1.6rem;
}

.ps .hero-meta {
  font-family: var(--mono);
  font-size: 11px;
  color: var(--muted-lt);
  display: flex;
  gap: 1.25rem;
  flex-wrap: wrap;
  align-items: center;
}

.ps .paper-badge {
  display: inline-flex;
  align-items: center;
  gap: 5px;
  background: var(--accent-soft);
  color: var(--accent);
  border: 1px solid #b5cfe6;
  padding: 3px 10px;
  border-radius: 20px;
  font-weight: 500;
  font-size: 10.5px;
}

/* ── ARTICLE ── */
.ps article {
  max-width: 820px;
  margin: 0 auto;
  padding: 2.5rem 2.5rem 6rem;
}

.ps article p { margin: 0 0 1.15rem; font-size: 1.02rem; }

/* drop cap */
.ps article p.lead::first-letter {
  font-family: var(--serif);
  font-size: 3.6em;
  font-weight: 600;
  line-height: 0.75;
  float: left;
  margin: 0.06em 0.1em 0 0;
  color: var(--accent);
}

.ps article h2 {
  font-family: var(--serif);
  font-size: 1.48rem;
  font-weight: 500;
  line-height: 1.22;
  letter-spacing: -0.01em;
  margin: 2.75rem 0 1rem;
  padding-top: 2rem;
  border-top: 1px solid var(--border);
  color: var(--text);
}

.ps article h2:first-child { border-top: none; padding-top: 0; margin-top: 0; }

.ps article h3 {
  font-family: var(--mono);
  font-size: 0.73rem;
  font-weight: 500;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--muted);
  margin: 2rem 0 0.65rem;
}

.ps strong { font-weight: 500; }

.ps code {
  font-family: var(--mono);
  font-size: 0.85em;
  background: var(--surface);
  border: 1px solid var(--border-lt);
  padding: 1px 6px;
  border-radius: 3px;
  color: var(--text-soft);
}

/* ── CALLOUT (gold) ── */
.ps .callout {
  background: var(--gold-soft);
  border-left: 3px solid var(--gold-bd);
  padding: 1.05rem 1.3rem;
  border-radius: 0 7px 7px 0;
  margin: 1.75rem 0;
  font-size: 0.98rem;
  line-height: 1.68;
  color: var(--text-soft);
}
.ps .callout strong { display: block; margin-bottom: 0.3rem; font-weight: 500; color: var(--text); }

/* ── FINDING (blue) ── */
.ps .finding {
  background: var(--accent-xs);
  border: 1px solid #c0d9ef;
  border-left: 3px solid var(--accent-mid);
  border-radius: 0 7px 7px 0;
  padding: 1rem 1.3rem;
  margin: 1.6rem 0;
  font-size: 0.95rem;
  color: var(--text-soft);
}
.ps .finding-label {
  font-family: var(--mono);
  font-size: 0.68rem;
  font-weight: 500;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--accent);
  margin-bottom: 0.4rem;
}

/* ── MATH ── */
.ps .math-display {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: 8px;
  padding: 1.35rem 1.75rem;
  margin: 1.6rem 0;
  text-align: center;
  overflow-x: auto;
}
.ps .math-label {
  font-family: var(--mono);
  font-size: 0.68rem;
  font-weight: 500;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--muted);
  margin-bottom: 0.65rem;
}
.ps .eq-highlight {
  background: var(--gold-soft);
  border: 1px solid var(--gold-bd);
  border-radius: 8px;
  padding: 1.15rem 1.75rem;
  margin: 1.6rem 0;
  text-align: center;
  overflow-x: auto;
}

/* ── NUMBERED STEPS ── */
.ps .steps { margin: 1.5rem 0; }
.ps .step { display: flex; gap: 1rem; margin-bottom: 1.15rem; align-items: flex-start; }
.ps .step-num {
  background: var(--accent);
  color: white;
  width: 26px; height: 26px;
  border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  font-family: var(--mono);
  font-size: 0.7rem; font-weight: 500;
  flex-shrink: 0; margin-top: 0.12rem;
  box-shadow: 0 1px 5px rgba(30,79,122,.22);
}
.ps .step-body { flex: 1; }
.ps .step-title { font-weight: 500; margin-bottom: 0.12rem; font-size: 0.97rem; }
.ps .step-desc { font-size: 0.9rem; color: var(--muted); line-height: 1.62; font-weight: 300; }

/* ── DIAGRAM WRAP ── */
.ps .diagram-wrap {
  background: var(--bg-warm);
  border: 1px solid var(--border);
  border-radius: 10px;
  padding: 1.6rem 1.5rem 1.2rem;
  margin: 2rem 0;
  overflow-x: auto;
}
.ps .diagram-caption {
  font-family: var(--mono);
  font-size: 10.5px;
  color: var(--muted-lt);
  margin-top: 0.85rem;
  text-align: center;
  line-height: 1.55;
  letter-spacing: 0.01em;
}

/* ── PAPER NOTE ── */
.ps .paper-note {
  font-family: var(--mono);
  font-size: 0.76rem;
  color: var(--accent);
  background: var(--accent-xs);
  border: 1px solid #c0d9ef;
  padding: 0.8rem 1rem 0.8rem 2.1rem;
  border-radius: 5px;
  margin: 1.1rem 0 1.6rem;
  line-height: 1.7;
  position: relative;
}
.ps .paper-note::before { content: "◆"; position: absolute; left: 0.8rem; top: 0.85rem; font-size: 8px; }
.ps .paper-note a { color: var(--accent); font-weight: 500; }

/* ── PULL QUOTE ── */
.ps .pull-quote {
  font-family: var(--serif);
  font-size: 1.2rem;
  font-style: italic;
  color: var(--accent);
  border-top: 2px solid var(--accent-soft);
  border-bottom: 2px solid var(--accent-soft);
  padding: 1.1rem 0;
  margin: 2rem 0;
  line-height: 1.55;
  text-align: center;
}

/* ── EXPLORER ── */
.ps .explorer {
  background: var(--bg-warm);
  border: 1px solid var(--border);
  border-radius: 10px;
  overflow: hidden;
  margin: 1.75rem 0;
}
.ps .explorer-header {
  background: var(--surface);
  border-bottom: 1px solid var(--border);
  padding: 0.8rem 1.25rem;
  display: flex;
  align-items: baseline;
  gap: 0.75rem;
}
.ps .explorer-title {
  font-family: var(--mono);
  font-size: 0.72rem;
  font-weight: 500;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: var(--text);
}
.ps .explorer-subtitle { font-size: 12px; color: var(--muted); font-weight: 300; }
.ps .explorer-body { padding: 1.1rem 1.25rem 1.25rem; }

.ps .controls-row { display: flex; gap: 20px; flex-wrap: wrap; margin-bottom: 1rem; }
.ps .control-group { flex: 1; min-width: 130px; }
.ps .control-group label {
  display: block;
  font-family: var(--mono);
  font-size: 10.5px;
  color: var(--muted);
  margin-bottom: 5px;
  letter-spacing: 0.04em;
}
.ps .ctrl-value { font-weight: 500; color: var(--accent); float: right; }

.ps input[type="range"] {
  -webkit-appearance: none;
  width: 100%; height: 3px;
  background: var(--border);
  border-radius: 2px; outline: none; cursor: pointer;
}
.ps input[type="range"]::-webkit-slider-thumb {
  -webkit-appearance: none;
  width: 14px; height: 14px;
  border-radius: 50%;
  background: var(--accent);
  border: 2px solid white;
  box-shadow: 0 1px 4px rgba(30,79,122,.35);
  cursor: pointer;
}

.ps .viz-area { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; margin-top: 1rem; }
.ps .viz-panel {
  background: var(--bg);
  border: 1px solid var(--border-lt);
  border-radius: 7px;
  padding: 0.9rem;
  min-width: 0;
}
.ps .viz-panel-title {
  font-family: var(--mono);
  font-size: 9.5px;
  font-weight: 500;
  color: var(--muted-lt);
  letter-spacing: 0.07em;
  text-transform: uppercase;
  margin-bottom: 8px;
}

.ps .heatmap-grid { display: grid; gap: 1px; aspect-ratio: 1; border-radius: 4px; overflow: hidden; }
.ps .heatmap-cell { width: 100%; aspect-ratio: 1; transition: background-color .3s; }

.ps .sv-bars { display: flex; align-items: flex-end; gap: 4px; height: 110px; padding-top: 8px; }
.ps .sv-bar-wrap { flex: 1; display: flex; flex-direction: column; align-items: center; height: 100%; justify-content: flex-end; }
.ps .sv-bar { width: 100%; border-radius: 2px 2px 0 0; transition: height .4s ease, background-color .3s; min-height: 2px; }
.ps .sv-label { font-family: var(--mono); font-size: 9px; color: var(--muted-lt); margin-top: 4px; }

.ps .stats-row { display: flex; gap: 8px; margin-top: 10px; }
.ps .stat-card { flex: 1; background: var(--surface-2); border: 1px solid var(--border-lt); border-radius: 6px; padding: 8px 10px; text-align: center; }
.ps .stat-label { font-family: var(--mono); font-size: 9px; color: var(--muted-lt); margin-bottom: 3px; letter-spacing: 0.06em; text-transform: uppercase; }
.ps .stat-value { font-family: var(--mono); font-size: 16px; font-weight: 500; color: var(--text); }

.ps .play-row { display: flex; gap: 7px; margin-top: 10px; align-items: center; }
.ps .play-btn {
  font-family: var(--mono);
  font-size: 10.5px; font-weight: 500;
  padding: 5px 14px; border-radius: 4px;
  border: 1px solid var(--border);
  background: var(--bg); color: var(--muted);
  cursor: pointer; letter-spacing: 0.03em;
  transition: all .15s;
}
.ps .play-btn:hover { background: var(--surface); color: var(--text-soft); }
.ps .play-btn.active { background: var(--accent); color: white; border-color: var(--accent); box-shadow: 0 1px 6px rgba(30,79,122,.3); }
.ps .step-counter { font-family: var(--mono); font-size: 10.5px; color: var(--muted-lt); margin-left: auto; }

.ps .timeline { display: flex; gap: 2px; margin-top: 10px; height: 30px; align-items: flex-end; overflow: hidden; border-radius: 3px; }
.ps .timeline-block { flex: 1; min-width: 4px; border-radius: 2px; transition: opacity .3s, height .3s; }

/* ── FIGCAPTION ── */
.ps .figcaption {
  font-family: var(--mono);
  font-size: 10.5px;
  color: var(--muted-lt);
  line-height: 1.6;
  margin-top: 0.75rem;
  margin-bottom: 2rem;
  letter-spacing: 0.01em;
}

/* ── TAKEAWAY ── */
.ps .takeaway {
  background: var(--text);
  color: #e8e2d8;
  padding: 1.85rem 2rem;
  border-radius: 12px;
  margin: 2.75rem 0 1.5rem;
  position: relative;
  overflow: hidden;
}
.ps .takeaway::before {
  content: '';
  position: absolute; top: 0; left: 0; right: 0;
  height: 3px;
  background: linear-gradient(90deg, var(--accent-mid), var(--gold));
}
.ps .takeaway h3 {
  font-family: var(--mono);
  font-size: 0.68rem; font-weight: 500;
  letter-spacing: 0.12em; text-transform: uppercase;
  color: var(--gold-bd); margin: 0 0 1.1rem;
  border: none; padding: 0;
}
.ps .takeaway p { color: #c2bdb4; margin-bottom: 1rem; font-size: 1rem; }
.ps .takeaway p:last-child { margin-bottom: 0; }
.ps .takeaway strong { color: #e8e2d8; }

/* ── POST FOOTER ── */
.ps .post-footer {
  max-width: 820px; margin: 0 auto;
  padding: 1.5rem 2.5rem 3rem;
  text-align: center;
  border-top: 1px solid var(--border);
}
.ps .post-footer p { font-family: var(--mono); font-size: 11px; color: var(--muted-lt); margin: 0; }
.ps .post-footer a { color: var(--accent-mid); }

.ps hr { border: none; border-top: 1px solid var(--border); margin: 0; }

.ps .fade-in { opacity: 0; transform: translateY(16px); transition: opacity .65s ease, transform .65s ease; }
.ps .fade-in.visible { opacity: 1; transform: translateY(0); }

@media (max-width: 700px) {
  .ps .viz-area { grid-template-columns: 1fr; }
  .ps .hero, .ps article, .ps .post-footer { padding-left: 1.25rem; padding-right: 1.25rem; }
  .ps .hero h1 { font-size: 1.8rem; }
}
</style>

<div class="ps">

  <div class="top-bar"></div>

  <div class="hero">
    <div class="hero-eyebrow">Low-Rank Bias &middot; SGD &middot; Compression</div>
    <h1>The Secret <em>Low-Rank Bias</em> of Regularized SGD</h1>
    <p class="hero-subtitle">Why do trained neural networks often end up low rank? Mini-batch SGD and weight decay together create a built-in pressure toward compressible layers. The mechanism is simple, general, and explains why post-training compression works so well.</p>
    <div class="hero-meta">
      <span>By Tomer Galanti</span>
      <span>&middot;</span>
      <span>March 11, 2026</span>
      <span>&middot;</span>
      <span>12 min read</span>
      <span>&middot;</span>
      <span class="paper-badge">&#9670; Galanti et al., CPAL 2025</span>
    </div>
  </div>

  <article>

    <h2>Introduction</h2>

    <p class="lead">Deep networks are heavily overparameterized, yet the solutions found in practice are far from arbitrary. Even when many parameter settings can fit the training data, stochastic gradient methods often converge to highly structured models. One particularly striking form of structure is <strong>low rank</strong>: across many architectures, trained weight matrices are far more compressible than their full dimension would suggest.</p>

    <p>Much of the existing theory explains low-rank behavior only in cleaner settings — linear models, specialized losses, exact symmetries, or global optimality arguments. What is still missing is a structural explanation for the regime practitioners actually use: <strong>training practical neural networks with mini-batch SGD and weight decay</strong>.</p>

    <div class="callout">
      <strong>The central claim</strong>
      Mini-batch SGD with weight decay creates a strong built-in pressure toward low-rank layers. This pressure becomes stronger with smaller batch size $B$, larger learning rate $\mu$, and stronger weight decay $\lambda$.
    </div>

    <p>The mechanism operates in three steps:</p>

    <div class="steps">
      <div class="step">
        <div class="step-num">I</div>
        <div class="step-body">
          <div class="step-title">Low-rank updates.</div>
          <div class="step-desc">A single-example gradient is rank 1. A mini-batch gradient has rank at most $B$. Every SGD step writes only a low-rank correction to the weight matrix.</div>
        </div>
      </div>
      <div class="step">
        <div class="step-num">II</div>
        <div class="step-body">
          <div class="step-title">Finite memory.</div>
          <div class="step-desc">Weight decay exponentially suppresses old updates. Only a short window of past gradients contributes meaningfully to the current weight matrix.</div>
        </div>
      </div>
      <div class="step">
        <div class="step-num">III</div>
        <div class="step-body">
          <div class="step-title">Low-rank layers.</div>
          <div class="step-desc">The current matrix is dominated by a short history of low-rank corrections, yielding an effective rank of roughly $B / (\mu\lambda)$.</div>
        </div>
      </div>
    </div>

    <div class="paper-note">
      Based on: T. Galanti, Z. Siegel, A. Gupte, T. Poggio. <a href="https://openreview.net/forum?id=xhW2WyPhRP">&ldquo;SGD and Weight Decay Secretly Minimize the Rank of Your Neural Network&rdquo;</a>, CPAL 2025.
    </div>

    <h2>Interactive explorer</h2>

    <p>Here is a live simulation of the mechanism. An $8 \times 8$ weight matrix is built step by step from rank-$B$ stochastic gradient updates under weight decay. Adjust the sliders to see how batch size, learning rate, and weight decay each affect the resulting rank structure.</p>

    <div class="explorer fade-in">
      <div class="explorer-header">
        <span class="explorer-title">Low-rank bias simulator</span>
        <span class="explorer-subtitle">— SGD + weight decay builds low-rank weight matrices</span>
      </div>
      <div class="explorer-body">
        <div class="controls-row">
          <div class="control-group">
            <label>Batch size $B$ <span class="ctrl-value" id="b-val">2</span></label>
            <input type="range" min="1" max="8" value="2" id="b-slider" oninput="updateParam()">
          </div>
          <div class="control-group">
            <label>Learning rate $\mu$ <span class="ctrl-value" id="lr-val">0.08</span></label>
            <input type="range" min="1" max="20" value="8" id="lr-slider" oninput="updateParam()">
          </div>
          <div class="control-group">
            <label>Weight decay $\lambda$ <span class="ctrl-value" id="wd-val">0.05</span></label>
            <input type="range" min="1" max="20" value="5" id="wd-slider" oninput="updateParam()">
          </div>
        </div>

        <div class="viz-area">
          <div class="viz-panel">
            <div class="viz-panel-title">Weight matrix $W_T$</div>
            <div class="heatmap-grid" id="heatmap" style="grid-template-columns:repeat(8,1fr);"></div>
          </div>
          <div class="viz-panel">
            <div class="viz-panel-title">Singular values</div>
            <div class="sv-bars" id="sv-bars"></div>
          </div>
        </div>

        <div class="stats-row">
          <div class="stat-card"><div class="stat-label">Effective rank</div><div class="stat-value" id="eff-rank">—</div></div>
          <div class="stat-card"><div class="stat-label">Decay factor</div><div class="stat-value" id="decay-factor">—</div></div>
          <div class="stat-card"><div class="stat-label">Memory window</div><div class="stat-value" id="mem-window">—</div></div>
        </div>

        <div class="play-row">
          <button class="play-btn" id="play-btn" onclick="togglePlay()">▶ Play</button>
          <button class="play-btn" onclick="stepOnce()">Step</button>
          <button class="play-btn" onclick="resetSim()">Reset</button>
          <span class="step-counter" id="step-counter">t = 0</span>
        </div>

        <div class="viz-panel" style="margin-top:10px;padding:10px 12px;">
          <div class="viz-panel-title">Gradient memory timeline</div>
          <div class="timeline" id="timeline"></div>
        </div>
      </div>
    </div>

    <p class="figcaption"><strong>Fig. 1.</strong> Gradient slabs enter from the right; weight decay fades older contributions. The singular value bars expose the resulting rank structure. Try $B=1$, $\mu=0.10$, $\lambda=0.10$ for extreme low rank, or $B=8$, $\mu=0.02$, $\lambda=0.01$ for higher rank.</p>

    <hr>

    <h2>Part I — Stochastic gradients are low rank</h2>

    <h3>A local view of one layer</h3>

    <p>Fix all parameters except one trainable matrix $W$. Locally around that layer, the network can be written as $h(x) = g(Wf(x))$, where $f(x)$ is the representation entering the layer and $g$ collects everything afterward. Under mini-batch SGD with weight decay, the update is:</p>

    <div class="eq-highlight">
      $$W_{t+1} = (1 - 2\mu\lambda)\,W_t \;-\; \mu\, G_t$$
    </div>

    <p>The previous matrix is shrunk by the factor $1 - 2\mu\lambda$, and a fresh stochastic gradient $G_t$ is added. The key question is: what kind of matrix is $G_t$?</p>

    <h3>One example gives a rank-1 gradient</h3>

    <p>For a single training example $x$, the chain rule gives an outer product — the simplest possible matrix structure:</p>

    <div class="math-display">
      <div class="math-label">Single-example gradient</div>
      $$\nabla_W \ell(h(x)) = \delta(x)\, f(x)^\top \qquad \Rightarrow \qquad \mathrm{rank} = 1$$
    </div>

    <p>where $\delta(x) := J_g(Wf(x))^\top \nabla_h \ell(h(x))$. One left direction times one right direction — and nothing else.</p>

    <h3>A mini-batch gives rank at most $B$</h3>

    <p>The mini-batch gradient averages $B$ rank-1 terms:</p>

    <div class="math-display">
      $$G_t = \frac{1}{B}\sum_{i=1}^B \delta_i\, f_i^\top, \qquad \text{rank}(G_t) \le \min(d_{\text{out}},\, d_{\text{in}},\, B)$$
    </div>

    <p>Every SGD step writes only a rank-$B$ correction. The diagram below illustrates what this looks like for a layer of dimension 8.</p>

    <!-- Rank-B update diagram -->
    <div class="diagram-wrap fade-in">
      <svg viewBox="0 0 600 130" xmlns="http://www.w3.org/2000/svg" style="width:100%;max-width:600px;display:block;margin:auto">
        <defs>
          <marker id="ra" markerWidth="6" markerHeight="6" refX="5" refY="3" orient="auto">
            <path d="M0,0 L6,3 L0,6 Z" fill="#a09880"/>
          </marker>
          <marker id="ra-b" markerWidth="6" markerHeight="6" refX="5" refY="3" orient="auto">
            <path d="M0,0 L6,3 L0,6 Z" fill="#1e4f7a"/>
          </marker>
        </defs>

        <!-- W_t matrix -->
        <rect x="10" y="20" width="60" height="60" rx="4" fill="#ede9e0" stroke="#d8d2c6" stroke-width="1"/>
        <text x="40" y="47" font-family="IBM Plex Mono,monospace" font-size="9" fill="#7a7060" text-anchor="middle">W<tspan baseline-shift="sub" font-size="70%">t</tspan></text>
        <text x="40" y="60" font-family="IBM Plex Mono,monospace" font-size="8" fill="#a09880" text-anchor="middle">8 × 8</text>
        <text x="40" y="96" font-family="DM Sans,sans-serif" font-size="9" fill="#a09880" text-anchor="middle">current</text>

        <!-- multiply by decay -->
        <line x1="72" y1="50" x2="110" y2="50" stroke="#a09880" stroke-width="1" marker-end="url(#ra)"/>
        <text x="91" y="44" font-family="IBM Plex Mono,monospace" font-size="8" fill="#b8860b" text-anchor="middle">×(1−2μλ)</text>

        <!-- W_t decayed -->
        <rect x="113" y="20" width="60" height="60" rx="4" fill="#fdf4d8" stroke="#d4a820" stroke-width="1"/>
        <text x="143" y="47" font-family="IBM Plex Mono,monospace" font-size="9" fill="#7a7060" text-anchor="middle">W<tspan baseline-shift="sub" font-size="70%">t</tspan></text>
        <text x="143" y="60" font-family="IBM Plex Mono,monospace" font-size="8" fill="#b8860b" text-anchor="middle">shrunk</text>
        <text x="143" y="96" font-family="DM Sans,sans-serif" font-size="9" fill="#a09880" text-anchor="middle">decayed</text>

        <!-- minus -->
        <text x="192" y="55" font-family="IBM Plex Mono,monospace" font-size="16" fill="#a09880" text-anchor="middle">−</text>

        <!-- rank-B slab G_t -->
        <rect x="204" y="20" width="60" height="60" rx="4" fill="#d4e6f5" stroke="#1e4f7a" stroke-width="1.2"/>
        <text x="234" y="44" font-family="IBM Plex Mono,monospace" font-size="9" fill="#1e4f7a" text-anchor="middle">μ G<tspan baseline-shift="sub" font-size="70%">t</tspan></text>
        <text x="234" y="57" font-family="IBM Plex Mono,monospace" font-size="8" fill="#2a6199" text-anchor="middle">rank ≤ B</text>
        <!-- rank stripes -->
        <line x1="208" y1="66" x2="260" y2="66" stroke="#2a6199" stroke-width="1" stroke-dasharray="3,2" opacity="0.5"/>
        <line x1="208" y1="70" x2="260" y2="70" stroke="#2a6199" stroke-width="1" stroke-dasharray="3,2" opacity="0.3"/>
        <text x="234" y="96" font-family="DM Sans,sans-serif" font-size="9" fill="#a09880" text-anchor="middle">gradient step</text>

        <!-- equals -->
        <text x="283" y="55" font-family="IBM Plex Mono,monospace" font-size="16" fill="#a09880" text-anchor="middle">=</text>

        <!-- W_{t+1} -->
        <rect x="295" y="20" width="60" height="60" rx="4" fill="#ede9e0" stroke="#d8d2c6" stroke-width="1"/>
        <text x="325" y="47" font-family="IBM Plex Mono,monospace" font-size="8.5" fill="#7a7060" text-anchor="middle">W<tspan baseline-shift="sub" font-size="70%">t+1</tspan></text>
        <text x="325" y="60" font-family="IBM Plex Mono,monospace" font-size="8" fill="#a09880" text-anchor="middle">updated</text>
        <text x="325" y="96" font-family="DM Sans,sans-serif" font-size="9" fill="#a09880" text-anchor="middle">next step</text>

        <!-- annotation -->
        <rect x="380" y="14" width="210" height="72" rx="5" fill="#f6f3ee" stroke="#e4dfd4" stroke-width="1"/>
        <text x="395" y="32" font-family="DM Sans,sans-serif" font-size="10" fill="#3a3628">Each update writes only</text>
        <text x="395" y="47" font-family="IBM Plex Mono,monospace" font-size="10" fill="#1e4f7a">B new directions</text>
        <text x="395" y="62" font-family="DM Sans,sans-serif" font-size="10" fill="#3a3628">into an 8×8 matrix</text>
        <text x="395" y="76" font-family="DM Sans,sans-serif" font-size="10" fill="#a09880">(just B/64 of capacity)</text>

        <text x="300" y="120" font-family="DM Sans,sans-serif" font-size="10" fill="#7a7060" text-anchor="middle">Alone, this is not enough — repeated rank-B additions could eventually fill the matrix. Weight decay is the missing piece.</text>
      </svg>
      <p class="diagram-caption">Fig. 2 — Each SGD step writes a rank-$B$ correction. With $B=2$ on an 8×8 matrix, each step touches just 3% of the available singular directions.</p>
    </div>

    <p>Low-rank updates alone are not enough — if we accumulate them forever with no forgetting, their sum can eventually become full rank. The second ingredient is weight decay.</p>

    <hr>

    <h2>Part II — Weight decay limits memory</h2>

    <p>Unrolling the recursion $W_{t+1} = (1 - 2\mu\lambda)\,W_t - \mu\, G_t$ for $n$ steps gives the identity at the heart of the argument:</p>

    <div class="eq-highlight">
      $$W_T = \underbrace{(1 - 2\mu\lambda)^n\, W_{T-n}}_{\text{decayed past}} \;-\; \mu \underbrace{\sum_{j=1}^{n}(1 - 2\mu\lambda)^{j-1}\, G_{T-j}}_{\text{recent low-rank updates}}$$
    </div>

    <p>The first term shrinks exponentially in $n$. The second is a weighted sum of recent mini-batch gradients, each of rank at most $B$. After enough training, the current matrix is well approximated by a <strong>short moving memory of low-rank corrections</strong>.</p>

    <!-- Memory decay diagram -->
    <div class="diagram-wrap fade-in">
      <svg viewBox="0 0 600 148" xmlns="http://www.w3.org/2000/svg" style="width:100%;max-width:600px;display:block;margin:auto">
        <defs>
          <linearGradient id="decay-g" x1="0" y1="0" x2="1" y2="0">
            <stop offset="0%" stop-color="#d4e6f5" stop-opacity="0.2"/>
            <stop offset="100%" stop-color="#d4e6f5" stop-opacity="1"/>
          </linearGradient>
        </defs>

        <!-- Timeline label -->
        <text x="10" y="18" font-family="IBM Plex Mono,monospace" font-size="9" fill="#a09880">older ←</text>
        <text x="540" y="18" font-family="IBM Plex Mono,monospace" font-size="9" fill="#1e4f7a" text-anchor="end">→ most recent</text>

        <!-- Gradient slabs, fading left to right (older = more faded) -->
        <rect x="10"  y="26" width="52" height="44" rx="3" fill="#d4e6f5" opacity="0.12" stroke="#8ab8d8" stroke-width="0.5"/>
        <text x="36"  y="45" font-family="IBM Plex Mono,monospace" font-size="8" fill="#a09880" text-anchor="middle" opacity="0.4">G<tspan baseline-shift="sub" font-size="70%">T-8</tspan></text>
        <text x="36"  y="57" font-family="IBM Plex Mono,monospace" font-size="7.5" fill="#a09880" text-anchor="middle" opacity="0.4">~forgotten</text>

        <rect x="70"  y="26" width="52" height="44" rx="3" fill="#d4e6f5" opacity="0.25" stroke="#8ab8d8" stroke-width="0.7"/>
        <text x="96"  y="45" font-family="IBM Plex Mono,monospace" font-size="8" fill="#7a7060" text-anchor="middle" opacity="0.5">G<tspan baseline-shift="sub" font-size="70%">T-6</tspan></text>

        <rect x="130" y="26" width="52" height="44" rx="3" fill="#d4e6f5" opacity="0.45" stroke="#8ab8d8" stroke-width="0.9"/>
        <text x="156" y="45" font-family="IBM Plex Mono,monospace" font-size="8" fill="#7a7060" text-anchor="middle">G<tspan baseline-shift="sub" font-size="70%">T-4</tspan></text>

        <rect x="190" y="26" width="52" height="44" rx="3" fill="#d4e6f5" opacity="0.68" stroke="#8ab8d8" stroke-width="1"/>
        <text x="216" y="45" font-family="IBM Plex Mono,monospace" font-size="8" fill="#3a3628" text-anchor="middle">G<tspan baseline-shift="sub" font-size="70%">T-3</tspan></text>

        <rect x="250" y="26" width="52" height="44" rx="3" fill="#d4e6f5" opacity="0.85" stroke="#2a6199" stroke-width="1.1"/>
        <text x="276" y="45" font-family="IBM Plex Mono,monospace" font-size="8" fill="#1e4f7a" text-anchor="middle">G<tspan baseline-shift="sub" font-size="70%">T-2</tspan></text>

        <rect x="310" y="22" width="56" height="52" rx="3" fill="#d4e6f5" opacity="0.95" stroke="#1e4f7a" stroke-width="1.3"/>
        <text x="338" y="44" font-family="IBM Plex Mono,monospace" font-size="8" fill="#1e4f7a" text-anchor="middle">G<tspan baseline-shift="sub" font-size="70%">T-1</tspan></text>
        <text x="338" y="56" font-family="IBM Plex Mono,monospace" font-size="7.5" fill="#2a6199" text-anchor="middle">rank ≤ B</text>

        <rect x="374" y="18" width="62" height="60" rx="3" fill="#d4e6f5" stroke="#1e4f7a" stroke-width="1.6"/>
        <text x="405" y="44" font-family="IBM Plex Mono,monospace" font-size="8.5" fill="#1e4f7a" text-anchor="middle">G<tspan baseline-shift="sub" font-size="70%">T</tspan></text>
        <text x="405" y="57" font-family="IBM Plex Mono,monospace" font-size="7.5" fill="#2a6199" text-anchor="middle">current</text>

        <!-- Decay weights annotation -->
        <text x="10"  y="86" font-family="IBM Plex Mono,monospace" font-size="8" fill="#c8c0b0" text-anchor="middle" style="dominant-baseline:middle">×(1−2μλ)<tspan baseline-shift="super" font-size="70%">8</tspan></text>
        <text x="96"  y="86" font-family="IBM Plex Mono,monospace" font-size="8" fill="#b0a898" text-anchor="middle">×(1−2μλ)<tspan baseline-shift="super" font-size="70%">6</tspan></text>
        <text x="156" y="86" font-family="IBM Plex Mono,monospace" font-size="8" fill="#908880" text-anchor="middle">×(1−2μλ)<tspan baseline-shift="super" font-size="70%">4</tspan></text>
        <text x="216" y="86" font-family="IBM Plex Mono,monospace" font-size="8" fill="#706860" text-anchor="middle">×(1−2μλ)<tspan baseline-shift="super" font-size="70%">3</tspan></text>
        <text x="276" y="86" font-family="IBM Plex Mono,monospace" font-size="8" fill="#505048" text-anchor="middle">×(1−2μλ)<tspan baseline-shift="super" font-size="70%">2</tspan></text>
        <text x="338" y="86" font-family="IBM Plex Mono,monospace" font-size="8" fill="#303028" text-anchor="middle">×(1−2μλ)<tspan baseline-shift="super" font-size="70%">1</tspan></text>
        <text x="405" y="86" font-family="IBM Plex Mono,monospace" font-size="8" fill="#1e4f7a" text-anchor="middle">×1</text>

        <!-- Bracket and label for "effective window" -->
        <line x1="190" y1="102" x2="436" y2="102" stroke="#2a6645" stroke-width="1"/>
        <line x1="190" y1="97" x2="190" y2="102" stroke="#2a6645" stroke-width="1"/>
        <line x1="436" y1="97" x2="436" y2="102" stroke="#2a6645" stroke-width="1"/>
        <text x="313" y="116" font-family="IBM Plex Mono,monospace" font-size="8.5" fill="#2a6645" text-anchor="middle">effective memory window ≈ log(1/ε) / (μλ)</text>

        <!-- right annotation -->
        <rect x="448" y="18" width="145" height="60" rx="5" fill="#f6f3ee" stroke="#e4dfd4" stroke-width="1"/>
        <text x="462" y="36" font-family="DM Sans,sans-serif" font-size="10" fill="#3a3628">Older updates</text>
        <text x="462" y="50" font-family="DM Sans,sans-serif" font-size="10" fill="#3a3628">fade to nothing.</text>
        <text x="462" y="65" font-family="DM Sans,sans-serif" font-size="10" fill="#a09880">Only recent rank-B</text>
        <text x="462" y="79" font-family="DM Sans,sans-serif" font-size="10" fill="#a09880">slabs matter.</text>
      </svg>
      <p class="diagram-caption">Fig. 3 — Weight decay exponentially suppresses old gradient contributions. Only a window of $\approx \log(1/\varepsilon)/(\mu\lambda)$ recent steps matters for the current weight matrix.</p>
    </div>

    <h3>A simple effective-rank bound</h3>

    <p>Choose $n$ so the decayed-past term is negligible: $(1 - 2\mu\lambda)^n \approx e^{-2\mu\lambda n} \le \varepsilon$, giving $n \approx \log(1/\varepsilon) / (\mu\lambda)$. The recent-updates term is a sum of $n$ gradients of rank at most $B$, so:</p>

    <div class="eq-highlight">
      $$\text{rank}_\varepsilon(W_T) \;\lesssim\; \frac{B\,\log(1/\varepsilon)}{\mu\lambda}$$
    </div>

    <p>This captures the correct qualitative dependencies: smaller batch size $B$, larger learning rate $\mu$, or larger weight decay $\lambda$ all shorten the effective memory window and produce lower effective rank.</p>

    <div class="paper-note">
      This bound is a structural heuristic, not a worst-case guarantee. In practice the rank is often even lower, because gradient directions are not independent — training on structured data concentrates updates in a small number of directions.
    </div>

    <hr>

    <h2>Part III — Shared operators</h2>

    <p>The rank-1 statement changes when the same matrix $W$ is reused multiple times within a single example — as happens in <strong>convolutions</strong> (same kernel applied at many spatial locations) and <strong>self-attention projections</strong> ($W_Q$, $W_K$, $W_V$ applied to many tokens).</p>

    <p>In that case, $h(x) = g(Wf_1(x), \dots, Wf_R(x))$, and the chain rule gives:</p>

    <div class="math-display">
      <div class="math-label">Shared operator gradient</div>
      $$\nabla_W \ell(h(x)) = \sum_{r=1}^R \delta_r(x)\, f_r(x)^\top, \qquad \text{rank}\bigl(\nabla_W \ell(h(x))\bigr) \le R$$
    </div>

    <p>For a mini-batch, $\text{rank}(G_t) \le \min(d_{\text{out}}, d_{\text{in}}, BR)$. The rest of the argument is unchanged — weight decay still exponentially suppresses old updates, so the current matrix remains close to a weighted sum of recent low-rank gradients. The one-use setting $R = 1$ is simply the cleanest case.</p>

    <h3>Why the local view is natural</h3>

    <p>The decomposition $h(x) = g(Wf(x))$ is not an artificial simplification. It is the natural local view of any layer: fix all other parameters, isolate the point where $W$ acts, and absorb everything before it into $f$ and everything after it into $g$. For fully connected layers this is immediate. For residual blocks, the dependence on $W$ still enters through $Wf(x)$, so the outer-product structure of the gradient is preserved.</p>

    <hr>

    <h2>What this does and does not say</h2>

    <p>This argument does <strong>not</strong> imply that every trained layer must be exactly low rank. Nor does it eliminate the influence of architecture, normalization, or data geometry. What it provides is a broad structural reason that low-rank behavior should often appear in practice — and two direct consequences.</p>

    <div class="finding">
      <div class="finding-label">Why LoRA works</div>
      If SGD already pushes layers toward low rank, fine-tuning with an explicit low-rank parameterization ($W = W_0 + AB$) is not imposing an alien constraint — it is matching the structure that the original training would have produced anyway.
    </div>

    <div class="finding">
      <div class="finding-label">Why post-training compression works</div>
      SVD truncation after training is often surprisingly effective. This result explains why: compression is not inventing structure. It is extracting structure that training had already encouraged into the weight matrices.
    </div>

    <div class="pull-quote">&ldquo;Low rank is not an accident. It is built into the training dynamics through the interaction of stochastic gradients and weight decay.&rdquo;</div>

    <div class="takeaway">
      <h3>Takeaway</h3>
      <p>SGD with weight decay does more than optimize the loss. It quietly pushes layers toward low-rank structure through three interlocking effects.</p>
      <p><strong>Low-rank updates.</strong> Each stochastic gradient is low rank — rank 1 per example, rank $B$ per mini-batch, rank $BR$ for shared operators like convolutions and attention projections.</p>
      <p><strong>Finite memory.</strong> Weight decay exponentially forgets old updates, limiting the effective memory to roughly $\log(1/\varepsilon)/(\mu\lambda)$ steps.</p>
      <p><strong>Low-rank layers.</strong> The current weight matrix is dominated by a short history of low-rank corrections, giving an effective rank bounded by $B\log(1/\varepsilon)/(\mu\lambda)$.</p>
      <p>Low-rank structure in trained neural networks is not an empirical curiosity. It is a natural consequence of how SGD with weight decay writes directions in and forgets them over time.</p>
    </div>

  </article>

  <div class="post-footer">
    <p>Published on <a href="https://dlfundamentals.github.io/blog/">Theory/Simplified</a> &nbsp;&middot;&nbsp; Based on <a href="https://openreview.net/forum?id=xhW2WyPhRP">Galanti et al., CPAL 2025</a></p>
  </div>

</div>

<script>
(function(){
  var scopeEl = document.querySelector('.ps');

  var katexCheck = setInterval(function(){
    if(typeof renderMathInElement !== 'undefined' && scopeEl){
      clearInterval(katexCheck);
      renderMathInElement(scopeEl,{
        delimiters:[{left:'$$',right:'$$',display:true},{left:'$',right:'$',display:false}],
        throwOnError:false
      });
    }
  },100);

  var N=8, W=[], t=0, playing=false, playInterval=null, gradHistory=[], maxHistory=30;
  var B=2, mu=0.08, wd=0.05;

  function zeros(n){var m=[];for(var i=0;i<n;i++){m.push([]);for(var j=0;j<n;j++)m[i].push(0);}return m;}

  function randn(){var u=0,v=0;while(u===0)u=Math.random();while(v===0)v=Math.random();return Math.sqrt(-2*Math.log(u))*Math.cos(2*Math.PI*v);}

  function makeGrad(bs){var G=zeros(N);for(var b=0;b<bs;b++){var d=[],f=[];for(var i=0;i<N;i++){d.push(randn());f.push(randn());}for(var i=0;i<N;i++)for(var j=0;j<N;j++)G[i][j]+=d[i]*f[j]/bs;}return G;}

  function computeSVD(M){var MtM=zeros(N);for(var i=0;i<N;i++)for(var j=0;j<N;j++){var s=0;for(var k=0;k<N;k++)s+=M[k][i]*M[k][j];MtM[i][j]=s;}var svals=[],deflated=[];for(var i=0;i<N;i++){deflated.push([]);for(var j=0;j<N;j++)deflated[i].push(MtM[i][j]);}for(var sv=0;sv<N;sv++){var v=[];for(var i=0;i<N;i++)v.push(randn());var norm=Math.sqrt(v.reduce(function(s,x){return s+x*x;},0));v=v.map(function(x){return x/norm;});for(var iter=0;iter<50;iter++){var nv=[];for(var i=0;i<N;i++){var s=0;for(var j=0;j<N;j++)s+=deflated[i][j]*v[j];nv.push(s);}norm=Math.sqrt(nv.reduce(function(s,x){return s+x*x;},0));if(norm<1e-12)break;v=nv.map(function(x){return x/norm;});}svals.push(Math.sqrt(Math.max(0,norm)));for(var i=0;i<N;i++)for(var j=0;j<N;j++)deflated[i][j]-=norm*v[i]*v[j];}svals.sort(function(a,b){return b-a;});return svals;}

  function effectiveRank(svals){var total=svals.reduce(function(s,x){return s+x;},0);if(total<1e-10)return 0;var H=0;for(var i=0;i<svals.length;i++){var p=svals[i]/total;if(p>1e-10)H-=p*Math.log(p);}return Math.exp(H);}

  function initSim(){W=zeros(N);t=0;gradHistory=[];updateViz();}

  window.stepOnce=function(){
    var decay=Math.max(0.01,1-2*mu*wd);
    var G=makeGrad(B);
    for(var i=0;i<N;i++)for(var j=0;j<N;j++)W[i][j]=decay*W[i][j]-mu*G[i][j];
    var gN=0;for(var i=0;i<N;i++)for(var j=0;j<N;j++)gN+=G[i][j]*G[i][j];
    gradHistory.push(Math.sqrt(gN));
    if(gradHistory.length>maxHistory)gradHistory.shift();
    t++;updateViz();
  };

  window.togglePlay=function(){
    playing=!playing;
    var btn=document.getElementById('play-btn');
    if(playing){btn.textContent='⏸ Pause';btn.classList.add('active');playInterval=setInterval(window.stepOnce,200);}
    else{btn.textContent='▶ Play';btn.classList.remove('active');clearInterval(playInterval);}
  };

  window.resetSim=function(){if(playing)window.togglePlay();initSim();};

  window.updateParam=function(){
    B=parseInt(document.getElementById('b-slider').value,10);
    mu=parseInt(document.getElementById('lr-slider').value,10)/100;
    wd=parseInt(document.getElementById('wd-slider').value,10)/100;
    document.getElementById('b-val').textContent=B;
    document.getElementById('lr-val').textContent=mu.toFixed(2);
    document.getElementById('wd-val').textContent=wd.toFixed(2);
  };

  function valToColor(v){
    var c=Math.max(-1,Math.min(1,v*3));
    if(c>0){return'rgb('+Math.round(200+55*(1-c))+','+Math.round(100+100*(1-c))+','+Math.round(60+140*(1-c))+')';}
    else{var a=-c;return'rgb('+Math.round(60+140*(1-a))+','+Math.round(120+80*(1-a))+','+Math.round(180+75*(1-a))+')';}
  }

  function updateViz(){
    var hm=document.getElementById('heatmap');if(!hm)return;
    if(hm.children.length===0)for(var i=0;i<N*N;i++){var cell=document.createElement('div');cell.className='heatmap-cell';hm.appendChild(cell);}
    for(var i=0;i<N;i++)for(var j=0;j<N;j++)hm.children[i*N+j].style.backgroundColor=valToColor(W[i][j]);

    var svals=computeSVD(W);
    var maxSV=Math.max.apply(null,svals)||1;
    var svC=document.getElementById('sv-bars');
    if(svC.children.length===0)for(var i=0;i<N;i++){var wrap=document.createElement('div');wrap.className='sv-bar-wrap';var bar=document.createElement('div');bar.className='sv-bar';var lbl=document.createElement('div');lbl.className='sv-label';lbl.textContent='σ'+(i+1);wrap.appendChild(bar);wrap.appendChild(lbl);svC.appendChild(wrap);}

    for(var i=0;i<N;i++){
      var bar=svC.children[i].querySelector('.sv-bar');
      var h=maxSV>1e-10?(svals[i]/maxSV*100):0;
      bar.style.height=Math.max(2,h)+'px';
      var intensity=maxSV>1e-10?svals[i]/maxSV:0;
      /* blue palette for singular value bars */
      var r=Math.round(30+80*intensity);
      var g=Math.round(79+40*intensity);
      var bv=Math.round(122-20*intensity);
      bar.style.backgroundColor='rgb('+r+','+g+','+bv+')';
    }

    var er=effectiveRank(svals);
    document.getElementById('eff-rank').textContent=er<0.01?'0':er.toFixed(1);
    var decay=Math.max(0.01,1-2*mu*wd);
    document.getElementById('decay-factor').textContent=decay.toFixed(3);
    var memWin=mu*wd>1e-8?Math.round(Math.log(100)/(mu*wd)):'∞';
    document.getElementById('mem-window').textContent=memWin==='∞'?'∞':'~'+memWin;
    document.getElementById('step-counter').textContent='t = '+t;

    var tl=document.getElementById('timeline');tl.innerHTML='';
    for(var i=0;i<gradHistory.length;i++){
      var block=document.createElement('div');block.className='timeline-block';
      var age=gradHistory.length-1-i;
      block.style.height=Math.max(4,Math.min(30,gradHistory[i]*12))+'px';
      block.style.opacity=Math.max(0.08,Math.pow(decay,age));
      block.style.backgroundColor='#2a6199';
      tl.appendChild(block);
    }
  }

  if('IntersectionObserver' in window){
    var obs=new IntersectionObserver(function(entries){entries.forEach(function(e){if(e.isIntersecting)e.target.classList.add('visible');});},{threshold:0.12});
    scopeEl.querySelectorAll('.fade-in').forEach(function(el){obs.observe(el);});
  }

  initSim();
})();
</script>
