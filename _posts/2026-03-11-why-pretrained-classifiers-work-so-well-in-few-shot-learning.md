<link rel="preconnect" href="https://cdn.jsdelivr.net" crossorigin>
<link rel="preconnect" href="https://cdnjs.cloudflare.com" crossorigin>
<link rel="preconnect" href="https://fonts.googleapis.com" crossorigin>
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>

<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.min.css">
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.min.js"></script>
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/contrib/auto-render.min.js"></script>
<link href="https://fonts.googleapis.com/css2?family=Newsreader:ital,wght@0,300;0,400;0,500;0,600;1,400&family=DM+Sans:wght@400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">

<style>
:root {
  --ink:#1a1714;--ink-soft:#4a4640;--ink-muted:#8a8680;
  --cream:#faf8f4;--paper:#ffffff;--rule:#e0dcd6;
  --accent:#c45028;--accent-soft:#f0e6df;
  --teal:#1a7a5c;--teal-soft:#e4f2ec;
  --purple:#5a4ab8;--purple-soft:#eeedfe;
  --amber:#a06810;--amber-soft:#faf0da;
  --coral:#d85a30;--coral-soft:#faece7;
  --serif:'Newsreader',Georgia,serif;
  --sans:'DM Sans',-apple-system,sans-serif;
  --mono:'JetBrains Mono',monospace;
}

.post-scope,
.post-scope *,
.post-scope *::before,
.post-scope *::after{
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

.post-scope code{
  font-family:var(--mono);
  font-size:.88em;
  background:#f0ede8;
  padding:2px 6px;
  border-radius:4px;
  color:var(--accent);
  white-space:nowrap;
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

.post-scope .paper-note a{
  color:var(--purple);
  font-weight:500;
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

.post-scope .compare-grid{
  display:grid;
  grid-template-columns:repeat(2,minmax(0,1fr));
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

.post-scope hr.section-rule{
  border:none;
  height:1px;
  background:var(--rule);
  margin:2.5rem 0;
}

.post-scope .figcaption{
  font-family:var(--sans);
  font-size:13px;
  color:var(--ink-muted);
  line-height:1.55;
  margin-top:10px;
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

.post-scope .ctrl-row{
  display:flex;
  gap:20px;
  flex-wrap:wrap;
  margin-bottom:1rem;
}

.post-scope .ctrl-group{
  flex:1;
  min-width:140px;
}

.post-scope .ctrl-group label{
  display:block;
  font-family:var(--sans);
  font-size:12px;
  color:var(--ink-muted);
  margin-bottom:4px;
}

.post-scope .ctrl-group .cv{
  font-family:var(--mono);
  font-size:13px;
  font-weight:500;
  color:var(--ink);
  float:right;
}

.post-scope .ctrl-group input[type=range]{
  width:100%;
  margin:0;
}

.post-scope .sim-btn{
  font-family:var(--sans);
  font-size:13px;
  font-weight:500;
  padding:5px 14px;
  border-radius:6px;
  border:.5px solid var(--rule);
  background:transparent;
  color:var(--ink-soft);
  cursor:pointer;
  transition:all .15s;
}

.post-scope .sim-btn:hover{
  background:var(--cream);
}

.post-scope .sim-btn.active{
  background:var(--accent);
  color:#fff;
  border-color:var(--accent);
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

.post-scope canvas{
  display:block;
  border-radius:8px;
  background:var(--cream);
}

.post-scope .gen-stepper{
  margin:1.2rem 0;
}

.post-scope .gen-tabs{
  display:flex;
  gap:0;
  margin-bottom:0;
}

.post-scope .gen-tab{
  flex:1;
  font-family:var(--sans);
  font-size:13px;
  font-weight:500;
  padding:10px 12px;
  border:1px solid var(--rule);
  background:transparent;
  color:var(--ink-muted);
  cursor:pointer;
  transition:all .15s;
  text-align:center;
}

.post-scope .gen-tab:first-child{
  border-radius:8px 0 0 0;
}

.post-scope .gen-tab:last-child{
  border-radius:0 8px 0 0;
}

.post-scope .gen-tab.active{
  background:var(--paper);
  color:var(--ink);
  border-bottom-color:var(--paper);
  font-weight:600;
}

.post-scope .gen-panel{
  background:var(--paper);
  border:1px solid var(--rule);
  border-top:none;
  border-radius:0 0 8px 8px;
  padding:1rem;
  min-height:340px;
  position:relative;
}

.post-scope .gen-panel canvas{
  margin:0 auto;
}

.post-scope .gen-desc{
  font-family:var(--sans);
  font-size:13px;
  color:var(--ink-soft);
  line-height:1.55;
  margin-top:12px;
}

.post-scope .nc3d-wrap{
  position:relative;
  border-radius:12px;
  overflow:hidden;
  background:#0a0a0a;
  margin:1.2rem 0;
  aspect-ratio:16/10;
}

.post-scope .nc3d-wrap canvas{
  display:block;
  width:100%;
  height:100%;
  background:#0a0a0a;
}

.post-scope .nc3d-legend{
  position:absolute;
  top:10px;
  left:12px;
  display:flex;
  gap:8px;
  flex-wrap:wrap;
  z-index:2;
}

.post-scope .nc3d-legend span{
  font-family:var(--sans);
  font-size:10px;
  display:flex;
  align-items:center;
  gap:3px;
}

.post-scope .nc3d-dot{
  width:8px;
  height:8px;
  border-radius:50%;
  display:inline-block;
}

.post-scope .nc3d-ring{
  width:8px;
  height:8px;
  border-radius:50%;
  display:inline-block;
  border:2px solid;
  background:transparent;
  box-sizing:border-box;
}

.post-scope .nc3d-info{
  position:absolute;
  top:10px;
  right:12px;
  text-align:right;
  z-index:2;
}

.post-scope .nc3d-hud{
  position:absolute;
  bottom:10px;
  left:12px;
  right:12px;
  display:flex;
  flex-direction:column;
  gap:6px;
  z-index:2;
}

.post-scope .nc3d-stats{
  display:flex;
  gap:4px;
}

.post-scope .nc3d-st{
  flex:1;
  padding:6px 8px;
  background:rgba(0,0,0,.55);
  backdrop-filter:blur(8px);
  border-radius:6px;
}

.post-scope .nc3d-st-l{
  font-family:var(--sans);
  font-size:9px;
  color:#999;
}

.post-scope .nc3d-st-v{
  font-family:var(--mono);
  font-size:13px;
  font-weight:500;
  color:#eee;
  margin-top:1px;
}

.post-scope .nc3d-slider-row{
  display:flex;
  align-items:center;
  gap:8px;
  padding:6px 14px;
  background:rgba(0,0,0,.55);
  backdrop-filter:blur(8px);
  border-radius:8px;
}

.post-scope .nc3d-slider-row input[type=range]{
  flex:1;
  height:3px;
  -webkit-appearance:none;
  appearance:none;
  background:rgba(255,255,255,.2);
  border-radius:2px;
  outline:none;
}

.post-scope .nc3d-slider-row input[type=range]::-webkit-slider-thumb{
  -webkit-appearance:none;
  width:14px;
  height:14px;
  border-radius:50%;
  background:#fff;
  cursor:pointer;
}

@media(max-width:700px){
  .post-scope .mechanism-grid{
    grid-template-columns:1fr;
  }
}

@media(max-width:600px){
  .post-scope .compare-grid{
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
    <div class="hero-eyebrow">Pre-Training &middot; Few-Shot Learning &middot; Neural Collapse</div>
    <h1>Why Pretrained Classifiers Work So Well in Few-Shot Learning</h1>
    <p class="hero-subtitle">A geometric explanation for why ordinary supervised pretraining can transfer remarkably well to new classes with only a few labeled examples — and the precise quantity that controls when this works.</p>
    <div class="hero-meta">
      <span>By Tomer Galanti</span>
      <span>&middot;</span>
      <span>March 11, 2026</span>
      <span>&middot;</span>
      <span>14 min read</span>
      <span>&middot;</span>
      <span class="paper-badge">◆ Based on Galanti, György, Hutter — arXiv 2022</span>
    </div>
  </div>

  <article>

    <h2 style="border-top:none;padding-top:0;margin-top:0">Introduction</h2>

    <p>Deep networks trained on large classification benchmarks such as ImageNet often transfer surprisingly well to new tasks. One trains on a large source dataset, freezes the learned representation, fits a simple head on only a handful of labeled examples from new classes, and the result often works remarkably well.</p>

    <p>From a theoretical perspective, however, this is not obvious. A classifier trained on ImageNet is optimized to separate the ImageNet classes. Why should the same representation also make it easy to separate <strong>new</strong> classes that never appeared during training? And why should only a few labeled examples be enough?</p>

    <div class="key-insight">
      The main idea is that few-shot transfer is not mysterious once the right geometric quantity is identified. What matters is not just that source classes are separated, but that their within-class variability is small relative to the distance between class means. If this geometry generalizes from source samples to source classes, and from source classes to unseen target classes, then few-shot learning becomes possible.
    </div>

    <p>The argument has three parts:</p>

    <div class="mechanism-grid fade-in">
      <div class="mechanism-card" style="border-top-color:var(--purple)">
        <div class="step-num" style="color:var(--purple)">Step 1</div>
        <h4>Classes as random draws</h4>
        <p>Model source and target classes as i.i.d. draws from a common population $\mathcal{D}$, so transfer to unseen classes becomes a well-posed question.</p>
      </div>
      <div class="mechanism-card" style="border-top-color:var(--teal)">
        <div class="step-num" style="color:var(--teal)">Step 2</div>
        <h4>Measure CDNV</h4>
        <p>The class-distance normalized variance compares within-class spread to between-class separation — the single quantity that controls transfer.</p>
      </div>
      <div class="mechanism-card" style="border-top-color:var(--coral)">
        <div class="step-num" style="color:var(--coral)">Step 3</div>
        <h4>Double generalization</h4>
        <p>Small source CDNV generalizes twice: from samples to source distributions, then from source classes to unseen target classes.</p>
      </div>
    </div>

    <div class="paper-note">
      Based on: T. Galanti, A. György, M. Hutter. <a href="https://arxiv.org/abs/2212.12532">"Generalization Bounds for Few-Shot Transfer Learning with Pretrained Classifiers"</a>, arXiv 2022.
    </div>

    <h2>Interactive: Neural collapse and transfer in 3D</h2>

    <p>The visualization below shows neural collapse unfolding in a 3D feature space. Drag the <strong>epoch slider</strong> to watch source-class features (filled dots) tighten into clusters while target-class features (rings) inherit the same geometry. Drag the viewport to rotate. The four source classes converge toward an equiangular tight frame; the three unseen target classes follow along — and nearest-center classification becomes possible from just a few examples.</p>

    <div class="nc3d-wrap fade-in" id="nc3d-wrap">
      <div class="nc3d-legend" id="nc3d-legend">
        <span><span class="nc3d-dot" style="background:#7F77DD"></span><span style="color:#7F77DD">src 1</span></span>
        <span><span class="nc3d-dot" style="background:#1D9E75"></span><span style="color:#1D9E75">src 2</span></span>
        <span><span class="nc3d-dot" style="background:#D85A30"></span><span style="color:#D85A30">src 3</span></span>
        <span><span class="nc3d-dot" style="background:#378ADD"></span><span style="color:#378ADD">src 4</span></span>
        <span><span class="nc3d-ring" style="border-color:#D4537E"></span><span style="color:#D4537E">tgt A</span></span>
        <span><span class="nc3d-ring" style="border-color:#BA7517"></span><span style="color:#BA7517">tgt B</span></span>
        <span><span class="nc3d-ring" style="border-color:#639922"></span><span style="color:#639922">tgt C</span></span>
      </div>
      <div class="nc3d-info">
        <div style="font-family:var(--sans);font-size:11px;color:var(--ink-muted)">Drag to rotate</div>
        <div id="nc3d-stage" style="font-family:var(--sans);font-size:12px;color:var(--ink);font-weight:500;margin-top:2px">Pre-training: features scattered</div>
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
          <span style="font-family:var(--sans);font-size:11px;color:var(--ink-muted)">Epoch 0</span>
          <input type="range" min="0" max="200" value="0" step="1" id="nc3d-epoch">
          <span style="font-family:var(--sans);font-size:11px;color:var(--ink-muted)">200</span>
          <span id="nc3d-epval" style="font-family:var(--mono);font-size:12px;color:var(--ink);min-width:28px;text-align:right">0</span>
        </div>
      </div>
    </div>

    <div class="figcaption" style="margin-top:-.5rem;margin-bottom:1.5rem">
      <strong>Figure 1.</strong> 3D feature space during training. Source classes (filled dots, 4 classes × 18 samples) collapse toward an equiangular tight frame as the epoch slider advances. Target classes (rings, 3 classes × 5 samples) are unseen during training but inherit the same favorable geometry. CDNV drops as within-class variance shrinks and class means separate. At epoch ~170+, nearest-center classification achieves 100% on the target classes.
    </div>

    <div class="compare-grid fade-in">
      <div class="compare-card" style="border-left:3px solid var(--purple)">
        <h4 style="color:var(--purple)">Watch: the collapse</h4>
        <p>Slowly drag the epoch slider from 0 to ~120. Source features tighten into distinct clusters (NC1). Then from ~120 to 200, class means spread toward the vertices of a regular tetrahedron (NC2).</p>
      </div>
      <div class="compare-card" style="border-left:3px solid var(--teal)">
        <h4 style="color:var(--teal)">Watch: the transfer</h4>
        <p>Target classes (rings) were never seen during training — yet they cluster and separate in lockstep with the source classes. By epoch ~170, nearest-center classification hits 100% from just 5 examples per target class.</p>
      </div>
    </div>

    <h2>Part I: A formal model for transfer to new classes</h2>

    <h3>Classes as random objects</h3>

    <p>To reason about transfer to new classes, one needs a model that relates source and target tasks. The key step is to treat classes themselves as random objects. There is an unknown distribution $\mathcal{D}$ over a collection $\mathcal{E}$ of class-conditional distributions. Source classes are i.i.d. draws $\tilde{P}_1, \dots, \tilde{P}_\ell \sim \mathcal{D}$, and target classes are new, independent draws $P_1, \dots, P_k \sim \mathcal{D}$.</p>

    <p>This captures the intended use of pretrained representations: we train on many source classes that are meant to represent a broader population, and then ask whether the learned feature map transfers to fresh classes drawn from the same population.</p>

    <h3>Notation for feature means and variances</h3>

    <p>Let $f: \mathcal{X} \to \mathbb{R}^p$ be the learned feature map. For any class-conditional distribution $Q$, define its population feature mean and within-class variance:</p>

    <div class="math-display">
      $$\mu_f(Q) := \mathbb{E}_{x \sim Q}[f(x)], \qquad \text{Var}_f(Q) := \mathbb{E}_{x \sim Q}\|f(x) - \mu_f(Q)\|^2$$
    </div>

    <p>At transfer time, we freeze $f$. For each new target class $P_c$, we observe only a few labeled examples $S_c \sim P_c^n$ and classify by <strong>nearest empirical class center</strong>:</p>

    <div class="eq-highlight">
      $$h(x) = \arg\min_{c \in [k]} \|f(x) - \mu_f(S_c)\|$$
    </div>

    <h2>Part II: The geometric quantity that controls transfer</h2>

    <h3>Class-distance normalized variance (CDNV)</h3>

    <p>For two class-conditionals $Q_i$ and $Q_j$, define:</p>

    <div class="eq-highlight">
      $$V_f(Q_i, Q_j) = \frac{\text{Var}_f(Q_i)}{\|\mu_f(Q_i) - \mu_f(Q_j)\|^2}$$
    </div>

    <p>This compares two competing effects: the within-class spread of $Q_i$ and the separation between class means $Q_i$ and $Q_j$. Small CDNV is the favorable regime — same-class samples stay concentrated, while different class means stay well separated.</p>

    <h3>Why CDNV is the right quantity</h3>

    <p>Few-shot learning with a nearest-center classifier succeeds only if a small number of labeled examples is enough to estimate each target class center accurately. That requires <strong>low within-class variability</strong> (samples stay close to their mean) and <strong>large between-class separation</strong> (different means stay far apart). CDNV combines both into a single scale-free quantity.</p>

    <h3>The connection to neural collapse</h3>

    <p>CDNV is closely connected to <strong>neural collapse</strong> geometry. The NC1 component says that features collapse toward their class mean (driving the numerator down). The NC2 component says class means become maximally separated, approaching a simplex equiangular tight frame (driving the denominator up). Neural collapse improves CDNV from both sides.</p>

    <h3>Visualizing the double generalization</h3>

    <p>The stepper below illustrates how CDNV drives the two-stage generalization argument. Click each tab to see the progression from observed clustering, through distributional generalization, to transfer:</p>

    <div class="gen-stepper fade-in">
      <div class="gen-tabs">
        <button class="gen-tab active" onclick="showGen(0)">Step 1: Empirical clustering</button>
        <button class="gen-tab" onclick="showGen(1)">Step 2: Samples → distributions</button>
        <button class="gen-tab" onclick="showGen(2)">Step 3: Source → target classes</button>
      </div>
      <div class="gen-panel">
        <canvas id="gen-canvas" style="width:100%;height:280px"></canvas>
        <div class="gen-desc" id="gen-desc"></div>
      </div>
    </div>

    <div class="figcaption" style="margin-top:-.5rem;margin-bottom:1.5rem">
      <strong>Figure 2.</strong> The double generalization in 2D. <strong>Step 1:</strong> Source training points cluster around empirical class centers. <strong>Step 2:</strong> With enough samples, this reflects the true class-conditional distributions (confidence ellipses). <strong>Step 3:</strong> Because classes are i.i.d. from the same population, unseen target classes inherit the same favorable geometry — and a few labeled examples suffice for nearest-center classification.
    </div>

    <h2>Part III: The transfer bound</h2>

    <h3>The main result</h3>

    <p>The transfer error of a pretrained feature map $f$ is controlled by the average empirical CDNV on the source classes, together with terms quantifying the two generalization steps:</p>

    <div class="eq-highlight">
      $$\mathcal{L}_{\mathcal{D}}(f) \;\lesssim\; k\,\text{Avg}_{i \neq j}\, V_f(\tilde{S}_i, \tilde{S}_j) \;+\; \frac{k\,\mathcal{C}(f)}{\min_{i \neq j}\|\mu_f(\tilde{S}_i) - \mu_f(\tilde{S}_j)\|}\left(\frac{n^2}{\sqrt{m}} + \frac{1}{\sqrt{\ell}}\right)$$
    </div>

    <h3>What each term means</h3>

    <div class="compare-grid fade-in">
      <div class="compare-card" style="border-left:3px solid var(--teal)">
        <h4 style="color:var(--teal)">Geometric term</h4>
        <p>$k \cdot \text{Avg}\, V_f$ is small when source training classes are tightly clustered relative to their separation. This is the observable signature of favorable few-shot transfer.</p>
      </div>
      <div class="compare-card" style="border-left:3px solid var(--purple)">
        <h4 style="color:var(--purple)">$1/\sqrt{m}$ — first generalization</h4>
        <p>More samples per source class means empirical clustering better reflects the true geometry of the underlying source-class distributions.</p>
      </div>
      <div class="compare-card" style="border-left:3px solid var(--coral)">
        <h4 style="color:var(--coral)">$1/\sqrt{\ell}$ — second generalization</h4>
        <p>More source classes means the average geometry better reflects the full population $\mathcal{D}$ — letting the argument extend to unseen target classes.</p>
      </div>
      <div class="compare-card" style="border-left:3px solid var(--amber)">
        <h4 style="color:var(--amber)">Min class distance</h4>
        <p>The minimum pairwise distance between source class means captures worst-case separation. Neural collapse pushes this up, strengthening the guarantee.</p>
      </div>
    </div>

    <p>The key point is that the bound remains informative even when $n$ — the number of target examples per class — is small. The downstream learner doesn't need to discover complicated structure from limited target data. That structure was already built into the feature space during pretraining.</p>

    <h2>What this does and does not claim</h2>

    <p>This theory does <strong>not</strong> say that every pretrained classifier transfers well to every target task, or that exact neural collapse must hold perfectly, or that source and target may come from unrelated class populations.</p>

    <p>What it <em>does</em> say is more precise: if the learned representation exhibits small CDNV on many source training classes, then this geometry first generalizes to the underlying source-class distributions and then, because classes are i.i.d. draws from a common population, to unseen target classes. In that regime, few-shot nearest-center classification succeeds.</p>

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
    <p>Originally published on <a href="https://dlfundamentals.github.io/blog/">Theory/Simplified</a> &middot; Based on <a href="https://arxiv.org/abs/2212.12532">Galanti, György, Hutter — arXiv 2022</a></p>
  </div>

</div>

<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
<script>
(function(){
  var scopeEl=document.querySelector('.post-scope');

  var ki=setInterval(function(){
    if(typeof renderMathInElement!=='undefined' && scopeEl){
      clearInterval(ki);
      renderMathInElement(scopeEl,{
        delimiters:[
          {left:'$$',right:'$$',display:true},
          {left:'$',right:'$',display:false}
        ],
        throwOnError:false
      });
    }
  },100);

  (function(){
    var canvas=document.getElementById('nc3d-canvas');
    var wrap=document.getElementById('nc3d-wrap');
    if(!canvas||!wrap||typeof THREE==='undefined')return;

    var scene=new THREE.Scene();
    var camera=new THREE.PerspectiveCamera(50,wrap.clientWidth/wrap.clientHeight,0.1,100);
    camera.position.set(0,0,7);
    var renderer=new THREE.WebGLRenderer({canvas:canvas,antialias:true,alpha:true});
    renderer.setSize(wrap.clientWidth,wrap.clientHeight);
    renderer.setPixelRatio(Math.min(window.devicePixelRatio,2));
    renderer.setClearColor(0x0a0a0a,1);

    var pivot=new THREE.Group();
    scene.add(pivot);

    var sd=42;
    function rn(){sd=(sd*1664525+1013904223)>>>0;return sd/4294967296}
    function gs(){return Math.sqrt(-2*Math.log(rn()+1e-15))*Math.cos(6.2832*rn())}

    var R=2.0;
    var srcETF=[
      new THREE.Vector3(0,R,0),
      new THREE.Vector3(R*Math.sqrt(8/9),-R/3,0),
      new THREE.Vector3(-R*Math.sqrt(2/9),-R/3,R*Math.sqrt(2/3)),
      new THREE.Vector3(-R*Math.sqrt(2/9),-R/3,-R*Math.sqrt(2/3))
    ];
    var tgtETF=[
      new THREE.Vector3(R*0.7,R*0.5,R*0.3),
      new THREE.Vector3(-R*0.6,-R*0.2,R*0.6),
      new THREE.Vector3(R*0.1,-R*0.7,-R*0.5)
    ];

    var srcColors=[0x7F77DD,0x1D9E75,0xD85A30,0x378ADD];
    var tgtColors=[0xD4537E,0xBA7517,0x639922];
    var srcColorsVec=srcColors.map(function(c){return new THREE.Color(c)});
    var tgtColorsVec=tgtColors.map(function(c){return new THREE.Color(c)});

    var NSrc=18,NTgt=5;
    var srcData=[],tgtData=[];

    sd=42;
    for(var ci=0;ci<4;ci++){
      for(var i=0;i<NSrc;i++){
        srcData.push({
          c:ci,
          start:new THREE.Vector3(gs()*1.3+(ci%2?0.5:-0.5),gs()*1.3+(ci<2?0.5:-0.5),gs()*1.3),
          end:srcETF[ci].clone()
        });
      }
    }

    sd=999;
    for(var ci=0;ci<3;ci++){
      for(var i=0;i<NTgt;i++){
        tgtData.push({
          c:ci,
          start:new THREE.Vector3(gs()*1.4+(ci===0?0.3:ci===1?-0.4:0.1),gs()*1.4+(ci===0?0.4:ci===1?-0.3:-0.5),gs()*1.4+(ci===0?0.2:ci===1?0.5:-0.3)),
          end:tgtETF[ci].clone()
        });
      }
    }

    var srcGeom=new THREE.BufferGeometry();
    var srcPos=new Float32Array(srcData.length*3);
    var srcCol=new Float32Array(srcData.length*3);
    for(var i=0;i<srcData.length;i++){
      var c=srcColorsVec[srcData[i].c];
      srcCol[i*3]=c.r;srcCol[i*3+1]=c.g;srcCol[i*3+2]=c.b;
    }
    srcGeom.setAttribute('position',new THREE.BufferAttribute(srcPos,3));
    srcGeom.setAttribute('color',new THREE.BufferAttribute(srcCol,3));
    var srcMat=new THREE.PointsMaterial({size:0.09,vertexColors:true,sizeAttenuation:true,transparent:true,opacity:0.8});
    pivot.add(new THREE.Points(srcGeom,srcMat));

    var tgtGeom=new THREE.BufferGeometry();
    var tgtPos=new Float32Array(tgtData.length*3);
    var tgtCol=new Float32Array(tgtData.length*3);
    for(var i=0;i<tgtData.length;i++){
      var c=tgtColorsVec[tgtData[i].c];
      tgtCol[i*3]=c.r;tgtCol[i*3+1]=c.g;tgtCol[i*3+2]=c.b;
    }
    tgtGeom.setAttribute('position',new THREE.BufferAttribute(tgtPos,3));
    tgtGeom.setAttribute('color',new THREE.BufferAttribute(tgtCol,3));
    pivot.add(new THREE.Points(tgtGeom,new THREE.PointsMaterial({size:0.14,vertexColors:true,sizeAttenuation:true,transparent:true,opacity:0.9})));

    var ringGeo=new THREE.RingGeometry(0.08,0.12,16);
    var tgtRings=[];
    for(var i=0;i<tgtData.length;i++){
      var mat=new THREE.MeshBasicMaterial({color:tgtColors[tgtData[i].c],side:THREE.DoubleSide,transparent:true,opacity:0.9});
      var mesh=new THREE.Mesh(ringGeo,mat);
      pivot.add(mesh);
      tgtRings.push(mesh);
    }

    var meanGeo=new THREE.SphereGeometry(0.08,12,12);
    var srcMeans=srcETF.map(function(_,i){
      var m=new THREE.Mesh(meanGeo,new THREE.MeshBasicMaterial({color:srcColors[i],transparent:true,opacity:0}));
      pivot.add(m);
      return m;
    });

    var tgtMeanGeo=new THREE.SphereGeometry(0.1,12,12);
    var tgtMeans=tgtETF.map(function(_,i){
      var m=new THREE.Mesh(tgtMeanGeo,new THREE.MeshBasicMaterial({color:tgtColors[i],transparent:true,opacity:0}));
      pivot.add(m);
      return m;
    });

    var edgePairs=[];
    for(var i=0;i<4;i++)for(var j=i+1;j<4;j++)edgePairs.push([i,j]);
    var edges=edgePairs.map(function(p){
      var g=new THREE.BufferGeometry().setFromPoints([srcETF[p[0]],srcETF[p[1]]]);
      var l=new THREE.Line(g,new THREE.LineBasicMaterial({color:0x666666,transparent:true,opacity:0}));
      l.visible=false;
      pivot.add(l);
      return l;
    });

    var axLen=0.5;
    var axMat=new THREE.LineBasicMaterial({color:0x444444,transparent:true,opacity:0.2});
    [[axLen,0,0],[-axLen,0,0],[0,axLen,0],[0,-axLen,0],[0,0,axLen],[0,0,-axLen]].forEach(function(a){
      var g=new THREE.BufferGeometry().setFromPoints([new THREE.Vector3(0,0,0),new THREE.Vector3(a[0],a[1],a[2])]);
      pivot.add(new THREE.Line(g,axMat));
    });
    pivot.add(new THREE.Mesh(new THREE.SphereGeometry(0.03,8,8),new THREE.MeshBasicMaterial({color:0x888888})));

    var t=0;
    var slider=document.getElementById('nc3d-epoch');

    function ease(v){return v*v*(3-2*v)}

    function computeCDNV(pos,data,nC){
      var means=[];
      for(var c=0;c<nC;c++){
        var mx=0,my=0,mz=0,n=0;
        for(var i=0;i<data.length;i++){
          if(data[i].c===c){
            mx+=pos[i*3];
            my+=pos[i*3+1];
            mz+=pos[i*3+2];
            n++;
          }
        }
        means.push(n>0?{x:mx/n,y:my/n,z:mz/n}:{x:0,y:0,z:0});
      }

      var tv=0;
      for(var c=0;c<nC;c++){
        var v=0,n=0;
        for(var i=0;i<data.length;i++){
          if(data[i].c===c){
            v+=Math.pow(pos[i*3]-means[c].x,2)+Math.pow(pos[i*3+1]-means[c].y,2)+Math.pow(pos[i*3+2]-means[c].z,2);
            n++;
          }
        }
        if(n>0)tv+=v/n;
      }
      tv/=nC;

      var md=Infinity;
      for(var i=0;i<nC;i++){
        for(var j=i+1;j<nC;j++){
          var d=Math.pow(means[i].x-means[j].x,2)+Math.pow(means[i].y-means[j].y,2)+Math.pow(means[i].z-means[j].z,2);
          if(d<md)md=d;
        }
      }
      return md>1e-10?tv/md:99;
    }

    function updateScene(){
      var e=ease(Math.min(1,t));
      var eTgt=ease(Math.min(1,t*0.8));

      for(var i=0;i<srcData.length;i++){
        var d=srcData[i];
        var spread=1-e*0.92;
        srcPos[i*3]=d.end.x+(d.start.x-srcETF[d.c].x)*spread;
        srcPos[i*3+1]=d.end.y+(d.start.y-srcETF[d.c].y)*spread;
        srcPos[i*3+2]=d.end.z+(d.start.z-srcETF[d.c].z)*spread;
      }
      srcGeom.attributes.position.needsUpdate=true;

      for(var i=0;i<tgtData.length;i++){
        var d=tgtData[i];
        var spread=1-eTgt*0.85;
        tgtPos[i*3]=d.end.x+(d.start.x-tgtETF[d.c].x)*spread;
        tgtPos[i*3+1]=d.end.y+(d.start.y-tgtETF[d.c].y)*spread;
        tgtPos[i*3+2]=d.end.z+(d.start.z-tgtETF[d.c].z)*spread;
        tgtRings[i].position.set(tgtPos[i*3],tgtPos[i*3+1],tgtPos[i*3+2]);
        tgtRings[i].lookAt(camera.position);
      }
      tgtGeom.attributes.position.needsUpdate=true;

      for(var ci=0;ci<4;ci++){
        var mx=0,my=0,mz=0,n=0;
        for(var i=0;i<srcData.length;i++){
          if(srcData[i].c===ci){
            mx+=srcPos[i*3];
            my+=srcPos[i*3+1];
            mz+=srcPos[i*3+2];
            n++;
          }
        }
        srcMeans[ci].position.set(mx/n,my/n,mz/n);
        srcMeans[ci].material.opacity=Math.min(0.9,t*3);
        srcMeans[ci].scale.setScalar(0.6+t*2);
      }

      for(var ci=0;ci<3;ci++){
        var mx=0,my=0,mz=0,n=0;
        for(var i=0;i<tgtData.length;i++){
          if(tgtData[i].c===ci){
            mx+=tgtPos[i*3];
            my+=tgtPos[i*3+1];
            mz+=tgtPos[i*3+2];
            n++;
          }
        }
        tgtMeans[ci].position.set(mx/n,my/n,mz/n);
        tgtMeans[ci].material.opacity=Math.min(0.9,t*2.5);
        tgtMeans[ci].scale.setScalar(0.5+t*1.8);
      }

      edges.forEach(function(l){
        l.visible=t>0.4;
        l.material.opacity=Math.max(0,(t-0.4)/0.5)*0.25;
      });

      document.getElementById('nc3d-scdnv').textContent=computeCDNV(srcPos,srcData,4).toFixed(3);
      document.getElementById('nc3d-tcdnv').textContent=computeCDNV(tgtPos,tgtData,3).toFixed(3);

      var minSep=Infinity;
      for(var i=0;i<4;i++){
        for(var j=i+1;j<4;j++){
          var d=srcMeans[i].position.distanceTo(srcMeans[j].position);
          if(d<minSep)minSep=d;
        }
      }
      document.getElementById('nc3d-sep').textContent=minSep.toFixed(2);

      if(t>0.3){
        var correct=0;
        for(var i=0;i<tgtData.length;i++){
          var p=new THREE.Vector3(tgtPos[i*3],tgtPos[i*3+1],tgtPos[i*3+2]);
          var bestD=Infinity,bestC=-1;
          for(var ci=0;ci<3;ci++){
            var d=p.distanceTo(tgtMeans[ci].position);
            if(d<bestD){
              bestD=d;
              bestC=ci;
            }
          }
          if(bestC===tgtData[i].c)correct++;
        }
        var accEl=document.getElementById('nc3d-acc');
        accEl.textContent=Math.round(correct/tgtData.length*100)+'%';
        accEl.style.color=correct===tgtData.length?'#5dcaa5':'#eee';
      }else{
        document.getElementById('nc3d-acc').textContent='—';
      }

      var stage='Pre-training: features scattered';
      if(t>0.05&&t<=0.3)stage='Training: clusters forming';
      else if(t>0.3&&t<=0.6)stage='NC1: within-class collapse';
      else if(t>0.6&&t<=0.85)stage='NC2: means maximally separated';
      else if(t>0.85)stage='Transfer: NCC classifies few-shot';
      document.getElementById('nc3d-stage').textContent=stage;
    }

    slider.addEventListener('input',function(e){
      t=e.target.value/200;
      document.getElementById('nc3d-epval').textContent=e.target.value;
    });

    var isDragging=false,prevX=0,prevY=0,rotX=0.3,rotY=0;
    canvas.addEventListener('pointerdown',function(e){
      isDragging=true;
      prevX=e.clientX;
      prevY=e.clientY;
    });
    window.addEventListener('pointerup',function(){isDragging=false});
    canvas.addEventListener('pointermove',function(e){
      if(!isDragging)return;
      rotY+=(e.clientX-prevX)*0.008;
      rotX+=(e.clientY-prevY)*0.008;
      rotX=Math.max(-Math.PI/2,Math.min(Math.PI/2,rotX));
      prevX=e.clientX;
      prevY=e.clientY;
    });

    var autoRot=0;
    function animate(){
      requestAnimationFrame(animate);
      autoRot+=0.002;
      pivot.rotation.set(rotX,rotY+autoRot,0);
      updateScene();
      renderer.render(scene,camera);
    }
    animate();

    window.addEventListener('resize',function(){
      if(!wrap.clientWidth)return;
      camera.aspect=wrap.clientWidth/wrap.clientHeight;
      camera.updateProjectionMatrix();
      renderer.setSize(wrap.clientWidth,wrap.clientHeight);
    });
  })();

  (function(){
    var genCanvas=document.getElementById('gen-canvas');
    if(!genCanvas)return;
    var genCtx=genCanvas.getContext('2d');
    var currentGenStep=0;
    var rng=[];

    function gRand(){
      var u=0,v=0;
      while(u===0)u=Math.random();
      while(v===0)v=Math.random();
      return Math.sqrt(-2*Math.log(u))*Math.cos(6.2832*v);
    }

    for(var i=0;i<500;i++)rng.push([gRand(),gRand()]);

    var genDescs=[
      'During pretraining, source training samples concentrate around empirical class centers. The colored dots are training points; the crosses mark empirical class centers. This is the geometry we can directly observe.',
      'With enough samples per source class, the empirical clustering reflects the true geometry of the underlying source-class distributions (shown as confidence ellipses). The observed clustering is not a finite-sample artifact — it represents real distributional structure. This is the first generalization: samples → distributions.',
      'Because classes are i.i.d. draws from the same population D, new unseen target classes (shown in muted colors, right side) inherit the same favorable geometry. A few labeled examples (large dots) are enough to estimate their centers. This is the second generalization: source classes → target classes.'
    ];

    window.showGen=function(step){
      currentGenStep=step;
      scopeEl.querySelectorAll('.gen-tab').forEach(function(t,i){
        t.classList.toggle('active',i===step);
      });
      document.getElementById('gen-desc').textContent=genDescs[step];
      drawGenStep(step);
    };

    var classColors2d=['#5a4ab8','#1a7a5c','#c45028','#a06810','#d85a30'];
    var classColorsFaded2d=['rgba(90,74,184,0.3)','rgba(26,122,92,0.3)','rgba(196,80,40,0.3)','rgba(160,104,16,0.3)','rgba(216,90,48,0.3)'];

    function drawGenStep(step){
      var dpr=window.devicePixelRatio||1;
      var W=genCanvas.clientWidth;
      var H=genCanvas.clientHeight;
      genCanvas.width=W*dpr;
      genCanvas.height=H*dpr;
      genCtx.setTransform(1,0,0,1,0,0);
      genCtx.scale(dpr,dpr);
      genCtx.clearRect(0,0,W,H);

      var pad=30;
      var srcW=(W-pad*3)*0.6;
      var srcY=pad;
      var srcH=H-pad*2;
      var srcX=pad;
      var spread=0.04;
      var nPts=15;

      genCtx.font='600 11px "DM Sans"';
      genCtx.fillStyle='#8a8680';
      genCtx.fillText('SOURCE CLASSES',srcX,pad-8);

      var sCenters=[[0.2,0.25],[0.55,0.2],[0.85,0.25],[0.3,0.75],[0.7,0.8]];
      for(var c=0;c<5;c++){
        var cx=srcX+sCenters[c][0]*srcW;
        var cy=srcY+sCenters[c][1]*srcH;

        if(step>=1){
          genCtx.beginPath();
          genCtx.ellipse(cx,cy,spread*srcW*3.5,spread*srcH*3.5,0,0,Math.PI*2);
          genCtx.fillStyle=classColorsFaded2d[c];
          genCtx.fill();
          genCtx.strokeStyle=classColors2d[c];
          genCtx.lineWidth=0.5;
          genCtx.setLineDash([3,3]);
          genCtx.stroke();
          genCtx.setLineDash([]);
        }

        for(var s=0;s<nPts;s++){
          var ri=(c*30+s)%rng.length;
          genCtx.beginPath();
          genCtx.arc(cx+rng[ri][0]*spread*srcW,cy+rng[ri][1]*spread*srcH,2,0,Math.PI*2);
          genCtx.fillStyle=step===0?classColors2d[c]:classColorsFaded2d[c];
          genCtx.fill();
        }

        genCtx.strokeStyle=classColors2d[c];
        genCtx.lineWidth=1.5;
        genCtx.beginPath();
        genCtx.moveTo(cx-5,cy);
        genCtx.lineTo(cx+5,cy);
        genCtx.moveTo(cx,cy-5);
        genCtx.lineTo(cx,cy+5);
        genCtx.stroke();
      }

      if(step>=2){
        var tgtX=srcX+srcW+pad*1.5;
        var tgtW=(W-pad*3)*0.4;
        genCtx.strokeStyle='#e0dcd6';
        genCtx.lineWidth=1;
        genCtx.setLineDash([4,4]);
        genCtx.beginPath();
        genCtx.moveTo(tgtX-pad*0.75,pad-8);
        genCtx.lineTo(tgtX-pad*0.75,H-pad+10);
        genCtx.stroke();
        genCtx.setLineDash([]);

        genCtx.font='600 11px "DM Sans"';
        genCtx.fillStyle='#8a8680';
        genCtx.fillText('TARGET CLASSES (unseen)',tgtX,pad-8);

        var tCenters=[[0.3,0.3],[0.7,0.4],[0.45,0.8]];
        var tColors=['#7f77dd','#5dcaa5','#f0997b'];
        var tColorsFaded=['rgba(127,119,221,0.25)','rgba(93,202,165,0.25)','rgba(240,153,123,0.25)'];

        for(var c=0;c<3;c++){
          var cx=tgtX+tCenters[c][0]*tgtW;
          var cy=srcY+tCenters[c][1]*srcH;

          genCtx.beginPath();
          genCtx.ellipse(cx,cy,spread*tgtW*3.5,spread*srcH*3.5,0,0,Math.PI*2);
          genCtx.fillStyle=tColorsFaded[c];
          genCtx.fill();
          genCtx.strokeStyle=tColors[c];
          genCtx.lineWidth=0.5;
          genCtx.setLineDash([3,3]);
          genCtx.stroke();
          genCtx.setLineDash([]);

          for(var s=0;s<4;s++){
            var ri=(c*40+s+200)%rng.length;
            genCtx.beginPath();
            genCtx.arc(cx+rng[ri][0]*spread*tgtW*0.8,cy+rng[ri][1]*spread*srcH*0.8,4,0,Math.PI*2);
            genCtx.fillStyle=tColors[c];
            genCtx.fill();
          }

          genCtx.strokeStyle=tColors[c];
          genCtx.lineWidth=2;
          genCtx.beginPath();
          genCtx.moveTo(cx-6,cy);
          genCtx.lineTo(cx+6,cy);
          genCtx.moveTo(cx,cy-6);
          genCtx.lineTo(cx,cy+6);
          genCtx.stroke();

          genCtx.font='500 10px "DM Sans"';
          genCtx.fillStyle=tColors[c];
          genCtx.fillText('4-shot',cx+10,cy+4);
        }

        var arrowY=H/2;
        var arrowX1=srcX+srcW+pad*0.3;
        var arrowX2=tgtX-pad*0.3;
        genCtx.strokeStyle='#8a8680';
        genCtx.lineWidth=1;
        genCtx.beginPath();
        genCtx.moveTo(arrowX1,arrowY);
        genCtx.lineTo(arrowX2-6,arrowY);
        genCtx.stroke();
        genCtx.beginPath();
        genCtx.moveTo(arrowX2,arrowY);
        genCtx.lineTo(arrowX2-8,arrowY-4);
        genCtx.lineTo(arrowX2-8,arrowY+4);
        genCtx.fillStyle='#8a8680';
        genCtx.fill();
        genCtx.font='500 10px "DM Sans"';
        genCtx.fillStyle='#8a8680';
        genCtx.fillText('same D',arrowX1+4,arrowY-8);
      }
    }

    showGen(0);
    window.addEventListener('resize',function(){drawGenStep(currentGenStep)});
  })();

  if('IntersectionObserver' in window){
    var obs=new IntersectionObserver(function(entries){
      entries.forEach(function(e){
        if(e.isIntersecting)e.target.classList.add('visible');
      });
    },{threshold:.15});

    scopeEl.querySelectorAll('.fade-in').forEach(function(el){
      obs.observe(el);
    });
  }
})();
</script>
