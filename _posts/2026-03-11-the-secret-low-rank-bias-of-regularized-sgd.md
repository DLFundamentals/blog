<link rel="preconnect" href="https://cdn.jsdelivr.net" crossorigin>
<link rel="preconnect" href="https://fonts.googleapis.com" crossorigin>
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>

<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.min.css">
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.min.js"></script>
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/contrib/auto-render.min.js"></script>
<link href="https://fonts.googleapis.com/css2?family=Newsreader:ital,wght@0,300;0,400;0,500;0,600;1,400&family=DM+Sans:wght@400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">

<style>
:root {
  --ink:#1a1714;
  --ink-soft:#4a4640;
  --ink-muted:#8a8680;
  --cream:#faf8f4;
  --paper:#ffffff;
  --rule:#e0dcd6;
  --accent:#c45028;
  --accent-soft:#f0e6df;
  --teal:#1a7a5c;
  --teal-soft:#e4f2ec;
  --purple:#5a4ab8;
  --purple-soft:#eeedfe;
  --amber:#a06810;
  --amber-soft:#faf0da;
  --coral:#d85a30;
  --coral-soft:#faece7;
  --serif:'Newsreader',Georgia,serif;
  --sans:'DM Sans',-apple-system,sans-serif;
  --mono:'JetBrains Mono',monospace;
}

.post-scope,
.post-scope *,
.post-scope *::before,
.post-scope *::after {
  box-sizing:border-box;
}

.post-scope{
  width:100%;
  max-width:100%;
  background:var(--cream);
  color:var(--ink);
  font-family:var(--serif);
  line-height:1.72;
  -webkit-font-smoothing:antialiased;
  overflow-x:clip;
}

.post-scope ::selection{
  background:var(--accent-soft);
  color:var(--ink);
}

.post-scope a{
  color:var(--accent);
  text-decoration:none;
}

.post-scope a:hover{
  text-decoration:underline;
}

.post-scope img{
  max-width:100%;
  height:auto;
  display:block;
}

.post-scope .hero{
  max-width:900px;
  margin:0 auto;
  padding:3.4rem 2rem 2.35rem;
  border-bottom:1px solid var(--rule);
}

.post-scope .hero-eyebrow{
  font-family:var(--sans);
  font-size:12px;
  font-weight:600;
  letter-spacing:2px;
  text-transform:uppercase;
  color:var(--accent);
  margin-bottom:.95rem;
}

.post-scope .hero h1{
  font-family:var(--serif);
  font-size:clamp(2rem,5vw,3rem);
  font-weight:500;
  line-height:1.2;
  color:var(--ink);
  margin:0 0 1.2rem 0;
  max-width:700px;
}

.post-scope .hero-subtitle{
  font-size:1.15rem;
  color:var(--ink-soft);
  max-width:620px;
  line-height:1.65;
  margin:0;
}

.post-scope .hero-meta{
  margin-top:1.5rem;
  font-family:var(--sans);
  font-size:13px;
  color:var(--ink-muted);
  display:flex;
  gap:1.5rem;
  flex-wrap:wrap;
  align-items:center;
}

.post-scope .paper-badge{
  display:inline-flex;
  align-items:center;
  gap:6px;
  background:var(--purple-soft);
  color:var(--purple);
  padding:4px 12px;
  border-radius:20px;
  font-weight:500;
  font-size:12px;
}

.post-scope article{
  max-width:680px;
  margin:0 auto;
  padding:1.7rem 2rem 1.35rem;
}

.post-scope .hero + article{
  padding-top:1.8rem;
}

.post-scope article p{
  font-size:1.05rem;
  margin:0 0 1.2rem 0;
}

.post-scope article h2{
  font-family:var(--serif);
  font-size:1.6rem;
  font-weight:500;
  margin:2.2rem 0 .95rem;
  color:var(--ink);
  padding-top:1.45rem;
  border-top:1px solid var(--rule);
}

.post-scope article h2:first-child{
  border-top:none;
  padding-top:0;
  margin-top:0;
}

.post-scope article h3{
  font-family:var(--sans);
  font-size:1rem;
  font-weight:600;
  margin:1.45rem 0 .6rem;
  color:var(--ink-soft);
  letter-spacing:.3px;
}

.post-scope .key-insight{
  border-left:3px solid var(--accent);
  padding:1rem 1.2rem;
  margin:1.2rem 0;
  background:var(--accent-soft);
  border-radius:0 8px 8px 0;
  color:var(--ink-soft);
  font-size:1.05rem;
  line-height:1.65;
}

.post-scope .math-display{
  text-align:center;
  padding:1.5rem 1rem;
  margin:1.5rem 0;
  background:var(--paper);
  border:1px solid var(--rule);
  border-radius:8px;
  overflow-x:auto;
}

.post-scope .math-display .katex{
  font-size:1.1em;
}

.post-scope .math-label{
  font-family:var(--sans);
  font-size:11px;
  font-weight:600;
  letter-spacing:1px;
  text-transform:uppercase;
  color:var(--ink-muted);
  margin-bottom:8px;
}

.post-scope code{
  font-family:var(--mono);
  font-size:.88em;
  background:#f0ede8;
  padding:2px 6px;
  border-radius:4px;
  color:var(--accent);
  white-space:nowrap;
}

.post-scope .compare-grid{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:10px;
  margin:1.2rem 0;
}

.post-scope .compare-card{
  background:var(--paper);
  border:1px solid var(--rule);
  border-radius:8px;
  padding:.9rem 1rem;
  min-width:0;
}

.post-scope .compare-card h4{
  font-family:var(--sans);
  font-size:13px;
  font-weight:600;
  margin:0 0 6px 0;
}

.post-scope .compare-card p{
  font-size:13px;
  color:var(--ink-soft);
  line-height:1.55;
  margin:0;
}

.post-scope .mechanism-grid{
  display:grid;
  grid-template-columns:repeat(3,minmax(0,1fr));
  gap:10px;
  margin:1.2rem 0;
}

.post-scope .mechanism-card{
  background:var(--paper);
  border:1px solid var(--rule);
  border-radius:8px;
  padding:1rem;
  border-top:3px solid var(--rule);
  min-width:0;
}

.post-scope .mechanism-card .step-num{
  font-family:var(--sans);
  font-size:11px;
  font-weight:600;
  letter-spacing:1px;
  text-transform:uppercase;
  margin-bottom:6px;
}

.post-scope .mechanism-card h4{
  font-family:var(--sans);
  font-size:14px;
  font-weight:600;
  margin:0 0 6px 0;
  color:var(--ink);
}

.post-scope .mechanism-card p{
  font-size:13px;
  color:var(--ink-soft);
  line-height:1.55;
  margin:0;
}

.post-scope .paper-note{
  font-family:var(--sans);
  font-size:12px;
  color:var(--purple);
  background:var(--purple-soft);
  padding:10px 14px 10px 32px;
  border-radius:6px;
  margin:1rem 0 1.5rem;
  line-height:1.6;
  position:relative;
}

.post-scope .paper-note::before{
  content:"◆";
  position:absolute;
  left:14px;
  top:10px;
  font-size:10px;
}

.post-scope .paper-note code{
  background:rgba(90,74,184,.1);
  color:#3c3489;
  white-space:normal;
}

.post-scope .takeaway{
  background:var(--ink);
  color:var(--cream);
  padding:1.55rem 1.7rem;
  border-radius:12px;
  margin:2.1rem 0 1.25rem;
}

.post-scope .takeaway h3{
  font-family:var(--sans);
  font-size:12px;
  font-weight:600;
  letter-spacing:2px;
  text-transform:uppercase;
  color:var(--accent);
  margin:0 0 1rem 0;
}

.post-scope .takeaway p{
  color:#d0cdc6;
  margin-bottom:1rem;
  font-size:1.02rem;
}

.post-scope .takeaway p:last-child{
  margin-bottom:0;
}

.post-scope .takeaway strong{
  color:var(--cream);
}

.post-scope .explorer{
  background:var(--paper);
  border:1px solid var(--rule);
  border-radius:12px;
  padding:1.15rem;
  margin:1.2rem 0;
}

.post-scope .explorer-title{
  font-family:var(--sans);
  font-size:14px;
  font-weight:600;
  color:var(--ink);
  margin-bottom:4px;
}

.post-scope .explorer-subtitle{
  font-family:var(--sans);
  font-size:13px;
  color:var(--ink-muted);
  margin-bottom:.95rem;
}

.post-scope .controls-row{
  display:flex;
  gap:20px;
  flex-wrap:wrap;
  margin-bottom:1rem;
}

.post-scope .control-group{
  flex:1;
  min-width:140px;
}

.post-scope .control-group label{
  display:block;
  font-family:var(--sans);
  font-size:12px;
  color:var(--ink-muted);
  margin-bottom:4px;
}

.post-scope .control-group .ctrl-value{
  font-family:var(--mono);
  font-size:13px;
  font-weight:500;
  color:var(--ink);
  float:right;
}

.post-scope .control-group input[type="range"]{
  width:100%;
  margin:0;
}

.post-scope .viz-area{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:16px;
  margin-top:1rem;
}

.post-scope .viz-panel{
  background:var(--cream);
  border-radius:8px;
  padding:1rem;
  position:relative;
  min-width:0;
}

.post-scope .viz-panel-title{
  font-family:var(--sans);
  font-size:12px;
  font-weight:600;
  color:var(--ink-muted);
  letter-spacing:.5px;
  text-transform:uppercase;
  margin-bottom:8px;
}

.post-scope .heatmap-grid{
  display:grid;
  gap:1px;
  aspect-ratio:1;
  border-radius:4px;
  overflow:hidden;
}

.post-scope .heatmap-cell{
  width:100%;
  aspect-ratio:1;
  transition:background-color .3s;
}

.post-scope .sv-bars{
  display:flex;
  align-items:flex-end;
  gap:4px;
  height:120px;
  padding-top:8px;
}

.post-scope .sv-bar-wrap{
  flex:1;
  display:flex;
  flex-direction:column;
  align-items:center;
  height:100%;
  justify-content:flex-end;
}

.post-scope .sv-bar{
  width:100%;
  border-radius:3px 3px 0 0;
  transition:height .4s ease,background-color .3s;
  min-height:2px;
}

.post-scope .sv-label{
  font-family:var(--mono);
  font-size:10px;
  color:var(--ink-muted);
  margin-top:4px;
}

.post-scope .stats-row{
  display:flex;
  gap:12px;
  margin-top:12px;
}

.post-scope .stat-card{
  flex:1;
  background:var(--cream);
  border-radius:8px;
  padding:10px 12px;
  text-align:center;
}

.post-scope .stat-label{
  font-family:var(--sans);
  font-size:11px;
  color:var(--ink-muted);
  margin-bottom:2px;
}

.post-scope .stat-value{
  font-family:var(--mono);
  font-size:18px;
  font-weight:500;
  color:var(--ink);
}

.post-scope .play-controls{
  display:flex;
  gap:8px;
  margin-top:12px;
  align-items:center;
}

.post-scope .play-btn{
  font-family:var(--sans);
  font-size:13px;
  font-weight:500;
  padding:6px 16px;
  border-radius:6px;
  border:.5px solid var(--rule);
  background:transparent;
  color:var(--ink-soft);
  cursor:pointer;
  transition:background .15s;
}

.post-scope .play-btn:hover{
  background:var(--cream);
}

.post-scope .play-btn.active{
  background:var(--accent);
  color:white;
  border-color:var(--accent);
}

.post-scope .step-counter{
  font-family:var(--mono);
  font-size:13px;
  color:var(--ink-muted);
  margin-left:auto;
}

.post-scope .timeline{
  display:flex;
  gap:2px;
  margin-top:12px;
  height:32px;
  align-items:flex-end;
  overflow:hidden;
  border-radius:4px;
}

.post-scope .timeline-block{
  flex:1;
  min-width:4px;
  border-radius:2px;
  transition:opacity .3s,height .3s;
}

.post-scope .figcaption{
  font-family:var(--sans);
  font-size:13px;
  color:var(--ink-muted);
  line-height:1.55;
  margin-top:10px;
}

.post-scope .post-footer{
  max-width:680px;
  margin:0 auto;
  padding:0 2rem 2.6rem;
  text-align:center;
}

.post-scope .post-footer p{
  font-family:var(--sans);
  font-size:13px;
  color:var(--ink-muted);
  margin:0;
}

.post-scope .post-footer a{
  color:var(--accent);
}

.post-scope .fade-in{
  opacity:0;
  transform:translateY(16px);
  transition:opacity .6s ease,transform .6s ease;
}

.post-scope .fade-in.visible{
  opacity:1;
  transform:translateY(0);
}

.post-scope .eq-highlight{
  background:var(--amber-soft);
  border:1px solid #e8d5b0;
  border-radius:8px;
  padding:1rem 1.2rem;
  margin:1.5rem 0;
  text-align:center;
  overflow-x:auto;
}

.post-scope .eq-highlight .katex{
  font-size:1.15em;
}

.post-scope hr.section-rule{
  border:none;
  height:1px;
  background:var(--rule);
  margin:2.5rem 0;
}

.post-scope .rank-chain{
  display:flex;
  align-items:center;
  gap:8px;
  margin:1.5rem 0;
  flex-wrap:wrap;
  justify-content:center;
}

.post-scope .rank-block{
  display:flex;
  flex-direction:column;
  align-items:center;
  gap:4px;
}

.post-scope .rank-rect{
  border-radius:4px;
  display:flex;
  align-items:center;
  justify-content:center;
  font-family:var(--mono);
  font-size:11px;
  font-weight:500;
  width:56px;
  height:40px;
}

.post-scope .rank-label{
  font-family:var(--sans);
  font-size:10px;
  color:var(--ink-muted);
}

.post-scope .rank-arrow{
  font-size:18px;
  color:var(--ink-muted);
}

@media(max-width:700px){
  .post-scope .mechanism-grid{
    grid-template-columns:1fr;
  }
}

@media(max-width:600px){
  .post-scope .compare-grid,
  .post-scope .viz-area{
    grid-template-columns:1fr;
  }
}

@media(max-width:480px){
  .post-scope .hero{
    padding:3rem 1rem 2rem;
  }

  .post-scope article{
    padding:1.75rem 1rem 2rem;
  }

  .post-scope .post-footer{
    padding:0 1rem 2.2rem;
  }

  .post-scope .hero h1{
    font-size:1.7rem;
  }

  .post-scope .hero-meta{
    font-size:.78rem;
  }
}
</style>

<div class="post-scope">

  <div class="hero">
    <div class="hero-eyebrow">Low-Rank Bias &middot; SGD &middot; Compression</div>
    <h1>The Secret Low Rank Bias Of Regularized SGD</h1>
    <p class="hero-subtitle">Why do trained neural networks often end up low rank? Mini-batch SGD and weight decay together create a built-in pressure toward compressible layers. The mechanism is simple, general, and explains why post-training compression works so well.</p>
    <div class="hero-meta">
      <span>By Tomer Galanti</span>
      <span>&middot;</span>
      <span>March 11, 2026</span>
      <span>&middot;</span>
      <span>12 min read</span>
      <span>&middot;</span>
      <span class="paper-badge">◆ Based on Galanti et al., CPAL 2025</span>
    </div>
  </div>

  <article>

    <h2 style="border-top:none;padding-top:0;margin-top:0;">Introduction</h2>

    <p>Deep networks are heavily overparameterized, yet the solutions found in practice are far from arbitrary. Even when many parameter settings can fit the training data, stochastic gradient methods often converge to highly structured models. One particularly striking form of structure is <strong>low rank</strong>: across many architectures, trained weight matrices are far more compressible than their full dimension would suggest.</p>

    <p>Much of the existing theory explains low-rank behavior only in cleaner settings than those used in modern practice — linear models, specialized losses, exact symmetries, or global optimality arguments. What is still missing is a structural explanation for the regime practitioners actually use: <strong>training practical neural networks with mini-batch SGD and weight decay</strong>.</p>

    <div class="key-insight">
      Mini-batch SGD with weight decay creates a strong pressure toward low-rank layers. This pressure becomes stronger with smaller batch size $B$, larger learning rate $\mu$, and stronger weight decay $\lambda$.
    </div>

    <p>The mechanism has three parts:</p>

    <div class="mechanism-grid fade-in">
      <div class="mechanism-card" style="border-top-color:var(--purple);">
        <div class="step-num" style="color:var(--purple);">Part I</div>
        <h4>Low-rank updates</h4>
        <p>A single-example gradient is rank 1. A mini-batch gradient has rank at most $B$. Every SGD step writes only a low-rank correction.</p>
      </div>
      <div class="mechanism-card" style="border-top-color:var(--teal);">
        <div class="step-num" style="color:var(--teal);">Part II</div>
        <h4>Finite memory</h4>
        <p>Weight decay exponentially suppresses old updates. Only a short window of past gradients contributes meaningfully to the current weight matrix.</p>
      </div>
      <div class="mechanism-card" style="border-top-color:var(--coral);">
        <div class="step-num" style="color:var(--coral);">Part III</div>
        <h4>Low-rank layers</h4>
        <p>The current matrix is dominated by a short history of low-rank corrections, yielding an effective rank of roughly $B / (\mu\lambda)$.</p>
      </div>
    </div>

    <div class="paper-note">
      Based on: T. Galanti, Z. Siegel, A. Gupte, T. Poggio. <a href="https://openreview.net/forum?id=xhW2WyPhRP" style="color:var(--purple);font-weight:500;">"SGD and Weight Decay Secretly Minimize the Rank of Your Neural Network"</a>, CPAL 2025.
    </div>

    <h2>Interactive explorer</h2>

    <p>Here is a live simulation of the mechanism. An $8 \times 8$ weight matrix is built step by step from rank-$B$ stochastic gradient updates under weight decay. Use the sliders to see how batch size, learning rate, and weight decay each affect the resulting rank structure.</p>

    <div class="explorer fade-in" id="explorer">
      <div class="explorer-title">Low-rank bias simulator</div>
      <div class="explorer-subtitle">Watch how SGD + weight decay builds low-rank weight matrices</div>

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
        <div class="stat-card">
          <div class="stat-label">Effective rank</div>
          <div class="stat-value" id="eff-rank">—</div>
        </div>
        <div class="stat-card">
          <div class="stat-label">Decay factor</div>
          <div class="stat-value" id="decay-factor">—</div>
        </div>
        <div class="stat-card">
          <div class="stat-label">Memory window</div>
          <div class="stat-value" id="mem-window">—</div>
        </div>
      </div>

      <div style="display:flex;align-items:center;gap:12px;margin-top:12px;">
        <div class="play-controls" style="flex:1;">
          <button class="play-btn" id="play-btn" onclick="togglePlay()">Play</button>
          <button class="play-btn" onclick="stepOnce()">Step</button>
          <button class="play-btn" onclick="resetSim()">Reset</button>
          <span class="step-counter" id="step-counter">t = 0</span>
        </div>
      </div>

      <div class="viz-panel" style="margin-top:12px;padding:10px 12px;">
        <div class="viz-panel-title">Gradient memory timeline</div>
        <div class="timeline" id="timeline"></div>
      </div>
    </div>

    <div class="figcaption" style="margin-top:-0.5rem;margin-bottom:2rem;">
      <strong>Figure 1.</strong> Interactive simulation. Gradient slabs enter from the right; weight decay fades older contributions. The singular value bars expose the resulting rank structure. Smaller batch size $B$, larger learning rate $\mu$, and stronger weight decay $\lambda$ each compress the effective rank.
    </div>

    <div class="compare-grid fade-in">
      <div class="compare-card" style="border-left:3px solid var(--purple);">
        <h4 style="color:var(--purple);">Try: extreme low rank</h4>
        <p>Set $B = 1$, $\mu = 0.10$, $\lambda = 0.10$. Each gradient is a single outer product, the memory is short, and the effective rank stays at 1–2.</p>
      </div>
      <div class="compare-card" style="border-left:3px solid var(--amber);">
        <h4 style="color:var(--amber);">Try: higher rank</h4>
        <p>Set $B = 8$, $\mu = 0.02$, $\lambda = 0.01$. Richer gradients with a longer memory window push the effective rank up toward 6–8.</p>
      </div>
    </div>

    <h2>Part I: Stochastic gradients are low rank</h2>

    <h3>A local view of one layer</h3>

    <p>Fix all parameters except one trainable matrix $W$. Locally around that layer, the network can be written as $h(x) = g(Wf(x))$, where $f(x)$ is the representation entering the layer and $g$ collects everything that comes afterward. Under mini-batch SGD with weight decay, the update is:</p>

    <div class="eq-highlight">
      $$W_{t+1} = (1 - 2\mu\lambda)\,W_t \;-\; \mu\, G_t$$
    </div>

    <p>The previous matrix is shrunk by the factor $1 - 2\mu\lambda$, and a fresh stochastic gradient $G_t$ is added. So the key question is: <strong>what kind of matrix is $G_t$?</strong></p>

    <h3>One example gives a rank-1 gradient</h3>

    <p>For a single training example $x$, the chain rule gives:</p>

    <div class="math-display">
      $$\nabla_W \ell(h(x)) = \delta(x)\, f(x)^\top$$
    </div>

    <p>where $\delta(x) := J_g(Wf(x))^\top \nabla_h \ell(h(x))$. This is an outer product of two vectors — the simplest possible structure. One left direction times one right direction. So $\text{rank}(\nabla_W \ell(h(x))) \le 1$.</p>

    <h3>A mini-batch gives rank at most $B$</h3>

    <p>The mini-batch gradient averages $B$ rank-1 terms:</p>

    <div class="math-display">
      $$G_t = \frac{1}{B}\sum_{i=1}^B \delta_i\, f_i^\top, \qquad \text{rank}(G_t) \le \min(d_{\text{out}},\, d_{\text{in}},\, B)$$
    </div>

    <p>Every SGD step writes only a low-rank correction. Smaller batch sizes make this restriction stronger; larger batch sizes relax it. But low-rank updates alone are not enough — if we accumulate them forever with no forgetting, their sum can eventually become full rank. The second ingredient is weight decay.</p>

    <h2>Part II: Weight decay limits memory</h2>

    <p>Unrolling the recursion $W_{t+1} = (1 - 2\mu\lambda)\,W_t - \mu\, G_t$ for $n$ steps gives the identity at the heart of the argument:</p>

    <div class="eq-highlight">
      $$W_T = \underbrace{(1 - 2\mu\lambda)^n\, W_{T-n}}_{\text{decayed past}} \;-\; \mu \underbrace{\sum_{j=1}^{n}(1 - 2\mu\lambda)^{j-1}\, G_{T-j}}_{\text{recent low-rank updates}}$$
    </div>

    <p>The first term shrinks exponentially in $n$. The second is a weighted sum of recent mini-batch gradients, each of rank at most $B$. After enough training, the current matrix is well approximated by a <strong>short moving memory of low-rank corrections</strong>. That is the mechanism.</p>

    <div class="compare-grid fade-in">
      <div class="compare-card">
        <h4 style="color:var(--teal);">SGD writes few directions</h4>
        <p>Each step adds at most $B$ new singular directions. With $B = 32$ on a 768-dimensional layer, each step writes just 4% of the available directions.</p>
      </div>
      <div class="compare-card">
        <h4 style="color:var(--teal);">Weight decay forgets old ones</h4>
        <p>Old directions decay as $(1 - 2\mu\lambda)^n$. With typical $\mu = 0.01$ and $\lambda = 0.01$, a direction from 1000 steps ago retains only $e^{-0.2} \approx 0.82$ of its original magnitude — and from 5000 steps, just $e^{-1} \approx 0.37$.</p>
      </div>
    </div>

    <h3>A simple effective-rank heuristic</h3>

    <p>Choose $n$ so that the old-memory term is negligible: $(1 - 2\mu\lambda)^n \approx e^{-2\mu\lambda n} \le \varepsilon$, which gives $n \approx \log(1/\varepsilon) / (\mu\lambda)$. The recent term is a sum of $n$ gradients of rank at most $B$, so:</p>

    <div class="eq-highlight">
      $$\text{rank}_\varepsilon(W_T) \;\lesssim\; \frac{B\,\log(1/\varepsilon)}{\mu\lambda}$$
    </div>

    <p>This captures the correct qualitative dependencies: <strong>smaller batch size</strong>, <strong>larger learning rate</strong>, or <strong>larger weight decay</strong> all shorten the effective memory and produce lower effective rank.</p>

    <div class="paper-note">
      This bound is a structural heuristic, not a worst-case guarantee. In practice the rank is often even lower, because gradient directions are not independent — training on structured data concentrates updates in a small number of directions.
    </div>

    <h2>Part III: Shared operators</h2>

    <p>The rank-1 statement changes when the same matrix $W$ is reused multiple times within a single example. This happens in <strong>convolutions</strong> (same kernel applied at many spatial locations), <strong>self-attention projections</strong> ($W_Q$, $W_K$, $W_V$ applied to many tokens), and any other shared linear operator.</p>

    <p>In that case, $h(x) = g(Wf_1(x), \dots, Wf_R(x))$, and the chain rule gives:</p>

    <div class="math-display">
      $$\nabla_W \ell(h(x)) = \sum_{r=1}^R \delta_r(x)\, f_r(x)^\top, \qquad \text{rank}(\nabla_W \ell(h(x))) \le R$$
    </div>

    <p>For a mini-batch, $\text{rank}(G_t) \le \min(d_{\text{out}}, d_{\text{in}}, BR)$. The rest of the argument is unchanged — weight decay still exponentially suppresses old updates, so the current matrix remains close to a weighted sum of recent low-rank gradients. The one-use setting $R = 1$ is simply the cleanest case.</p>

    <h3>Why the local view is natural</h3>

    <p>The representation $h(x) = g(Wf(x))$ is not an artificial simplification. It is the natural local view of any layer: fix all other parameters, isolate the point where $W$ acts, and absorb everything before it into $f$ and everything after it into $g$. For fully connected layers this is immediate. For residual blocks, the dependence on $W$ still enters through $Wf(x)$, so the outer-product structure of the gradient is preserved.</p>

    <h2>What this does and does not say</h2>

    <p>This argument does <strong>not</strong> imply that every trained layer must be exactly low rank. Nor does it eliminate the influence of architecture, normalization, or data geometry.</p>

    <p>What it <em>does</em> provide is a broad structural reason that low-rank behavior should often appear in practice. Low rank is not an accident, and it is not merely a pattern discovered afterward by compression. It is built into the training dynamics through the interaction of stochastic gradients and weight decay.</p>

    <div class="compare-grid fade-in">
      <div class="compare-card" style="border-left:3px solid var(--teal);">
        <h4 style="color:var(--teal);">Why LoRA works</h4>
        <p>If training already pushes layers toward low rank, then fine-tuning with an explicit low-rank parameterization ($W = W_0 + AB$) is not imposing an alien constraint — it is matching the structure that SGD would have produced anyway.</p>
      </div>
      <div class="compare-card" style="border-left:3px solid var(--coral);">
        <h4 style="color:var(--coral);">Why compression works</h4>
        <p>Post-training low-rank compression (SVD truncation) is often surprisingly effective. This result explains why: it is not inventing structure but extracting structure that training had already encouraged.</p>
      </div>
    </div>

    <div class="takeaway">
      <h3>Takeaway</h3>
      <p>SGD with weight decay does more than optimize the loss. It quietly pushes layers toward low-rank structure. The mechanism operates in three parts:</p>
      <p><strong>Low-rank updates.</strong> Each stochastic gradient is low rank — rank 1 per example, rank $B$ per mini-batch, rank $BR$ for shared operators.</p>
      <p><strong>Finite memory.</strong> Weight decay exponentially forgets old updates, limiting the effective memory to roughly $1/(\mu\lambda)$ steps.</p>
      <p><strong>Low-rank layers.</strong> The current weight matrix is dominated by a short history of low-rank corrections, yielding an effective rank of roughly $B\log(1/\varepsilon)/(\mu\lambda)$.</p>
      <p>Low-rank structure in trained neural networks is not just an empirical curiosity. It is a natural consequence of how SGD with weight decay writes and forgets directions over time.</p>
    </div>

  </article>

  <div class="post-footer">
    <p>Originally published on <a href="https://dlfundamentals.github.io/blog/">Theory/Simplified</a> &middot; Based on <a href="https://openreview.net/forum?id=xhW2WyPhRP">Galanti et al., CPAL 2025</a></p>
  </div>

</div>

<script>
(function(){
  var scopeEl = document.querySelector('.post-scope');

  var katexCheck = setInterval(function() {
    if (typeof renderMathInElement !== 'undefined' && scopeEl) {
      clearInterval(katexCheck);
      renderMathInElement(scopeEl, {
        delimiters: [
          {left: '$$', right: '$$', display: true},
          {left: '$', right: '$', display: false}
        ],
        throwOnError: false
      });
    }
  }, 100);

  var N = 8;
  var W = [];
  var t = 0;
  var playing = false;
  var playInterval = null;
  var gradHistory = [];
  var maxHistory = 30;

  var B = 2, mu = 0.08, wd = 0.05;

  function zeros(n) {
    var m = [];
    for (var i = 0; i < n; i++) {
      m.push([]);
      for (var j = 0; j < n; j++) m[i].push(0);
    }
    return m;
  }

  function randn() {
    var u = 0, v = 0;
    while (u === 0) u = Math.random();
    while (v === 0) v = Math.random();
    return Math.sqrt(-2.0 * Math.log(u)) * Math.cos(2.0 * Math.PI * v);
  }

  function makeGrad(batchSize) {
    var G = zeros(N);
    for (var b = 0; b < batchSize; b++) {
      var d = [], f = [];
      for (var i = 0; i < N; i++) {
        d.push(randn());
        f.push(randn());
      }
      for (var i = 0; i < N; i++) {
        for (var j = 0; j < N; j++) {
          G[i][j] += d[i] * f[j] / batchSize;
        }
      }
    }
    return G;
  }

  function computeSVD(M) {
    var MtM = zeros(N);
    for (var i = 0; i < N; i++) {
      for (var j = 0; j < N; j++) {
        var s = 0;
        for (var k = 0; k < N; k++) s += M[k][i] * M[k][j];
        MtM[i][j] = s;
      }
    }

    var svals = [];
    var deflated = [];
    for (var i = 0; i < N; i++) {
      deflated.push([]);
      for (var j = 0; j < N; j++) deflated[i].push(MtM[i][j]);
    }

    for (var sv = 0; sv < N; sv++) {
      var v = [];
      for (var i = 0; i < N; i++) v.push(randn());
      var norm = Math.sqrt(v.reduce(function(s, x){ return s + x * x; }, 0));
      v = v.map(function(x){ return x / norm; });

      for (var iter = 0; iter < 50; iter++) {
        var nv = [];
        for (var i = 0; i < N; i++) {
          var s = 0;
          for (var j = 0; j < N; j++) s += deflated[i][j] * v[j];
          nv.push(s);
        }
        norm = Math.sqrt(nv.reduce(function(s, x){ return s + x * x; }, 0));
        if (norm < 1e-12) break;
        v = nv.map(function(x){ return x / norm; });
      }

      svals.push(Math.sqrt(Math.max(0, norm)));

      for (var i = 0; i < N; i++) {
        for (var j = 0; j < N; j++) {
          deflated[i][j] -= norm * v[i] * v[j];
        }
      }
    }

    svals.sort(function(a, b){ return b - a; });
    return svals;
  }

  function effectiveRank(svals) {
    var total = svals.reduce(function(s, x){ return s + x; }, 0);
    if (total < 1e-10) return 0;
    var H = 0;
    for (var i = 0; i < svals.length; i++) {
      var p = svals[i] / total;
      if (p > 1e-10) H -= p * Math.log(p);
    }
    return Math.exp(H);
  }

  function initSim() {
    W = zeros(N);
    t = 0;
    gradHistory = [];
    updateViz();
  }

  window.stepOnce = function() {
    var decay = 1 - 2 * mu * wd;
    if (decay < 0.01) decay = 0.01;
    var G = makeGrad(B);

    for (var i = 0; i < N; i++) {
      for (var j = 0; j < N; j++) {
        W[i][j] = decay * W[i][j] - mu * G[i][j];
      }
    }

    var gNorm = 0;
    for (var i = 0; i < N; i++) {
      for (var j = 0; j < N; j++) {
        gNorm += G[i][j] * G[i][j];
      }
    }
    gradHistory.push(Math.sqrt(gNorm));
    if (gradHistory.length > maxHistory) gradHistory.shift();

    t++;
    updateViz();
  };

  window.togglePlay = function() {
    playing = !playing;
    var btn = document.getElementById('play-btn');
    if (playing) {
      if (btn) {
        btn.textContent = 'Pause';
        btn.classList.add('active');
      }
      playInterval = setInterval(window.stepOnce, 200);
    } else {
      if (btn) {
        btn.textContent = 'Play';
        btn.classList.remove('active');
      }
      clearInterval(playInterval);
    }
  };

  window.resetSim = function() {
    if (playing) window.togglePlay();
    initSim();
  };

  window.updateParam = function() {
    B = parseInt(document.getElementById('b-slider').value, 10);
    mu = parseInt(document.getElementById('lr-slider').value, 10) / 100;
    wd = parseInt(document.getElementById('wd-slider').value, 10) / 100;

    document.getElementById('b-val').textContent = B;
    document.getElementById('lr-val').textContent = mu.toFixed(2);
    document.getElementById('wd-val').textContent = wd.toFixed(2);
  };

  function valToColor(v) {
    var clamp = Math.max(-1, Math.min(1, v * 3));
    if (clamp > 0) {
      var r = Math.round(200 + 55 * (1 - clamp));
      var g = Math.round(100 + 100 * (1 - clamp));
      var b = Math.round(60 + 140 * (1 - clamp));
      return 'rgb(' + r + ',' + g + ',' + b + ')';
    } else {
      var amt = -clamp;
      var r = Math.round(60 + 140 * (1 - amt));
      var g = Math.round(120 + 80 * (1 - amt));
      var b = Math.round(180 + 75 * (1 - amt));
      return 'rgb(' + r + ',' + g + ',' + b + ')';
    }
  }

  function updateViz() {
    var hm = document.getElementById('heatmap');
    if (!hm) return;

    if (hm.children.length === 0) {
      for (var i = 0; i < N * N; i++) {
        var cell = document.createElement('div');
        cell.className = 'heatmap-cell';
        hm.appendChild(cell);
      }
    }

    for (var i = 0; i < N; i++) {
      for (var j = 0; j < N; j++) {
        hm.children[i * N + j].style.backgroundColor = valToColor(W[i][j]);
      }
    }

    var svals = computeSVD(W);
    var maxSV = Math.max.apply(null, svals) || 1;
    var svContainer = document.getElementById('sv-bars');

    if (svContainer.children.length === 0) {
      for (var i = 0; i < N; i++) {
        var wrap = document.createElement('div');
        wrap.className = 'sv-bar-wrap';
        var bar = document.createElement('div');
        bar.className = 'sv-bar';
        var label = document.createElement('div');
        label.className = 'sv-label';
        label.textContent = 'σ' + (i + 1);
        wrap.appendChild(bar);
        wrap.appendChild(label);
        svContainer.appendChild(wrap);
      }
    }

    for (var i = 0; i < N; i++) {
      var bar = svContainer.children[i].querySelector('.sv-bar');
      var h = maxSV > 1e-10 ? (svals[i] / maxSV * 100) : 0;
      bar.style.height = Math.max(2, h) + 'px';
      var intensity = maxSV > 1e-10 ? svals[i] / maxSV : 0;
      var r = Math.round(90 + 110 * intensity);
      var g = Math.round(74 - 30 * intensity);
      var b = Math.round(184 - 40 * intensity);
      bar.style.backgroundColor = 'rgb(' + r + ',' + g + ',' + b + ')';
    }

    var er = effectiveRank(svals);
    document.getElementById('eff-rank').textContent = er < 0.01 ? '0' : er.toFixed(1);

    var decay = Math.max(0.01, 1 - 2 * mu * wd);
    document.getElementById('decay-factor').textContent = decay.toFixed(3);

    var memWin = mu * wd > 1e-8 ? Math.round(Math.log(100) / (mu * wd)) : '∞';
    document.getElementById('mem-window').textContent = memWin === '∞' ? '∞' : '~' + memWin;

    document.getElementById('step-counter').textContent = 't = ' + t;

    var tl = document.getElementById('timeline');
    tl.innerHTML = '';
    for (var i = 0; i < gradHistory.length; i++) {
      var block = document.createElement('div');
      block.className = 'timeline-block';
      var age = gradHistory.length - 1 - i;
      var opacity = Math.max(0.08, Math.pow(decay, age));
      var gNorm = gradHistory[i];
      block.style.height = Math.max(4, Math.min(32, gNorm * 12)) + 'px';
      block.style.opacity = opacity;
      block.style.backgroundColor = 'var(--purple)';
      tl.appendChild(block);
    }
  }

  if ('IntersectionObserver' in window) {
    var observer = new IntersectionObserver(function(entries) {
      entries.forEach(function(entry) {
        if (entry.isIntersecting) entry.target.classList.add('visible');
      });
    }, { threshold: 0.15 });

    scopeEl.querySelectorAll('.fade-in').forEach(function(el) {
      observer.observe(el);
    });
  }

  initSim();
})();
</script>
