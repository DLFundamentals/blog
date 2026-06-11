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
.ps .gen-tabs{display:flex;border-radius:8px 8px 0 0;overflow:hidden;border:1px solid var(--border);border-bottom:none;}
.ps .gen-tab{flex:1;font-family:var(--mono);font-size:10.5px;font-weight:500;padding:9px 10px;border:none;border-right:1px solid var(--border);background:var(--surface);color:var(--muted-lt);cursor:pointer;transition:all .18s ease;text-align:center;letter-spacing:.02em;position:relative;}
.ps .gen-tab:last-child{border-right:none;}
.ps .gen-tab:hover:not(.active){background:var(--surface-2);color:var(--text-soft);}
.ps .gen-tab.active{background:var(--bg);color:var(--accent);}
.ps .gen-tab.active::after{content:'';position:absolute;left:0;right:0;bottom:0;height:2px;background:var(--gold);}
.ps .gen-tab .gen-tab-k{display:inline-block;width:15px;height:15px;line-height:15px;border-radius:50%;background:var(--border);color:var(--bg);font-size:9px;margin-right:6px;vertical-align:1px;transition:background .18s ease;}
.ps .gen-tab.active .gen-tab-k{background:var(--accent);}
.ps .gen-panel{background:var(--bg);border:1px solid var(--border);border-top:none;border-radius:0 0 8px 8px;padding:1rem 1rem .9rem;}
.ps .gen-canvas-shell{border-radius:7px;background:linear-gradient(180deg,#faf8f3,#f1ede5);border:1px solid var(--border-lt);overflow:hidden;}
.ps #gen-canvas{display:block;width:100%;height:272px;}
.ps .gen-desc{font-family:var(--sans);font-size:13px;color:var(--text-soft);line-height:1.62;margin-top:.85rem;font-weight:300;min-height:52px;}
.ps .gen-desc strong{font-weight:500;color:var(--text);}

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
@media(max-width:700px){.ps .hero,.ps article,.ps .post-footer{padding-left:1.25rem;padding-right:1.25rem;}.ps .hero h1{font-size:1.8rem;}.ps .gen-tab{font-size:9px;padding:8px 5px;}.ps .gen-tab .gen-tab-k{margin-right:3px;}.ps #gen-canvas{height:248px;}}
@media(prefers-reduced-motion:reduce){.ps .fade-in{transition:none;}}
</style>

<div class="ps">
<div class="top-bar"></div>

<div class="hero">
  <div class="hero-eyebrow">Pre-Training &middot; Few-Shot Learning &middot; Neural Collapse</div>
  <h1>Why Pretrained Classifiers Work So Well in <em>Few-Shot Learning</em></h1>
  <p class="hero-subtitle">A deeper geometric explanation for why supervised pretraining can make new classes learnable from only a few labels: neural collapse shrinks class clouds, spreads their centers, and leaves behind a feature space where nearest-center classification becomes statistically cheap.</p>
  <div class="hero-meta">
    <span>By Tomer Galanti</span>
    <span>&middot;</span>
    <span>March 11, 2026</span>
    <span>&middot;</span>
    <span>14 min read</span>
    <span>&middot;</span>
    <span class="paper-badge">&#9670; Galanti, György, Hutter — JMLR 2026</span>
  </div>
</div>


<article>

  <h2>Introduction</h2>

  <p class="lead">Few-shot transfer has a slightly magical flavor. We train a classifier on a large source problem — say, many ImageNet-like classes — throw away the last layer, freeze the representation, and then classify entirely new classes from only one or five labeled examples. In practice, this simple recipe is often shockingly strong.</p>

  <p>The puzzle is mathematical. The source classifier was never asked to separate the target classes. It only saw its own labels. So why should its penultimate layer arrange <strong>unseen</strong> classes in a way that a nearest-center classifier can recover from a handful of samples?</p>

  <p>The answer in the paper is not that pretraining learns every future task. It is subtler and prettier: supervised pretraining can learn a <em>geometry of classes</em>. If features from the same class concentrate tightly, and class means are far apart, then the class identity is almost encoded by the location of its center. Few-shot learning then becomes less like learning a new classifier from scratch and more like placing a few pins on an already organized map.</p>

  <div class="callout">
    <strong>The main idea</strong>
    A pretrained classifier transfers well when its feature map makes classes look like small, well-separated clouds. The key quantity is <em>class-distance normalized variance</em> (CDNV): within-class spread divided by squared distance to another class mean. If this quantity is small on many source classes, and those classes are representative of a larger population, then nearest-center classification can succeed on new classes with very few examples.
  </div>

  <p>The mathematical story has four moving parts:</p>

  <div class="steps">
    <div class="step">
      <div class="step-num" style="background:#5a4ab8;">1</div>
      <div class="step-body">
        <div class="step-title">Treat classes as random objects.</div>
        <div class="step-desc">Source and target classes are modeled as independent draws from a common population $\mathcal{D}$ of class-conditional distributions.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num" style="background:var(--teal);">2</div>
      <div class="step-body">
        <div class="step-title">Use nearest centers as the test-time rule.</div>
        <div class="step-desc">At transfer time, freeze the representation and estimate each new class center from only $n$ examples.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num">3</div>
      <div class="step-body">
        <div class="step-title">Relate few-shot error to CDNV.</div>
        <div class="step-desc">A soft-margin NCC loss turns geometric collapse into a controllable classification error.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num" style="background:var(--amber);">4</div>
      <div class="step-body">
        <div class="step-title">Generalize twice.</div>
        <div class="step-desc">The source geometry must generalize from finite samples to source distributions, and then from source classes to unseen target classes.</div>
      </div>
    </div>
  </div>

  <div class="paper-note">
    Based on: T. Galanti, A. György, M. Hutter. <a href="https://arxiv.org/abs/2212.12532">&ldquo;Generalization Bounds for Few-Shot Transfer Learning with Pretrained Classifiers&rdquo;</a>, JMLR 2026 / arXiv 2022.
  </div>

  <hr>

  <h2>Interactive — Neural collapse and transfer in 3D</h2>

  <p>The visualization below is a toy version of the paper's geometry. Drag the <strong>epoch slider</strong>. The filled source points tighten into clusters, while the class means spread apart. The target points, shown as rings, were never used during pretraining — but in this cartoon they inherit the same geometry. Drag the viewport to rotate.</p>

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
<input id="nc3d-epoch" max="200" min="0" step="1" type="range" value="0"/>
<span style="font-family:var(--mono);font-size:9.5px;color:#6a6460;">200</span>
<span id="nc3d-epval" style="font-family:var(--mono);font-size:11px;color:#d4a820;min-width:28px;text-align:right;">0</span>
</div>
</div>
</div>

  <p class="figcaption"><strong>Fig. 1.</strong> 3D feature space during training. Source classes (filled dots, 4 classes × 18 samples) collapse toward an equiangular tight frame as the epoch slider advances. Target classes (rings, 3 classes × 5 samples) are unseen during training but inherit the same favorable geometry. CDNV drops because within-class variance shrinks while class means separate. At epoch ~170+, nearest-center classification succeeds from only a few target examples.</p>

  <div class="steps">
    <div class="step">
      <div class="step-num" style="background:#5a4ab8;">→</div>
      <div class="step-body">
        <div class="step-title">Watch the numerator shrink.</div>
        <div class="step-desc">Early in training, points from the same class scatter broadly. As NC1 emerges, each class becomes a tight little cloud around its feature mean.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num" style="background:var(--teal);">→</div>
      <div class="step-body">
        <div class="step-title">Watch the denominator grow.</div>
        <div class="step-desc">Later, class means spread toward a maximally separated configuration. Transfer improves when both effects happen together: small clouds, large gaps.</div>
      </div>
    </div>
  </div>

  <hr>

  <h2>Part I — A formal model for transfer to new classes</h2>

  <h3>Classes as random objects</h3>

  <p>To make transfer a theorem rather than a slogan, the paper models <em>classes themselves</em> as random objects. There is an unknown distribution $\mathcal{D}$ over class-conditional distributions. A source task is formed by drawing $\tilde P_1,\dots,\tilde P_\ell \sim \mathcal{D}$. A target task is formed later by drawing fresh classes $P_1,\dots,P_k \sim \mathcal{D}$, independently of the source draw.</p>

  <div class="math-display">
    <div class="math-label">Source and target classes</div>
    $$\tilde P_1,\dots,\tilde P_\ell \sim \mathcal{D}, \qquad P_1,\dots,P_k \sim \mathcal{D}$$
  </div>

  <p>This assumption is doing real work. Without some shared population of classes, there is no reason for a representation learned on the source task to help on the target task. But the assumption is also modest: $\mathcal{D}$ is not known to the algorithm and does not need a parametric form. It is a mathematical way to say that the source labels are a sample from the kind of classes we hope to see again.</p>

  <h3>What gets learned, and what gets adapted</h3>

  <p>Pretraining learns a feature map $f:\mathcal{X}\to\mathbb{R}^p$. At transfer time, $f$ is frozen. For each new class $P_c$, we only get $n$ examples $S_c\sim P_c^n$, and we classify by the nearest empirical class center:</p>

  <div class="eq-highlight">
    $$h_{f,S}^{\mathrm{NCC}}(x)=\arg\min_{c\in[k]}\|f(x)-\mu_f(S_c)\|$$
  </div>

  <p>The object of interest is not the training error on one lucky target task. It is the expected few-shot error over a random future task and over the small random support set used to estimate the centers:</p>

  <div class="math-display">
    <div class="math-label">Transfer risk</div>
    $$\mathcal{L}_\mathcal{D}(f)=
    \mathbb{E}_{P_1,\dots,P_k\sim\mathcal{D}}
    \mathbb{E}_{S_c\sim P_c^n}
    \big[L_P(h_{f,S}^{\mathrm{NCC}})\big]$$
  </div>

  <p>This is the right quantity for foundation models. The feature map is trained before the target classes are known, and the target sample size $n$ may remain tiny. The theorem asks whether $\mathcal{L}_\mathcal{D}(f)$ can still go to zero as the source problem becomes rich: many source classes $\ell$, many samples per source class $m$, and increasingly collapsed feature geometry.</p>

  <hr>

  <h2>Part II — The geometric quantity that controls transfer</h2>

  <h3>Class-distance normalized variance (CDNV)</h3>

  <p>For a class-conditional distribution $Q$, write its feature mean and feature variance as</p>

  <div class="math-display">
    <div class="math-label">Feature mean and feature variance</div>
    $$\mu_f(Q)=\mathbb{E}_{x\sim Q}[f(x)], \qquad
    \operatorname{Var}_f(Q)=\mathbb{E}_{x\sim Q}\|f(x)-\mu_f(Q)\|^2.$$
  </div>

  <p>For two classes $Q_i$ and $Q_j$, the paper's basic geometric quantity is</p>

  <div class="eq-highlight">
    $$V_f(Q_i,Q_j)=
    \frac{\operatorname{Var}_f(Q_i)}{\|\mu_f(Q_i)-\mu_f(Q_j)\|^2}.$$
  </div>

  <p>CDNV is deliberately local and pairwise. The numerator asks: how fuzzy is class $i$ in feature space? The denominator asks: how far is its center from class $j$? The ratio is scale-free, which is important because multiplying all features by a constant should not make transfer magically easier.</p>

  <div class="pull-quote">&ldquo;Neural collapse helps twice: NC1 shrinks the clouds; NC2 pulls the class means apart.&rdquo;</div>

  <p>The ratio is asymmetric because it measures mistakes made by samples from $Q_i$ when competing against the center of $Q_j$. In the final bound, the average is taken over ordered pairs, so both directions matter. This asymmetry is not a cosmetic detail — it is what lets the proof control the pairwise nearest-center error more directly.</p>

  <h3>The bridge: a soft-margin nearest-center loss</h3>

  <p>To connect geometry to classification, compare the distance from a point $x\sim Q_i$ to its own center with the distance to the competing center. Define the nearest-center margin</p>

  <div class="math-display">
    <div class="math-label">Pairwise NCC margin</div>
    $$r_{ij}(x)=\|f(x)-\mu_f(Q_i)\|-\|f(x)-\mu_f(Q_j)\|.$$
  </div>

  <p>If $r_{ij}(x)<0$, the point is closer to its own class center. If $r_{ij}(x)>0$, it is closer to the wrong center. The paper uses a softened version of this mistake indicator, with margin parameter $\Delta>0$:</p>

  <div class="math-display">
    <div class="math-label">Soft-margin loss</div>
    $$\ell_\Delta(r)=
    \begin{cases}
    0, & r<-\Delta,\\
    1+r/\Delta, & -\Delta\le r\le 0,\\
    1, & r>0.
    \end{cases}$$
  </div>

  <p>This little loss is the proof's workhorse. It upper-bounds the actual nearest-center mistake, lower-bounds a stricter margin mistake, and is $1/\Delta$-Lipschitz. That last property is what allows concentration tools to compare finite source samples with the underlying class distributions.</p>

  <div class="eq-highlight">
    $$\mathbf{1}\{r>0\}\le \ell_\Delta(r)\le \mathbf{1}\{r>-\Delta\}, \qquad
    \ell_\Delta \text{ is } \frac1\Delta\text{-Lipschitz}.$$
  </div>

  <p>Now CDNV enters through a clean geometric implication: when the clouds are small relative to their separation, the soft-margin nearest-center loss is small. Very roughly, the paper proves bounds of the form</p>

  <div class="eq-highlight">
    $$\ell_\Delta(f;Q_i,Q_j)
    \;\lesssim\;
    \left(1+\frac1n\right)V_f(Q_i,Q_j)
    +\frac1n\,V_f(Q_j,Q_i),$$
  </div>

  <p>provided the margin scale $\Delta$ is chosen below a constant fraction of the class-mean distance. The exact statement has constants and a symmetric center-estimation term, but the intuition is simple: a few-shot center is noisy, yet if the class cloud is tiny compared to the gap between class means, even a noisy center is enough.</p>

  <h3>The double generalization</h3>

  <p>The stepper below illustrates the two-level argument. First, the empirical source geometry must reflect the true geometry of the source class-conditionals. Second, because the source classes are themselves random draws from $\mathcal{D}$, the average geometry of many source classes estimates the average geometry of new target classes.</p>

  <div class="gen-stepper fade-in">
<div class="gen-tabs">
<button class="gen-tab active" onclick="showGen(0)"><span class="gen-tab-k">1</span>Empirical clustering</button>
<button class="gen-tab" onclick="showGen(1)"><span class="gen-tab-k">2</span>Samples &rarr; distributions</button>
<button class="gen-tab" onclick="showGen(2)"><span class="gen-tab-k">3</span>Source &rarr; target</button>
</div>
<div class="gen-panel">
<div class="gen-canvas-shell"><canvas id="gen-canvas"></canvas></div>
<div class="gen-desc" id="gen-desc"></div>
</div>
</div>

  <p class="figcaption"><strong>Fig. 2.</strong> The double generalization in 2D. Step 1: empirical source points cluster around empirical centers. Step 2: with enough samples per source class, this reflects the source class-conditional distributions. Step 3: with enough source classes, the average pairwise geometry reflects the population $\mathcal{D}$, so unseen target classes inherit the same favorable nearest-center behavior.</p>

  <hr>

  <h2>Part III — The transfer bound</h2>

  <h3>The theorem in one line</h3>

  <p>Suppressing universal constants and logarithmic factors, the CDNV version of the transfer bound says that with high probability over the source classes and source samples,</p>

  <div class="eq-highlight">
    $$\mathcal{L}_\mathcal{D}(f)
    \;\lesssim\;
    (k-1)\operatorname{Avg}_{i\ne j}V_f(\tilde S_i,\tilde S_j)
    +
    \frac{(k-1)\alpha_f B}{\Lambda}
    \,\widetilde{O}\!\left(\frac{n^2}{\sqrt m}+\frac1{\sqrt\ell}\right).$$
  </div>

  <p>Here $k$ is the number of target classes, $n$ is the number of target examples per class, $m$ is the number of source examples per class, and $\ell$ is the number of source classes. The quantity $\alpha_f$ is a norm/complexity proxy for the network, $B$ bounds the input radius, and</p>

  <div class="math-display">
    <div class="math-label">Minimum empirical source separation</div>
    $$\Lambda=\min_{i\ne j}\|\mu_f(\tilde S_i)-\mu_f(\tilde S_j)\|.$$
  </div>

  <p>This display is not the full theorem — the paper keeps the constants, the confidence parameter, the margin scale, and several logarithms. But this is the mathematical shape that matters for intuition.</p>

  <h3>What each term means</h3>

  <div class="finding">
    <div class="finding-label">Empirical CDNV — the observable geometric term</div>
    This is the term pretraining directly improves. Small source CDNV says that source training classes are already arranged as tight, separated clouds. In the neural-collapse picture, this is the measurable certificate that the representation has become few-shot-friendly.
  </div>

  <div class="finding">
    <div class="finding-label">$1/\sqrt{m}$ — samples → distributions</div>
    More examples per source class make empirical class means and variances reliable estimates of the true source class-conditionals. This is the usual sample-level concentration step.
  </div>

  <div class="finding">
    <div class="finding-label">$1/\sqrt{\ell}$ — source classes → target classes</div>
    More source classes improve the estimate of the class population $\mathcal{D}$. This term cannot be replaced by more samples per class: if every class had identical duplicate images, increasing $m$ would not teach us about new classes.
  </div>

  <div class="finding">
    <div class="finding-label">$\Lambda$ — the price of small margins</div>
    If two empirical class means are too close, nearest-center classification is fragile. Neural collapse helps by pushing class means toward a well-spread configuration, effectively increasing the margin scale available to the theorem.
  </div>

  <div class="finding">
    <div class="finding-label">$\alpha_f B$ — complexity and scale</div>
    The representation cannot wiggle arbitrarily. The bound pays for the network norm and the input radius because concentration for composed neural features depends on the size of the function class.
  </div>

  <h3>Why this is genuinely few-shot</h3>

  <p>The striking part is the role of $n$. Ordinary learning guarantees usually need the number of target samples to grow. Here, $n$ can remain a small constant. If the average empirical CDNV goes to zero during pretraining, and if $m$ and $\ell$ grow so the two generalization terms vanish, the transfer risk can converge to zero even though the target task still supplies only a few examples per class.</p>

  <div class="pull-quote">&ldquo;The target examples do not learn the representation. They only locate the new class centers inside a representation that was already organized.&rdquo;</div>

  <p>The somewhat awkward $n^2$ dependence in the simplified bound is not the philosophical point. The paper explicitly treats it as a proof artifact and focuses on the small-$n$ regime. The important message is that few-shot transfer is possible because the hard statistical work has moved upstream into source pretraining.</p>

  <h3>What the proof is doing, without the proof</h3>

  <p>At a high level, the proof is a chain of reductions:</p>

  <div class="steps">
    <div class="step">
      <div class="step-num" style="background:#5a4ab8;">I</div>
      <div class="step-body">
        <div class="step-title">Reduce $k$-class error to pairwise errors.</div>
        <div class="step-desc">A target mistake means some wrong class center beats the correct one, so a union bound introduces the factor $(k-1)$.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num" style="background:var(--teal);">II</div>
      <div class="step-body">
        <div class="step-title">Compare target pairs to source pairs.</div>
        <div class="step-desc">Because source and target classes are i.i.d. from $\mathcal{D}$, average pairwise behavior over many source classes estimates future pairwise behavior.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num">III</div>
      <div class="step-body">
        <div class="step-title">Estimate source-pair losses from finite samples.</div>
        <div class="step-desc">The soft-margin loss is Lipschitz, so Rademacher-style concentration controls the gap between empirical and population pairwise losses.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num" style="background:var(--amber);">IV</div>
      <div class="step-body">
        <div class="step-title">Upper-bound soft-margin loss by CDNV.</div>
        <div class="step-desc">This final geometric step converts neural collapse into a concrete few-shot transfer guarantee.</div>
      </div>
    </div>
  </div>

  <p>That is the whole mechanism. The theorem does not require the target learner to discover a complicated classifier. It only requires the target support set to estimate a few class centers in a geometry where centers already carry the class identity.</p>

  <hr>

  <h2>What this does and does not claim</h2>

  <p>This theory does <strong>not</strong> say that every pretrained classifier transfers to every possible target task. The source and target classes must be meaningfully modeled as draws from the same class population. If the target classes come from a different world, the theorem has no reason to apply.</p>

  <p>It also does not say that exact neural collapse is necessary, or that NCC is always the best downstream classifier. The paper uses NCC because it makes the geometry transparent and because NC3/NC4 suggest that trained linear heads become closely related to nearest-center rules. In practice, linear probes, ridge regression, or logistic regression may do better. The theorem is explaining why a very simple rule can already work.</p>

  <p>Finally, the bound is a generalization bound, not a sharp prediction of test accuracy. It has constants, logarithms, norm factors, and worst-case margins. Its value is conceptual: it identifies a route by which a single supervised classifier can produce a representation that transfers in the few-shot regime.</p>

  <div class="takeaway">
    <h3>Takeaway</h3>
    <p>Few-shot transfer works when pretraining learns a class geometry that survives two kinds of randomness.</p>
    <p><strong>Geometry:</strong> neural collapse makes each class a small cloud and pushes class means apart. CDNV measures exactly this ratio: cloud size divided by squared inter-center distance.</p>
    <p><strong>Statistics:</strong> the geometry observed on finite source samples must generalize to the true source classes, and the average over source classes must generalize to new classes drawn from the same population.</p>
    <p><strong>Few-shot adaptation:</strong> once unseen classes inherit this geometry, a few labeled examples are enough to estimate class centers. The target learner is not discovering the representation; it is placing names on an already structured feature space.</p>
    <p>The cute picture is this: pretraining turns the feature space into a constellation. Few-shot learning only has to identify which little cluster is which.</p>
  </div>

</article>


<div class="post-footer">
  <p>Published on <a href="https://dlfundamentals.github.io/blog/">Theory/Simplified</a> &nbsp;&middot;&nbsp; Based on <a href="https://arxiv.org/abs/2212.12532">Galanti, György, Hutter — JMLR 2026 / arXiv 2022</a></p>
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

  /* ── Double-generalization illustration (Fig. 2) ── */
  (function(){
    var cv=document.getElementById('gen-canvas');if(!cv)return;
    var ctx=cv.getContext('2d');
    var step=0, animating=false;
    var reduce=window.matchMedia&&window.matchMedia('(prefers-reduced-motion: reduce)').matches;

    function mkRng(seed){var s=seed>>>0;return function(){s=(s*1664525+1013904223)>>>0;return s/4294967296;};}
    function gauss(r){var u=0,v=0;while(u===0)u=r();while(v===0)v=r();return Math.sqrt(-2*Math.log(u))*Math.cos(6.2831853*v);}
    function rgba(hex,a){var n=parseInt(hex.slice(1),16);return 'rgba('+((n>>16)&255)+','+((n>>8)&255)+','+(n&255)+','+a+')';}

    /* source: 5 classes, layout chosen so clouds don't collide */
    var srcC=['#7F77DD','#1D9E75','#D85A30','#378ADD','#9B5DB8'];
    var srcCtr=[[0.16,0.27],[0.5,0.17],[0.84,0.27],[0.30,0.76],[0.70,0.77]];
    var NS=srcC.length, SAMP=12, srcOff=[];
    (function(){var r=mkRng(7);for(var c=0;c<NS;c++){var a=[];for(var s=0;s<SAMP;s++)a.push([gauss(r),gauss(r)]);srcOff.push(a);}})();

    /* target: 3 unseen classes, 4-shot each (colors echo the 3D figure) */
    var tgtC=['#D4537E','#BA7517','#639922'];
    var tgtCtr=[[0.33,0.30],[0.70,0.46],[0.47,0.78]];
    var NT=tgtC.length, SHOT=4, tgtOff=[];
    (function(){var r=mkRng(101);for(var c=0;c<NT;c++){var a=[];for(var s=0;s<SHOT;s++)a.push([gauss(r)*0.62,gauss(r)*0.62]);tgtOff.push(a);}})();

    /* animated scene state — one continuous morph between steps */
    var st={ell:0,split:0,tgt:0,conn:1};
    function goalFor(k){
      if(k===0)return{ell:0,split:0,tgt:0,conn:1};
      if(k===1)return{ell:1,split:0,tgt:0,conn:0};
      return{ell:1,split:1,tgt:1,conn:0};
    }
    var goal=goalFor(0);

    function marker(x,y,col,sc){
      sc=sc||1;
      ctx.beginPath();ctx.arc(x,y,6.5*sc,0,6.2832);ctx.fillStyle='rgba(250,248,243,0.95)';ctx.fill();
      ctx.beginPath();ctx.arc(x,y,5*sc,0,6.2832);ctx.lineWidth=2*sc;ctx.strokeStyle=col;ctx.stroke();
      ctx.beginPath();ctx.arc(x,y,1.7*sc,0,6.2832);ctx.fillStyle=col;ctx.fill();
    }
    function cloud(x,y,r,col,a){
      var g=ctx.createRadialGradient(x,y,0,x,y,r);
      g.addColorStop(0,rgba(col,0.26*a));g.addColorStop(0.65,rgba(col,0.11*a));g.addColorStop(1,rgba(col,0));
      ctx.beginPath();ctx.arc(x,y,r,0,6.2832);ctx.fillStyle=g;ctx.fill();
      ctx.setLineDash([4,4]);ctx.lineWidth=1;ctx.strokeStyle=rgba(col,0.55*a);ctx.stroke();ctx.setLineDash([]);
    }

    function draw(){
      var dpr=window.devicePixelRatio||1, W=cv.clientWidth, H=cv.clientHeight;
      if(!W||!H)return;
      if(cv.width!==Math.round(W*dpr)||cv.height!==Math.round(H*dpr)){cv.width=W*dpr;cv.height=H*dpr;}
      ctx.setTransform(dpr,0,0,dpr,0,0);ctx.clearRect(0,0,W,H);

      var pad=24, top=pad+16;
      var fullW=W-pad*2, areaH=H-top-pad;
      var srcW=fullW*(1-0.44*st.split);
      var gap=fullW*0.045*st.split;
      var tgtX=pad+srcW+gap, tgtW=fullW*0.40*st.split;
      var sig=areaH*0.052;

      ctx.textBaseline='alphabetic';
      ctx.font='500 9.5px "IBM Plex Mono",monospace';ctx.textAlign='left';
      ctx.fillStyle='#a09880';ctx.fillText('SOURCE  CLASSES',pad,pad+7);

      /* ── source clusters ── */
      for(var c=0;c<NS;c++){
        var cx=pad+srcCtr[c][0]*srcW, cy=top+srcCtr[c][1]*areaH;
        if(st.ell>0.01) cloud(cx,cy,sig*2.5,srcC[c],st.ell);
        if(st.conn>0.01){
          ctx.strokeStyle=rgba(srcC[c],0.16*st.conn);ctx.lineWidth=0.8;
          for(var s=0;s<SAMP;s++){ctx.beginPath();ctx.moveTo(cx,cy);ctx.lineTo(cx+srcOff[c][s][0]*sig,cy+srcOff[c][s][1]*sig);ctx.stroke();}
        }
        ctx.fillStyle=rgba(srcC[c],1-0.45*st.ell);
        for(var s=0;s<SAMP;s++){ctx.beginPath();ctx.arc(cx+srcOff[c][s][0]*sig,cy+srcOff[c][s][1]*sig,2.3,0,6.2832);ctx.fill();}
        marker(cx,cy,srcC[c],1);
      }
      /* a single quiet annotation, so step 2 reads as "cloud = true distribution" */
      if(st.ell>0.55){
        var ax=pad+srcCtr[1][0]*srcW, ay=top+srcCtr[1][1]*areaH, fa=(st.ell-0.55)/0.45;
        ctx.font='italic 500 11px "Lora",serif';ctx.fillStyle=rgba(srcC[1],fa);ctx.textAlign='center';
        ctx.fillText('P',ax,ay-sig*2.5-5);ctx.textAlign='left';
      }

      /* ── divider, arrow, target panel ── */
      if(st.tgt>0.02){
        var dx=pad+srcW+gap*0.5;
        ctx.setLineDash([4,5]);ctx.lineWidth=1;ctx.strokeStyle=rgba('#cbc4b6',st.tgt);
        ctx.beginPath();ctx.moveTo(dx,pad);ctx.lineTo(dx,H-pad);ctx.stroke();ctx.setLineDash([]);

        var midY=top+areaH*0.5, x1=pad+srcW+5, x2=tgtX-5;
        ctx.strokeStyle=rgba('#8a8070',0.85*st.tgt);ctx.lineWidth=1.5;
        ctx.beginPath();ctx.moveTo(x1,midY);ctx.lineTo(x2-7,midY);ctx.stroke();
        ctx.beginPath();ctx.moveTo(x2,midY);ctx.lineTo(x2-8,midY-4.5);ctx.lineTo(x2-8,midY+4.5);ctx.closePath();
        ctx.fillStyle=rgba('#8a8070',0.85*st.tgt);ctx.fill();
        ctx.font='italic 500 11px "Lora",serif';ctx.fillStyle=rgba('#5d564a',st.tgt);ctx.textAlign='center';
        ctx.fillText('same  𝒟',(x1+x2)/2,midY-8);ctx.textAlign='left';

        ctx.font='500 9.5px "IBM Plex Mono",monospace';ctx.fillStyle=rgba('#a09880',st.tgt);
        ctx.fillText('TARGET · UNSEEN',tgtX,pad+7);

        for(var c=0;c<NT;c++){
          var cx=tgtX+tgtCtr[c][0]*tgtW, cy=top+tgtCtr[c][1]*areaH, r=sig*2.0;
          cloud(cx,cy,r,tgtC[c],st.tgt*0.85);
          ctx.strokeStyle=rgba(tgtC[c],st.tgt);ctx.lineWidth=1.6;
          for(var s=0;s<SHOT;s++){ctx.beginPath();ctx.arc(cx+tgtOff[c][s][0]*sig,cy+tgtOff[c][s][1]*sig,3.3,0,6.2832);ctx.stroke();}
          marker(cx,cy,tgtC[c],1.05);
          ctx.font='400 8.5px "IBM Plex Mono",monospace';ctx.fillStyle=rgba(tgtC[c],st.tgt);ctx.textAlign='left';
          ctx.fillText('4-shot',cx+r*0.7+5,cy+3);
        }
      }
    }

    function tick(){
      var done=true;
      for(var k in goal){var d=goal[k]-st[k];if(Math.abs(d)>0.0015){st[k]+=d*0.14;done=false;}else st[k]=goal[k];}
      draw();
      if(!done)requestAnimationFrame(tick);else animating=false;
    }
    function go(k){
      goal=goalFor(k);
      if(reduce){for(var key in goal)st[key]=goal[key];draw();return;}
      if(!animating){animating=true;requestAnimationFrame(tick);}
    }

    var descs=[
      'Step 1 — what we can actually <strong>measure</strong> after pretraining: source training samples cluster around their empirical class centers. This is the finite-sample geometry the algorithm sees — fuzzy little clouds, each with a center pin.',
      'Step 2 — <strong>sample-level</strong> generalization. With enough examples per source class (large m), each empirical center and variance becomes a reliable estimate of the underlying class-conditional — the dashed clouds. This is where the 1/√m term comes from.',
      'Step 3 — <strong>class-level</strong> generalization. Because classes are i.i.d. draws from the same population 𝒟, average pairwise geometry over many source classes predicts the geometry of brand-new target classes — so a few shots per unseen class suffice to place its center. This is where the 1/√ℓ term comes from.'
    ];

    window.showGen=function(k){
      step=k;
      root.querySelectorAll('.gen-tab').forEach(function(t,i){t.classList.toggle('active',i===k);});
      document.getElementById('gen-desc').innerHTML=descs[k];
      go(k);
    };

    draw();
    if(document.fonts&&document.fonts.ready)document.fonts.ready.then(draw);
    showGen(0);
    window.addEventListener('resize',draw);
  })();

  if('IntersectionObserver' in window){var obs=new IntersectionObserver(function(entries){entries.forEach(function(e){if(e.isIntersecting)e.target.classList.add('visible');});},{threshold:.1});root.querySelectorAll('.fade-in').forEach(function(el){obs.observe(el);});}
})();
</script>
