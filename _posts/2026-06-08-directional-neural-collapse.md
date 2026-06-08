<link rel="preconnect" href="https://cdn.jsdelivr.net" crossorigin>
<link rel="preconnect" href="https://fonts.googleapis.com" crossorigin>
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.min.css">
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.min.js"></script>
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/contrib/auto-render.min.js"></script>
<link href="https://fonts.googleapis.com/css2?family=Lora:ital,wght@0,400;0,500;0,600;1,400;1,500&family=IBM+Plex+Mono:wght@400;500&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&display=swap" rel="stylesheet">

<style>
.ps{--bg:#f6f3ee;--bg-warm:#f0ece4;--surface:#ede9e0;--surface-2:#e8e3d8;--border:#d8d2c6;--border-lt:#e4dfd4;--text:#18160f;--text-soft:#3a3628;--muted:#7a7060;--muted-lt:#a09880;--accent:#1e4f7a;--accent-mid:#2a6199;--accent-soft:#d4e6f5;--accent-xs:#ebf4fc;--gold:#b8860b;--gold-soft:#fdf4d8;--gold-bd:#d4a820;--green:#2a6645;--green-soft:#e4f0ea;--red:#8f2a2a;--red-soft:#f5e8e8;--teal:#1a7a5c;--teal-soft:#e4f2ec;--amber:#a06810;--amber-soft:#faf0da;--purple:#6e48aa;--purple-soft:#f1ecfa;--serif:'Lora',Georgia,serif;--sans:'DM Sans',-apple-system,sans-serif;--mono:'IBM Plex Mono',monospace;}
.ps,.ps *,.ps *::before,.ps *::after{box-sizing:border-box;}
.ps{width:100%;max-width:100%;background:var(--bg);color:var(--text);font-family:var(--sans);font-weight:300;font-size:17px;line-height:1.78;-webkit-font-smoothing:antialiased;overflow-x:clip;}
.ps ::selection{background:var(--accent-soft);color:var(--text);}
.ps a{color:var(--accent-mid);text-decoration:none;}
.ps a:hover{text-decoration:underline;}
.ps img{max-width:100%;height:auto;display:block;}
.ps .top-bar{height:3px;background:linear-gradient(90deg,#1e4f7a 0%,#2a6199 55%,#b8860b 100%);}

/* ── HERO ── */
.ps .hero{max-width:820px;margin:0 auto;padding:3.5rem 2.5rem 2.5rem;border-bottom:1px solid var(--border);}
.ps .hero-eyebrow{font-family:var(--mono);font-size:10.5px;font-weight:500;letter-spacing:0.12em;text-transform:uppercase;color:var(--muted);margin-bottom:1.1rem;display:flex;align-items:center;gap:.5rem;}
.ps .hero-eyebrow::before{content:'';display:inline-block;width:18px;height:2px;background:var(--gold);flex-shrink:0;}
.ps .hero h1{font-family:var(--serif);font-size:clamp(1.9rem,4.5vw,2.9rem);font-weight:600;line-height:1.13;letter-spacing:-0.025em;color:var(--text);margin:0 0 1.3rem;max-width:680px;}
.ps .hero h1 em{font-style:italic;font-weight:400;color:var(--accent);}
.ps .hero-subtitle{font-size:1.08rem;color:var(--muted);font-style:italic;font-weight:300;max-width:600px;line-height:1.68;border-left:2px solid var(--border);padding-left:1.1rem;margin:0 0 1.6rem;}
.ps .hero-meta{font-family:var(--mono);font-size:11px;color:var(--muted-lt);display:flex;gap:1.25rem;flex-wrap:wrap;align-items:center;}
.ps .paper-badge{display:inline-flex;align-items:center;gap:5px;background:var(--accent-soft);color:var(--accent);border:1px solid #b5cfe6;padding:3px 10px;border-radius:20px;font-weight:500;font-size:10.5px;}

/* ── ARTICLE ── */
.ps article{max-width:820px;margin:0 auto;padding:2.5rem 2.5rem 6rem;}
.ps article p{margin:0 0 1.15rem;font-size:1.02rem;}
.ps article p.lead::first-letter{font-family:var(--serif);font-size:3.6em;font-weight:600;line-height:.75;float:left;margin:.06em .1em 0 0;color:var(--accent);}
.ps article h2{font-family:var(--serif);font-size:1.48rem;font-weight:500;line-height:1.22;letter-spacing:-0.01em;margin:2.75rem 0 1rem;padding-top:2rem;border-top:1px solid var(--border);color:var(--text);}
.ps article h2:first-child{border-top:none;padding-top:0;margin-top:0;}
.ps article h3{font-family:var(--mono);font-size:.73rem;font-weight:500;letter-spacing:.1em;text-transform:uppercase;color:var(--muted);margin:2rem 0 .65rem;}
.ps strong{font-weight:500;}
.ps code{font-family:var(--mono);font-size:.85em;background:var(--surface);border:1px solid var(--border-lt);padding:1px 6px;border-radius:3px;color:var(--text-soft);}

/* ── CALLOUTS ── */
.ps .callout{background:var(--gold-soft);border-left:3px solid var(--gold-bd);padding:1.05rem 1.3rem;border-radius:0 7px 7px 0;margin:1.75rem 0;font-size:.98rem;line-height:1.68;color:var(--text-soft);}
.ps .callout strong{display:block;margin-bottom:.3rem;font-weight:500;color:var(--text);}
.ps .callout p:last-child{margin:0;}
.ps .finding{background:var(--accent-xs);border:1px solid #c0d9ef;border-left:3px solid var(--accent-mid);border-radius:0 7px 7px 0;padding:1rem 1.3rem;margin:1.6rem 0;font-size:.95rem;color:var(--text-soft);}
.ps .finding-label{font-family:var(--mono);font-size:.68rem;font-weight:500;letter-spacing:.1em;text-transform:uppercase;color:var(--accent);margin-bottom:.4rem;}
.ps .finding-green{background:var(--teal-soft);border:1px solid #a8d8c8;border-left:3px solid var(--teal);border-radius:0 7px 7px 0;padding:1rem 1.3rem;margin:1.6rem 0;font-size:.95rem;color:var(--text-soft);}
.ps .finding-green .finding-label{color:var(--teal);}

/* ── MATH ── */
.ps .math-display{background:var(--surface);border:1px solid var(--border);border-radius:8px;padding:1.35rem 1.75rem;margin:1.6rem 0;text-align:center;overflow-x:auto;}
.ps .math-label{font-family:var(--mono);font-size:.68rem;font-weight:500;letter-spacing:.1em;text-transform:uppercase;color:var(--muted);margin-bottom:.65rem;}
.ps .eq-highlight{background:var(--gold-soft);border:1px solid var(--gold-bd);border-radius:8px;padding:1.15rem 1.75rem;margin:1.6rem 0;text-align:center;overflow-x:auto;}

/* ── STEPS ── */
.ps .steps{margin:1.5rem 0;}
.ps .step{display:flex;gap:1rem;margin-bottom:1.15rem;align-items:flex-start;}
.ps .step-num{background:var(--accent);color:white;width:26px;height:26px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-family:var(--mono);font-size:.7rem;font-weight:500;flex-shrink:0;margin-top:.12rem;box-shadow:0 1px 5px rgba(30,79,122,.22);}
.ps .step-num.gold{background:var(--gold);}
.ps .step-num.teal{background:var(--teal);}
.ps .step-num.amber{background:var(--amber);}
.ps .step-num.purple{background:var(--purple);}
.ps .step-num.red{background:var(--red);}
.ps .step-body{flex:1;}
.ps .step-title{font-weight:500;margin-bottom:.12rem;font-size:.97rem;}
.ps .step-desc{font-size:.9rem;color:var(--muted);line-height:1.62;font-weight:300;}

/* ── DIAGRAM WRAP ── */
.ps .diagram-wrap{background:var(--bg-warm);border:1px solid var(--border);border-radius:10px;padding:1.6rem 1.5rem 1.2rem;margin:2rem 0;overflow-x:auto;}
.ps .diagram-caption{font-family:var(--mono);font-size:10.5px;color:var(--muted-lt);margin-top:.85rem;text-align:center;line-height:1.55;letter-spacing:.01em;}

/* ── PAPER NOTE ── */
.ps .paper-note{font-family:var(--mono);font-size:.76rem;color:var(--accent);background:var(--accent-xs);border:1px solid #c0d9ef;padding:.8rem 1rem .8rem 2.1rem;border-radius:5px;margin:1.1rem 0 1.6rem;line-height:1.7;position:relative;}
.ps .paper-note::before{content:"◆";position:absolute;left:.8rem;top:.85rem;font-size:8px;}
.ps .paper-note a{color:var(--accent);font-weight:500;}

/* ── PULL QUOTE ── */
.ps .pull-quote{font-family:var(--serif);font-size:1.2rem;font-style:italic;color:var(--accent);border-top:2px solid var(--accent-soft);border-bottom:2px solid var(--accent-soft);padding:1.1rem 0;margin:2rem 0;line-height:1.55;text-align:center;}

/* ── STAT STRIP ── */
.ps .stat-strip{display:flex;gap:.75rem;flex-wrap:wrap;margin:1.7rem 0;}
.ps .stat{flex:1;min-width:150px;background:var(--bg-warm);border:1px solid var(--border);border-radius:9px;padding:.95rem 1.05rem;}
.ps .stat-num{font-family:var(--serif);font-size:1.5rem;font-weight:600;color:var(--accent);line-height:1.1;}
.ps .stat-num.teal{color:var(--teal);}
.ps .stat-num.gold{color:var(--amber);}
.ps .stat-lbl{font-family:var(--mono);font-size:10px;color:var(--muted);letter-spacing:.04em;text-transform:uppercase;margin-top:.45rem;line-height:1.45;}

/* ── EXPLORER / SIM ── */
.ps .explorer{background:var(--bg-warm);border:1px solid var(--border);border-radius:10px;overflow:hidden;margin:1.75rem 0;}
.ps .explorer-header{background:var(--surface);border-bottom:1px solid var(--border);padding:.8rem 1.25rem;display:flex;align-items:baseline;gap:.75rem;flex-wrap:wrap;}
.ps .explorer-title{font-family:var(--mono);font-size:.72rem;font-weight:500;letter-spacing:.08em;text-transform:uppercase;color:var(--text);}
.ps .explorer-subtitle{font-size:12px;color:var(--muted);font-weight:300;}
.ps .explorer-body{padding:1.1rem 1.25rem 1.25rem;}
.ps .bd-controls{display:flex;flex-wrap:wrap;gap:.9rem 1.3rem;margin-bottom:1.1rem;}
.ps .bd-ctrl{flex:1;min-width:135px;}
.ps .bd-ctrl label{font-family:var(--mono);font-size:10px;color:var(--muted);display:flex;justify-content:space-between;margin-bottom:5px;}
.ps .bd-ctrl label b{color:var(--accent);font-weight:500;}
.ps .bd-ctrl input[type=range]{width:100%;accent-color:var(--accent);cursor:pointer;}
.ps .cl-svg{display:flex;justify-content:center;margin:.3rem 0 1rem;}
.ps .bd-bars{margin:.4rem 0 1rem;}
.ps .bd-bar-row{display:flex;align-items:center;gap:8px;margin-bottom:8px;}
.ps .bd-bar-label{font-family:var(--mono);font-size:10px;width:150px;flex-shrink:0;text-align:right;color:var(--text-soft);}
.ps .bd-bar-track{flex:1;height:18px;background:var(--surface-2);border-radius:3px;overflow:hidden;}
.ps .bd-bar-fill{height:100%;border-radius:3px;transition:width .35s ease;min-width:2px;}
.ps .bd-bar-val{font-family:var(--mono);font-size:10px;font-weight:500;color:var(--muted-lt);min-width:84px;flex-shrink:0;}
.ps .bd-result{background:var(--bg);border:1px solid var(--border-lt);border-radius:7px;padding:.85rem 1rem;font-size:13px;color:var(--text-soft);line-height:1.7;}
.ps .bd-result b{color:var(--accent);font-weight:500;}
.ps .bd-result .bd-big{font-family:var(--serif);font-size:1.2rem;color:var(--teal);font-weight:600;}
.ps .cl-readout{display:flex;flex-wrap:wrap;gap:.6rem;margin-bottom:.9rem;}
.ps .cl-chip{flex:1;min-width:120px;background:var(--bg);border:1px solid var(--border-lt);border-radius:7px;padding:.6rem .8rem;text-align:center;}
.ps .cl-chip .v{font-family:var(--serif);font-size:1.2rem;font-weight:600;line-height:1;}
.ps .cl-chip .l{font-family:var(--mono);font-size:9px;color:var(--muted);text-transform:uppercase;letter-spacing:.03em;margin-top:.35rem;line-height:1.4;}

/* ── TAKEAWAY ── */
.ps .takeaway{background:var(--text);color:#e8e2d8;padding:1.85rem 2rem;border-radius:12px;margin:2.75rem 0 1.5rem;position:relative;overflow:hidden;}
.ps .takeaway::before{content:'';position:absolute;top:0;left:0;right:0;height:3px;background:linear-gradient(90deg,var(--accent-mid),var(--gold));}
.ps .takeaway h3{font-family:var(--mono);font-size:.68rem;font-weight:500;letter-spacing:.12em;text-transform:uppercase;color:var(--gold-bd);margin:0 0 1.1rem;border:none;padding:0;}
.ps .takeaway p{color:#c2bdb4;margin-bottom:1rem;font-size:1rem;}
.ps .takeaway p:last-child{margin-bottom:0;}
.ps .takeaway strong{color:#e8e2d8;}

/* ── FIGCAPTION ── */
.ps .figcaption{font-family:var(--mono);font-size:10.5px;color:var(--muted-lt);line-height:1.6;margin-top:.75rem;margin-bottom:2rem;letter-spacing:.01em;}

/* ── FOOTER ── */
.ps .post-footer{max-width:820px;margin:0 auto;padding:1.5rem 2.5rem 3rem;text-align:center;border-top:1px solid var(--border);}
.ps .post-footer p{font-family:var(--mono);font-size:11px;color:var(--muted-lt);margin:0;}
.ps .post-footer a{color:var(--accent-mid);}

.ps hr{border:none;border-top:1px solid var(--border);margin:0;}
.ps .fade-in{opacity:0;transform:translateY(16px);transition:opacity .65s ease,transform .65s ease;}
.ps .fade-in.visible{opacity:1;transform:translateY(0);}

@media(max-width:700px){
  .ps .hero,.ps article,.ps .post-footer{padding-left:1.25rem;padding-right:1.25rem;}
  .ps .hero h1{font-size:1.8rem;}
  .ps .bd-bar-label{width:120px;}
}
@media(max-width:600px){.ps table{font-size:11.5px;}}
</style>

<div class="ps">

<div class="top-bar"></div>

<div class="hero">
  <div class="hero-eyebrow">Self-Supervised Learning &middot; Neural Collapse &middot; Few-Shot Theory</div>
  <h1>Directional <em>Neural Collapse</em></h1>
  <p class="hero-subtitle">Frozen self-supervised features transfer with only a few labels, across many tasks at once — yet their clusters look messy and spread out. The resolution is that only one direction per pair of classes actually matters, and that's the direction self-supervised training quietly tightens.</p>
  <div class="hero-meta">
    <span>By Tomer Galanti</span>
    <span>&middot;</span>
    <span>March 3, 2026</span>
    <span>&middot;</span>
    <span>14 min read</span>
    <span>&middot;</span>
    <span class="paper-badge">&#9670; Luthra, Salunkhe, Galanti — ICML 2026</span>
  </div>
</div>

<article>

  <h2>Introduction</h2>

  <p class="lead">A frozen self-supervised encoder is a strange object. It was never shown a single label, yet attach a tiny classifier on top — a handful of examples per class — and it works, often across several unrelated tasks simultaneously. We have known this empirically for years. What we have lacked is a clean geometric reason.</p>

  <p>In supervised networks, the explanation is <em>neural collapse</em>: by the end of training, each class's features concentrate near a single mean, the means spread into a tidy simplex, and the classifier aligns with them. Small within-class scatter relative to between-class separation is exactly what makes a nearest-centroid rule succeed from few examples. The trouble is that self-supervised learning (SSL) has no labels, so nothing pushes the features to collapse globally. Measured the usual way, SSL clusters stay fat and anisotropic — and yet they transfer beautifully. The standard geometry says they shouldn't.</p>

  <div class="callout">
    <strong>The resolution in one line</strong>
    For a pair of classes, the only within-class variability that can change a decision is the part <em>along the line joining their means</em>. SSL suppresses exactly that — the <em>directional</em> variance — while leaving large, harmless variance in every other direction.
  </div>

  <p>The paper builds the whole story on one geometric quantity, <strong>directional CDNV</strong> (decision-axis variance), and shows it governs two good behaviors at once:</p>

  <div class="steps">
    <div class="step">
      <div class="step-num red">I</div>
      <div class="step-body">
        <div class="step-title">The anisotropy puzzle.</div>
        <div class="step-desc">Classical clustering measures average variance over <em>all</em> directions, so they look pessimistic for SSL — even when the features are well organized for decisions.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num teal">II</div>
      <div class="step-body">
        <div class="step-title">Only one direction matters.</div>
        <div class="step-desc">Directional CDNV keeps only the variance along the class-separating axis and ignores the rest. That is the right target for anisotropic representations.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num amber">III</div>
      <div class="step-body">
        <div class="step-title">A sharp few-shot bound.</div>
        <div class="step-desc">Few-shot error is bounded by $4\times$ directional CDNV plus finite-shot corrections — and the constant $4$ is provably optimal.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num purple">IV</div>
      <div class="step-body">
        <div class="step-title">Many tasks, forced orthogonal.</div>
        <div class="step-desc">If directional CDNV is small for several independent labelings, their decision axes must be nearly orthogonal — so one representation serves many tasks with little interference.</div>
      </div>
    </div>
  </div>

  <div class="paper-note">
    Based on: A. Luthra, Y. Salunkhe, T. Galanti. &ldquo;Directional Neural Collapse Explains Few-Shot Transfer in Self-Supervised Learning&rdquo;, ICML, 2026.
  </div>

  <hr>

  <h2>Part I — The anisotropy puzzle</h2>

  <p>Start with the standard predictor of few-shot transfer, the <strong>class-distance-normalized variance</strong> (CDNV). For two classes it is the total within-class scatter divided by the squared gap between their means:</p>

  <div class="math-display">
    <div class="math-label">Classical CDNV</div>
    $$V_{ij} = \frac{v_i + v_j}{\|\mu_i-\mu_j\|^2}, \qquad v_c = \mathbb{E}_{x\sim D_c}\,\|f(x)-\mu_c\|^2$$
  </div>

  <p>Small CDNV means tight clusters far apart — ideal for nearest-class-centroid (NCC) and linear probes. In supervised training, neural collapse drives $v_c \to 0$ while the gaps stay large, so CDNV shrinks and the few-shot bound tightens. Clean.</p>

  <p>SSL breaks the assumption. With no labels, there is no pressure to shrink <em>total</em> within-class variance. Instead, SSL features are strongly <strong>anisotropic</strong>: lots of variance survives in nuisance directions — think augmentation-induced wobble, lighting, pose — that have nothing to do with telling classes apart. Because $v_c$ sums variance over <em>all</em> directions, classical CDNV stays large and predicts poor transfer. But the features transfer fine. The measure, not the representation, is the problem.</p>

  <div class="pull-quote">&ldquo;Only the variance along the line between two class means can flip the decision. Everything orthogonal to it is free.&rdquo;</div>

  <hr>

  <h2>Part II — Only one direction matters</h2>

  <p>Fix two classes $i$ and $j$. The nearest-centroid rule compares distances to the two means, which is decided entirely by where a point falls along the <strong>decision axis</strong> — the unit vector pointing from one mean to the other:</p>

  <div class="math-display">
    <div class="math-label">Decision axis &amp; directional CDNV</div>
    $$u_{ij} = \frac{\mu_j-\mu_i}{\|\mu_j-\mu_i\|}, \qquad \tilde V_{ij} = \frac{u_{ij}^\top \Sigma_i\, u_{ij}}{\|\mu_i-\mu_j\|^2}$$
  </div>

  <p>Directional CDNV $\tilde V_{ij}$ keeps only the class-$i$ variance <em>projected onto</em> $u_{ij}$, normalized by the gap. Variance orthogonal to $u_{ij}$ can stretch the cluster as far as it likes; it never moves a point across the midpoint, so it never changes an NCC decision. That is the geometry the figure below makes concrete — and the explorer after it lets you feel it.</p>

  <div class="diagram-wrap fade-in">
    <svg viewBox="0 0 640 250" xmlns="http://www.w3.org/2000/svg" style="width:100%;max-width:640px;display:block;margin:auto">
      <defs>
        <marker id="dax" markerWidth="7" markerHeight="7" refX="6" refY="3.5" orient="auto"><path d="M0,0 L7,3.5 L0,7 Z" fill="#1e4f7a"/></marker>
      </defs>
      <!-- two anisotropic clusters elongated vertically (nuisance), tight horizontally (decision axis) -->
      <ellipse cx="190" cy="125" rx="34" ry="92" fill="#d4e6f5" stroke="#2a6199" stroke-width="1.2" opacity="0.85"/>
      <ellipse cx="450" cy="125" rx="34" ry="92" fill="#e4f2ec" stroke="#1a7a5c" stroke-width="1.2" opacity="0.85"/>
      <circle cx="190" cy="125" r="4" fill="#1e4f7a"/>
      <circle cx="450" cy="125" r="4" fill="#1a7a5c"/>
      <text x="190" y="234" font-family="IBM Plex Mono,monospace" font-size="11" fill="#1e4f7a" text-anchor="middle">class i</text>
      <text x="450" y="234" font-family="IBM Plex Mono,monospace" font-size="11" fill="#1a7a5c" text-anchor="middle">class j</text>
      <!-- decision axis -->
      <line x1="194" y1="125" x2="446" y2="125" stroke="#1e4f7a" stroke-width="1.6" stroke-dasharray="2 3" marker-end="url(#dax)"/>
      <text x="320" y="116" font-family="IBM Plex Mono,monospace" font-size="11" fill="#1e4f7a" text-anchor="middle">decision axis u</text>
      <text x="320" y="146" font-family="DM Sans,sans-serif" font-size="10.5" fill="#7a7060" text-anchor="middle">small variance here ⇒ small directional CDNV</text>
      <!-- nuisance direction arrow -->
      <line x1="552" y1="55" x2="552" y2="195" stroke="#a09880" stroke-width="1.4"/>
      <path d="M552,50 l-4,8 l8,0 Z" fill="#a09880"/><path d="M552,200 l-4,-8 l8,0 Z" fill="#a09880"/>
      <text x="566" y="128" font-family="IBM Plex Mono,monospace" font-size="10" fill="#7a7060" transform="rotate(90 566 128)" text-anchor="middle">nuisance direction</text>
      <!-- midpoint boundary -->
      <line x1="320" y1="38" x2="320" y2="212" stroke="#8f2a2a" stroke-width="1" stroke-dasharray="4 4"/>
      <text x="320" y="32" font-family="IBM Plex Mono,monospace" font-size="9.5" fill="#8f2a2a" text-anchor="middle">NCC boundary</text>
    </svg>
    <p class="diagram-caption">Fig. 1 — Anisotropic clusters. Both classes carry large within-class variance, but it lives mostly in the nuisance (vertical) direction. Classical CDNV averages over all directions and looks large; directional CDNV reads only the tight spread along $u$ and is small. Only the latter governs the decision.</p>
  </div>

  <div class="explorer fade-in" id="cluster-sim">
    <div class="explorer-header">
      <span class="explorer-title">Decision-axis explorer</span>
      <span class="explorer-subtitle">— tune the two kinds of variance and watch which one moves the error</span>
    </div>
    <div class="explorer-body">
      <div class="bd-controls">
        <div class="bd-ctrl"><label>gap between means <span>d</span> <b><span id="cl-d-val">3.0</span></b></label><input type="range" id="cl-d" min="1.5" max="5" step="0.1" value="3.0" oninput="clRender()"></div>
        <div class="bd-ctrl"><label>variance ALONG axis <span>σ∥</span> <b><span id="cl-sp-val">0.50</span></b></label><input type="range" id="cl-sp" min="0.2" max="1.6" step="0.05" value="0.5" oninput="clRender()"></div>
        <div class="bd-ctrl"><label>nuisance variance <span>σ⊥</span> <b><span id="cl-so-val">2.0</span></b></label><input type="range" id="cl-so" min="0.2" max="3" step="0.1" value="2.0" oninput="clRender()"></div>
      </div>
      <div class="cl-svg" id="cl-svg"></div>
      <div class="cl-readout">
        <div class="cl-chip"><div class="v" style="color:var(--red)" id="cl-classical">–</div><div class="l">classical CDNV<br>(all directions)</div></div>
        <div class="cl-chip"><div class="v" style="color:var(--teal)" id="cl-directional">–</div><div class="l">directional CDNV<br>(along axis)</div></div>
        <div class="cl-chip"><div class="v" style="color:var(--accent)" id="cl-err">–</div><div class="l">true NCC error<br>(known centroids)</div></div>
        <div class="cl-chip"><div class="v" style="color:var(--amber)" id="cl-bound">–</div><div class="l">bound 4·directional<br>CDNV</div></div>
      </div>
      <div class="bd-result" id="cl-note"></div>
    </div>
  </div>

  <p class="figcaption"><strong>Fig. 2.</strong> Drag <em>nuisance variance</em> up: the clusters balloon vertically, classical CDNV climbs, but the true error and directional CDNV do not budge. Drag <em>variance along axis</em> up: the clusters overlap at the boundary and the error rises in lockstep with directional CDNV. The error is a Gaussian tail along the axis; the $4\tilde V$ value is the distribution-free Cantelli bound.</p>

  <hr>

  <h2>Part III — A sharp few-shot bound</h2>

  <p>The main theorem turns this picture into a guarantee. With $m$ shots per class and $C'$ classes, the average NCC error (which also upper-bounds the linear probe) is governed by directional CDNV, plus corrections that vanish as you get more shots:</p>

  <div class="eq-highlight">
    $$\mathrm{err}^{\mathrm{NCC}}_{m,\mathcal{C}}(f) \;\le\; \frac{1}{C'}\sum_{i}\sum_{j\ne i}\frac{4\,\tilde V_{ij}}{\big(1+\tfrac{v_j-v_i}{m\,d_{ij}^2}\big)^2}\;+\;\big(\text{finite-shot corrections}\big)$$
  </div>

  <p>Two things make this tighter and more honest than prior bounds. First, the leading term is <strong>directional</strong> CDNV, not the coarse classical one — so it stays informative in exactly the anisotropic regime where SSL lives. Second, the analysis cleanly separates the genuine decision-axis difficulty from the cost of <em>estimating centroids from few samples</em>. There are three finite-shot pieces: a linear centroid-estimation term ($\sim V_{ij}/m$), a quadratic one ($\sim V_{ij}^2/m$), and a fourth-moment tail term ($\sim \Theta_{ij}/m^3$). All decay with $m$, leaving the directional certificate behind.</p>

  <div class="finding-green">
    <div class="finding-label">The constant 4 is optimal</div>
    In the known-centroid limit, a pairwise NCC error is a one-sided tail event along the axis with variance $d_{ij}^2\,\tilde V_{ij}$. Cantelli's inequality gives $p^{\mathrm{NCC}}_{i\to j}\le \tfrac{4\tilde V_{ij}}{1+4\tilde V_{ij}}\le 4\tilde V_{ij}$, and a two-point construction shows no distribution-free second-moment bound can beat the factor $4$. The leading coefficient is not slack in the proof — it is the best possible without extra tail assumptions.
  </div>

  <p>The explorer below decomposes the bound. Notice the shape of it: the centroid and tail terms shrink as shots grow, but the floor is set by $4\tilde V$ — the irreducible decision-axis difficulty. More shots help you <em>find</em> the centroids; they cannot fix a representation whose classes genuinely overlap along the axis.</p>

  <div class="explorer fade-in" id="bound-sim">
    <div class="explorer-header">
      <span class="explorer-title">Few-shot bound decomposition</span>
      <span class="explorer-subtitle">— the leading term is a floor; the corrections melt with shots</span>
    </div>
    <div class="explorer-body">
      <div class="bd-controls">
        <div class="bd-ctrl"><label>directional CDNV <span>Ṽ</span> <b><span id="b-vt-val">0.05</span></b></label><input type="range" id="b-vt" min="0.01" max="0.25" step="0.005" value="0.05" oninput="boundRender()"></div>
        <div class="bd-ctrl"><label>classical CDNV <span>V</span> <b><span id="b-v-val">1.00</span></b></label><input type="range" id="b-v" min="0.1" max="2" step="0.05" value="1.0" oninput="boundRender()"></div>
        <div class="bd-ctrl"><label>shots per class <span>m</span> <b><span id="b-m-val">20</span></b></label><input type="range" id="b-m" min="1" max="200" step="1" value="20" oninput="boundRender()"></div>
      </div>
      <div class="bd-bars">
        <div class="bd-bar-row"><div class="bd-bar-label">4·Ṽ — decision axis</div><div class="bd-bar-track"><div class="bd-bar-fill" id="b-bar-lead" style="background:var(--teal)"></div></div><div class="bd-bar-val" id="b-val-lead"></div></div>
        <div class="bd-bar-row"><div class="bd-bar-label">centroid estimation</div><div class="bd-bar-track"><div class="bd-bar-fill" id="b-bar-cent" style="background:var(--amber)"></div></div><div class="bd-bar-val" id="b-val-cent"></div></div>
        <div class="bd-bar-row"><div class="bd-bar-label">tail / higher order</div><div class="bd-bar-track"><div class="bd-bar-fill" id="b-bar-tail" style="background:var(--red)"></div></div><div class="bd-bar-val" id="b-val-tail"></div></div>
      </div>
      <div class="bd-result" id="b-note"></div>
    </div>
  </div>

  <p class="figcaption"><strong>Fig. 3.</strong> Illustrative decomposition: leading term $4\tilde V$, a centroid-estimation term shown as $\propto \sqrt{V}/\sqrt{m}$, and a tail term shown as $\propto V/m$ (constants are schematic for intuition; the paper's exact corrections are the $V/m$, $V^2/m$ and $\Theta/m^3$ terms). Raise the shots $m$ and the corrections collapse toward the directional-CDNV floor.</p>

  <hr>

  <h2>Part IV — Many tasks at once, forced orthogonal</h2>

  <p>Here is where directional CDNV pays a second dividend. A single SSL representation is asked to support many labelings at once — color, shape, size, texture. Each labeling has its own decision axis. The paper proves a structural consequence: if directional CDNV is simultaneously small for two independent balanced labelings, their decision axes must be <strong>nearly orthogonal</strong>.</p>

  <p>The intuition is a budget argument. Small directional CDNV along axis $A$ means each class is tightly concentrated in that direction. If axis $B$ were aligned with $A$, then $B$'s classes would also have to be separated along nearly the same direction — but the two labelings are independent, so that would force the same coordinate to carry two unrelated bits of information without overlap. The only way to keep both directional variances small is to route the second task into a direction the first one isn't using. Orthogonality is what lets one representation hold many tasks without interference.</p>

  <div class="explorer fade-in" id="orth-sim">
    <div class="explorer-header">
      <span class="explorer-title">Multitask orthogonality</span>
      <span class="explorer-subtitle">— smaller directional CDNV forces decision axes apart</span>
    </div>
    <div class="explorer-body">
      <div class="bd-controls">
        <div class="bd-ctrl"><label>directional CDNV per task <span>Ṽ</span> <b><span id="o-vt-val">0.03</span></b></label><input type="range" id="o-vt" min="0.005" max="0.3" step="0.005" value="0.03" oninput="orthRender()"></div>
      </div>
      <div class="cl-svg" id="o-svg"></div>
      <div class="bd-result" id="o-note"></div>
    </div>
  </div>

  <p class="figcaption"><strong>Fig. 4.</strong> Two tasks' decision axes (blue, green) with their class blobs. As directional CDNV shrinks, the geometry is squeezed toward right angles — low alignment means task $B$'s separation barely projects onto task $A$'s axis, so adapting one task leaves the other untouched. The angle shown is an illustrative worst case consistent with the orthogonality result.</p>

  <hr>

  <h2>Part V — What SSL actually does</h2>

  <p>The experiments check the whole chain across a broad span of self-supervised paradigms — contrastive (SimCLR), masked prediction (MAE), distillation (DINO-v2), redundancy reduction (VICReg), and multimodal pretraining (CLIP, SigLIP). The findings line up with the theory:</p>

  <div class="stat-strip fade-in">
    <div class="stat">
      <div class="stat-num teal">Ṽ &darr;</div>
      <div class="stat-lbl">directional CDNV collapses during pretraining — across every objective</div>
    </div>
    <div class="stat">
      <div class="stat-num gold">V &rarr;</div>
      <div class="stat-lbl">classical CDNV stays large: the anisotropy is real and pervasive</div>
    </div>
    <div class="stat">
      <div class="stat-num">tracks</div>
      <div class="stat-lbl">the directional bound follows few-shot error at practical shot sizes</div>
    </div>
  </div>

  <p>The defining signature is the gap between the two curves: variability <em>along</em> the decision axis falls steadily with training, while substantial variance persists in the orthogonal, task-irrelevant subspace. Suppressing variance along discriminative directions appears to be an implicit, method-agnostic outcome of self-supervision — even though no objective asks for it and total within-class variance stays high.</p>

  <div class="diagram-wrap fade-in">
    <svg viewBox="0 0 620 230" xmlns="http://www.w3.org/2000/svg" style="width:100%;max-width:620px;display:block;margin:auto">
      <!-- axes -->
      <line x1="60" y1="30" x2="60" y2="185" stroke="#a09880" stroke-width="1"/>
      <line x1="60" y1="185" x2="560" y2="185" stroke="#a09880" stroke-width="1"/>
      <text x="44" y="30" font-family="IBM Plex Mono,monospace" font-size="9" fill="#7a7060" text-anchor="end">high</text>
      <text x="44" y="185" font-family="IBM Plex Mono,monospace" font-size="9" fill="#7a7060" text-anchor="end">0</text>
      <text x="310" y="212" font-family="IBM Plex Mono,monospace" font-size="10" fill="#7a7060" text-anchor="middle">pretraining progress →</text>
      <text x="22" y="110" font-family="IBM Plex Mono,monospace" font-size="9.5" fill="#7a7060" text-anchor="middle" transform="rotate(-90 22 110)">variance / CDNV</text>
      <!-- classical stays high -->
      <path d="M60,70 C180,62 340,66 560,60" fill="none" stroke="#a06810" stroke-width="2.4"/>
      <text x="500" y="50" font-family="IBM Plex Mono,monospace" font-size="10" fill="#a06810" text-anchor="middle">classical CDNV (V)</text>
      <!-- directional collapses -->
      <path d="M60,78 C160,150 320,172 560,178" fill="none" stroke="#1a7a5c" stroke-width="2.4"/>
      <text x="470" y="170" font-family="IBM Plex Mono,monospace" font-size="10" fill="#1a7a5c" text-anchor="middle">directional CDNV (Ṽ)</text>
    </svg>
    <p class="diagram-caption">Fig. 5 — Schematic of the reported qualitative finding (not measured values). During SSL pretraining, directional CDNV collapses toward zero while classical CDNV stays high — the gap is the anisotropy that classical clustering measures misread.</p>
  </div>

  <p>The multitask prediction holds up too. On controlled synthetic data with independent visual factors — shape, size, color, pattern — SSL encoders map distinct factors to <strong>approximately orthogonal</strong> directions: the median absolute cosine similarity between decision axes from different labelings decays toward zero over training, staying below the curve the theory predicts.</p>

  <hr>

  <h2>What this does and does not say</h2>

  <p>The claim is geometric and specific. It does not say SSL induces full neural collapse — it explicitly does not, and the persistence of large orthogonal variance is the whole point. It does not certify a particular accuracy number for a particular encoder; it identifies the one quantity that <em>controls</em> few-shot error and proves the dependence is sharp. The bound is distribution-free at second order, which is why the constant $4$ is unimprovable without assuming light tails — and the fourth-moment term is there precisely to handle the heavy ones.</p>

  <p>It also rests on the NCC / linear-probe family of downstream rules and on having enough shots to estimate centroids; the finite-shot terms are honest about that cost. And the multitask orthogonality result is proved for independent balanced binary labelings, a clean idealization of the messier real-world case. What survives all of this is a reframing: stop averaging variance over directions that decisions ignore, and a frozen SSL encoder stops looking mysterious.</p>

  <div class="steps">
    <div class="step">
      <div class="step-num teal">✓</div>
      <div class="step-body">
        <div class="step-title">Measure variance where decisions happen.</div>
        <div class="step-desc">Directional CDNV reads only the spread along the class-separating axis — the only variance that can change an NCC or linear-probe label.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num purple">✓</div>
      <div class="step-body">
        <div class="step-title">One representation, many tasks.</div>
        <div class="step-desc">Small directional CDNV across independent labelings forces near-orthogonal decision axes, the geometric basis for low-interference multitask transfer.</div>
      </div>
    </div>
  </div>

  <div class="takeaway">
    <h3>Takeaway</h3>
    <p>Frozen self-supervised features transfer from a few labels because the variance that <strong>matters for decisions</strong> collapses, even though total within-class variance does not.</p>
    <p><strong>Directional CDNV is the right ruler.</strong> Project within-class variance onto the line between two class means; ignore everything orthogonal. That single number governs few-shot error.</p>
    <p><strong>The bound is sharp.</strong> Few-shot NCC error is at most $4\,\tilde V$ plus finite-shot corrections that vanish with more shots, and the constant $4$ is provably optimal under second-moment information.</p>
    <p><strong>Orthogonality comes for free.</strong> When directional CDNV is small across independent tasks, the decision axes are forced apart, letting one frozen encoder serve many tasks at once. Across SimCLR, MAE, DINO-v2, VICReg, CLIP, and SigLIP, this directional collapse shows up while classical CDNV stays large — anisotropy is the rule, and it is exactly what makes SSL transfer.</p>
  </div>

</article>

<div class="post-footer">
  <p>Published on <a href="https://dlfundamentals.github.io/blog/">Theory/Simplified</a> &nbsp;&middot;&nbsp; Based on Luthra, Salunkhe &amp; Galanti — arXiv:2603.03530, 2026</p>
</div>

</div>

<script>
(function(){
  var root = document.querySelector('.ps');

  var katexCheck = setInterval(function(){
    if(typeof renderMathInElement !== 'undefined' && root){
      clearInterval(katexCheck);
      renderMathInElement(root,{delimiters:[{left:'$$',right:'$$',display:true},{left:'$',right:'$',display:false}],throwOnError:false});
    }
  },100);

  /* ── math helpers ── */
  function erf(x){var s=x<0?-1:1;x=Math.abs(x);var t=1/(1+0.3275911*x);var y=1-(((((1.061405429*t-1.453152027)*t)+1.421413741)*t-0.284496736)*t+0.254829592)*t*Math.exp(-x*x);return s*y;}
  function Phi(x){return 0.5*(1+erf(x/Math.SQRT2));}
  function Qf(x){return 1-Phi(x);}
  function fmt(v,n){return v.toFixed(n===undefined?3:n);}

  /* ── CLUSTER EXPLORER ── */
  window.clRender = function(){
    var d=+document.getElementById('cl-d').value;
    var sp=+document.getElementById('cl-sp').value;
    var so=+document.getElementById('cl-so').value;
    document.getElementById('cl-d-val').textContent=d.toFixed(1);
    document.getElementById('cl-sp-val').textContent=sp.toFixed(2);
    document.getElementById('cl-so-val').textContent=so.toFixed(1);

    var v=sp*sp+so*so;
    var classical=2*v/(d*d);
    var directional=sp*sp/(d*d);
    var err=100*Qf(d/(2*sp));
    var bound=100*Math.min(1,4*directional);

    document.getElementById('cl-classical').textContent=fmt(classical,2);
    document.getElementById('cl-directional').textContent=fmt(directional,3);
    document.getElementById('cl-err').textContent=err.toFixed(1)+'%';
    document.getElementById('cl-bound').textContent=bound.toFixed(1)+'%';

    var W=460,H=240,cx=230,cy=120,sc=30;
    var xi=cx-(d/2)*sc, xj=cx+(d/2)*sc;
    var rx=1.3*sp*sc, ry=Math.min(112,1.3*so*sc);
    var svg='<svg viewBox="0 0 '+W+' '+H+'" xmlns="http://www.w3.org/2000/svg" style="width:100%;max-width:460px">';
    svg+='<line x1="'+cx+'" y1="14" x2="'+cx+'" y2="'+(H-26)+'" stroke="#8f2a2a" stroke-width="1" stroke-dasharray="4 4"/>';
    svg+='<text x="'+cx+'" y="12" font-family="IBM Plex Mono,monospace" font-size="9" fill="#8f2a2a" text-anchor="middle">boundary</text>';
    svg+='<ellipse cx="'+xi+'" cy="'+cy+'" rx="'+rx+'" ry="'+ry+'" fill="#d4e6f5" stroke="#2a6199" stroke-width="1.2" opacity="0.8"/>';
    svg+='<ellipse cx="'+xj+'" cy="'+cy+'" rx="'+rx+'" ry="'+ry+'" fill="#e4f2ec" stroke="#1a7a5c" stroke-width="1.2" opacity="0.8"/>';
    svg+='<line x1="'+xi+'" y1="'+cy+'" x2="'+xj+'" y2="'+cy+'" stroke="#1e4f7a" stroke-width="1.4" stroke-dasharray="2 3"/>';
    svg+='<circle cx="'+xi+'" cy="'+cy+'" r="3.5" fill="#1e4f7a"/><circle cx="'+xj+'" cy="'+cy+'" r="3.5" fill="#1a7a5c"/>';
    svg+='<text x="'+xi+'" y="'+(H-8)+'" font-family="IBM Plex Mono,monospace" font-size="10" fill="#1e4f7a" text-anchor="middle">class i</text>';
    svg+='<text x="'+xj+'" y="'+(H-8)+'" font-family="IBM Plex Mono,monospace" font-size="10" fill="#1a7a5c" text-anchor="middle">class j</text>';
    svg+='<text x="'+cx+'" y="'+(cy-8)+'" font-family="IBM Plex Mono,monospace" font-size="9.5" fill="#1e4f7a" text-anchor="middle">u</text>';
    svg+='</svg>';
    document.getElementById('cl-svg').innerHTML=svg;

    var note;
    if(so>2*sp+0.6){
      note='Nuisance variance is large but the clusters stay <b>tight along the axis</b>: classical CDNV is inflated ('+fmt(classical,2)+') while the true error stays low ('+err.toFixed(1)+'%) and tracks <b>4·directional CDNV</b>. This is the SSL regime.';
    } else if(sp>0.9){
      note='Variance along the axis is large, so the clusters overlap at the boundary — error climbs to <b>'+err.toFixed(1)+'%</b>, in step with directional CDNV. This is genuine difficulty that more shots cannot remove.';
    } else {
      note='Tight along the axis, well separated: low error (<b>'+err.toFixed(1)+'%</b>) and the directional bound is informative. Try cranking the nuisance variance — the error will not move.';
    }
    document.getElementById('cl-note').innerHTML=note;
  };

  /* ── BOUND DECOMPOSITION ── */
  window.boundRender = function(){
    var vt=+document.getElementById('b-vt').value;
    var v=Math.max(vt,+document.getElementById('b-v').value);
    var m=+document.getElementById('b-m').value;
    document.getElementById('b-vt-val').textContent=vt.toFixed(3);
    document.getElementById('b-v-val').textContent=v.toFixed(2);
    document.getElementById('b-m-val').textContent=m;

    var lead=4*vt;
    var cent=2*Math.sqrt(v)/Math.sqrt(m);
    var tail=v/m;
    var total=Math.min(1,lead+cent+tail);

    function pct(x){return (Math.min(1,x)*100).toFixed(1)+'%';}
    document.getElementById('b-bar-lead').style.width=pct(lead);
    document.getElementById('b-bar-cent').style.width=pct(cent);
    document.getElementById('b-bar-tail').style.width=pct(tail);
    document.getElementById('b-val-lead').textContent=fmt(lead,3);
    document.getElementById('b-val-cent').textContent=fmt(cent,3);
    document.getElementById('b-val-tail').textContent=fmt(tail,3);

    var note;
    if(cent+tail>lead){
      note='At <b>m='+m+'</b> shots the corrections dominate — most of the bound is the cost of <b>estimating centroids</b>, not the representation. Raise the shots and watch them melt.';
    } else {
      note='The corrections have shrunk below the leading term: the bound is now close to its floor of <b>4·Ṽ = '+fmt(lead,3)+'</b>. More shots barely help; this floor is set purely by decision-axis variance.';
    }
    note+=' &nbsp;→ total error bound <span class="bd-big">'+(total*100).toFixed(1)+'%</span>';
    document.getElementById('b-note').innerHTML=note;
  };

  /* ── MULTITASK ORTHOGONALITY ── */
  window.orthRender = function(){
    var vt=+document.getElementById('o-vt').value;
    document.getElementById('o-vt-val').textContent=vt.toFixed(3);
    // illustrative: smaller directional CDNV -> smaller allowed alignment -> angle near 90deg
    var cosmax=Math.min(0.92, 2.0*Math.sqrt(vt));
    var theta=Math.acos(cosmax); // radians from axis A
    var deg=theta*180/Math.PI;

    var W=380,H=200,cx=150,cy=110,L=80;
    // axis A horizontal
    var ax2=cx+L, ax1=cx-L;
    // axis B at angle theta above horizontal
    var bx=cx+L*Math.cos(theta), by=cy-L*Math.sin(theta);
    var bx1=cx-L*Math.cos(theta), by1=cy+L*Math.sin(theta);
    var svg='<svg viewBox="0 0 '+W+' '+H+'" xmlns="http://www.w3.org/2000/svg" style="width:100%;max-width:380px">';
    // arc
    svg+='<path d="M'+(cx+34)+','+cy+' A 34 34 0 0 0 '+(cx+34*Math.cos(theta))+','+(cy-34*Math.sin(theta))+'" fill="none" stroke="#a09880" stroke-width="1"/>';
    svg+='<text x="'+(cx+50)+'" y="'+(cy-14)+'" font-family="IBM Plex Mono,monospace" font-size="10" fill="#7a7060">'+deg.toFixed(0)+'&#176;</text>';
    // axis A (blue)
    svg+='<line x1="'+ax1+'" y1="'+cy+'" x2="'+ax2+'" y2="'+cy+'" stroke="#1e4f7a" stroke-width="2.2"/>';
    svg+='<circle cx="'+ax1+'" cy="'+cy+'" r="6" fill="#1e4f7a"/><circle cx="'+ax2+'" cy="'+cy+'" r="6" fill="#7fb0db"/>';
    svg+='<text x="'+(ax2+4)+'" y="'+(cy+4)+'" font-family="IBM Plex Mono,monospace" font-size="9.5" fill="#1e4f7a">task A</text>';
    // axis B (green)
    svg+='<line x1="'+bx1+'" y1="'+by1+'" x2="'+bx+'" y2="'+by+'" stroke="#1a7a5c" stroke-width="2.2"/>';
    svg+='<circle cx="'+bx1+'" cy="'+by1+'" r="6" fill="#1a7a5c"/><circle cx="'+bx+'" cy="'+by+'" r="6" fill="#6cc4a4"/>';
    svg+='<text x="'+(bx+4)+'" y="'+(by-4)+'" font-family="IBM Plex Mono,monospace" font-size="9.5" fill="#1a7a5c">task B</text>';
    svg+='</svg>';
    document.getElementById('o-svg').innerHTML=svg;

    var note='Allowed alignment between axes: <b>|cos&#952;| &le; '+cosmax.toFixed(2)+'</b> (angle &#8776; '+deg.toFixed(0)+'&#176;). ';
    if(vt<0.05) note+='With directional CDNV this small, the two tasks are forced almost <b>orthogonal</b> — adapting one leaves the other essentially untouched.';
    else note+='As directional CDNV grows, the geometry permits more alignment, so the tasks begin to <b>interfere</b>.';
    document.getElementById('o-note').innerHTML=note;
  };

  /* ── INIT ── */
  clRender(); boundRender(); orthRender();

  if('IntersectionObserver' in window){
    var obs=new IntersectionObserver(function(entries){entries.forEach(function(e){if(e.isIntersecting)e.target.classList.add('visible');});},{threshold:0.1});
    root.querySelectorAll('.fade-in').forEach(function(el){obs.observe(el);});
  }
})();
</script>
