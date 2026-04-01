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
.post-scope *::before,
.post-scope *::after {
  box-sizing:border-box;
}

.post-scope{
  width:100%;
  background:var(--cream);
  color:var(--ink);
  font-family:var(--serif);
  line-height:1.72;
  -webkit-font-smoothing:antialiased;
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
  padding:4rem 2rem 3rem;
  border-bottom:1px solid var(--rule);
}

.post-scope .hero-eyebrow{
  font-family:var(--sans);
  font-size:12px;
  font-weight:600;
  letter-spacing:2px;
  text-transform:uppercase;
  color:var(--accent);
  margin-bottom:1.25rem;
}

.post-scope .hero h1{
  font-family:var(--serif);
  font-size:clamp(2rem,5vw,3rem);
  font-weight:500;
  line-height:1.2;
  color:var(--ink);
  margin:0 0 1.5rem 0;
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
  padding:3rem 2rem 5rem;
}

.post-scope article p{
  font-size:1.05rem;
  margin:0 0 1.5rem 0;
}

.post-scope article h2{
  font-family:var(--serif);
  font-size:1.6rem;
  font-weight:500;
  margin:3rem 0 1.25rem;
  color:var(--ink);
  padding-top:2rem;
  border-top:1px solid var(--rule);
}

.post-scope article h3{
  font-family:var(--sans);
  font-size:1rem;
  font-weight:600;
  margin:2rem 0 .75rem;
  color:var(--ink-soft);
  letter-spacing:.3px;
}

.post-scope .key-insight{
  border-left:3px solid var(--accent);
  padding:1.25rem 1.5rem;
  margin:2rem 0;
  background:var(--accent-soft);
  border-radius:0 8px 8px 0;
  color:var(--ink-soft);
  font-size:1.05rem;
  line-height:1.65;
}

.post-scope .key-insight p:last-child{
  margin-bottom:0;
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
  padding:1.25rem 1.5rem;
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
  grid-template-columns:1fr 1fr 1fr;
  gap:12px;
  margin:1.5rem 0;
}

.post-scope .mechanism-card{
  background:var(--paper);
  border:1px solid var(--rule);
  border-radius:8px;
  padding:1.25rem;
  border-top:3px solid var(--rule);
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
  grid-template-columns:1fr 1fr;
  gap:12px;
  margin:1.5rem 0;
}

.post-scope .compare-card{
  background:var(--paper);
  border:1px solid var(--rule);
  border-radius:8px;
  padding:1rem 1.25rem;
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
  padding:2rem 2.25rem;
  border-radius:12px;
  margin:3rem 0 2rem;
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
  padding:0 2rem 4rem;
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

.post-scope .figcaption,
.post-scope figcaption{
  font-family:var(--sans);
  font-size:13px;
  color:var(--ink-muted);
  line-height:1.55;
  margin-top:10px;
}

.post-scope .fig-wide{
  max-width:1120px;
  margin:2rem auto;
  padding:0 2rem;
}

.post-scope .fig-grid{
  display:grid;
  gap:14px;
  align-items:start;
}

.post-scope .fig-grid > div{
  min-width:0;
}

.post-scope .fig-grid img{
  width:100%;
  border:1px solid var(--rule);
  border-radius:10px;
  background:var(--paper);
}

.post-scope .fig-grid-label{
  font-family:var(--sans);
  font-size:12px;
  color:var(--ink-muted);
  line-height:1.4;
  margin-top:8px;
  text-align:center;
}

.post-scope .fig-row-label{
  font-family:var(--sans);
  font-size:13px;
  color:var(--ink);
  margin:0 0 8px 0;
}

.post-scope .denom-viz{
  display:grid;
  grid-template-columns:1fr auto 1fr;
  gap:18px;
  align-items:start;
}

.post-scope .denom-panel{
  min-width:0;
}

.post-scope .denom-label{
  font-family:var(--sans);
  font-size:13px;
  font-weight:600;
  margin-bottom:8px;
}

.post-scope .denom-grid{
  display:grid;
  gap:4px;
  background:var(--paper);
  border:1px solid var(--rule);
  border-radius:10px;
  padding:10px;
  min-height:120px;
}

.post-scope .denom-cell{
  width:100%;
  aspect-ratio:1/1;
  border-radius:4px;
}

.post-scope .gap-chart{
  margin-top:16px;
  background:var(--paper);
  border:1px solid var(--rule);
  border-radius:10px;
  padding:14px;
}

.post-scope .gap-bar-row{
  display:grid;
  grid-template-columns:56px 1fr 48px;
  gap:10px;
  align-items:center;
  margin:8px 0;
}

.post-scope .gap-bar-label,
.post-scope .gap-bar-val{
  font-family:var(--sans);
  font-size:12px;
  color:var(--ink-muted);
}

.post-scope .gap-bar-track{
  height:8px;
  background:#efe9e2;
  border-radius:999px;
  overflow:hidden;
}

.post-scope .gap-bar-fill{
  height:100%;
  border-radius:999px;
}

.post-scope .collapse-grid{
  display:grid;
  grid-template-columns:1fr 1fr 1fr;
  gap:12px;
  margin:1.5rem 0;
}

.post-scope .collapse-card{
  background:var(--paper);
  border:1px solid var(--rule);
  border-radius:10px;
  padding:1.25rem;
  text-align:left;
}

.post-scope .collapse-icon{
  display:inline-flex;
  align-items:center;
  justify-content:center;
  width:34px;
  height:34px;
  border-radius:999px;
  background:var(--accent-soft);
  color:var(--accent);
  font-family:var(--sans);
  font-weight:700;
  margin-bottom:10px;
}

.post-scope .collapse-card h4{
  font-family:var(--sans);
  font-size:14px;
  margin:0 0 8px 0;
  color:var(--ink);
}

.post-scope .collapse-card p{
  margin:0;
  font-size:13px;
  color:var(--ink-soft);
  line-height:1.55;
}

.post-scope .align-grid{
  display:grid;
  grid-template-columns:1fr 1fr 1fr 1fr;
  gap:12px;
  margin-bottom:14px;
}

.post-scope .align-card{
  background:var(--paper);
  border:1px solid var(--rule);
  border-radius:10px;
  padding:14px;
}

.post-scope .align-card-title{
  font-family:var(--sans);
  font-size:13px;
  font-weight:600;
  color:var(--ink);
  margin-bottom:12px;
}

.post-scope .align-row{
  display:grid;
  grid-template-columns:92px 1fr 34px;
  gap:8px;
  align-items:center;
  margin:8px 0;
}

.post-scope .align-row-label{
  font-family:var(--sans);
  font-size:12px;
  color:var(--ink-muted);
}

.post-scope .align-bar-track{
  height:8px;
  background:#efe9e2;
  border-radius:999px;
  overflow:hidden;
}

.post-scope .align-bar-fill{
  height:100%;
  border-radius:999px;
}

.post-scope .align-val{
  font-family:var(--sans);
  font-size:12px;
  font-weight:600;
  text-align:right;
}

.post-scope .explorer{
  background:var(--paper);
  border:1px solid var(--rule);
  border-radius:12px;
  padding:1.5rem;
  margin:2rem 0;
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
  margin-bottom:1.25rem;
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
  margin:2rem 0;
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
  padding:1.25rem;
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
  margin:2rem 0;
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
  background:rgba(0,0,0,0.55);
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
  background:rgba(0,0,0,0.55);
  backdrop-filter:blur(8px);
  border-radius:8px;
}

.post-scope .nc3d-slider-row input[type=range]{
  flex:1;
  height:3px;
  -webkit-appearance:none;
  appearance:none;
  background:rgba(255,255,255,0.2);
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

@media(max-width:900px){
  .post-scope .align-grid{
    grid-template-columns:1fr 1fr;
  }
}

@media(max-width:700px){
  .post-scope .mechanism-grid,
  .post-scope .collapse-grid{
    grid-template-columns:1fr;
  }

  .post-scope .denom-viz{
    grid-template-columns:1fr;
  }

  .post-scope .fig-wide{
    padding:0 1rem;
  }
}

@media(max-width:600px){
  .post-scope .compare-grid,
  .post-scope .align-grid{
    grid-template-columns:1fr;
  }

  .post-scope .fig-grid{
    grid-template-columns:1fr 1fr !important;
  }
}

@media(max-width:768px){
  .post-scope .hero h1{
    font-size:2rem;
  }
}

@media(max-width:480px){
  .post-scope .hero{
    padding:3rem 1rem 2rem;
  }

  .post-scope article{
    padding:2rem 1rem 4rem;
  }

  .post-scope .hero h1{
    font-size:1.7rem;
  }

  .post-scope .hero-meta{
    font-size:0.78rem;
  }

  .post-scope .fig-grid{
    grid-template-columns:1fr !important;
  }
}
</style>

<div class="post-scope">
<div class="hero">
  <div class="hero-eyebrow">Representation Learning &middot; Contrastive Learning &middot; Theory</div>
  <h1>Self-Supervised Learning ≈ Supervised Learning</h1>
  <p class="hero-subtitle">Self-supervised contrastive learning is trained without labels, yet the representations look remarkably class-aware. The reason is structural: its objective and learned geometry are already much closer to a supervised contrastive counterpart than they first appear.</p>
  <div class="hero-meta">
    <span>By Tomer Galanti</span>
    <span>&middot;</span>
    <span>March 11, 2026</span>
    <span>&middot;</span>
    <span>16 min read</span>
    <span>&middot;</span>
    <span class="paper-badge">◆ NeurIPS 2025 + ICLR 2025</span>
  </div>
</div>

<article>

<h2 style="border-top:none;padding-top:0;margin-top:0">Introduction</h2>

<p>Self-supervised contrastive learning is trained without labels, yet the learned representations often display clear semantic structure: same-class samples cluster together, linear probes perform well, and downstream transfer can approach supervised pretraining. This raises a basic question: <strong>why does a label-free objective produce representations that look so class-aware?</strong></p>

<p>A useful way to think about this phenomenon is that standard contrastive learning is not as far from supervised contrastive learning as it may first appear. The closeness appears at two levels:</p>

<div class="key-insight">
  <p><strong>1. The objectives are close.</strong> The standard self-supervised contrastive loss is close to a supervised variant that excludes same-class negatives, with a gap that shrinks as $O(1/C)$ in the number of classes.</p>
  <p><strong>2. The induced geometry is close.</strong> Under shared training randomness, the learned representations remain strongly aligned throughout training, even when the parameters themselves diverge.</p>
  <p><strong>3. The supervised counterpart is geometrically tractable.</strong> Its global minimizers exhibit augmentation collapse, within-class collapse, and simplex ETF structure.</p>
</div>

<p>Taken together, these results suggest a more precise picture: rather than viewing contrastive learning as a completely separate principle that somehow recovers class structure indirectly, it is often more accurate to view it as operating near a specific supervised contrastive objective, both at the level of the loss and at the level of the learned representation geometry.</p>

<div class="mechanism-grid fade-in">
  <div class="mechanism-card" style="border-top-color:var(--purple)">
    <div class="step-num" style="color:var(--purple)">Paper 1</div>
    <h4>Objectives are close</h4>
    <p>DCL ≈ NSCL with gap $O(1/C)$. The only difference is whether same-class samples appear in the denominator.</p>
  </div>
  <div class="mechanism-card" style="border-top-color:var(--teal)">
    <div class="step-num" style="color:var(--teal)">Paper 2</div>
    <h4>Representations align</h4>
    <p>Under shared randomness, CKA and RSA between DCL and NSCL exceed 0.81 across all datasets and architectures.</p>
  </div>
  <div class="mechanism-card" style="border-top-color:var(--coral)">
    <div class="step-num" style="color:var(--coral)">Structure</div>
    <h4>NSCL → neural collapse</h4>
    <p>The supervised counterpart has clean global minimizers: augmentation collapse + within-class collapse + simplex ETF.</p>
  </div>
</div>

</article>

<div class="fig-wide">
  <div class="fig-row-label"><strong>DCL</strong> (self-supervised)</div>
  <div class="fig-grid" style="grid-template-columns:repeat(6,1fr)">
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/umap_imagenet_random.png" alt="Random init"><div class="fig-grid-label">Init</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/umap_imagenet_dcl_epoch10.png" alt="DCL epoch 10"><div class="fig-grid-label">Epoch 10</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/umap_imagenet_dcl_epoch100.png" alt="DCL epoch 100"><div class="fig-grid-label">Epoch 100</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/umap_imagenet_dcl_epoch500.png" alt="DCL epoch 500"><div class="fig-grid-label">Epoch 500</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/umap_imagenet_dcl_epoch1000.png" alt="DCL epoch 1000"><div class="fig-grid-label">Epoch 1000</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/umap_imagenet_dcl_epoch1900.png" alt="DCL epoch 2000"><div class="fig-grid-label">Epoch 2000</div></div>
  </div>
  <div class="fig-row-label" style="margin-top:12px"><strong>NSCL</strong> (supervised)</div>
  <div class="fig-grid" style="grid-template-columns:repeat(6,1fr)">
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/umap_imagenet_random.png" alt="Random init"><div class="fig-grid-label">Init</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/umap_imagenet_nscl_epoch10.png" alt="NSCL epoch 10"><div class="fig-grid-label">Epoch 10</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/umap_imagenet_nscl_epoch100.png" alt="NSCL epoch 100"><div class="fig-grid-label">Epoch 100</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/umap_imagenet_nscl_epoch500.png" alt="NSCL epoch 500"><div class="fig-grid-label">Epoch 500</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/umap_imagenet_nscl_epoch1000.png" alt="NSCL epoch 1000"><div class="fig-grid-label">Epoch 1000</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/umap_imagenet_nscl_epoch1900.png" alt="NSCL epoch 2000"><div class="fig-grid-label">Epoch 2000</div></div>
  </div>
  <div class="figcaption">
    <strong>Figure 1.</strong> UMAP visualizations on mini-ImageNet across training. <strong>Top row:</strong> DCL (self-supervised) progressively forms semantic clusters without access to labels. <strong>Bottom row:</strong> NSCL (supervised) yields tighter, more separable clusters. Both runs start from the same random initialization. The similarity between the two trajectories is one of the central observations of this post.
  </div>
</div>

<article style="padding-top:.5rem">

<div class="paper-note">
Based on two papers: (1) A. Luthra, T. Yang, T. Galanti. <a href="https://arxiv.org/abs/2506.04411">"Self-Supervised Contrastive Learning is Approximately Supervised Contrastive Learning"</a>, NeurIPS 2025. (2) A. Luthra, P. Mishra, T. Galanti. <a href="https://arxiv.org/abs/2510.08852">"On the Alignment Between Supervised and Self-Supervised Contrastive Learning"</a>, ICLR 2025.
</div>

<h2>Part I: A supervised objective sits very near the self-supervised one</h2>

<h3>The setup</h3>

<p>Consider a labeled dataset $S = \{(x_i, y_i)\}_{i=1}^N$, but suppose that during self-supervised training we only use the inputs $x_i$, not the labels. For each sample $x_i$, we generate $K$ augmentations and map them through an encoder $f$. A standard <strong>decoupled contrastive loss</strong> (DCL) takes the form:</p>

<div class="math-display">
$$\mathcal{L}^{\text{DCL}}(f) = -\frac{1}{K^2 N}\sum_{l_1,l_2}\sum_{i} \log\frac{\exp(\text{sim}(z_i^{l_1}, z_i^{l_2}))}{\sum_{l_3}\sum_{j \neq i}\exp(\text{sim}(z_i^{l_1}, z_j^{l_3}))}$$
</div>

<p>Now compare it with the <strong>negatives-only supervised contrastive learning</strong> (NSCL) variant:</p>

<div class="math-display">
$$\mathcal{L}^{\text{NSCL}}(f) = -\frac{1}{K^2 N}\sum_{l_1,l_2}\sum_{i} \log\frac{\exp(\text{sim}(z_i^{l_1}, z_i^{l_2}))}{\sum_{l_3}\sum_{j: y_j \neq y_i}\exp(\text{sim}(z_i^{l_1}, z_j^{l_3}))}$$
</div>

<p>The numerator and positive pairs are identical. The only difference is in the denominator:</p>

<div class="compare-grid fade-in">
  <div class="compare-card" style="border-left:3px solid var(--coral)">
    <h4 style="color:var(--coral)">DCL (self-supervised)</h4>
    <p>Treats <em>every</em> other sample as a negative, including same-class samples that ideally should be positives.</p>
  </div>
  <div class="compare-card" style="border-left:3px solid var(--teal)">
    <h4 style="color:var(--teal)">NSCL (supervised)</h4>
    <p>Removes same-class samples from the negative set. Only genuinely different-class samples contribute to the denominator.</p>
  </div>
</div>

<h3>Why the gap is small</h3>

<p>Fix an anchor. In DCL, the denominator sums over all $N-1$ other samples. In NSCL, it sums over only the $N - n = n(C-1)$ different-class samples. The discrepancy is controlled by a simple quantity: the <strong>fraction of the denominator occupied by same-class samples</strong>. In a balanced $C$-class problem, that fraction is roughly $1/C$.</p>

</article>

<div class="fig-wide">
<div class="explorer fade-in">
  <div class="explorer-title">DCL vs NSCL: what's in the denominator?</div>
  <div class="explorer-subtitle">Drag the slider to change the number of classes. Red cells = same-class "false negatives" that DCL includes but NSCL removes.</div>

  <div style="display:flex;align-items:center;gap:12px;margin-bottom:16px">
    <span style="font-family:var(--sans);font-size:12px;color:var(--ink-muted)">Classes $C$:</span>
    <input type="range" min="2" max="20" value="5" id="c-slider" style="flex:1;max-width:300px" oninput="updateDenom()">
    <span id="c-val" style="font-family:var(--mono);font-size:14px;font-weight:500;color:var(--ink);min-width:24px">5</span>
  </div>

  <div class="denom-viz">
    <div class="denom-panel">
      <div class="denom-label" style="color:var(--coral)">DCL denominator</div>
      <div class="denom-grid" id="dcl-grid"></div>
      <div style="font-family:var(--sans);font-size:11px;color:var(--ink-muted);margin-top:4px" id="dcl-count"></div>
    </div>
    <div style="display:flex;align-items:center;font-family:var(--sans);font-size:13px;color:var(--ink-muted);padding-top:20px">≈</div>
    <div class="denom-panel">
      <div class="denom-label" style="color:var(--teal)">NSCL denominator</div>
      <div class="denom-grid" id="nscl-grid"></div>
      <div style="font-family:var(--sans);font-size:11px;color:var(--ink-muted);margin-top:4px" id="nscl-count"></div>
    </div>
  </div>

  <div class="gap-chart" id="gap-chart">
    <div style="font-family:var(--sans);font-size:12px;font-weight:600;color:var(--ink-muted);letter-spacing:.3px;text-transform:uppercase;margin-bottom:8px">Gap bound: $e^2 / (C-1)$</div>
    <div id="gap-bars"></div>
  </div>

  <div style="font-family:var(--sans);font-size:13px;color:var(--ink-soft);margin-top:12px;line-height:1.55" id="gap-insight"></div>
</div>

<article style="padding-top:0">

<p>This can be made precise:</p>

<div class="eq-highlight">
$$\mathcal{L}^{\text{NSCL}}(f) \;\le\; \mathcal{L}^{\text{DCL}}(f) \;\le\; \mathcal{L}^{\text{NSCL}}(f) + \frac{e^2}{C-1}$$
</div>

<p>The bound holds for any encoder $f$, without assumptions on data distribution or model class. For problems with many semantic classes, DCL is already very close to NSCL.</p>

<h3>Validating the bound during training</h3>

<p>To examine this behavior empirically, we train models using SimCLR to minimize the DCL loss and track both losses throughout training, along with the theoretical upper bound.</p>

</article>

<div class="fig-wide">
  <div class="fig-grid" style="grid-template-columns:repeat(4,1fr)">
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/svhn_simclr_losses.png" alt="SVHN losses"><div class="fig-grid-label"><strong>(a)</strong> SVHN</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/cifar10_simclr_losses.png" alt="CIFAR-10 losses"><div class="fig-grid-label"><strong>(b)</strong> CIFAR-10</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/cifar100_simclr_losses.png" alt="CIFAR-100 losses"><div class="fig-grid-label"><strong>(c)</strong> CIFAR-100</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/imagenet_simclr_losses.png" alt="mini-ImageNet losses"><div class="fig-grid-label"><strong>(d)</strong> mini-ImageNet</div></div>
  </div>
  <div class="figcaption">
    <strong>Figure 2 (top).</strong> DCL loss, NSCL loss, and the theoretical bound tracked during SimCLR training on train and test sets. All three quantities are highly correlated. The gap between DCL and NSCL becomes tighter as the number of classes increases; compare CIFAR-10 with CIFAR-100.
  </div>
</div>

<div class="fig-wide" style="margin-top:1rem">
  <div class="fig-grid" style="grid-template-columns:repeat(4,1fr)">
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/svhn_simclr_nscl_corollary.png" alt="SVHN corollary"><div class="fig-grid-label"><strong>(a)</strong> SVHN</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/cifar10_simclr_nscl_corollary.png" alt="CIFAR-10 corollary"><div class="fig-grid-label"><strong>(b)</strong> CIFAR-10</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/cifar100_simclr_nscl_corollary.png" alt="CIFAR-100 corollary"><div class="fig-grid-label"><strong>(c)</strong> CIFAR-100</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/imagenet_simclr_nscl_corollary.png" alt="mini-ImageNet corollary"><div class="fig-grid-label"><strong>(d)</strong> mini-ImageNet</div></div>
  </div>
  <div class="figcaption">
    <strong>Figure 2 (bottom).</strong> Comparing the NSCL loss of two models, one trained with DCL and the other with NSCL. The resulting NSCL losses are comparable regardless of training objective, suggesting that minimizing DCL already brings the NSCL loss close to the value achieved by direct NSCL minimization.
  </div>
</div>

<article style="padding-top:.5rem">

<h3>The gap scales as predicted with $C$</h3>

<p>The gap $\mathcal{L}^{\text{DCL}} - \mathcal{L}^{\text{NSCL}}$ as a function of the number of classes $C$ follows the theoretical bound $\log(1 + e^2/(C-1))$ closely across all training epochs and datasets.</p>

</article>

<div class="fig-wide">
  <div class="fig-grid" style="grid-template-columns:repeat(3,1fr)">
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/th1_exp2_cifar10.png" alt="CIFAR-10 gap vs C"><div class="fig-grid-label"><strong>(a)</strong> CIFAR-10</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/th1_exp2_cifar100.png" alt="CIFAR-100 gap vs C"><div class="fig-grid-label"><strong>(b)</strong> CIFAR-100</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/th1_exp2_imagenet.png" alt="mini-ImageNet gap vs C"><div class="fig-grid-label"><strong>(c)</strong> mini-ImageNet</div></div>
  </div>
  <div class="figcaption">
    <strong>Figure 3.</strong> The gap $\mathcal{L}^{\text{DCL}} - \mathcal{L}^{\text{NSCL}}$ as a function of the number of classes $C$, compared with the theoretical bound. The gap shrinks with $C$ and is highly correlated with the bound at all training epochs. Models were trained from scratch for each value of $C$ using randomly sampled class subsets.
  </div>
</div>

<article style="padding-top:.5rem">

<h3>What NSCL minimizers look like</h3>

<p>Since DCL sits close to NSCL at the level of the loss, it is natural to ask what the global minimizers of NSCL look like. The answer is remarkably structured:</p>

<div class="collapse-grid fade-in">
  <div class="collapse-card">
    <span class="collapse-icon">≡</span>
    <h4>Augmentation collapse</h4>
    <p>All augmented views of the same sample map to the same point in feature space.</p>
  </div>
  <div class="collapse-card">
    <span class="collapse-icon">⊕</span>
    <h4>Within-class collapse</h4>
    <p>All samples from the same class share a single representation.</p>
  </div>
  <div class="collapse-card">
    <span class="collapse-icon">△</span>
    <h4>Simplex ETF</h4>
    <p>Class centers form a maximally separated symmetric configuration on the unit sphere.</p>
  </div>
</div>

<p>This places NSCL within the same broader geometric picture that appears in supervised learning. The supervised problem adjacent to DCL is not arbitrary; it has the same neural-collapse structure familiar from other well-studied supervised objectives.</p>

<h2>Part II: The learned representations stay close</h2>

<p>Loss-level closeness is informative, but it does not by itself imply similar learned geometry. Two nearby objectives can still drive optimization in meaningfully different directions. The second paper addresses this directly.</p>

<h3>Shared-randomness coupling</h3>

<p>Consider training DCL and NSCL under shared randomness: same initialization, same mini-batches, same augmentations, same hyperparameters. The only difference is the objective. To compare the learned representations, define the cosine similarity matrix $\Sigma(Z)_{ij} = \cos(z_i, z_j)$, from which CKA and RSA follow naturally.</p>

<h3>The similarity matrices stay close</h3>

<p>Under this coupled training protocol, the difference between DCL and NSCL similarity matrices satisfies:</p>

<div class="math-display">
$$\|\Sigma_T^{\text{CL}} - \Sigma_T^{\text{NS}}\|_F \;\lesssim\; \frac{e^{2/\tau}}{\tau C \sqrt{B}} \cdot \exp\!\left(\frac{1}{2\tau^2 B}\sum_{t=0}^{T-1}\eta_t\right) \cdot \left(\sum_{t=0}^{T-1}\eta_t\right)$$
</div>

<p>The right-hand side becomes smaller when $C$ is larger, $B$ is larger, $\tau$ is higher, and cumulative step size is moderate. This immediately yields lower bounds on CKA and RSA:</p>

<div class="eq-highlight">
$$\text{CKA}_T \;\ge\; \frac{1-\rho_T}{1+\rho_T}, \qquad \text{RSA}_T \;\ge\; \frac{1-r_T}{1+r_T}$$
</div>

<h3>Empirical confirmation</h3>

<p>DCL and NSCL models trained under exactly matched conditions for 300 epochs yield consistently high alignment scores across datasets and architectures:</p>

</article>

<div class="fig-wide">

<div class="align-grid fade-in">
  <div class="align-card">
    <div class="align-card-title">RSA — ResNet-50</div>
    <div class="align-row"><span class="align-row-label">CIFAR-10</span><div class="align-bar-track"><div class="align-bar-fill" style="width:84%;background:var(--teal)"></div></div><span class="align-val" style="color:var(--teal)">0.84</span></div>
    <div class="align-row"><span class="align-row-label">CIFAR-100</span><div class="align-bar-track"><div class="align-bar-fill" style="width:91%;background:var(--teal)"></div></div><span class="align-val" style="color:var(--teal)">0.91</span></div>
    <div class="align-row"><span class="align-row-label">mini-ImageNet</span><div class="align-bar-track"><div class="align-bar-fill" style="width:88%;background:var(--teal)"></div></div><span class="align-val" style="color:var(--teal)">0.88</span></div>
  </div>
  <div class="align-card">
    <div class="align-card-title">CKA — ResNet-50</div>
    <div class="align-row"><span class="align-row-label">CIFAR-10</span><div class="align-bar-track"><div class="align-bar-fill" style="width:81%;background:var(--purple)"></div></div><span class="align-val" style="color:var(--purple)">0.81</span></div>
    <div class="align-row"><span class="align-row-label">CIFAR-100</span><div class="align-bar-track"><div class="align-bar-fill" style="width:91%;background:var(--purple)"></div></div><span class="align-val" style="color:var(--purple)">0.91</span></div>
    <div class="align-row"><span class="align-row-label">mini-ImageNet</span><div class="align-bar-track"><div class="align-bar-fill" style="width:87%;background:var(--purple)"></div></div><span class="align-val" style="color:var(--purple)">0.87</span></div>
  </div>
  <div class="align-card">
    <div class="align-card-title">RSA — ViT-Base</div>
    <div class="align-row"><span class="align-row-label">CIFAR-10</span><div class="align-bar-track"><div class="align-bar-fill" style="width:83%;background:var(--teal)"></div></div><span class="align-val" style="color:var(--teal)">0.83</span></div>
    <div class="align-row"><span class="align-row-label">CIFAR-100</span><div class="align-bar-track"><div class="align-bar-fill" style="width:92%;background:var(--teal)"></div></div><span class="align-val" style="color:var(--teal)">0.92</span></div>
    <div class="align-row"><span class="align-row-label">mini-ImageNet</span><div class="align-bar-track"><div class="align-bar-fill" style="width:86%;background:var(--teal)"></div></div><span class="align-val" style="color:var(--teal)">0.86</span></div>
  </div>
  <div class="align-card">
    <div class="align-card-title">CKA — ViT-Base</div>
    <div class="align-row"><span class="align-row-label">CIFAR-10</span><div class="align-bar-track"><div class="align-bar-fill" style="width:82%;background:var(--purple)"></div></div><span class="align-val" style="color:var(--purple)">0.82</span></div>
    <div class="align-row"><span class="align-row-label">CIFAR-100</span><div class="align-bar-track"><div class="align-bar-fill" style="width:93%;background:var(--purple)"></div></div><span class="align-val" style="color:var(--purple)">0.93</span></div>
    <div class="align-row"><span class="align-row-label">mini-ImageNet</span><div class="align-bar-track"><div class="align-bar-fill" style="width:85%;background:var(--purple)"></div></div><span class="align-val" style="color:var(--purple)">0.85</span></div>
  </div>
</div>
<div class="figcaption" style="max-width:680px;margin:0 auto;padding:0 2rem">
  <strong>Figure 5.</strong> Representation similarity between DCL and NSCL models trained with matched initialization and mini-batch order. All values exceed 0.81. Alignment is strongest when the number of classes is largest (CIFAR-100), matching the theory. Scores are nearly identical across ResNet-50 and ViT-Base, confirming the relationship is not architecture-specific.
</div>
</div>

<article style="padding-top:.5rem">

<p>Two patterns are especially notable. First, alignment is strongest when the number of classes is largest — CIFAR-100 and mini-ImageNet reach 0.91+ — matching the theory that more classes imply a smaller loss gap. Second, scores are nearly identical across ResNet-50 and ViT-Base, indicating the DCL-NSCL relationship is not an artifact of a particular architecture.</p>

<h3>But weights can still diverge</h3>

<p>In contrast, parameter-space coupling is much less stable. The weight-space bound has no batch-size moderation in the exponent, so representation-level alignment can remain stable even when parameter-space divergence becomes large. This is not especially surprising — deep networks have substantial parameter redundancy, so two models can follow very different paths in weight space while still inducing very similar representation geometry.</p>

<div class="compare-grid fade-in">
  <div class="compare-card" style="border-left:3px solid var(--teal)">
    <h4 style="color:var(--teal)">Representation similarity</h4>
    <p>Stays high (>0.81) because the bound scales as $1/(\tau C \sqrt{B})$ — batch size moderates the divergence. The geometry is what matters for downstream tasks.</p>
  </div>
  <div class="compare-card" style="border-left:3px solid var(--coral)">
    <h4 style="color:var(--coral)">Parameter divergence</h4>
    <p>Can grow large because the weight-space bound lacks batch-size moderation in its exponent. But this doesn't matter — deep networks have enough redundancy that different weights can encode the same geometry.</p>
  </div>
</div>

<h2>The right mental model</h2>

<p>The standard description is that contrastive learning is a self-supervised method that nonetheless learns semantic structure. While true, it leaves open why this happens so consistently.</p>

<p>The picture here is more specific. The self-supervised contrastive objective is already close to a supervised contrastive objective that excludes same-class negatives. That supervised objective has global minimizers with the same neural-collapse geometry familiar from supervised learning. And under shared training randomness, the two methods learn highly aligned representations throughout training.</p>

<p>This does not mean that self-supervised and supervised learning are identical, nor that labels are irrelevant. But it does suggest that the gap between the two is <strong>narrower, and more structured</strong>, than the usual informal description implies.</p>

<div class="takeaway">
  <h3>Takeaway</h3>
  <p>The main point is not merely that self-supervised and supervised contrastive learning are related. It is that the relation is surprisingly tight and structurally clean.</p>
  <p><strong>The objectives are close.</strong> The standard self-supervised contrastive loss approximates the NSCL loss, with a gap that shrinks as $O(1/C)$.</p>
  <p><strong>The nearby supervised problem has elegant geometry.</strong> NSCL minimizers exhibit augmentation collapse, within-class collapse, and simplex ETF structure.</p>
  <p><strong>The learned representations stay aligned.</strong> Under shared training randomness, DCL and NSCL produce highly similar representation geometry (CKA, RSA > 0.81), even when their parameters diverge.</p>
  <p>A useful way to view contrastive learning, then, is not as a completely separate mechanism that somehow recovers semantics, but as a self-supervised procedure whose objective and learned geometry already lie close to a specific supervised counterpart.</p>
</div>

</article>

<div class="post-footer">
  <p>Originally published on <a href="https://dlfundamentals.github.io/blog/">Theory/Simplified</a> &middot; Based on <a href="https://arxiv.org/abs/2506.04411">Luthra, Yang, Galanti — NeurIPS 2025</a> and <a href="https://arxiv.org/abs/2510.08852">Luthra, Mishra, Galanti — ICLR 2025</a></p>
</div>
</div>

<script>
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

function updateDenom(){
  var C=parseInt(document.getElementById('c-slider').value,10);
  document.getElementById('c-val').textContent=C;

  var n=3;
  var N=C*n;
  var gridSize=Math.min(N-1,35);
  var cols=Math.ceil(Math.sqrt(gridSize));

  var dclGrid=document.getElementById('dcl-grid');
  dclGrid.innerHTML='';
  dclGrid.style.gridTemplateColumns='repeat('+cols+',1fr)';
  for(var i=0;i<gridSize;i++){
    var cell=document.createElement('div');
    cell.className='denom-cell';
    var isSameClass=i<(n-1);
    cell.style.background=isSameClass?'var(--coral)':'var(--teal-soft)';
    cell.style.opacity=isSameClass?'0.7':'1';
    dclGrid.appendChild(cell);
  }
  document.getElementById('dcl-count').textContent='All '+(N-1)+' other samples';

  var nscGrid=document.getElementById('nscl-grid');
  nscGrid.innerHTML='';
  nscGrid.style.gridTemplateColumns='repeat('+cols+',1fr)';
  var nscCount=N-n;
  for(var j=0;j<Math.min(nscCount,gridSize);j++){
    var cell2=document.createElement('div');
    cell2.className='denom-cell';
    cell2.style.background='var(--teal-soft)';
    nscGrid.appendChild(cell2);
  }
  document.getElementById('nscl-count').textContent=nscCount+' different-class only';

  var gaps=[2,5,10,20,50,100];
  var barsHtml='';
  gaps.forEach(function(gc){
    var bound=Math.log(1+Math.exp(2)/(gc-1));
    var pct=Math.min(100,bound/2.5*100);
    var isActive=gc===C;
    barsHtml+='<div class="gap-bar-row">';
    barsHtml+='<span class="gap-bar-label" style="'+(isActive?'font-weight:600;color:var(--ink)':'')+'">C='+gc+'</span>';
    barsHtml+='<div class="gap-bar-track"><div class="gap-bar-fill" style="width:'+pct+'%;background:'+(isActive?'var(--accent)':'var(--ink-muted)')+';opacity:'+(isActive?1:0.3)+'"></div></div>';
    barsHtml+='<span class="gap-bar-val" style="'+(isActive?'font-weight:600;color:var(--ink)':'')+'">'+bound.toFixed(3)+'</span>';
    barsHtml+='</div>';
  });
  document.getElementById('gap-bars').innerHTML=barsHtml;

  var frac=((n-1)/(N-1)*100).toFixed(1);
  var gapVal=(Math.exp(2)/(C-1)).toFixed(3);
  document.getElementById('gap-insight').innerHTML='With <strong>C = '+C+'</strong> classes, same-class samples are <strong>'+frac+'%</strong> of DCL\\'s denominator. The gap bound is <strong>'+gapVal+'</strong> — '+(C>=20?'negligibly small.':C>=10?'already quite small.':'noticeable but shrinking fast.');
}
updateDenom();

var obs=new IntersectionObserver(function(entries){
  entries.forEach(function(e){
    if(e.isIntersecting)e.target.classList.add('visible');
  });
},{threshold:.15});

document.querySelectorAll('.post-scope .fade-in').forEach(function(el){
  obs.observe(el);
});
</script>
