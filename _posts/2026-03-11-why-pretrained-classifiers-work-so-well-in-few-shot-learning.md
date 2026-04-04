<link rel="preconnect" href="https://cdn.jsdelivr.net" crossorigin>
<link rel="preconnect" href="https://cdnjs.cloudflare.com" crossorigin>
<link rel="preconnect" href="https://fonts.googleapis.com" crossorigin>
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.min.css">
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.min.js"></script>
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/contrib/auto-render.min.js"></script>
<link href="https://fonts.googleapis.com/css2?family=Lora:ital,wght@0,400;0,500;0,600;1,400;1,500&family=IBM+Plex+Mono:wght@400;500&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&display=swap" rel="stylesheet">

<style>
.ps{--bg:#f6f3ee;--bg-warm:#f0ece4;--surface:#ede9e0;--surface-2:#e8e3d8;--border:#d8d2c6;--border-lt:#e4dfd4;--text:#18160f;--text-soft:#3a3628;--muted:#7a7060;--muted-lt:#a09880;--accent:#1e4f7a;--accent-mid:#2a6199;--accent-soft:#d4e6f5;--accent-xs:#ebf4fc;--gold:#b8860b;--gold-soft:#fdf4d8;--gold-bd:#d4a820;--green:#2a6645;--green-soft:#e4f0ea;--teal:#1a7a5c;--teal-soft:#e4f2ec;--amber:#a06810;--amber-soft:#faf0da;--serif:'Lora',Georgia,serif;--sans:'DM Sans',-apple-system,sans-serif;--mono:'IBM Plex Mono',monospace;}
.ps,.ps *,.ps *::before,.ps *::after{box-sizing:border-box;}
.ps{width:100%;max-width:100%;background:var(--bg);color:var(--text);font-family:var(--sans);font-weight:300;font-size:17px;line-height:1.78;-webkit-font-smoothing:antialiased;overflow-x:clip;}
.ps ::selection{background:var(--accent-soft);color:var(--text);}
.ps a{color:var(--accent-mid);text-decoration:none;}
.ps a:hover{text-decoration:underline;}
.ps .top-bar{height:3px;background:linear-gradient(90deg,#1e4f7a 0%,#2a6199 55%,#b8860b 100%);}
.ps .hero{max-width:820px;margin:0 auto;padding:3.5rem 2.5rem 2.5rem;border-bottom:1px solid var(--border);}
.ps .hero-eyebrow{font-family:var(--mono);font-size:10.5px;font-weight:500;letter-spacing:.12em;text-transform:uppercase;color:var(--muted);margin-bottom:1.1rem;display:flex;align-items:center;gap:.5rem;}
.ps .hero-eyebrow::before{content:'';display:inline-block;width:18px;height:2px;background:var(--gold);flex-shrink:0;}
.ps .hero h1{font-family:var(--serif);font-size:clamp(1.9rem,4.5vw,2.9rem);font-weight:600;line-height:1.13;letter-spacing:-.025em;color:var(--text);margin:0 0 1.3rem;max-width:680px;}
.ps .hero h1 em{font-style:italic;font-weight:400;color:var(--accent);}
.ps .hero-subtitle{font-size:1.08rem;color:var(--muted);font-style:italic;font-weight:300;max-width:600px;line-height:1.68;border-left:2px solid var(--border);padding-left:1.1rem;margin:0 0 1.6rem;}
.ps .hero-meta{font-family:var(--mono);font-size:11px;color:var(--muted-lt);display:flex;gap:1.25rem;flex-wrap:wrap;align-items:center;}
.ps .paper-badge{display:inline-flex;align-items:center;gap:5px;background:var(--accent-soft);color:var(--accent);border:1px solid #b5cfe6;padding:3px 10px;border-radius:20px;font-weight:500;font-size:10.5px;}
.ps article{max-width:820px;margin:0 auto;padding:2.5rem 2.5rem 6rem;}
.ps article p{margin:0 0 1.15rem;font-size:1.02rem;}
.ps article p.lead::first-letter{font-family:var(--serif);font-size:3.6em;font-weight:600;line-height:.75;float:left;margin:.06em .1em 0 0;color:var(--accent);}
.ps article h2{font-family:var(--serif);font-size:1.48rem;font-weight:500;line-height:1.22;letter-spacing:-.01em;margin:2.75rem 0 1rem;padding-top:2rem;border-top:1px solid var(--border);color:var(--text);}
.ps article h2:first-child{border-top:none;padding-top:0;margin-top:0;}
.ps article h3{font-family:var(--mono);font-size:.73rem;font-weight:500;letter-spacing:.1em;text-transform:uppercase;color:var(--muted);margin:2rem 0 .65rem;}
.ps strong{font-weight:500;}
.ps code{font-family:var(--mono);font-size:.85em;background:var(--surface);border:1px solid var(--border-lt);padding:1px 6px;border-radius:3px;color:var(--text-soft);}
.ps .callout{background:var(--gold-soft);border-left:3px solid var(--gold-bd);padding:1.05rem 1.3rem;border-radius:0 7px 7px 0;margin:1.75rem 0;font-size:.98rem;line-height:1.68;color:var(--text-soft);}
.ps .callout strong{display:block;margin-bottom:.3rem;font-weight:500;color:var(--text);}
.ps .finding{background:var(--accent-xs);border:1px solid #c0d9ef;border-left:3px solid var(--accent-mid);border-radius:0 7px 7px 0;padding:1rem 1.3rem;margin:1.6rem 0;font-size:.95rem;color:var(--text-soft);}
.ps .finding-label{font-family:var(--mono);font-size:.68rem;font-weight:500;letter-spacing:.1em;text-transform:uppercase;color:var(--accent);margin-bottom:.4rem;}
.ps .math-display{background:var(--surface);border:1px solid var(--border);border-radius:8px;padding:1.35rem 1.75rem;margin:1.6rem 0;text-align:center;overflow-x:auto;}
.ps .math-label{font-family:var(--mono);font-size:.68rem;font-weight:500;letter-spacing:.1em;text-transform:uppercase;color:var(--muted);margin-bottom:.65rem;}
.ps .eq-highlight{background:var(--gold-soft);border:1px solid var(--gold-bd);border-radius:8px;padding:1.15rem 1.75rem;margin:1.6rem 0;text-align:center;overflow-x:auto;}
.ps .steps{margin:1.5rem 0;}
.ps .step{display:flex;gap:1rem;margin-bottom:1.15rem;align-items:flex-start;}
.ps .step-num{background:var(--accent);color:white;width:26px;height:26px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-family:var(--mono);font-size:.7rem;font-weight:500;flex-shrink:0;margin-top:.12rem;box-shadow:0 1px 5px rgba(30,79,122,.22);}
.ps .step-body{flex:1;}
.ps .step-title{font-weight:500;margin-bottom:.12rem;font-size:.97rem;}
.ps .step-desc{font-size:.9rem;color:var(--muted);line-height:1.62;font-weight:300;}
.ps .paper-note{font-family:var(--mono);font-size:.76rem;color:var(--accent);background:var(--accent-xs);border:1px solid #c0d9ef;padding:.8rem 1rem .8rem 2.1rem;border-radius:5px;margin:1.1rem 0 1.6rem;line-height:1.7;position:relative;}
.ps .paper-note::before{content:"◆";position:absolute;left:.8rem;top:.85rem;font-size:8px;}
.ps .paper-note a{color:var(--accent);font-weight:500;}
.ps .pull-quote{font-family:var(--serif);font-size:1.2rem;font-style:italic;color:var(--accent);border-top:2px solid var(--accent-soft);border-bottom:2px solid var(--accent-soft);padding:1.1rem 0;margin:2rem 0;line-height:1.55;text-align:center;}
.ps .figcaption{font-family:var(--mono);font-size:10.5px;color:var(--muted-lt);line-height:1.6;margin-top:.75rem;margin-bottom:2rem;letter-spacing:.01em;}

/* ── 3D ── */
.ps .nc3d-wrap{position:relative;border-radius:12px;overflow:hidden;background:#0d0c0a;margin:1.75rem 0;aspect-ratio:16/10;border:1px solid var(--border);}
.ps .nc3d-wrap canvas{display:block;width:100%;height:100%;}
.ps .nc3d-legend{position:absolute;top:12px;left:14px;display:flex;gap:8px;flex-wrap:wrap;z-index:2;}
.ps .nc3d-legend span{font-family:var(--mono);font-size:9.5px;display:flex;align-items:center;gap:3px;}
.ps .nc3d-dot{width:7px;height:7px;border-radius:50%;display:inline-block;}
.ps .nc3d-ring{width:7px;height:7px;border-radius:50%;display:inline-block;border:1.5px solid;background:transparent;}
.ps .nc3d-info{position:absolute;top:12px;right:14px;text-align:right;z-index:2;}
.ps .nc3d-hud{position:absolute;bottom:10px;left:12px;right:12px;display:flex;flex-direction:column;gap:5px;z-index:2;}
.ps .nc3d-stats{display:flex;gap:4px;}
.ps .nc3d-st{flex:1;padding:5px 8px;background:rgba(10,10,8,.75);backdrop-filter:blur(8px);border-radius:5px;border:.5px solid rgba(255,255,255,.06);}
.ps .nc3d-st-l{font-family:var(--mono);font-size:8px;color:#6a6460;letter-spacing:.06em;text-transform:uppercase;}
.ps .nc3d-st-v{font-family:var(--mono);font-size:13px;font-weight:500;color:#e8e2d8;margin-top:1px;}
.ps .nc3d-slider-row{display:flex;align-items:center;gap:8px;padding:6px 14px;background:rgba(10,10,8,.75);backdrop-filter:blur(8px);border-radius:7px;border:.5px solid rgba(255,255,255,.06);}
.ps .nc3d-slider-row input[type=range]{flex:1;height:3px;-webkit-appearance:none;background:rgba(255,255,255,.18);border-radius:2px;outline:none;cursor:pointer;}
.ps .nc3d-slider-row input[type=range]::-webkit-slider-thumb{-webkit-appearance:none;width:14px;height:14px;border-radius:50%;background:#d4a820;cursor:pointer;}

/* ── Gen stepper ── */
.ps .gen-stepper{margin:1.75rem 0;}
.ps .gen-tabs{display:flex;border-radius:7px 7px 0 0;overflow:hidden;border:1px solid var(--border);border-bottom:none;}
.ps .gen-tab{flex:1;font-family:var(--mono);font-size:10.5px;font-weight:500;padding:8px 10px;border:none;border-right:1px solid var(--border);background:var(--surface);color:var(--muted-lt);cursor:pointer;transition:all .15s;text-align:center;letter-spacing:.02em;}
.ps .gen-tab:last-child{border-right:none;}
.ps .gen-tab:hover:not(.active){background:var(--surface-2);color:var(--text-soft);}
.ps .gen-tab.active{background:var(--bg);color:var(--accent);border-bottom:2px solid var(--gold);}
.ps .gen-panel{background:var(--bg);border:1px solid var(--border);border-top:none;border-radius:0 0 8px 8px;padding:1rem;min-height:280px;}
.ps .gen-desc{font-family:var(--sans);font-size:13px;color:var(--text-soft);line-height:1.6;margin-top:10px;font-weight:300;}

/* ── Takeaway ── */
.ps .takeaway{background:var(--text);color:#e8e2d8;padding:1.85rem 2rem;border-radius:12px;margin:2.75rem 0 1.5rem;position:relative;overflow:hidden;}
.ps .takeaway::before{content:'';position:absolute;top:0;left:0;right:0;height:3px;background:linear-gradient(90deg,var(--accent-mid),var(--gold));}
.ps .takeaway h3{font-family:var(--mono);font-size:.68rem;font-weight:500;letter-spacing:.12em;text-transform:uppercase;color:var(--gold-bd);margin:0 0 1.1rem;border:none;padding:0;}
.ps .takeaway p{color:#c2bdb4;margin-bottom:1rem;font-size:1rem;line-height:1.72;}
.ps .takeaway p:last-child{margin-bottom:0;}
.ps .takeaway strong{color:#e8e2d8;}
.ps .post-footer{max-width:820px;margin:0 auto;padding:1.5rem 2.5rem 3rem;text-align:center;border-top:1px solid var(--border);}
.ps .post-footer p{font-family:var(--mono);font-size:11px;color:var(--muted-lt);margin:0;}
.ps .post-footer a{color:var(--accent-mid);}
.ps hr{border:none;border-top:1px solid var(--border);margin:0;}
.ps .fade-in{opacity:0;transform:translateY(16px);transition:opacity .65s ease,transform .65s ease;}
.ps .fade-in.visible{opacity:1;transform:translateY(0);}
@media(max-width:700px){.ps .hero,.ps article,.ps .post-footer{padding-left:1.25rem;padding-right:1.25rem;}.ps .hero h1{font-size:1.8rem;}.ps .gen-tab{font-size:9px;padding:7px 6px;}}
</style>

<div class="ps">
<div class="top-bar"></div>

<div class="hero">
  <div class="hero-eyebrow">Pre-Training &middot; Few-Shot Learning &middot; Neural Collapse</div>
  <h1>Why Pretrained Classifiers Work So Well in <em>Few-Shot Learning</em></h1>
  <p class="hero-subtitle">A geometric explanation for why ordinary supervised pretraining transfers remarkably well to new classes with only a few labeled examples — and the precise quantity that controls when this works.</p>
  <div class="hero-meta">
    <span>By Tomer Galanti</span>
    <span>&middot;</span>
    <span>March 11, 2026</span>
    <span>&middot;</span>
    <span>14 min read</span>
    <span>&middot;</span>
    <span class="paper-badge">&#9670; Galanti, György, Hutter — arXiv 2022</span>
  </div>
</div>

<article>

  <h2>Introduction</h2>

  <p class="lead">Deep networks trained on large classification benchmarks such as ImageNet often transfer surprisingly well to new tasks. One trains on a large source dataset, freezes the learned representation, fits a simple head on only a handful of labeled examples from new classes, and the result often works remarkably well.</p>

  <p>From a theoretical perspective, however, this is not obvious. A classifier trained on ImageNet is optimized to separate the ImageNet classes. Why should the same representation make it easy to separate <strong>new</strong> classes that never appeared during training? And why should only a few labeled examples be enough?</p>

  <div class="callout">
    <strong>The main idea</strong>
    Few-shot transfer is not mysterious once the right geometric quantity is identified. What matters is not just that source classes are separated, but that their within-class variability is small relative to the distance between class means. If this geometry generalizes from source samples to source classes, and from source classes to unseen target classes, then few-shot learning becomes possible.
  </div>

  <p>The argument has three parts:</p>

  <div class="steps">
    <div class="step">
      <div class="step-num" style="background:#5a4ab8;">1</div>
      <div class="step-body">
        <div class="step-title">Classes as random draws.</div>
        <div class="step-desc">Model source and target classes as i.i.d. draws from a common population $\mathcal{D}$, so transfer to unseen classes becomes a well-posed question.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num" style="background:var(--teal);">2</div>
      <div class="step-body">
        <div class="step-title">Measure CDNV.</div>
        <div class="step-desc">The class-distance normalized variance compares within-class spread to between-class separation — the single quantity that controls transfer.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num">3</div>
      <div class="step-body">
        <div class="step-title">Double generalization.</div>
        <div class="step-desc">Small source CDNV generalizes twice: from samples to source distributions, then from source classes to unseen target classes.</div>
      </div>
    </div>
  </div>

  <div class="paper-note">
    Based on: T. Galanti, A. György, M. Hutter. <a href="https://arxiv.org/abs/2212.12532">&ldquo;Generalization Bounds for Few-Shot Transfer Learning with Pretrained Classifiers&rdquo;</a>, arXiv 2022.
  </div>

  <hr>

  <h2>Interactive — Neural collapse and transfer in 3D</h2>

  <p>The visualization below shows neural collapse unfolding in a 3D feature space. Drag the <strong>epoch slider</strong> to watch source-class features (filled dots) tighten into clusters while target-class features (rings) inherit the same geometry. Drag the viewport to rotate.</p>

  <div class="nc3d-wrap fade-in" id="nc3d-wrap">
    <div class="nc3d-legend">
      <span><span class="nc3d-dot" style="background:#7F77DD"></span><span style="color:#7F77DD">src 1</span></span>
      <span><span class="nc3d-dot" style="background:#1D9E75"></span><span style="color:#1D9E75">src 2</span></span>
      <span><span class="nc3d-dot" style="background:#D85A30"></span><span style="color:#D85A30">src 3</span></span>
      <span><span class="nc3d-dot" style="background:#378ADD"></span><span style="color:#378ADD">src 4</span></span>
      <span><span class="nc3d-ring" style="border-color:#D4537E"></span><span style="color:#D4537E">tgt A</span></span>
      <span><span class="nc3d-ring" style="border-color:#BA7517"></span><span style="color:#BA7517">tgt B</span></span>
      <span><span class="nc3d-ring" style="border-color:#639922"></span><span style="color:#639922">tgt C</span></span>
    </div>
    <div class="nc3d-info">
      <div style="font-family:var(--mono);font-size:9.5px;color:#6a6460;letter-spacing:.04em;">Drag to rotate</div>
      <div id="nc3d-stage" style="font-family:var(--mono);font-size:10.5px;color:#d4a820;font-weight:500;margin-top:3px;letter-spacing:.02em;">Pre-training: features scattered</div>
    </div>
    <canvas id="nc3d-canvas"></canvas>
    <div class="nc3d-hud">
      <div class="nc3d-stats">
        <div class="nc3d-st"><div class="nc3d-st-l">Source CDNV</div><div class="nc3d-st-v" id="nc3d-scdnv">—</div></div>
        <div class="nc3d-st"><div class="nc3d-st-l">Target CDNV</div><div class="nc3d-st-v" id="nc3d-tcdnv">—</div></div>
        <div class="nc3d-st"><div class="nc3d-st-l">NCC accuracy</div><div class="nc3d-st-v" id="nc3d-acc">—</div></div>
        <div class="nc3d-st"><div class="nc3d-st-l">Min class sep.</div><div class="nc3d-st-v" id="nc3d-sep">—</div></div>
      </div>
      <div class="nc3d-slider-row">
        <span style="font-family:var(--mono);font-size:9.5px;color:#6a6460;">Epoch 0</span>
        <input type="range" min="0" max="200" value="0" step="1" id="nc3d-epoch">
        <span style="font-family:var(--mono);font-size:9.5px;color:#6a6460;">200</span>
        <span id="nc3d-epval" style="font-family:var(--mono);font-size:11px;color:#d4a820;min-width:28px;text-align:right;">0</span>
      </div>
    </div>
  </div>

  <p class="figcaption"><strong>Fig. 1.</strong> 3D feature space during training. Source classes (filled dots, 4 classes × 18 samples) collapse toward an equiangular tight frame as the epoch slider advances. Target classes (rings, 3 classes × 5 samples) are unseen during training but inherit the same favorable geometry. CDNV drops as within-class variance shrinks and class means separate. At epoch ~170+, nearest-center classification achieves 100% on target classes.</p>

  <div class="steps">
    <div class="step">
      <div class="step-num" style="background:#5a4ab8;">→</div>
      <div class="step-body">
        <div class="step-title">Watch the collapse.</div>
        <div class="step-desc">Drag the epoch slider from 0 to ~120. Source features tighten into distinct clusters (NC1). Then from ~120 to 200, class means spread toward the vertices of a regular tetrahedron (NC2).</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num" style="background:var(--teal);">→</div>
      <div class="step-body">
        <div class="step-title">Watch the transfer.</div>
        <div class="step-desc">Target classes (rings) were never seen during training — yet they cluster and separate in lockstep with source classes. By epoch ~170, nearest-center classification hits 100% from just 5 examples per target class.</div>
      </div>
    </div>
  </div>

  <hr>

  <h2>Part I — A formal model for transfer to new classes</h2>

  <h3>Classes as random objects</h3>

  <p>To reason about transfer to new classes, we need a model relating source and target tasks. The key step is to treat classes themselves as random objects. There is an unknown distribution $\mathcal{D}$ over a collection $\mathcal{E}$ of class-conditional distributions. Source classes are i.i.d. draws $\tilde{P}_1, \dots, \tilde{P}_\ell \sim \mathcal{D}$, and target classes are new, independent draws $P_1, \dots, P_k \sim \mathcal{D}$.</p>

  <h3>Feature means and within-class variance</h3>

  <p>Let $f: \mathcal{X} \to \mathbb{R}^p$ be the learned feature map. For any class-conditional distribution $Q$:</p>

  <div class="math-display">
    <div class="math-label">Population feature mean and variance</div>
    $$\mu_f(Q) := \mathbb{E}_{x \sim Q}[f(x)], \qquad \text{Var}_f(Q) := \mathbb{E}_{x \sim Q}\|f(x) - \mu_f(Q)\|^2$$
  </div>

  <p>At transfer time, we freeze $f$. For each new target class $P_c$, we observe only a few labeled examples $S_c \sim P_c^n$ and classify by <strong>nearest empirical class center</strong>:</p>

  <div class="eq-highlight">
    $$h(x) = \arg\min_{c \in [k]} \|f(x) - \mu_f(S_c)\|$$
  </div>

  <hr>

  <h2>Part II — The geometric quantity that controls transfer</h2>

  <h3>Class-distance normalized variance (CDNV)</h3>

  <p>For two class-conditionals $Q_i$ and $Q_j$, define:</p>

  <div class="eq-highlight">
    $$V_f(Q_i, Q_j) = \frac{\text{Var}_f(Q_i)}{\|\mu_f(Q_i) - \mu_f(Q_j)\|^2}$$
  </div>

  <p>This compares within-class spread to between-class separation in a single scale-free number. Small CDNV is the favorable regime — same-class samples stay concentrated while different class means stay well separated.</p>

  <div class="pull-quote">&ldquo;CDNV is improved by neural collapse from both sides: NC1 shrinks the numerator, NC2 expands the denominator.&rdquo;</div>

  <h3>The double generalization</h3>

  <p>The stepper below illustrates how CDNV drives the two-stage generalization argument:</p>

  <div class="gen-stepper fade-in">
    <div class="gen-tabs">
      <button class="gen-tab active" onclick="showGen(0)">Step 1 — Empirical clustering</button>
      <button class="gen-tab" onclick="showGen(1)">Step 2 — Samples → distributions</button>
      <button class="gen-tab" onclick="showGen(2)">Step 3 — Source → target</button>
    </div>
    <div class="gen-panel">
      <canvas id="gen-canvas" style="width:100%;height:250px;"></canvas>
      <div class="gen-desc" id="gen-desc"></div>
    </div>
  </div>

  <p class="figcaption"><strong>Fig. 2.</strong> The double generalization in 2D. Step 1: Source training points cluster around empirical class centers. Step 2: With enough samples, this reflects the true class-conditional distributions (confidence ellipses). Step 3: Because classes are i.i.d. from the same population, unseen target classes inherit the same favorable geometry — and a few labeled examples suffice for nearest-center classification.</p>

  <hr>

  <h2>Part III — The transfer bound</h2>

  <h3>The main result</h3>

  <p>The transfer error of a pretrained feature map $f$ is controlled by the average empirical CDNV on source classes, together with terms quantifying the two generalization steps:</p>

  <div class="eq-highlight">
    $$\mathcal{L}_{\mathcal{D}}(f) \;\lesssim\; k\,\text{Avg}_{i \neq j}\, V_f(\tilde{S}_i, \tilde{S}_j) \;+\; \frac{k\,\mathcal{C}(f)}{\min_{i \neq j}\|\mu_f(\tilde{S}_i) - \mu_f(\tilde{S}_j)\|}\left(\frac{n^2}{\sqrt{m}} + \frac{1}{\sqrt{\ell}}\right)$$
  </div>

  <h3>What each term means</h3>

  <div class="finding">
    <div class="finding-label">Geometric term — $k \cdot \text{Avg}\, V_f$</div>
    Small when source training classes are tightly clustered relative to their separation. This is the observable signature of favorable few-shot transfer — visible in the 3D visualization as CDNV drops.
  </div>

  <div class="finding">
    <div class="finding-label">$1/\sqrt{m}$ — first generalization: samples → distributions</div>
    More samples per source class means empirical clustering better reflects the true geometry of the underlying source-class distributions.
  </div>

  <div class="finding">
    <div class="finding-label">$1/\sqrt{\ell}$ — second generalization: source → target classes</div>
    More source classes means the average geometry better reflects the full population $\mathcal{D}$, letting the argument extend to unseen target classes.
  </div>

  <div class="finding">
    <div class="finding-label">Min class distance</div>
    The minimum pairwise distance between source class means captures worst-case separation. Neural collapse pushes this up — the equiangular tight frame is the maximal configuration.
  </div>

  <p>The key point is that the bound remains informative even when $n$ is small. The downstream learner doesn't need to discover complicated structure from limited target data. That structure was already built into the feature space during pretraining.</p>

  <hr>

  <h2>What this does and does not claim</h2>

  <p>This theory does <strong>not</strong> say that every pretrained classifier transfers well to every target task, or that exact neural collapse must hold perfectly, or that source and target may come from unrelated class populations.</p>

  <p>What it <em>does</em> say is more precise: if the learned representation exhibits small CDNV on many source training classes, then this geometry first generalizes to the underlying source-class distributions and then, because classes are i.i.d. draws from a common population, to unseen target classes.</p>

  <div class="takeaway">
    <h3>Takeaway</h3>
    <p>Few-shot transfer works because pretraining learns a feature geometry that generalizes twice.</p>
    <p><strong>From source samples to source classes.</strong> If source training points cluster tightly and class means are well separated, then with enough samples per class this reflects the true geometry of the source-class distributions.</p>
    <p><strong>From source classes to unseen classes.</strong> Because classes are i.i.d. draws from a common population, favorable geometry on many source classes extends to new target classes.</p>
    <p><strong>From geometry to few-shot learning.</strong> Once unseen classes also form tight, well-separated clusters, a nearest-center classifier can learn them from only a handful of labeled examples.</p>
    <p>The hard part of few-shot learning is therefore not done at transfer time. It is done during pretraining, by shaping a representation whose clustering geometry survives both kinds of generalization.</p>
  </div>

</article>

<div class="post-footer">
  <p>Published on <a href="https://dlfundamentals.github.io/blog/">Theory/Simplified</a> &nbsp;&middot;&nbsp; Based on <a href="https://arxiv.org/abs/2212.12532">Galanti, György, Hutter — arXiv 2022</a></p>
</div>

</div>

<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
<script>
(function(){
  var root=document.querySelector('.ps');

  var ki=setInterval(function(){if(typeof renderMathInElement!=='undefined'&&root){clearInterval(ki);renderMathInElement(root,{delimiters:[{left:'$$',right:'$$',display:true},{left:'$',right:'$',display:false}],throwOnError:false});}},100);

  /* ── 3D ── */
  (function(){
    var canvas=document.getElementById('nc3d-canvas'),wrap=document.getElementById('nc3d-wrap');
    if(!canvas||!wrap||typeof THREE==='undefined')return;
    var scene=new THREE.Scene(),camera=new THREE.PerspectiveCamera(50,wrap.clientWidth/wrap.clientHeight,0.1,100);
    camera.position.set(0,0,7);
    var renderer=new THREE.WebGLRenderer({canvas:canvas,antialias:true,alpha:true});
    renderer.setSize(wrap.clientWidth,wrap.clientHeight);renderer.setPixelRatio(Math.min(window.devicePixelRatio,2));renderer.setClearColor(0x0d0c0a,1);
    var pivot=new THREE.Group();scene.add(pivot);
    var sd=42;function rn(){sd=(sd*1664525+1013904223)>>>0;return sd/4294967296;}function gs(){return Math.sqrt(-2*Math.log(rn()+1e-15))*Math.cos(6.2832*rn());}
    var R=2.0,srcETF=[new THREE.Vector3(0,R,0),new THREE.Vector3(R*Math.sqrt(8/9),-R/3,0),new THREE.Vector3(-R*Math.sqrt(2/9),-R/3,R*Math.sqrt(2/3)),new THREE.Vector3(-R*Math.sqrt(2/9),-R/3,-R*Math.sqrt(2/3))];
    var tgtETF=[new THREE.Vector3(R*0.7,R*0.5,R*0.3),new THREE.Vector3(-R*0.6,-R*0.2,R*0.6),new THREE.Vector3(R*0.1,-R*0.7,-R*0.5)];
    var srcColors=[0x7F77DD,0x1D9E75,0xD85A30,0x378ADD],tgtColors=[0xD4537E,0xBA7517,0x639922];
    var srcCV=srcColors.map(function(c){return new THREE.Color(c);}),tgtCV=tgtColors.map(function(c){return new THREE.Color(c);});
    var NSrc=18,NTgt=5,srcData=[],tgtData=[];
    sd=42;for(var ci=0;ci<4;ci++)for(var i=0;i<NSrc;i++)srcData.push({c:ci,start:new THREE.Vector3(gs()*1.3+(ci%2?0.5:-0.5),gs()*1.3+(ci<2?0.5:-0.5),gs()*1.3),end:srcETF[ci].clone()});
    sd=999;for(var ci=0;ci<3;ci++)for(var i=0;i<NTgt;i++)tgtData.push({c:ci,start:new THREE.Vector3(gs()*1.4+(ci===0?0.3:ci===1?-0.4:0.1),gs()*1.4+(ci===0?0.4:ci===1?-0.3:-0.5),gs()*1.4+(ci===0?0.2:ci===1?0.5:-0.3)),end:tgtETF[ci].clone()});
    var srcPos=new Float32Array(srcData.length*3),srcCol=new Float32Array(srcData.length*3);
    var tgtPos=new Float32Array(tgtData.length*3),tgtCol=new Float32Array(tgtData.length*3);
    for(var i=0;i<srcData.length;i++){var c=srcCV[srcData[i].c];srcCol[i*3]=c.r;srcCol[i*3+1]=c.g;srcCol[i*3+2]=c.b;}
    for(var i=0;i<tgtData.length;i++){var c=tgtCV[tgtData[i].c];tgtCol[i*3]=c.r;tgtCol[i*3+1]=c.g;tgtCol[i*3+2]=c.b;}
    var srcGeom=new THREE.BufferGeometry();srcGeom.setAttribute('position',new THREE.BufferAttribute(srcPos,3));srcGeom.setAttribute('color',new THREE.BufferAttribute(srcCol,3));
    pivot.add(new THREE.Points(srcGeom,new THREE.PointsMaterial({size:0.09,vertexColors:true,sizeAttenuation:true,transparent:true,opacity:0.85})));
    var tgtGeom=new THREE.BufferGeometry();tgtGeom.setAttribute('position',new THREE.BufferAttribute(tgtPos,3));tgtGeom.setAttribute('color',new THREE.BufferAttribute(tgtCol,3));
    pivot.add(new THREE.Points(tgtGeom,new THREE.PointsMaterial({size:0.13,vertexColors:true,sizeAttenuation:true,transparent:true,opacity:0.9})));
    var ringGeo=new THREE.RingGeometry(0.08,0.12,16),tgtRings=[];
    for(var i=0;i<tgtData.length;i++){var mat=new THREE.MeshBasicMaterial({color:tgtColors[tgtData[i].c],side:THREE.DoubleSide,transparent:true,opacity:0.9});var mesh=new THREE.Mesh(ringGeo,mat);pivot.add(mesh);tgtRings.push(mesh);}
    var mGeo=new THREE.SphereGeometry(0.08,12,12),srcMeans=srcETF.map(function(_,i){var m=new THREE.Mesh(mGeo,new THREE.MeshBasicMaterial({color:srcColors[i],transparent:true,opacity:0}));pivot.add(m);return m;});
    var tmGeo=new THREE.SphereGeometry(0.1,12,12),tgtMeans=tgtETF.map(function(_,i){var m=new THREE.Mesh(tmGeo,new THREE.MeshBasicMaterial({color:tgtColors[i],transparent:true,opacity:0}));pivot.add(m);return m;});
    var edgePairs=[];for(var i=0;i<4;i++)for(var j=i+1;j<4;j++)edgePairs.push([i,j]);
    var edges=edgePairs.map(function(p){var g=new THREE.BufferGeometry().setFromPoints([srcETF[p[0]],srcETF[p[1]]]);var l=new THREE.Line(g,new THREE.LineBasicMaterial({color:0x504e48,transparent:true,opacity:0}));l.visible=false;pivot.add(l);return l;});
    var axLen=0.5,axMat=new THREE.LineBasicMaterial({color:0x3a3830,transparent:true,opacity:0.25});
    [[axLen,0,0],[-axLen,0,0],[0,axLen,0],[0,-axLen,0],[0,0,axLen],[0,0,-axLen]].forEach(function(a){var g=new THREE.BufferGeometry().setFromPoints([new THREE.Vector3(0,0,0),new THREE.Vector3(a[0],a[1],a[2])]);pivot.add(new THREE.Line(g,axMat));});
    pivot.add(new THREE.Mesh(new THREE.SphereGeometry(0.03,8,8),new THREE.MeshBasicMaterial({color:0x3a3830})));
    var t=0;
    document.getElementById('nc3d-epoch').addEventListener('input',function(e){t=e.target.value/200;document.getElementById('nc3d-epval').textContent=e.target.value;});
    function ease(v){return v*v*(3-2*v);}
    function cdnv(pos,data,nC){var means=[];for(var c=0;c<nC;c++){var mx=0,my=0,mz=0,n=0;for(var i=0;i<data.length;i++){if(data[i].c===c){mx+=pos[i*3];my+=pos[i*3+1];mz+=pos[i*3+2];n++;}}means.push(n>0?{x:mx/n,y:my/n,z:mz/n}:{x:0,y:0,z:0});}var tv=0;for(var c=0;c<nC;c++){var v=0,n=0;for(var i=0;i<data.length;i++){if(data[i].c===c){v+=Math.pow(pos[i*3]-means[c].x,2)+Math.pow(pos[i*3+1]-means[c].y,2)+Math.pow(pos[i*3+2]-means[c].z,2);n++;}}if(n>0)tv+=v/n;}tv/=nC;var md=Infinity;for(var i=0;i<nC;i++)for(var j=i+1;j<nC;j++){var d=Math.pow(means[i].x-means[j].x,2)+Math.pow(means[i].y-means[j].y,2)+Math.pow(means[i].z-means[j].z,2);if(d<md)md=d;}return md>1e-10?tv/md:99;}
    var isDragging=false,prevX=0,prevY=0,rotX=0.3,rotY=0;
    canvas.addEventListener('pointerdown',function(e){isDragging=true;prevX=e.clientX;prevY=e.clientY;});
    window.addEventListener('pointerup',function(){isDragging=false;});
    canvas.addEventListener('pointermove',function(e){if(!isDragging)return;rotY+=(e.clientX-prevX)*0.008;rotX+=(e.clientY-prevY)*0.008;rotX=Math.max(-Math.PI/2,Math.min(Math.PI/2,rotX));prevX=e.clientX;prevY=e.clientY;});
    var autoRot=0;
    function animate(){requestAnimationFrame(animate);autoRot+=0.002;pivot.rotation.set(rotX,rotY+autoRot,0);
      var e=ease(Math.min(1,t)),eT=ease(Math.min(1,t*0.8));
      for(var i=0;i<srcData.length;i++){var d=srcData[i],sp=1-e*0.92;srcPos[i*3]=d.end.x+(d.start.x-srcETF[d.c].x)*sp;srcPos[i*3+1]=d.end.y+(d.start.y-srcETF[d.c].y)*sp;srcPos[i*3+2]=d.end.z+(d.start.z-srcETF[d.c].z)*sp;}srcGeom.attributes.position.needsUpdate=true;
      for(var i=0;i<tgtData.length;i++){var d=tgtData[i],sp=1-eT*0.85;tgtPos[i*3]=d.end.x+(d.start.x-tgtETF[d.c].x)*sp;tgtPos[i*3+1]=d.end.y+(d.start.y-tgtETF[d.c].y)*sp;tgtPos[i*3+2]=d.end.z+(d.start.z-tgtETF[d.c].z)*sp;tgtRings[i].position.set(tgtPos[i*3],tgtPos[i*3+1],tgtPos[i*3+2]);tgtRings[i].lookAt(camera.position);}tgtGeom.attributes.position.needsUpdate=true;
      for(var ci=0;ci<4;ci++){var mx=0,my=0,mz=0,n=0;for(var i=0;i<srcData.length;i++){if(srcData[i].c===ci){mx+=srcPos[i*3];my+=srcPos[i*3+1];mz+=srcPos[i*3+2];n++;}}srcMeans[ci].position.set(mx/n,my/n,mz/n);srcMeans[ci].material.opacity=Math.min(0.9,t*3);srcMeans[ci].scale.setScalar(0.6+t*2);}
      for(var ci=0;ci<3;ci++){var mx=0,my=0,mz=0,n=0;for(var i=0;i<tgtData.length;i++){if(tgtData[i].c===ci){mx+=tgtPos[i*3];my+=tgtPos[i*3+1];mz+=tgtPos[i*3+2];n++;}}tgtMeans[ci].position.set(mx/n,my/n,mz/n);tgtMeans[ci].material.opacity=Math.min(0.9,t*2.5);tgtMeans[ci].scale.setScalar(0.5+t*1.8);}
      edges.forEach(function(l){l.visible=t>0.4;l.material.opacity=Math.max(0,(t-0.4)/0.5)*0.18;});
      document.getElementById('nc3d-scdnv').textContent=cdnv(srcPos,srcData,4).toFixed(3);
      document.getElementById('nc3d-tcdnv').textContent=cdnv(tgtPos,tgtData,3).toFixed(3);
      var minSep=Infinity;for(var i=0;i<4;i++)for(var j=i+1;j<4;j++){var d=srcMeans[i].position.distanceTo(srcMeans[j].position);if(d<minSep)minSep=d;}document.getElementById('nc3d-sep').textContent=minSep.toFixed(2);
      if(t>0.3){var correct=0;for(var i=0;i<tgtData.length;i++){var p=new THREE.Vector3(tgtPos[i*3],tgtPos[i*3+1],tgtPos[i*3+2]),bd=Infinity,bc=-1;for(var ci=0;ci<3;ci++){var d=p.distanceTo(tgtMeans[ci].position);if(d<bd){bd=d;bc=ci;}}if(bc===tgtData[i].c)correct++;}var aEl=document.getElementById('nc3d-acc');aEl.textContent=Math.round(correct/tgtData.length*100)+'%';aEl.style.color=correct===tgtData.length?'#5dcaa5':'#e8e2d8';}else{document.getElementById('nc3d-acc').textContent='—';}
      var stage='Pre-training: features scattered';if(t>0.05&&t<=0.3)stage='Training: clusters forming';else if(t>0.3&&t<=0.6)stage='NC1: within-class collapse';else if(t>0.6&&t<=0.85)stage='NC2: means maximally separated';else if(t>0.85)stage='Transfer: NCC classifies few-shot';document.getElementById('nc3d-stage').textContent=stage;
      renderer.render(scene,camera);}
    animate();
    window.addEventListener('resize',function(){if(!wrap.clientWidth)return;camera.aspect=wrap.clientWidth/wrap.clientHeight;camera.updateProjectionMatrix();renderer.setSize(wrap.clientWidth,wrap.clientHeight);});
  })();

  /* ── Gen stepper ── */
  (function(){
    var genCanvas=document.getElementById('gen-canvas');if(!genCanvas)return;
    var genCtx=genCanvas.getContext('2d'),currentStep=0,rng=[];
    function gR(){var u=0,v=0;while(u===0)u=Math.random();while(v===0)v=Math.random();return Math.sqrt(-2*Math.log(u))*Math.cos(6.2832*v);}
    for(var i=0;i<500;i++)rng.push([gR(),gR()]);
    var descs=['During pretraining, source training samples concentrate around empirical class centers. The colored dots are training points; the crosses mark empirical class centers. This is the geometry we can directly observe.','With enough samples per source class, the empirical clustering reflects the true geometry of the underlying source-class distributions (shown as confidence ellipses). The observed clustering is not a finite-sample artifact — it represents real distributional structure. This is the first generalization: samples → distributions.','Because classes are i.i.d. draws from the same population 𝒟, new unseen target classes (right side) inherit the same favorable geometry. A few labeled examples (large dots) are enough to estimate their centers. This is the second generalization: source classes → target classes.'];
    var cls=['#5a4ab8','#1a7a5c','#c45028','#a06810','#d85a30'],clsF=['rgba(90,74,184,0.18)','rgba(26,122,92,0.18)','rgba(196,80,40,0.18)','rgba(160,104,16,0.18)','rgba(216,90,48,0.18)'];
    window.showGen=function(step){currentStep=step;root.querySelectorAll('.gen-tab').forEach(function(t,i){t.classList.toggle('active',i===step);});document.getElementById('gen-desc').textContent=descs[step];drawStep(step);};
    function drawStep(step){
      var dpr=window.devicePixelRatio||1,W=genCanvas.clientWidth,H=genCanvas.clientHeight;
      genCanvas.width=W*dpr;genCanvas.height=H*dpr;genCtx.setTransform(1,0,0,1,0,0);genCtx.scale(dpr,dpr);
      genCtx.fillStyle='#f6f3ee';genCtx.fillRect(0,0,W,H);
      var pad=28,srcW=(W-pad*3)*0.62,srcH=H-pad*2-16,srcX=pad,srcY=pad+16,sp=0.038,nP=13;
      genCtx.font='500 9.5px "IBM Plex Mono"';genCtx.fillStyle='#a09880';genCtx.textAlign='left';genCtx.fillText('SOURCE CLASSES',srcX,pad+10);
      var sCtr=[[0.2,0.25],[0.55,0.2],[0.85,0.25],[0.3,0.75],[0.7,0.78]];
      for(var c=0;c<5;c++){
        var cx=srcX+sCtr[c][0]*srcW,cy=srcY+sCtr[c][1]*srcH;
        if(step>=1){genCtx.beginPath();genCtx.ellipse(cx,cy,sp*srcW*3.8,sp*srcH*3.8,0,0,Math.PI*2);genCtx.fillStyle=clsF[c];genCtx.fill();genCtx.strokeStyle=cls[c];genCtx.lineWidth=0.6;genCtx.setLineDash([3,3]);genCtx.stroke();genCtx.setLineDash([]);}
        for(var s=0;s<nP;s++){var ri=(c*30+s)%rng.length;genCtx.beginPath();genCtx.arc(cx+rng[ri][0]*sp*srcW,cy+rng[ri][1]*sp*srcH,2,0,Math.PI*2);genCtx.fillStyle=step===0?cls[c]:clsF[c].replace(/[\d.]+\)$/,'0.5)');genCtx.fill();}
        genCtx.strokeStyle=cls[c];genCtx.lineWidth=1.8;genCtx.beginPath();genCtx.moveTo(cx-5,cy);genCtx.lineTo(cx+5,cy);genCtx.moveTo(cx,cy-5);genCtx.lineTo(cx,cy+5);genCtx.stroke();
      }
      if(step>=2){
        var tX=srcX+srcW+pad*1.5,tW=(W-pad*3)*0.38;
        genCtx.strokeStyle='#d8d2c6';genCtx.lineWidth=1;genCtx.setLineDash([4,4]);genCtx.beginPath();genCtx.moveTo(tX-pad*0.75,pad);genCtx.lineTo(tX-pad*0.75,H-pad+8);genCtx.stroke();genCtx.setLineDash([]);
        genCtx.font='500 9.5px "IBM Plex Mono"';genCtx.fillStyle='#a09880';genCtx.textAlign='left';genCtx.fillText('TARGET CLASSES (unseen)',tX,pad+10);
        var tCtr=[[0.3,0.28],[0.72,0.42],[0.45,0.78]],tCl=['#7f77dd','#5dcaa5','#f0997b'],tF=['rgba(127,119,221,0.18)','rgba(93,202,165,0.18)','rgba(240,153,123,0.18)'];
        for(var c=0;c<3;c++){var cx=tX+tCtr[c][0]*tW,cy=srcY+tCtr[c][1]*srcH;genCtx.beginPath();genCtx.ellipse(cx,cy,sp*tW*3.5,sp*srcH*3.5,0,0,Math.PI*2);genCtx.fillStyle=tF[c];genCtx.fill();genCtx.strokeStyle=tCl[c];genCtx.lineWidth=0.6;genCtx.setLineDash([3,3]);genCtx.stroke();genCtx.setLineDash([]);for(var s=0;s<4;s++){var ri=(c*40+s+200)%rng.length;genCtx.beginPath();genCtx.arc(cx+rng[ri][0]*sp*tW*0.8,cy+rng[ri][1]*sp*srcH*0.8,3.5,0,Math.PI*2);genCtx.fillStyle=tCl[c];genCtx.fill();}genCtx.strokeStyle=tCl[c];genCtx.lineWidth=2;genCtx.beginPath();genCtx.moveTo(cx-6,cy);genCtx.lineTo(cx+6,cy);genCtx.moveTo(cx,cy-6);genCtx.lineTo(cx,cy+6);genCtx.stroke();genCtx.font='400 9px "IBM Plex Mono"';genCtx.fillStyle=tCl[c];genCtx.textAlign='left';genCtx.fillText('4-shot',cx+8,cy+4);}
        var ay=H/2,ax1=srcX+srcW+pad*0.25,ax2=tX-pad*0.25;genCtx.strokeStyle='#a09880';genCtx.lineWidth=1;genCtx.beginPath();genCtx.moveTo(ax1,ay);genCtx.lineTo(ax2-6,ay);genCtx.stroke();genCtx.beginPath();genCtx.moveTo(ax2,ay);genCtx.lineTo(ax2-8,ay-4);genCtx.lineTo(ax2-8,ay+4);genCtx.fillStyle='#a09880';genCtx.fill();genCtx.font='400 9px "IBM Plex Mono"';genCtx.fillStyle='#a09880';genCtx.fillText('same 𝒟',ax1+3,ay-6);
      }
    }
    showGen(0);
    window.addEventListener('resize',function(){drawStep(currentStep);});
  })();

  if('IntersectionObserver' in window){var obs=new IntersectionObserver(function(entries){entries.forEach(function(e){if(e.isIntersecting)e.target.classList.add('visible');});},{threshold:.1});root.querySelectorAll('.fade-in').forEach(function(el){obs.observe(el);});}
})();
</script>
