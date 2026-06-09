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
  <p class="hero-subtitle">Frozen self-supervised features can transfer from a handful of labels, even when their class clusters look wide, anisotropic, and nothing like classical neural collapse. The trick is beautifully geometric: decisions only care about variance along one line, and SSL quietly suppresses exactly that direction.</p>
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

  <p class="lead">A frozen self-supervised encoder is a strange little miracle. It was never told what a dog, chair, texture, or shape is. Yet after pretraining, attach a nearest-centroid classifier or a tiny linear probe on top, give it only a few labeled examples per class, and it often behaves as if the relevant categories were already drawn in the feature space.</p>

  <p>For supervised classifiers, we have a satisfying story: <em>neural collapse</em>. Late in training, examples from the same class concentrate near their class mean, different class means spread apart in a nearly symmetric pattern, and the last-layer classifier aligns with those means. This is exactly the geometry a nearest-class-center rule wants. But self-supervised learning (SSL) is not trained with those labels. It has no explicit reason to compress every semantic class into a tiny ball. Measured by the usual global clustering statistics, SSL features remain broad and highly anisotropic — and still transfer beautifully. So the classical ruler is reading the wrong thing.</p>

  <div class="callout">
    <strong>The resolution in one line</strong>
    For two classes, a nearest-centroid decision only depends on the projection onto the line joining their means. SSL need not collapse a whole class cloud; it only has to shrink the variance in this <em>decision direction</em>. The rest of the cloud can stay fluffy.
  </div>

  <p>The paper turns this observation into a compact theory built around one quantity: <strong>directional CDNV</strong>, the class-distance-normalized variance after projecting onto the decision axis. It explains two phenomena that otherwise look unrelated:</p>

  <div class="steps">
    <div class="step">
      <div class="step-num red">I</div>
      <div class="step-body">
        <div class="step-title">The anisotropy puzzle.</div>
        <div class="step-desc">Classical CDNV measures total within-class scatter, so it punishes harmless nuisance directions and badly underestimates SSL transfer geometry.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num teal">II</div>
      <div class="step-body">
        <div class="step-title">Only one direction matters.</div>
        <div class="step-desc">The NCC decision is a one-dimensional margin test after projection onto the line between class means. Directional CDNV measures exactly that margin noise.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num amber">III</div>
      <div class="step-body">
        <div class="step-title">A sharp few-shot bound.</div>
        <div class="step-desc">The few-shot NCC error is controlled by $4\tilde V$ plus explicit centroid-estimation and fourth-moment corrections; the leading constant cannot be improved distribution-free.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num purple">IV</div>
      <div class="step-body">
        <div class="step-title">Many tasks, forced orthogonal.</div>
        <div class="step-desc">Small directional CDNV across independent labelings forces their decision axes apart, giving a geometric reason multitask transfer can coexist inside one frozen encoder.</div>
      </div>
    </div>
  </div>

  <div class="paper-note">
    Based on: A. Luthra, Y. Salunkhe, T. Galanti. &ldquo;Directional Neural Collapse Explains Few-Shot Transfer in Self-Supervised Learning&rdquo;, ICML 2026.
  </div>

  <hr>

  <h2>Part I — The anisotropy puzzle</h2>

  <p>Start with the classical quantity used to certify few-shot transfer: <strong>class-distance-normalized variance</strong> (CDNV). For two classes, it compares how much the feature clouds spread inside each class to how far apart their means are:</p>

  <div class="math-display">
    <div class="math-label">Classical CDNV</div>
    $$V_{ij} = \frac{v_i + v_j}{\|\mu_i-\mu_j\|^2}, \qquad v_c = \mathbb{E}_{x\sim D_c}\,\|f(x)-\mu_c\|^2$$
  </div>

  <p>Small $V_{ij}$ says that the two clouds are tight compared with the gap $d_{ij}=\|\mu_i-\mu_j\|$. In supervised training, this is the familiar neural-collapse picture: $v_c$ shrinks, the class means remain separated, and a nearest-class-centroid (NCC) classifier becomes almost inevitable. A few labeled examples are enough because the representation has already done the hard geometric work.</p>

  <p>SSL breaks this story in the most interesting way. Without labels, there is no obvious force making every semantic class collapse into a small Euclidean ball. Instead, SSL representations are <strong>anisotropic</strong>: they often keep large variance in directions corresponding to style, pose, background, augmentation, or other nuisance factors. Classical CDNV adds all of those directions into $v_c$, so it can remain large even when the representation is perfectly organized for the downstream decision. The transfer succeeds; the scalar summary is too blunt.</p>

  <div class="pull-quote">&ldquo;A class cloud can be huge and still easy to classify — provided it is thin in the one direction where the boundary lives.&rdquo;</div>

  <hr>

  <h2>Part II — Only one direction matters</h2>

  <p>Fix two classes $i$ and $j$. The NCC rule compares the two squared distances, but after expanding the algebra almost everything cancels. A point from class $i$ is misclassified as $j$ exactly when its projection along the line from $\mu_i$ to $\mu_j$ crosses the midpoint. All orthogonal coordinates vanish from the decision.</p>

  <div class="math-display">
    <div class="math-label">NCC is a one-dimensional margin test</div>
    $$\|f(x)-\mu_j\|^2 \le \|f(x)-\mu_i\|^2
    \quad\Longleftrightarrow\quad
    u_{ij}^{\top}\!\big(f(x)-\mu_i\big) \ge \frac{\|\mu_i-\mu_j\|}{2}$$
  </div>

  <p>This identity tells us the right variance to measure. The decision axis is the unit vector pointing from one mean to the other, and directional CDNV is the variance of class $i$ after projecting onto that axis, normalized by the squared gap:</p>

  <div class="math-display">
    <div class="math-label">Decision axis &amp; directional CDNV</div>
    $$u_{ij} = \frac{\mu_j-\mu_i}{\|\mu_j-\mu_i\|}, \qquad \tilde V_{ij} = \frac{u_{ij}^\top \Sigma_i\, u_{ij}}{\|\mu_i-\mu_j\|^2}$$
  </div>

  <p>So $\tilde V_{ij}$ is not merely another clustering score; it is the second moment of the actual margin variable. Variance orthogonal to $u_{ij}$ can make the cluster visually enormous, but it cannot move the point through the NCC boundary. That is the geometry the figure below makes concrete — and the explorer after it lets you feel it.</p>

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
    <p class="diagram-caption">Fig. 1 — Anisotropic clusters. The clouds are tall, so classical CDNV sees a lot of variance. But the boundary is vertical and the decision axis is horizontal; only horizontal spread can cause mistakes. Directional CDNV reads that narrow projection and ignores the harmless height.</p>
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

  <p>The main theorem turns the one-dimensional margin picture into a finite-shot guarantee. Suppose each target class is represented by only $m$ labeled examples, so the class means used by NCC are empirical centroids rather than population means. Then the average few-shot NCC error over $C'$ classes splits into two pieces: the intrinsic decision-axis overlap, and the extra noise introduced by estimating the centroids from few samples.</p>

  <div class="math-display">
    <div class="math-label">Theorem 4.1 — finite-shot NCC bound</div>
    $$\mathrm{err}^{\mathrm{NCC}}_{m,\mathcal{C}}(f) \;\le\; \underbrace{\frac{1}{C'}\sum_{i}\sum_{j\ne i}\frac{4\,\tilde V_{ij}}{\big(1+\tfrac{v_j-v_i}{m\,d_{ij}^2}\big)^2}}_{\text{decision-axis term}} \;+\; \underbrace{\frac{1}{C'}\sum_{i}\sum_{j\ne i}\frac{\big(\sqrt{E^1_{ij}}+\sqrt{E^2_{ij}}+\sqrt{E^3_{ij}}\,\big)^2}{\big(1+\tfrac{v_j-v_i}{m\,d_{ij}^2}\big)^2}}_{\text{finite-shot remainder}}$$
  </div>

  <p>The theorem keeps the correction terms explicit, which is useful because each one corresponds to a real statistical cost. Let $\Theta_{ij}=\big(M_{4,i}+M_{4,j}\big)/d_{ij}^4$ be the normalized fourth moment, with $M_{4,i}=\mathbb{E}\|f(x)-\mu_i\|^4$. Then the finite-shot price decomposes as:</p>

  <div class="eq-highlight">
    $$E^{1}_{ij}=\frac{4}{m}\Big(V_{ij}^2+\tfrac14 V_{ij}\Big),\qquad E^{2}_{ij}=\frac{V_{ij}}{m},\qquad E^{3}_{ij}=\frac{\Theta_{ij}+2(m-1)V_{ij}^2}{m^3}$$
  </div>

  <p>Here is the intuition. $E^{2}_{ij}\asymp V_{ij}/m$ is the ordinary centroid-estimation cost: with few shots, the empirical class mean wiggles. $E^{1}_{ij}$ is a quadratic correction coming from the interaction between class spread and the random centroid. $E^{3}_{ij}$ is the higher-moment term that protects the theorem from heavy tails. The important asymmetry is that the <em>leading</em> term is directional CDNV $\tilde V_{ij}$, while the finite-shot corrections depend on the coarser global CDNV $V_{ij}$ but shrink with $m$. In the many-shot limit, all that remains is the sharp directional certificate.</p>

  <div class="finding-green">
    <div class="finding-label">The constant 4 is optimal</div>
    In the known-centroid limit, the pairwise NCC error is a one-sided tail event for the scalar random variable $u_{ij}^{\top}(f(x)-\mu_i)$. Its variance is $d_{ij}^2\tilde V_{ij}$ and the mistake threshold is $d_{ij}/2$. Cantelli's inequality gives $p^{\mathrm{NCC}}_{i\to j}\le \tfrac{4\tilde V_{ij}}{1+4\tilde V_{ij}}\le 4\tilde V_{ij}$, and a two-point construction shows that no distribution-free bound using only second moments can improve the leading factor. The $4$ is not proof slack; it is the geometry of one-sided deviation.
  </div>

  <p>The explorer below decomposes the bound. Its moral is simple: more shots help estimate centroids, but they do not repair a representation whose class clouds overlap along the decision axis. The asymptotic floor is $4\tilde V$; the rest is the price of learning the centers from a tiny support set.</p>

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

  <p>Directional CDNV also explains why one frozen SSL encoder can support many downstream labelings at once. Real images have several semantic factors — object identity, color, texture, pose, shape, size — and a good representation should let us read out many of them without rewriting the whole space. The clean model is a <strong>factor model</strong>: $M$ independent binary tasks, each carried by its own orthonormal direction $v_\ell$, with the embedding</p>

  <div class="math-display">
    <div class="math-label">Orthogonal factor model (§4.3)</div>
    $$z \;=\; \sum_{\ell=1}^{M}\frac{\Delta_\ell}{2}\,t^{(\ell)}\,v_\ell \;+\; \eta \;+\; \xi$$
  </div>

  <p>Each task label $t^{(\ell)}\in\{\pm1\}$ shifts $z$ by $\pm\tfrac{\Delta_\ell}{2}$ along its own axis. Thus the task-$\ell$ centroid gap is $\mu^{(\ell)}_+ - \mu^{(\ell)}_- = \Delta_\ell v_\ell$, so $v_\ell$ is literally the decision axis for that task. The term $\xi$ is small on-axis noise; $\eta$ is nuisance variation in the orthogonal complement. Plugging this into the definitions gives the whole phenomenon in one line: directional CDNV can be tiny while classical CDNV can be arbitrarily large,</p>

  <div class="eq-highlight">
    $$\tilde V^{(\ell)} = \frac{v_\ell^\top \mathrm{Cov}(\xi)\,v_\ell}{\Delta_\ell^2}\ \text{(small)}, \qquad V^{(\ell)} \ge \frac{2\,\mathrm{tr}\!\big(\mathrm{Cov}(\eta)\big)}{\Delta_\ell^2}\ \text{(arbitrarily large)}$$
  </div>

  <p>With three tasks, the picture is a box. The eight combinations of $(t^{(1)},t^{(2)},t^{(3)})$ become eight <strong>granular class centers</strong> at the corners of a hyperrectangle. Each edge direction is a task axis; each task cuts the box in half. The large nuisance variance $\eta$ lives outside this displayed subspace, which is exactly why a low-dimensional picture of SSL can look deceptively tidy while the full feature cloud remains broad. Drag to rotate:</p>

  <div class="explorer fade-in" id="cube-sim">
    <div class="explorer-header">
      <span class="explorer-title">Three tasks, one representation</span>
      <span class="explorer-subtitle">— drag to rotate · 3 orthogonal decision axes · 8 granular centers</span>
    </div>
    <div class="explorer-body">
      <div class="bd-controls">
        <div class="bd-ctrl"><label>on-axis noise <span>ξ</span> <b><span id="cube-xi-val">0.16</span></b></label><input type="range" id="cube-xi" min="0.03" max="0.5" step="0.01" value="0.16" oninput="cubeUpdate()"></div>
        <div class="bd-ctrl"><label>sample clouds <b><span id="cube-pts-lbl">shown</span></b></label><input type="range" id="cube-pts" min="0" max="1" step="1" value="1" oninput="cubeUpdate()"></div>
      </div>
      <div class="cl-svg" id="cube-svg" style="touch-action:none;cursor:grab;user-select:none;"></div>
      <div class="bd-result" id="cube-note"></div>
    </div>
  </div>

  <p class="figcaption"><strong>Fig. 4.</strong> The factor model with $M=3$. Eight granular centers (◆) sit at the corners of a hyperrectangle with unequal gaps $\Delta_1,\Delta_2,\Delta_3$. The three colored double-arrows are the decision axes: each task splits the box across one axis (blue = task A, green = task B, purple = task C). Sample clouds hug the corners along the axes; turning up $\xi$ loosens them and raises directional CDNV. Axes are orthogonal by construction — the geometry Proposition 4.2 forces from small directional CDNV alone.</p>

  <h3>The orthogonalization theorem, stated</h3>

  <p>The factor model is only a cartoon; the structural theorem does not assume such a clean generative story. Take two <em>independent</em> balanced labelings $y^{(1)}\in[K_1]$ and $y^{(2)}\in[K_2]$ of the same representation. Let $u^{(1)}_{aa'}$ be the decision axis between two classes of task 1, with gap $d^{(1)}_{aa'}$, and let $\tilde V^{(1)}_{aa'}$ be the worst directional CDNV along that axis; define the analogous quantities for task 2.</p>

  <div class="finding">
    <div class="finding-label">Proposition 4.2 — near-orthogonality from small directional CDNV</div>
    For any pair $a\ne a'$ in task 1 and $b\ne b'$ in task 2,
    <div class="math-display" style="background:transparent;border:none;margin:.7rem 0 .2rem;padding:.3rem 0;">
      $$\Big|\,(u^{(1)}_{aa'})^{\top} u^{(2)}_{bb'}\,\Big| \;\le\; \min\!\left\{\, \frac{d^{(1)}_{aa'}}{d^{(2)}_{bb'}}\sqrt{2K_2\,\tilde V^{(1)}_{aa'}}\;,\;\; \frac{d^{(2)}_{bb'}}{d^{(1)}_{aa'}}\sqrt{2K_1\,\tilde V^{(2)}_{bb'}} \,\right\}$$
    </div>
  </div>

  <p>Read the inequality as an interference budget. The left side is the cosine similarity between a decision axis for task 1 and a decision axis for task 2. The right side shrinks like $\sqrt{\tilde V}$: if either task has very small directional CDNV, the two decision-axis families are forced toward orthogonality. Intuitively, a single direction cannot simultaneously be a low-variance separator for two independent labelings; if it tried, one labeling would inject variance into the other. For balanced binary tasks with equal gaps, the clean form is $|\cos\theta|\le 2\sqrt{\tilde V}$ — the relation the slider below traces.</p>

  <div class="explorer fade-in" id="orth-sim">
    <div class="explorer-header">
      <span class="explorer-title">Two binary tasks — the bound in action</span>
      <span class="explorer-subtitle">— smaller directional CDNV forces the axes apart</span>
    </div>
    <div class="explorer-body">
      <div class="bd-controls">
        <div class="bd-ctrl"><label>directional CDNV per task <span>Ṽ</span> <b><span id="o-vt-val">0.03</span></b></label><input type="range" id="o-vt" min="0.005" max="0.3" step="0.005" value="0.03" oninput="orthRender()"></div>
      </div>
      <div class="cl-svg" id="o-svg"></div>
      <div class="bd-result" id="o-note"></div>
    </div>
  </div>

  <p class="figcaption"><strong>Fig. 5.</strong> The binary case of Proposition 4.2 with equal gaps: the guaranteed alignment ceiling is $|\cos\theta|\le 2\sqrt{\tilde V}$. As directional CDNV shrinks the worst-case angle is pushed toward $90^\circ$, so task B's separation barely projects onto task A's axis and adapting one leaves the other untouched.</p>

  <hr>

  <h2>Part V — What SSL actually does</h2>

  <p>The experiments are deliberately broad: contrastive learning (SimCLR), masked prediction (MAE), distillation-style pretraining (DINO-v2), redundancy reduction (VICReg), and multimodal pretraining (CLIP, SigLIP). These objectives are very different, but the same geometric signature appears:</p>

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

  <p>The important observation is not merely that $\tilde V$ is smaller than $V$. It is that training moves them differently. Variability <em>along</em> downstream decision axes falls steadily, while substantial orthogonal variance persists. SSL is not producing classical class collapse; it is producing a subtler, task-compatible collapse of margins. Different objectives arrive at the same geometry, suggesting that directional collapse is a broad consequence of learning invariances rather than an artifact of one loss.</p>

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
    <p class="diagram-caption">Fig. 6 — Schematic of the reported qualitative finding (not measured values). During SSL pretraining, directional CDNV collapses toward zero while classical CDNV stays high — the gap is the anisotropy that classical clustering measures misread.</p>
  </div>

  <p>The multitask prediction also survives the empirical check. On controlled synthetic data with independent visual factors — shape, size, color, pattern — SSL encoders map distinct factors to <strong>approximately orthogonal</strong> directions. The median absolute cosine similarity between decision axes from different labelings decays toward zero over training, staying within the qualitative envelope predicted by the theorem. In plain language: the representation learns a little coordinate system for independent factors.</p>

  <hr>

  <h2>What this does and does not say</h2>

  <p>The claim is geometric and specific. It does not say SSL induces full neural collapse; it says something more delicate and more useful. The total class cloud may remain large, but the projection that controls the decision becomes small. The theorem also does not promise a precise accuracy number for every encoder and every dataset. It identifies the right control variable, proves a sharp dependence in a distribution-free setting, and separates representation error from finite-shot centroid-estimation error.</p>

  <p>The scope matters. The analysis is centered on NCC and linear-probe-style downstream rules, so it is a theory of geometry seen by simple heads, not a universal theorem about every possible adaptation procedure. The finite-shot terms are honest about the fact that support-set centroids must be estimated. And the orthogonality theorem assumes independent balanced labelings, a clean abstraction of real visual factors. Still, the message survives these caveats: stop averaging over directions the decision ignores, and SSL transfer stops looking mysterious.</p>

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
    <p>Frozen self-supervised features transfer from a few labels because the variance that <strong>matters for decisions</strong> collapses, even when the full class cloud remains broad and anisotropic.</p>
    <p><strong>Directional CDNV is the right ruler.</strong> Project within-class variance onto the line between two class means. That projection is the NCC margin noise; everything orthogonal is mostly scenery.</p>
    <p><strong>The bound is sharp.</strong> In the known-centroid limit, few-shot NCC error is controlled by $4\tilde V$, and no distribution-free second-moment argument can improve that leading constant.</p>
    <p><strong>Orthogonality comes for free.</strong> When directional CDNV is small across independent tasks, the decision axes are forced apart, letting one frozen encoder serve many tasks at once. Across SimCLR, MAE, DINO-v2, VICReg, CLIP, and SigLIP, this directional collapse shows up while classical CDNV stays large — anisotropy is the rule, and it is exactly what makes SSL transfer.</p>
  </div>

</article>

<div class="post-footer">
  <p>Published on <a href="https://dlfundamentals.github.io/blog/">Theory/Simplified</a> &nbsp;&middot;&nbsp; Based on Luthra, Salunkhe &amp; Galanti — ICML 2026</p>
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

    var note='Guaranteed by Prop. 4.2: <b>|cos&#952;| &le; 2&#8730;Ṽ = '+cosmax.toFixed(2)+'</b> (angle &#8807; '+deg.toFixed(0)+'&#176;). ';
    if(vt<0.05) note+='With directional CDNV this small, the two tasks are forced almost <b>orthogonal</b> — adapting one leaves the other essentially untouched.';
    else note+='As directional CDNV grows, the bound relaxes and the geometry permits more alignment, so the tasks begin to <b>interfere</b>.';
    document.getElementById('o-note').innerHTML=note;
  };

  /* ── ROTATABLE 3D HYPERRECTANGLE (factor model, M=3) ── */
  (function(){
    var svgEl=document.getElementById('cube-svg');
    if(!svgEl) return;
    var W=440,H=300,cx=220,cy=150,scale=70;
    var ax=-0.45, ay=0.62;               // pitch, yaw
    var D=[1.7,1.2,0.85];                // half-gaps Δ/2 along the 3 axes (unequal => hyperrectangle)
    // 8 granular centers at (±D0,±D1,±D2)
    var corners=[];
    for(var sx=-1;sx<=1;sx+=2)for(var sy=-1;sy<=1;sy+=2)for(var sz=-1;sz<=1;sz+=2)
      corners.push([sx*D[0],sy*D[1],sz*D[2]]);
    // cube edges (pairs of corner indices differing in one coord)
    var edges=[];
    for(var i=0;i<8;i++)for(var j=i+1;j<8;j++){
      var diff=0; for(var k=0;k<3;k++) if(corners[i][k]!==corners[j][k]) diff++;
      if(diff===1) edges.push([i,j]);
    }
    // fixed sample offsets per corner (seeded, stable across rotations)
    var seed=12345; function rnd(){seed=(seed*1103515245+12345)&0x7fffffff;return seed/0x7fffffff-0.5;}
    var NS=7, offs=[];
    for(var c=0;c<8;c++){var arr=[];for(var s=0;s<NS;s++)arr.push([rnd(),rnd(),rnd()]);offs.push(arr);}

    function proj(p){
      var x=p[0],y=p[1],z=p[2];
      var x1=x*Math.cos(ay)+z*Math.sin(ay), z1=-x*Math.sin(ay)+z*Math.cos(ay), y1=y;
      var y2=y1*Math.cos(ax)-z1*Math.sin(ax), z2=y1*Math.sin(ax)+z1*Math.cos(ax);
      return {x:cx+x1*scale, y:cy-y2*scale, z:z2};
    }
    var taskCol=['#1e4f7a','#1a7a5c','#6e48aa'];

    window.cubeRender=function(){
      var xi=+document.getElementById('cube-xi').value;
      var showPts=+document.getElementById('cube-pts').value;
      document.getElementById('cube-xi-val').textContent=xi.toFixed(2);
      document.getElementById('cube-pts-lbl').textContent=showPts?'shown':'hidden';

      var parts=[]; // {z, svg}
      // edges
      for(var e=0;e<edges.length;e++){
        var a=proj(corners[edges[e][0]]), b=proj(corners[edges[e][1]]);
        parts.push({z:(a.z+b.z)/2-5, s:'<line x1="'+a.x.toFixed(1)+'" y1="'+a.y.toFixed(1)+'" x2="'+b.x.toFixed(1)+'" y2="'+b.y.toFixed(1)+'" stroke="#cfc8ba" stroke-width="1"/>'});
      }
      // 3 decision axes through origin, slightly beyond the box
      var axEnds=[[D[0]*1.5,0,0],[0,D[1]*1.8,0],[0,0,D[2]*1.9]];
      var lbls=[['A','+','−'],['B','+','−'],['C','+','−']];
      for(var t=0;t<3;t++){
        var p1=proj([-axEnds[t][0],-axEnds[t][1],-axEnds[t][2]]);
        var p2=proj([axEnds[t][0],axEnds[t][1],axEnds[t][2]]);
        var col=taskCol[t];
        parts.push({z:Math.max(p1.z,p2.z)+1, s:'<line x1="'+p1.x.toFixed(1)+'" y1="'+p1.y.toFixed(1)+'" x2="'+p2.x.toFixed(1)+'" y2="'+p2.y.toFixed(1)+'" stroke="'+col+'" stroke-width="2.2" stroke-linecap="round"/>'
          +'<circle cx="'+p2.x.toFixed(1)+'" cy="'+p2.y.toFixed(1)+'" r="3" fill="'+col+'"/>'
          +'<text x="'+(p2.x+5).toFixed(1)+'" y="'+(p2.y-3).toFixed(1)+'" font-family="IBM Plex Mono,monospace" font-size="10" font-weight="500" fill="'+col+'">task '+lbls[t][0]+'</text>'});
      }
      // sample clouds
      if(showPts){
        for(var c=0;c<8;c++){
          for(var s=0;s<NS;s++){
            var o=offs[c][s];
            var pt=proj([corners[c][0]+o[0]*xi, corners[c][1]+o[1]*xi, corners[c][2]+o[2]*xi]);
            var depth=(pt.z+2)/4; var op=(0.28+0.42*Math.max(0,Math.min(1,depth))).toFixed(2);
            parts.push({z:pt.z-2, s:'<circle cx="'+pt.x.toFixed(1)+'" cy="'+pt.y.toFixed(1)+'" r="1.7" fill="#7a7060" opacity="'+op+'"/>'});
          }
        }
      }
      // granular centers (corners) on top
      for(var c2=0;c2<8;c2++){
        var pc=proj(corners[c2]);
        var depth2=(pc.z+2)/4; var r=(3.0+1.6*Math.max(0,Math.min(1,depth2)));
        parts.push({z:pc.z+0.5, s:'<rect x="'+(pc.x-r).toFixed(1)+'" y="'+(pc.y-r).toFixed(1)+'" width="'+(2*r).toFixed(1)+'" height="'+(2*r).toFixed(1)+'" transform="rotate(45 '+pc.x.toFixed(1)+' '+pc.y.toFixed(1)+')" fill="#b8860b" stroke="#7a5a08" stroke-width="0.8"/>'});
      }
      parts.sort(function(p,q){return p.z-q.z;});
      var svg='<svg viewBox="0 0 '+W+' '+H+'" xmlns="http://www.w3.org/2000/svg" style="width:100%;max-width:440px">';
      for(var i=0;i<parts.length;i++) svg+=parts[i].s;
      svg+='</svg>';
      svgEl.innerHTML=svg;

      var Vt=(xi*xi)/(4*D[0]*D[0]); // illustrative directional CDNV along the widest axis (gap=2*D0)
      document.getElementById('cube-note').innerHTML='Eight granular centers (◆), three orthogonal decision axes. Directional CDNV here is tiny (≈ <b>'+Vt.toFixed(3)+'</b> on the longest axis) — set by how tightly samples hug the corners along the axes — while the model\u2019s <b>classical</b> CDNV is dominated by nuisance variance in directions outside this box. That gap is exactly what lets one representation carry all three tasks.';
    };
    window.cubeUpdate=window.cubeRender;

    // drag-to-rotate
    var dragging=false, lx=0, ly=0;
    function down(e){dragging=true;svgEl.style.cursor='grabbing';var p=e.touches?e.touches[0]:e;lx=p.clientX;ly=p.clientY;if(e.touches)e.preventDefault();}
    function move(e){if(!dragging)return;var p=e.touches?e.touches[0]:e;ay+=(p.clientX-lx)*0.01;ax+=(p.clientY-ly)*0.01;ax=Math.max(-1.4,Math.min(1.4,ax));lx=p.clientX;ly=p.clientY;window.cubeRender();if(e.touches)e.preventDefault();}
    function up(){dragging=false;svgEl.style.cursor='grab';}
    svgEl.addEventListener('mousedown',down); window.addEventListener('mousemove',move); window.addEventListener('mouseup',up);
    svgEl.addEventListener('touchstart',down,{passive:false}); svgEl.addEventListener('touchmove',move,{passive:false}); svgEl.addEventListener('touchend',up);
  })();

  /* ── INIT ── */
  clRender(); boundRender(); orthRender(); if(window.cubeRender) cubeRender();

  if('IntersectionObserver' in window){
    var obs=new IntersectionObserver(function(entries){entries.forEach(function(e){if(e.isIntersecting)e.target.classList.add('visible');});},{threshold:0.1});
    root.querySelectorAll('.fade-in').forEach(function(el){obs.observe(el);});
  }
})();
</script>
