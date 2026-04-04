<link rel="preconnect" href="https://raw.githubusercontent.com" crossorigin>
<link rel="preconnect" href="https://cdn.jsdelivr.net" crossorigin>
<link rel="preconnect" href="https://fonts.googleapis.com" crossorigin>
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.min.css">
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.min.js"></script>
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/contrib/auto-render.min.js"></script>
<link href="https://fonts.googleapis.com/css2?family=Lora:ital,wght@0,400;0,500;0,600;1,400;1,500&family=IBM+Plex+Mono:wght@400;500&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&display=swap" rel="stylesheet">

<style>
.ps{--bg:#f6f3ee;--bg-warm:#f0ece4;--surface:#ede9e0;--surface-2:#e8e3d8;--border:#d8d2c6;--border-lt:#e4dfd4;--text:#18160f;--text-soft:#3a3628;--muted:#7a7060;--muted-lt:#a09880;--accent:#1e4f7a;--accent-mid:#2a6199;--accent-soft:#d4e6f5;--accent-xs:#ebf4fc;--gold:#b8860b;--gold-soft:#fdf4d8;--gold-bd:#d4a820;--green:#2a6645;--green-soft:#e4f0ea;--red:#8f2a2a;--red-soft:#f5e8e8;--teal:#1a7a5c;--teal-soft:#e4f2ec;--amber:#a06810;--amber-soft:#faf0da;--serif:'Lora',Georgia,serif;--sans:'DM Sans',-apple-system,sans-serif;--mono:'IBM Plex Mono',monospace;}
.ps,.ps *,.ps *::before,.ps *::after{box-sizing:border-box;}
.ps{width:100%;max-width:100%;background:var(--bg);color:var(--text);font-family:var(--sans);font-weight:300;font-size:17px;line-height:1.78;-webkit-font-smoothing:antialiased;overflow-x:clip;}
.ps ::selection{background:var(--accent-soft);color:var(--text);}
.ps a{color:var(--accent-mid);text-decoration:none;}
.ps a:hover{text-decoration:underline;}
.ps img{max-width:100%;height:auto;display:block;}
.ps .top-bar{height:3px;background:linear-gradient(90deg,#1e4f7a 0%,#2a6199 55%,#b8860b 100%);}

/* ── HERO ── */
.ps .hero{max-width:820px;margin:0 auto;padding:3.5rem 2.5rem 2.5rem;border-bottom:1px solid var(--border);}
.ps .hero-eyebrow{font-family:var(--mono);font-size:10.5px;font-weight:500;letter-spacing:.12em;text-transform:uppercase;color:var(--muted);margin-bottom:1.1rem;display:flex;align-items:center;gap:.5rem;}
.ps .hero-eyebrow::before{content:'';display:inline-block;width:18px;height:2px;background:var(--gold);flex-shrink:0;}
.ps .hero h1{font-family:var(--serif);font-size:clamp(1.9rem,4.5vw,2.9rem);font-weight:600;line-height:1.13;letter-spacing:-.025em;color:var(--text);margin:0 0 1.3rem;max-width:680px;}
.ps .hero h1 em{font-style:italic;font-weight:400;color:var(--accent);}
.ps .hero-subtitle{font-size:1.08rem;color:var(--muted);font-style:italic;font-weight:300;max-width:600px;line-height:1.68;border-left:2px solid var(--border);padding-left:1.1rem;margin:0 0 1.6rem;}
.ps .hero-meta{font-family:var(--mono);font-size:11px;color:var(--muted-lt);display:flex;gap:1.25rem;flex-wrap:wrap;align-items:center;}
.ps .paper-badge{display:inline-flex;align-items:center;gap:5px;background:var(--accent-soft);color:var(--accent);border:1px solid #b5cfe6;padding:3px 10px;border-radius:20px;font-weight:500;font-size:10.5px;}

/* ── ARTICLE ── */
.ps article{max-width:820px;margin:0 auto;padding:2.5rem 2.5rem 2rem;}
.ps article p{margin:0 0 1.15rem;font-size:1.02rem;}
.ps article p.lead::first-letter{font-family:var(--serif);font-size:3.6em;font-weight:600;line-height:.75;float:left;margin:.06em .1em 0 0;color:var(--accent);}
.ps article h2{font-family:var(--serif);font-size:1.48rem;font-weight:500;line-height:1.22;letter-spacing:-.01em;margin:2.75rem 0 1rem;padding-top:2rem;border-top:1px solid var(--border);color:var(--text);}
.ps article h2:first-child{border-top:none;padding-top:0;margin-top:0;}
.ps article h3{font-family:var(--mono);font-size:.73rem;font-weight:500;letter-spacing:.1em;text-transform:uppercase;color:var(--muted);margin:2rem 0 .65rem;}
.ps strong{font-weight:500;}
.ps code{font-family:var(--mono);font-size:.85em;background:var(--surface);border:1px solid var(--border-lt);padding:1px 6px;border-radius:3px;color:var(--text-soft);}

/* ── CALLOUTS & FINDINGS ── */
.ps .callout{background:var(--gold-soft);border-left:3px solid var(--gold-bd);padding:1.05rem 1.3rem;border-radius:0 7px 7px 0;margin:1.75rem 0;font-size:.98rem;line-height:1.68;color:var(--text-soft);}
.ps .callout strong{display:block;margin-bottom:.3rem;font-weight:500;color:var(--text);}
.ps .callout p{margin-bottom:.6rem;}
.ps .callout p:last-child{margin:0;}
.ps .finding{background:var(--accent-xs);border:1px solid #c0d9ef;border-left:3px solid var(--accent-mid);border-radius:0 7px 7px 0;padding:1rem 1.3rem;margin:1.4rem 0;font-size:.95rem;color:var(--text-soft);}
.ps .finding-label{font-family:var(--mono);font-size:.68rem;font-weight:500;letter-spacing:.1em;text-transform:uppercase;color:var(--accent);margin-bottom:.4rem;}
.ps .finding-red{background:var(--red-soft);border:1px solid #d4a0a0;border-left:3px solid var(--red);border-radius:0 7px 7px 0;padding:1rem 1.3rem;margin:1.4rem 0;font-size:.95rem;color:var(--text-soft);}
.ps .finding-red .finding-label{color:var(--red);}
.ps .finding-teal{background:var(--teal-soft);border:1px solid #9fd4b4;border-left:3px solid var(--teal);border-radius:0 7px 7px 0;padding:1rem 1.3rem;margin:1.4rem 0;font-size:.95rem;color:var(--text-soft);}
.ps .finding-teal .finding-label{color:var(--teal);}

/* ── MATH ── */
.ps .math-display{background:var(--surface);border:1px solid var(--border);border-radius:8px;padding:1.35rem 1.75rem;margin:1.6rem 0;text-align:center;overflow-x:auto;}
.ps .math-label{font-family:var(--mono);font-size:.68rem;font-weight:500;letter-spacing:.1em;text-transform:uppercase;color:var(--muted);margin-bottom:.65rem;}
.ps .eq-highlight{background:var(--gold-soft);border:1px solid var(--gold-bd);border-radius:8px;padding:1.15rem 1.75rem;margin:1.6rem 0;text-align:center;overflow-x:auto;}

/* ── STEPS ── */
.ps .steps{margin:1.5rem 0;}
.ps .step{display:flex;gap:1rem;margin-bottom:1.15rem;align-items:flex-start;}
.ps .step-num{background:var(--accent);color:white;width:26px;height:26px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-family:var(--mono);font-size:.7rem;font-weight:500;flex-shrink:0;margin-top:.12rem;box-shadow:0 1px 5px rgba(30,79,122,.22);}
.ps .step-body{flex:1;}
.ps .step-title{font-weight:500;margin-bottom:.12rem;font-size:.97rem;}
.ps .step-desc{font-size:.9rem;color:var(--muted);line-height:1.62;font-weight:300;}

/* ── PAPER NOTE ── */
.ps .paper-note{font-family:var(--mono);font-size:.76rem;color:var(--accent);background:var(--accent-xs);border:1px solid #c0d9ef;padding:.8rem 1rem .8rem 2.1rem;border-radius:5px;margin:1.1rem 0 1.6rem;line-height:1.7;position:relative;}
.ps .paper-note::before{content:"◆";position:absolute;left:.8rem;top:.85rem;font-size:8px;}
.ps .paper-note a{color:var(--accent);font-weight:500;}

/* ── PULL QUOTE ── */
.ps .pull-quote{font-family:var(--serif);font-size:1.2rem;font-style:italic;color:var(--accent);border-top:2px solid var(--accent-soft);border-bottom:2px solid var(--accent-soft);padding:1.1rem 0;margin:2rem 0;line-height:1.55;text-align:center;}

/* ── FIGURES (full-bleed) ── */
.ps .fig-wide{max-width:1120px;margin:.8rem auto 1.1rem;padding:0 2.5rem;}
.ps .fig-grid{display:grid;gap:10px;align-items:start;}
.ps .fig-grid>div{min-width:0;}
.ps .fig-grid img{width:100%;border:1px solid var(--border);border-radius:8px;background:var(--surface);}
.ps .fig-grid-label{font-family:var(--mono);font-size:10px;color:var(--muted-lt);line-height:1.4;margin-top:5px;text-align:center;letter-spacing:.02em;}
.ps .fig-row-label{font-family:var(--mono);font-size:10.5px;font-weight:500;color:var(--muted);margin:0 0 6px;letter-spacing:.04em;text-transform:uppercase;}
.ps .figcaption{font-family:var(--mono);font-size:10.5px;color:var(--muted-lt);line-height:1.6;margin-top:8px;letter-spacing:.01em;}

/* ── EXPLORER ── */
.ps .explorer{background:var(--bg-warm);border:1px solid var(--border);border-radius:10px;overflow:hidden;margin:1.75rem 0;}
.ps .explorer-header{background:var(--surface);border-bottom:1px solid var(--border);padding:.8rem 1.25rem;display:flex;align-items:baseline;gap:.75rem;}
.ps .explorer-title{font-family:var(--mono);font-size:.72rem;font-weight:500;letter-spacing:.08em;text-transform:uppercase;color:var(--text);}
.ps .explorer-subtitle{font-size:12px;color:var(--muted);font-weight:300;}
.ps .explorer-body{padding:1.1rem 1.25rem 1.25rem;}

/* ── DENOM VIZ ── */
.ps .denom-viz{display:grid;grid-template-columns:minmax(0,1fr) auto minmax(0,1fr);gap:16px;align-items:start;margin-top:1rem;}
.ps .denom-label{font-family:var(--mono);font-size:.72rem;font-weight:500;letter-spacing:.06em;text-transform:uppercase;margin-bottom:6px;}
.ps .denom-grid{display:grid;gap:3px;background:var(--bg);border:1px solid var(--border-lt);border-radius:8px;padding:9px;min-height:90px;}
.ps .denom-cell{width:100%;aspect-ratio:1;border-radius:3px;}
.ps .denom-count{font-family:var(--mono);font-size:10px;color:var(--muted-lt);margin-top:4px;letter-spacing:.02em;}

/* ── GAP CHART ── */
.ps .gap-chart{margin-top:12px;background:var(--bg);border:1px solid var(--border-lt);border-radius:8px;padding:10px 12px;}
.ps .gap-chart-title{font-family:var(--mono);font-size:9.5px;font-weight:500;color:var(--muted-lt);letter-spacing:.08em;text-transform:uppercase;margin-bottom:8px;}
.ps .gap-bar-row{display:grid;grid-template-columns:40px 1fr 52px;gap:8px;align-items:center;margin:5px 0;}
.ps .gap-bar-label{font-family:var(--mono);font-size:10px;color:var(--muted-lt);}
.ps .gap-bar-track{height:6px;background:var(--surface-2);border-radius:3px;overflow:hidden;}
.ps .gap-bar-fill{height:100%;border-radius:3px;transition:width .3s ease;}
.ps .gap-bar-val{font-family:var(--mono);font-size:10px;color:var(--muted-lt);text-align:right;}
.ps .gap-insight{font-family:var(--sans);font-size:13px;color:var(--text-soft);margin-top:10px;line-height:1.6;font-weight:300;}

/* ── ALIGNMENT BARS ── */
.ps .align-grid{display:grid;grid-template-columns:repeat(4,minmax(0,1fr));gap:10px;margin-bottom:14px;}
.ps .align-card{background:var(--bg-warm);border:1px solid var(--border);border-radius:8px;padding:10px 12px;}
.ps .align-card-title{font-family:var(--mono);font-size:10px;font-weight:500;color:var(--muted);letter-spacing:.06em;text-transform:uppercase;margin-bottom:10px;}
.ps .align-row{display:grid;grid-template-columns:90px 1fr 36px;gap:6px;align-items:center;margin:5px 0;}
.ps .align-row-label{font-family:var(--mono);font-size:10px;color:var(--muted-lt);}
.ps .align-bar-track{height:6px;background:var(--surface-2);border-radius:3px;overflow:hidden;}
.ps .align-bar-fill{height:100%;border-radius:3px;}
.ps .align-val{font-family:var(--mono);font-size:11px;font-weight:500;text-align:right;}

/* ── RANGE INPUTS ── */
.ps input[type=range]{-webkit-appearance:none;width:100%;height:3px;background:var(--border);border-radius:2px;outline:none;cursor:pointer;}
.ps input[type=range]::-webkit-slider-thumb{-webkit-appearance:none;width:14px;height:14px;border-radius:50%;background:var(--accent);border:2px solid white;box-shadow:0 1px 4px rgba(30,79,122,.35);cursor:pointer;}

/* ── TAKEAWAY ── */
.ps .takeaway{background:var(--text);color:#e8e2d8;padding:1.85rem 2rem;border-radius:12px;margin:2.75rem 0 1.5rem;position:relative;overflow:hidden;}
.ps .takeaway::before{content:'';position:absolute;top:0;left:0;right:0;height:3px;background:linear-gradient(90deg,var(--accent-mid),var(--gold));}
.ps .takeaway h3{font-family:var(--mono);font-size:.68rem;font-weight:500;letter-spacing:.12em;text-transform:uppercase;color:var(--gold-bd);margin:0 0 1.1rem;border:none;padding:0;}
.ps .takeaway p{color:#c2bdb4;margin-bottom:1rem;font-size:1rem;line-height:1.72;}
.ps .takeaway p:last-child{margin-bottom:0;}
.ps .takeaway strong{color:#e8e2d8;}

/* ── FOOTER ── */
.ps .post-footer{max-width:820px;margin:0 auto;padding:1.5rem 2.5rem 3rem;text-align:center;border-top:1px solid var(--border);}
.ps .post-footer p{font-family:var(--mono);font-size:11px;color:var(--muted-lt);margin:0;}
.ps .post-footer a{color:var(--accent-mid);}

.ps hr{border:none;border-top:1px solid var(--border);margin:0;}
.ps .fade-in{opacity:0;transform:translateY(16px);transition:opacity .65s ease,transform .65s ease;}
.ps .fade-in.visible{opacity:1;transform:translateY(0);}

@media(max-width:900px){.ps .align-grid{grid-template-columns:repeat(2,minmax(0,1fr));}}
@media(max-width:700px){.ps .denom-viz{grid-template-columns:1fr;}.ps .fig-wide{padding:0 1.25rem;}}
@media(max-width:600px){.ps .align-grid{grid-template-columns:1fr 1fr;}.ps .fig-grid{grid-template-columns:1fr 1fr !important;}}
@media(max-width:480px){.ps .hero,.ps article,.ps .post-footer,.ps .fig-wide{padding-left:1.25rem;padding-right:1.25rem;}.ps .hero h1{font-size:1.8rem;}.ps .fig-grid{grid-template-columns:1fr !important;}}
</style>

<div class="ps">
<div class="top-bar"></div>

<div class="hero">
  <div class="hero-eyebrow">Representation Learning &middot; Contrastive Learning &middot; Theory</div>
  <h1>Self-Supervised Learning <em>≈</em> Supervised Learning</h1>
  <p class="hero-subtitle">Self-supervised contrastive learning is trained without labels, yet the representations look remarkably class-aware. The reason is structural: its objective and learned geometry are already much closer to a supervised contrastive counterpart than they first appear.</p>
  <div class="hero-meta">
    <span>By Tomer Galanti &amp; Achleshwar Luthra</span>
    <span>&middot;</span>
    <span>March 11, 2026</span>
    <span>&middot;</span>
    <span>16 min read</span>
    <span>&middot;</span>
    <span class="paper-badge">&#9670; NeurIPS 2025 + ICLR 2025</span>
  </div>
</div>

<article>

  <h2>Introduction</h2>

  <p class="lead">Self-supervised contrastive learning is trained without labels, yet the learned representations often display clear semantic structure: same-class samples cluster together, linear probes perform well, and downstream transfer can approach supervised pretraining. This raises a basic question: <strong>why does a label-free objective produce representations that look so class-aware?</strong></p>

  <p>A useful way to think about this phenomenon is that standard contrastive learning is not as far from supervised contrastive learning as it may first appear. The closeness appears at two levels:</p>

  <div class="callout">
    <strong>Three interlocking results</strong>
    <p><strong>1. The objectives are close.</strong> The standard self-supervised contrastive loss is close to a supervised variant that excludes same-class negatives, with a gap that shrinks as $O(1/C)$ in the number of classes.</p>
    <p><strong>2. The induced geometry is close.</strong> Under shared training randomness, the learned representations remain strongly aligned throughout training, even when the parameters themselves diverge.</p>
    <p><strong>3. The supervised counterpart is geometrically tractable.</strong> Its global minimizers exhibit augmentation collapse, within-class collapse, and simplex ETF structure.</p>
  </div>

  <p>Taken together, these results suggest a more precise picture: rather than viewing contrastive learning as a completely separate principle that somehow recovers class structure indirectly, it is often more accurate to view it as operating near a specific supervised contrastive objective, both at the level of the loss and at the level of the learned representation geometry.</p>

  <div class="steps">
    <div class="step">
      <div class="step-num" style="background:#5a4ab8;">P1</div>
      <div class="step-body">
        <div class="step-title">Objectives are close.</div>
        <div class="step-desc">DCL ≈ NSCL with gap $O(1/C)$. The only difference is whether same-class samples appear in the denominator.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num" style="background:var(--teal);">P2</div>
      <div class="step-body">
        <div class="step-title">Representations align.</div>
        <div class="step-desc">Under shared randomness, CKA and RSA between DCL and NSCL exceed 0.81 across all datasets and architectures.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num">NC</div>
      <div class="step-body">
        <div class="step-title">NSCL → neural collapse.</div>
        <div class="step-desc">The supervised counterpart has clean global minimizers: augmentation collapse + within-class collapse + simplex ETF.</div>
      </div>
    </div>
  </div>

</article>

<!-- UMAP figures -->
<div class="fig-wide">
  <div class="fig-row-label">DCL (self-supervised)</div>
  <div class="fig-grid" style="grid-template-columns:repeat(6,1fr)">
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/umap_imagenet_random.png" alt="Random init" width="300" height="300" decoding="async"><div class="fig-grid-label">Init</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/umap_imagenet_dcl_epoch10.png" alt="DCL epoch 10" width="300" height="300" loading="lazy" decoding="async"><div class="fig-grid-label">Epoch 10</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/umap_imagenet_dcl_epoch100.png" alt="DCL epoch 100" width="300" height="300" loading="lazy" decoding="async"><div class="fig-grid-label">Epoch 100</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/umap_imagenet_dcl_epoch500.png" alt="DCL epoch 500" width="300" height="300" loading="lazy" decoding="async"><div class="fig-grid-label">Epoch 500</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/umap_imagenet_dcl_epoch1000.png" alt="DCL epoch 1000" width="300" height="300" loading="lazy" decoding="async"><div class="fig-grid-label">Epoch 1000</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/umap_imagenet_dcl_epoch1900.png" alt="DCL epoch 2000" width="300" height="300" loading="lazy" decoding="async"><div class="fig-grid-label">Epoch 2000</div></div>
  </div>
  <div class="fig-row-label" style="margin-top:12px">NSCL (supervised)</div>
  <div class="fig-grid" style="grid-template-columns:repeat(6,1fr)">
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/umap_imagenet_random.png" alt="Random init" width="300" height="300" loading="lazy" decoding="async"><div class="fig-grid-label">Init</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/umap_imagenet_nscl_epoch10.png" alt="NSCL epoch 10" width="300" height="300" loading="lazy" decoding="async"><div class="fig-grid-label">Epoch 10</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/umap_imagenet_nscl_epoch100.png" alt="NSCL epoch 100" width="300" height="300" loading="lazy" decoding="async"><div class="fig-grid-label">Epoch 100</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/umap_imagenet_nscl_epoch500.png" alt="NSCL epoch 500" width="300" height="300" loading="lazy" decoding="async"><div class="fig-grid-label">Epoch 500</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/umap_imagenet_nscl_epoch1000.png" alt="NSCL epoch 1000" width="300" height="300" loading="lazy" decoding="async"><div class="fig-grid-label">Epoch 1000</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/umap_imagenet_nscl_epoch1900.png" alt="NSCL epoch 2000" width="300" height="300" loading="lazy" decoding="async"><div class="fig-grid-label">Epoch 2000</div></div>
  </div>
  <p class="figcaption"><strong>Fig. 1.</strong> UMAP visualizations on mini-ImageNet across training. DCL (self-supervised, top) progressively forms semantic clusters without access to labels. NSCL (supervised, bottom) yields tighter clusters. Both runs start from the same random initialization.</p>
</div>

<article>

  <div class="paper-note">
    Based on two papers: (1) A. Luthra, T. Yang, T. Galanti. <a href="https://arxiv.org/abs/2506.04411">&ldquo;Self-Supervised Contrastive Learning is Approximately Supervised Contrastive Learning&rdquo;</a>, NeurIPS 2025. (2) A. Luthra, P. Mishra, T. Galanti. <a href="https://arxiv.org/abs/2510.08852">&ldquo;On the Alignment Between Supervised and Self-Supervised Contrastive Learning&rdquo;</a>, ICLR 2025.
  </div>

  <h2>Part I — A supervised objective sits very near the self-supervised one</h2>

  <h3>The setup</h3>

  <p>Consider a labeled dataset $S = \{(x_i, y_i)\}_{i=1}^N$, but suppose that during self-supervised training we only use the inputs $x_i$, not the labels. For each sample $x_i$, we generate $K$ augmentations and map them through an encoder $f$. A standard <strong>decoupled contrastive loss</strong> (DCL) takes the form:</p>

  <div class="math-display">
    $$\mathcal{L}^{\text{DCL}}(f) = -\frac{1}{K^2 N}\sum_{l_1,l_2}\sum_{i} \log\frac{\exp(\text{sim}(z_i^{l_1}, z_i^{l_2}))}{\sum_{l_3}\sum_{j \neq i}\exp(\text{sim}(z_i^{l_1}, z_j^{l_3}))}$$
  </div>

  <p>Compare it with the <strong>negatives-only supervised contrastive learning</strong> (NSCL) variant:</p>

  <div class="math-display">
    $$\mathcal{L}^{\text{NSCL}}(f) = -\frac{1}{K^2 N}\sum_{l_1,l_2}\sum_{i} \log\frac{\exp(\text{sim}(z_i^{l_1}, z_i^{l_2}))}{\sum_{l_3}\sum_{j: y_j \neq y_i}\exp(\text{sim}(z_i^{l_1}, z_j^{l_3}))}$$
  </div>

  <p>The numerator and positive pairs are identical. The only difference is in the denominator:</p>

  <div class="finding-red">
    <div class="finding-label">DCL (self-supervised)</div>
    Treats <em>every</em> other sample as a negative, including same-class samples that ideally should be positives. These are "false negatives" — they inflate the denominator and create a systematic bias.
  </div>

  <div class="finding-teal">
    <div class="finding-label">NSCL (supervised)</div>
    Removes same-class samples from the negative set. Only genuinely different-class samples contribute to the denominator. This is the ideal supervised counterpart.
  </div>

  <h3>Why the gap is small</h3>

  <p>Fix an anchor. In DCL, the denominator sums over all $N-1$ other samples. In NSCL, it sums over only the $N - n = n(C-1)$ different-class samples. The discrepancy is controlled by a simple quantity: the <strong>fraction of the denominator occupied by same-class samples</strong>. In a balanced $C$-class problem, that fraction is roughly $1/C$.</p>

</article>

<!-- Interactive denominator explorer -->
<div class="fig-wide">
  <div class="explorer fade-in">
    <div class="explorer-header">
      <span class="explorer-title">DCL vs NSCL — what's in the denominator?</span>
      <span class="explorer-subtitle">— drag to change the number of classes</span>
    </div>
    <div class="explorer-body">
      <div style="display:flex;align-items:center;gap:12px;margin-bottom:14px;">
        <span style="font-family:var(--mono);font-size:10.5px;color:var(--muted);letter-spacing:.04em;">Classes $C$:</span>
        <input type="range" min="2" max="20" value="5" id="c-slider" style="flex:1;max-width:300px;" oninput="updateDenom()">
        <span id="c-val" style="font-family:var(--mono);font-size:14px;font-weight:500;color:var(--accent);min-width:24px;">5</span>
      </div>

      <div class="denom-viz">
        <div>
          <div class="denom-label" style="color:var(--red);">DCL denominator</div>
          <div class="denom-grid" id="dcl-grid"></div>
          <div class="denom-count" id="dcl-count"></div>
        </div>
        <div style="display:flex;align-items:center;font-family:var(--serif);font-size:1.4rem;color:var(--muted-lt);padding-top:18px;">≈</div>
        <div>
          <div class="denom-label" style="color:var(--teal);">NSCL denominator</div>
          <div class="denom-grid" id="nscl-grid"></div>
          <div class="denom-count" id="nscl-count"></div>
        </div>
      </div>

      <div class="gap-chart">
        <div class="gap-chart-title">Gap bound — $e^2 / (C-1)$</div>
        <div id="gap-bars"></div>
      </div>

      <div class="gap-insight" id="gap-insight"></div>
    </div>
  </div>
</div>

<article>

  <p>This can be made precise:</p>

  <div class="eq-highlight">
    $$\mathcal{L}^{\text{NSCL}}(f) \;\le\; \mathcal{L}^{\text{DCL}}(f) \;\le\; \mathcal{L}^{\text{NSCL}}(f) + \frac{e^2}{C-1}$$
  </div>

  <p>The bound holds for any encoder $f$, without assumptions on data distribution or model class. For problems with many semantic classes, DCL is already very close to NSCL.</p>

  <div class="pull-quote">&ldquo;The gap between DCL and NSCL shrinks as $O(1/C)$ — meaning self-supervised contrastive learning on ImageNet is already very close to its supervised counterpart.&rdquo;</div>

  <h3>Validating the bound during training</h3>

  <p>Training models using SimCLR to minimize the DCL loss, tracking both losses throughout training alongside the theoretical upper bound, confirms that all three quantities are highly correlated — and that the gap tightens as $C$ grows.</p>

</article>

<div class="fig-wide">
  <div class="fig-grid" style="grid-template-columns:repeat(4,1fr)">
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/svhn_simclr_losses.png" alt="SVHN losses" width="400" height="300" loading="lazy" decoding="async"><div class="fig-grid-label">(a) SVHN</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/cifar10_simclr_losses.png" alt="CIFAR-10 losses" width="400" height="300" loading="lazy" decoding="async"><div class="fig-grid-label">(b) CIFAR-10</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/cifar100_simclr_losses.png" alt="CIFAR-100 losses" width="400" height="300" loading="lazy" decoding="async"><div class="fig-grid-label">(c) CIFAR-100</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/imagenet_simclr_losses.png" alt="mini-ImageNet losses" width="400" height="300" loading="lazy" decoding="async"><div class="fig-grid-label">(d) mini-ImageNet</div></div>
  </div>
  <p class="figcaption"><strong>Fig. 2 (top).</strong> DCL loss, NSCL loss, and the theoretical bound tracked during SimCLR training. All three quantities are highly correlated. The gap between DCL and NSCL becomes tighter as the number of classes increases; compare CIFAR-10 with CIFAR-100.</p>
</div>

<div class="fig-wide" style="margin-top:.45rem;">
  <div class="fig-grid" style="grid-template-columns:repeat(4,1fr)">
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/svhn_simclr_nscl_corollary.png" alt="SVHN corollary" width="400" height="300" loading="lazy" decoding="async"><div class="fig-grid-label">(a) SVHN</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/cifar10_simclr_nscl_corollary.png" alt="CIFAR-10 corollary" width="400" height="300" loading="lazy" decoding="async"><div class="fig-grid-label">(b) CIFAR-10</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/cifar100_simclr_nscl_corollary.png" alt="CIFAR-100 corollary" width="400" height="300" loading="lazy" decoding="async"><div class="fig-grid-label">(c) CIFAR-100</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/imagenet_simclr_nscl_corollary.png" alt="mini-ImageNet corollary" width="400" height="300" loading="lazy" decoding="async"><div class="fig-grid-label">(d) mini-ImageNet</div></div>
  </div>
  <p class="figcaption"><strong>Fig. 2 (bottom).</strong> Comparing the NSCL loss of two models — one trained with DCL, one with NSCL. The resulting NSCL losses are comparable regardless of training objective, suggesting minimizing DCL already brings the NSCL loss close to the value achieved by direct NSCL minimization.</p>
</div>

<article>

  <h3>The gap scales as predicted with $C$</h3>

  <p>The gap $\mathcal{L}^{\text{DCL}} - \mathcal{L}^{\text{NSCL}}$ as a function of the number of classes $C$ follows the theoretical bound $\log(1 + e^2/(C-1))$ closely across all training epochs and datasets.</p>

</article>

<div class="fig-wide">
  <div class="fig-grid" style="grid-template-columns:repeat(3,1fr)">
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/th1_exp2_cifar10.png" alt="CIFAR-10 gap vs C" width="400" height="300" loading="lazy" decoding="async"><div class="fig-grid-label">(a) CIFAR-10</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/th1_exp2_cifar100.png" alt="CIFAR-100 gap vs C" width="400" height="300" loading="lazy" decoding="async"><div class="fig-grid-label">(b) CIFAR-100</div></div>
    <div><img src="https://raw.githubusercontent.com/DLFundamentals/blog/main/assets/figures/cl-nscl/th1_exp2_imagenet.png" alt="mini-ImageNet gap vs C" width="400" height="300" loading="lazy" decoding="async"><div class="fig-grid-label">(c) mini-ImageNet</div></div>
  </div>
  <p class="figcaption"><strong>Fig. 3.</strong> The gap $\mathcal{L}^{\text{DCL}} - \mathcal{L}^{\text{NSCL}}$ as a function of $C$, compared with the theoretical bound. The gap shrinks with $C$ at all training epochs.</p>
</div>

<article>

  <h3>What NSCL minimizers look like</h3>

  <p>Since DCL sits close to NSCL at the level of the loss, it is natural to ask what the global minimizers of NSCL look like. The answer is remarkably structured:</p>

  <div class="steps">
    <div class="step">
      <div class="step-num" style="font-size:.6rem;">≡</div>
      <div class="step-body">
        <div class="step-title">Augmentation collapse.</div>
        <div class="step-desc">All augmented views of the same sample map to the same point in feature space.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num" style="font-size:.6rem;">⊕</div>
      <div class="step-body">
        <div class="step-title">Within-class collapse.</div>
        <div class="step-desc">All samples from the same class share a single representation.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num" style="font-size:.6rem;">△</div>
      <div class="step-body">
        <div class="step-title">Simplex ETF.</div>
        <div class="step-desc">Class centers form a maximally separated symmetric configuration on the unit sphere — an equiangular tight frame.</div>
      </div>
    </div>
  </div>

  <p>This places NSCL within the same broader geometric picture that appears in supervised learning. The supervised problem adjacent to DCL is not arbitrary; it has the same neural-collapse structure familiar from other well-studied supervised objectives.</p>

  <hr>

  <h2>Part II — The learned representations stay close</h2>

  <p>Loss-level closeness is informative, but it does not by itself imply similar learned geometry. Two nearby objectives can still drive optimization in meaningfully different directions. The second paper addresses this directly.</p>

  <h3>Shared-randomness coupling</h3>

  <p>Consider training DCL and NSCL under shared randomness: same initialization, same mini-batches, same augmentations, same hyperparameters. The only difference is the objective. The cosine similarity matrix $\Sigma(Z)_{ij} = \cos(z_i, z_j)$ provides the basis for CKA and RSA comparison.</p>

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

  <p>DCL and NSCL models trained under exactly matched conditions for 300 epochs yield consistently high alignment scores:</p>

</article>

<div class="fig-wide">
  <div class="align-grid fade-in">
    <div class="align-card">
      <div class="align-card-title">RSA — ResNet-50</div>
      <div class="align-row"><span class="align-row-label">CIFAR-10</span><div class="align-bar-track"><div class="align-bar-fill" style="width:84%;background:var(--teal);"></div></div><span class="align-val" style="color:var(--teal);">0.84</span></div>
      <div class="align-row"><span class="align-row-label">CIFAR-100</span><div class="align-bar-track"><div class="align-bar-fill" style="width:91%;background:var(--teal);"></div></div><span class="align-val" style="color:var(--teal);">0.91</span></div>
      <div class="align-row"><span class="align-row-label">mini-ImageNet</span><div class="align-bar-track"><div class="align-bar-fill" style="width:88%;background:var(--teal);"></div></div><span class="align-val" style="color:var(--teal);">0.88</span></div>
    </div>
    <div class="align-card">
      <div class="align-card-title">CKA — ResNet-50</div>
      <div class="align-row"><span class="align-row-label">CIFAR-10</span><div class="align-bar-track"><div class="align-bar-fill" style="width:81%;background:var(--accent-mid);"></div></div><span class="align-val" style="color:var(--accent-mid);">0.81</span></div>
      <div class="align-row"><span class="align-row-label">CIFAR-100</span><div class="align-bar-track"><div class="align-bar-fill" style="width:91%;background:var(--accent-mid);"></div></div><span class="align-val" style="color:var(--accent-mid);">0.91</span></div>
      <div class="align-row"><span class="align-row-label">mini-ImageNet</span><div class="align-bar-track"><div class="align-bar-fill" style="width:87%;background:var(--accent-mid);"></div></div><span class="align-val" style="color:var(--accent-mid);">0.87</span></div>
    </div>
    <div class="align-card">
      <div class="align-card-title">RSA — ViT-Base</div>
      <div class="align-row"><span class="align-row-label">CIFAR-10</span><div class="align-bar-track"><div class="align-bar-fill" style="width:83%;background:var(--teal);"></div></div><span class="align-val" style="color:var(--teal);">0.83</span></div>
      <div class="align-row"><span class="align-row-label">CIFAR-100</span><div class="align-bar-track"><div class="align-bar-fill" style="width:92%;background:var(--teal);"></div></div><span class="align-val" style="color:var(--teal);">0.92</span></div>
      <div class="align-row"><span class="align-row-label">mini-ImageNet</span><div class="align-bar-track"><div class="align-bar-fill" style="width:86%;background:var(--teal);"></div></div><span class="align-val" style="color:var(--teal);">0.86</span></div>
    </div>
    <div class="align-card">
      <div class="align-card-title">CKA — ViT-Base</div>
      <div class="align-row"><span class="align-row-label">CIFAR-10</span><div class="align-bar-track"><div class="align-bar-fill" style="width:82%;background:var(--accent-mid);"></div></div><span class="align-val" style="color:var(--accent-mid);">0.82</span></div>
      <div class="align-row"><span class="align-row-label">CIFAR-100</span><div class="align-bar-track"><div class="align-bar-fill" style="width:93%;background:var(--accent-mid);"></div></div><span class="align-val" style="color:var(--accent-mid);">0.93</span></div>
      <div class="align-row"><span class="align-row-label">mini-ImageNet</span><div class="align-bar-track"><div class="align-bar-fill" style="width:85%;background:var(--accent-mid);"></div></div><span class="align-val" style="color:var(--accent-mid);">0.85</span></div>
    </div>
  </div>
  <p class="figcaption" style="max-width:820px;margin:0 auto;padding:0 2.5rem;"><strong>Fig. 5.</strong> Representation similarity between DCL and NSCL models trained with matched initialization and mini-batch order. All values exceed 0.81. Alignment is strongest when the number of classes is largest (CIFAR-100, mini-ImageNet), matching the theory. Scores are nearly identical across ResNet-50 and ViT-Base.</p>
</div>

<article>

  <p>Two patterns are especially notable. First, alignment is strongest when the number of classes is largest — CIFAR-100 and mini-ImageNet reach 0.91+ — matching the theory that more classes imply a smaller loss gap. Second, scores are nearly identical across ResNet-50 and ViT-Base, indicating the DCL-NSCL relationship is not an artifact of a particular architecture.</p>

  <h3>But weights can still diverge</h3>

  <p>In contrast, parameter-space coupling is much less stable. The weight-space bound has no batch-size moderation in the exponent, so representation-level alignment can remain stable even when parameter-space divergence becomes large.</p>

  <div class="finding-teal">
    <div class="finding-label">Representation similarity</div>
    Stays high (&gt;0.81) because the bound scales as $1/(\tau C \sqrt{B})$ — batch size moderates the divergence. The geometry is what matters for downstream tasks.
  </div>

  <div class="finding-red">
    <div class="finding-label">Parameter divergence</div>
    Can grow large because the weight-space bound lacks batch-size moderation in its exponent. But this doesn't matter: deep networks have enough redundancy that different weights can encode the same geometry.
  </div>

  <hr>

  <h2>The right mental model</h2>

  <p>The standard description is that contrastive learning is a self-supervised method that nonetheless learns semantic structure. While true, it leaves open <em>why</em> this happens so consistently.</p>

  <p>The picture here is more specific. The self-supervised contrastive objective is already close to a supervised contrastive objective that excludes same-class negatives. That supervised objective has global minimizers with the same neural-collapse geometry familiar from supervised learning. And under shared training randomness, the two methods learn highly aligned representations throughout training.</p>

  <p>This does not mean that self-supervised and supervised learning are identical, nor that labels are irrelevant. But it does suggest that the gap between the two is <strong>narrower, and more structured</strong>, than the usual informal description implies.</p>

  <div class="takeaway">
    <h3>Takeaway</h3>
    <p>The main point is not merely that self-supervised and supervised contrastive learning are related. It is that the relation is surprisingly tight and structurally clean.</p>
    <p><strong>The objectives are close.</strong> The standard self-supervised contrastive loss approximates the NSCL loss, with a gap that shrinks as $O(1/C)$.</p>
    <p><strong>The nearby supervised problem has elegant geometry.</strong> NSCL minimizers exhibit augmentation collapse, within-class collapse, and simplex ETF structure.</p>
    <p><strong>The learned representations stay aligned.</strong> Under shared training randomness, DCL and NSCL produce highly similar representation geometry (CKA, RSA &gt; 0.81), even when their parameters diverge.</p>
    <p>A useful way to view contrastive learning, then, is not as a completely separate mechanism that somehow recovers semantics, but as a self-supervised procedure whose objective and learned geometry already lie close to a specific supervised counterpart.</p>
  </div>

</article>

<div class="post-footer">
  <p>Published on <a href="https://dlfundamentals.github.io/blog/">Theory/Simplified</a> &nbsp;&middot;&nbsp; Based on <a href="https://arxiv.org/abs/2506.04411">Luthra, Yang, Galanti — NeurIPS 2025</a> and <a href="https://arxiv.org/abs/2510.08852">Luthra, Mishra, Galanti — ICLR 2025</a></p>
</div>
</div>

<script>
(function(){
  var root=document.querySelector('.ps');

  var ki=setInterval(function(){if(typeof renderMathInElement!=='undefined'&&root){clearInterval(ki);renderMathInElement(root,{delimiters:[{left:'$$',right:'$$',display:true},{left:'$',right:'$',display:false}],throwOnError:false});}},100);

  function updateDenom(){
    var slider=document.getElementById('c-slider'); if(!slider) return;
    var C=parseInt(slider.value,10);
    document.getElementById('c-val').textContent=C;

    var n=3, N=C*n, gridSize=Math.min(N-1,40), cols=Math.ceil(Math.sqrt(gridSize));

    var dclGrid=document.getElementById('dcl-grid');
    dclGrid.innerHTML=''; dclGrid.style.gridTemplateColumns='repeat('+cols+',1fr)';
    for(var i=0;i<gridSize;i++){
      var cell=document.createElement('div'); cell.className='denom-cell';
      var isSame=i<(n-1);
      cell.style.background=isSame?'#c89898':'var(--teal-soft)';
      cell.style.opacity=isSame?'0.75':'1';
      dclGrid.appendChild(cell);
    }
    document.getElementById('dcl-count').textContent='All '+(N-1)+' other samples';

    var nscGrid=document.getElementById('nscl-grid');
    nscGrid.innerHTML=''; nscGrid.style.gridTemplateColumns='repeat('+cols+',1fr)';
    var nscCount=N-n;
    for(var j=0;j<Math.min(nscCount,gridSize);j++){
      var cell2=document.createElement('div'); cell2.className='denom-cell';
      cell2.style.background='var(--teal-soft)';
      nscGrid.appendChild(cell2);
    }
    document.getElementById('nscl-count').textContent=nscCount+' different-class only';

    var gaps=[2,5,10,20,50,100], barsHtml='';
    gaps.forEach(function(gc){
      var bound=Math.log(1+Math.exp(2)/(gc-1));
      var pct=Math.min(100,bound/2.5*100);
      var isActive=gc===C;
      barsHtml+='<div class="gap-bar-row">';
      barsHtml+='<span class="gap-bar-label" style="'+(isActive?'font-weight:500;color:var(--accent);':'')+'">C='+gc+'</span>';
      barsHtml+='<div class="gap-bar-track"><div class="gap-bar-fill" style="width:'+pct+'%;background:'+(isActive?'var(--accent)':'var(--muted-lt)')+';opacity:'+(isActive?1:0.35)+'"></div></div>';
      barsHtml+='<span class="gap-bar-val" style="'+(isActive?'font-weight:500;color:var(--accent);':'')+'">'+bound.toFixed(3)+'</span>';
      barsHtml+='</div>';
    });
    document.getElementById('gap-bars').innerHTML=barsHtml;

    var frac=((n-1)/(N-1)*100).toFixed(1);
    var gapVal=(Math.exp(2)/(C-1)).toFixed(3);
    document.getElementById('gap-insight').innerHTML=
      'With <strong>C = '+C+'</strong> classes, same-class samples are <strong>'+frac+'%</strong> of DCL\'s denominator. The gap bound is <strong>'+gapVal+'</strong> — '+(C>=20?'negligibly small.':C>=10?'already quite small.':'noticeable but shrinking fast.');
  }

  updateDenom();
  window.updateDenom=updateDenom;

  if('IntersectionObserver' in window){
    var obs=new IntersectionObserver(function(entries){entries.forEach(function(e){if(e.isIntersecting)e.target.classList.add('visible');});},{threshold:.1});
    root.querySelectorAll('.fade-in').forEach(function(el){obs.observe(el);});
  }
})();
</script>
