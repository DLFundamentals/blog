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

/* ── TABLE ── */
.ps .table-wrap{margin:1.4rem 0;overflow-x:auto;border-radius:8px;border:1px solid var(--border);}
.ps table{width:100%;border-collapse:collapse;font-family:var(--sans);font-size:13px;background:var(--bg-warm);}
.ps table th{text-align:left;font-weight:500;padding:9px 12px;border-bottom:2px solid var(--border);color:var(--muted);font-family:var(--mono);font-size:10px;letter-spacing:.06em;text-transform:uppercase;white-space:nowrap;background:var(--surface);}
.ps table td{padding:7px 12px;border-bottom:1px solid var(--border-lt);vertical-align:middle;white-space:nowrap;}
.ps table tr:last-child td{border-bottom:none;}
.ps table td:first-child{font-weight:400;color:var(--text);}
.ps .td-best{font-weight:500;color:var(--teal);}
.ps .td-chance{color:var(--muted-lt);}
.ps .td-llmpv{background:rgba(212,230,245,.25);}
.ps table th.col-llmpv{background:rgba(212,230,245,.4);color:var(--accent);}

/* ── TENSION TABLE ── */
.ps .tension-table{width:100%;border-collapse:collapse;font-family:var(--sans);font-size:13px;margin:1.4rem 0;background:var(--bg-warm);border:1px solid var(--border);border-radius:8px;overflow:hidden;}
.ps .tension-table th{padding:9px 14px;border-bottom:2px solid var(--border);font-weight:500;font-family:var(--mono);font-size:10px;letter-spacing:.06em;text-transform:uppercase;color:var(--muted);text-align:left;background:var(--surface);}
.ps .tension-table td{padding:10px 14px;border-bottom:1px solid var(--border-lt);vertical-align:middle;}
.ps .tension-table tr:last-child td{border-bottom:none;}
.ps .tension-table td:first-child{font-weight:500;color:var(--text);}
.ps .td-red{color:var(--red);}
.ps .td-green{color:var(--teal);}

/* ── BAR CHART ── */
.ps .bar-chart{margin:1.4rem 0;background:var(--bg-warm);border:1px solid var(--border);border-radius:10px;padding:1.1rem 1.25rem;}
.ps .bar-chart-title{font-family:var(--mono);font-size:10px;font-weight:500;color:var(--muted-lt);letter-spacing:.06em;text-transform:uppercase;margin-bottom:12px;}
.ps .filter-tabs{display:flex;gap:5px;margin-bottom:12px;flex-wrap:wrap;}
.ps .filter-tab{font-family:var(--mono);font-size:10.5px;padding:3px 11px;border-radius:3px;border:1px solid var(--border);background:transparent;color:var(--muted);cursor:pointer;letter-spacing:.03em;transition:all .15s;}
.ps .filter-tab:hover{background:var(--surface);}
.ps .filter-tab.active{background:var(--teal-soft);color:var(--teal);border-color:var(--teal);font-weight:500;}
.ps .bar-row{display:flex;align-items:center;margin-bottom:5px;gap:8px;}
.ps .bar-label{font-family:var(--mono);font-size:10.5px;color:var(--text-soft);width:110px;flex-shrink:0;text-align:right;}
.ps .bar-track{flex:1;height:18px;background:var(--surface-2);border-radius:3px;overflow:hidden;position:relative;}
.ps .bar-fill{height:100%;border-radius:3px;transition:width .6s ease;display:flex;align-items:center;justify-content:flex-end;padding-right:6px;}
.ps .bar-value{font-family:var(--mono);font-size:9.5px;font-weight:500;color:white;}
.ps .bar-value-out{font-family:var(--mono);font-size:9.5px;font-weight:500;color:var(--muted-lt);margin-left:5px;flex-shrink:0;}

/* ── PIPELINE ── */
.ps .explorer{background:var(--bg-warm);border:1px solid var(--border);border-radius:10px;overflow:hidden;margin:1.75rem 0;}
.ps .explorer-header{background:var(--surface);border-bottom:1px solid var(--border);padding:.8rem 1.25rem;display:flex;align-items:baseline;gap:.75rem;}
.ps .explorer-title{font-family:var(--mono);font-size:.72rem;font-weight:500;letter-spacing:.08em;text-transform:uppercase;color:var(--text);}
.ps .explorer-subtitle{font-size:12px;color:var(--muted);font-weight:300;}
.ps .explorer-body{padding:1.1rem 1.25rem 1.25rem;}

.ps .pipeline-steps{display:flex;gap:0;align-items:stretch;}
.ps .pipe-step{flex:1;border-radius:7px;padding:.9rem .8rem;text-align:center;cursor:pointer;transition:transform .15s,box-shadow .15s;position:relative;}
.ps .pipe-step:hover{transform:translateY(-2px);box-shadow:0 3px 10px rgba(0,0,0,.06);}
.ps .pipe-step.active{box-shadow:0 4px 14px rgba(0,0,0,.1);transform:translateY(-3px);}
.ps .pipe-step-num{font-family:var(--mono);font-size:9.5px;font-weight:500;letter-spacing:.08em;text-transform:uppercase;margin-bottom:5px;}
.ps .pipe-step-title{font-family:var(--sans);font-size:13px;font-weight:500;margin-bottom:3px;}
.ps .pipe-step-desc{font-family:var(--sans);font-size:11px;line-height:1.5;color:var(--text-soft);}
.ps .pipe-arrow{display:flex;align-items:center;font-size:18px;color:var(--muted-lt);padding:0 3px;flex-shrink:0;}
.ps .pipe-detail{margin-top:1rem;padding:.9rem 1rem;background:var(--bg);border:1px solid var(--border-lt);border-radius:7px;font-family:var(--sans);font-size:13px;color:var(--text-soft);line-height:1.65;min-height:60px;}

/* ── TRACE SIMULATOR ── */
.ps .trace-cand{background:var(--bg);border:.5px solid var(--border);border-radius:7px;padding:11px 13px;transition:all .3s;}
.ps .trace-cand.best{border-color:var(--accent-mid);border-width:1.5px;}
.ps .trace-cand.eliminated{opacity:.3;}
.ps .trace-cand-header{display:flex;justify-content:space-between;align-items:center;margin-bottom:6px;gap:10px;flex-wrap:wrap;}
.ps .trace-cand-label{font-family:var(--mono);font-size:10.5px;color:var(--muted);}
.ps .trace-badge{font-family:var(--mono);font-size:10px;padding:2px 8px;border-radius:3px;font-weight:500;}
.ps .trace-badge-pass{background:var(--teal-soft);color:var(--teal);}
.ps .trace-badge-fail{background:var(--red-soft);color:var(--red);}
.ps .trace-badge-partial{background:var(--amber-soft);color:var(--amber);}
.ps .trace-badge-best{background:var(--accent-soft);color:var(--accent);}
.ps .trace-code{font-family:var(--mono);font-size:11.5px;line-height:1.6;color:var(--text);white-space:pre-wrap;word-break:break-word;}
.ps .trace-footer{display:flex;justify-content:space-between;align-items:center;margin-top:8px;padding-top:8px;border-top:.5px solid var(--border-lt);gap:10px;}
.ps .trace-score{font-family:var(--mono);font-size:10.5px;color:var(--muted-lt);}
.ps .trace-bar-track{flex:1;height:3px;background:var(--border-lt);border-radius:2px;margin:0 10px;max-width:200px;}
.ps .trace-bar-fill{height:100%;border-radius:2px;transition:width .5s ease;}

/* ── PLAY BUTTONS ── */
.ps .play-btn{font-family:var(--mono);font-size:10.5px;font-weight:500;padding:5px 14px;border-radius:4px;border:1px solid var(--border);background:var(--bg);color:var(--muted);cursor:pointer;letter-spacing:.03em;transition:all .15s;}
.ps .play-btn:hover{background:var(--surface);color:var(--text-soft);}
.ps .play-btn.active{background:var(--accent);color:white;border-color:var(--accent);box-shadow:0 1px 6px rgba(30,79,122,.3);}

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
  .ps .pipeline-steps{flex-direction:column;}
  .ps .pipe-arrow{transform:rotate(90deg);align-self:center;}
  .ps .hero,.ps article,.ps .post-footer{padding-left:1.25rem;padding-right:1.25rem;}
  .ps .hero h1{font-size:1.8rem;}
}
@media(max-width:600px){.ps table{font-size:11.5px;}}
</style>

<div class="ps">

<div class="top-bar"></div>

<div class="hero">
  <div class="hero-eyebrow">Learning Theory &middot; Program Synthesis &middot; LLMs</div>
  <h1>Revisiting <em>ERM</em> in the LLM Era</h1>
  <p class="hero-subtitle">How pretrained LLMs can serve as search priors for empirical risk minimization over programs, recovering exact algorithmic rules from just a handful of examples — while SGD-trained models remain at chance.</p>
  <div class="hero-meta">
    <span>By Tomer Galanti</span>
    <span>&middot;</span>
    <span>March 20, 2026</span>
    <span>&middot;</span>
    <span>14 min read</span>
    <span>&middot;</span>
    <span class="paper-badge">&#9670; Singhal, Mishra, Malach, Galanti — arXiv 2025</span>
  </div>
</div>

<article>

  <h2>Introduction</h2>

  <p class="lead">Deep learning works extraordinarily well in vision, language, and audio. But outside these regimes there are many simple tasks that standard training methods still do not handle well: primality testing, parity, Boolean circuits, graph connectivity, and other rule-based problems. One can cast them as supervised learning tasks and train a large model on labeled examples. In practice, the model often fits the training data and still fails to recover the underlying rule.</p>

  <p>A natural alternative is to use the fact that many such tasks admit short exact implementations — often just a few lines of Python. Instead of training a model to imitate the input-output map, we can search directly for a <strong>program</strong> that explains the data. This is empirical risk minimization (ERM) over a discrete class of programs, and classical learning theory tells us that such an approach can generalize from surprisingly little data.</p>

  <p>The difficulty is computational. Exhaustive search over all Python programs is clearly infeasible. The number of candidates grows exponentially with program length, so even when the correct hypothesis is very short, brute-force ERM is usually not practical.</p>

  <div class="callout">
    <strong>The central claim</strong>
    Pretrained LLMs can serve as search priors for empirical risk minimization over short programs — making classical program-based ERM practically searchable while preserving its strong sample-efficiency advantages.
  </div>

  <p>The story has four parts:</p>

  <div class="steps">
    <div class="step">
      <div class="step-num" style="background:var(--red);">I</div>
      <div class="step-body">
        <div class="step-title">SGD is the wrong search.</div>
        <div class="step-desc">SGD-trained networks fit the training data and still fail to recover algorithmic rules. The failure is fundamental on SQ-hard tasks, not a tuning issue.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num" style="background:var(--teal);">II</div>
      <div class="step-body">
        <div class="step-title">Program ERM is sample-efficient.</div>
        <div class="step-desc">PAC-style guarantees scale with description length $L$, not input dimension $n$. A compact parity program generalizes from $O(k \log n)$ examples.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num" style="background:var(--amber);">III</div>
      <div class="step-body">
        <div class="step-title">LLM-PV makes ERM feasible.</div>
        <div class="step-desc">A pretrained LLM replaces uniform search with a structured proposal distribution. Verification still comes from held-out data — the ERM principle is preserved.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num" style="background:var(--accent);">IV</div>
      <div class="step-body">
        <div class="step-title">Exact rules from few examples.</div>
        <div class="step-desc">LLM-PV recovers perfect accuracy on 10 of 13 algorithmic tasks from only 200 examples, while all neural baselines remain near chance.</div>
      </div>
    </div>
  </div>

  <div class="paper-note">
    Based on: S. Singhal, P. Mishra, E. Malach, T. Galanti. <a href="#">&ldquo;LLM Priors for ERM over Programs&rdquo;</a>, arXiv, 2025.
  </div>

  <hr>

  <h2>Part I — Deep learning can be the wrong search procedure</h2>

  <h3>Where our usual intuition breaks down</h3>

  <p>Most of our intuitions about sample efficiency come from settings where deep learning is well matched to the structure of the problem. Algorithmic tasks are fundamentally different — here the target hypothesis is compact as code, but opaque to gradient descent.</p>

  <!-- Algorithmic tasks diagram -->
  <div class="diagram-wrap fade-in">
    <svg viewBox="0 0 620 148" xmlns="http://www.w3.org/2000/svg" style="width:100%;max-width:620px;display:block;margin:auto">
      <defs>
        <marker id="da" markerWidth="6" markerHeight="6" refX="5" refY="3" orient="auto"><path d="M0,0 L6,3 L0,6 Z" fill="#a09880"/></marker>
      </defs>
      <!-- Four task boxes -->
      <rect x="8"   y="14" width="132" height="54" rx="5" fill="#f5e8e8" stroke="#c89898" stroke-width="1"/>
      <text x="74"  y="34" font-family="IBM Plex Mono,monospace" font-size="9.5" fill="#8f2a2a" text-anchor="middle" font-weight="500">Parity</text>
      <text x="74"  y="50" font-family="DM Sans,sans-serif" font-size="9" fill="#a06060" text-anchor="middle">XOR of k chosen bits</text>
      <text x="74"  y="63" font-family="IBM Plex Mono,monospace" font-size="8.5" fill="#c89898" text-anchor="middle">sum(x) % 2  — 1 line</text>

      <rect x="160" y="14" width="132" height="54" rx="5" fill="#f5e8e8" stroke="#c89898" stroke-width="1"/>
      <text x="226" y="34" font-family="IBM Plex Mono,monospace" font-size="9.5" fill="#8f2a2a" text-anchor="middle" font-weight="500">Primality</text>
      <text x="226" y="50" font-family="DM Sans,sans-serif" font-size="9" fill="#a06060" text-anchor="middle">Is integer prime?</text>
      <text x="226" y="63" font-family="IBM Plex Mono,monospace" font-size="8.5" fill="#c89898" text-anchor="middle">trial_div(x)  — 3 lines</text>

      <rect x="312" y="14" width="132" height="54" rx="5" fill="#f5e8e8" stroke="#c89898" stroke-width="1"/>
      <text x="378" y="34" font-family="IBM Plex Mono,monospace" font-size="9.5" fill="#8f2a2a" text-anchor="middle" font-weight="500">Dyck-2</text>
      <text x="378" y="50" font-family="DM Sans,sans-serif" font-size="9" fill="#a06060" text-anchor="middle">Balanced brackets?</text>
      <text x="378" y="63" font-family="IBM Plex Mono,monospace" font-size="8.5" fill="#c89898" text-anchor="middle">stack_check(x) — 5 lines</text>

      <rect x="464" y="14" width="148" height="54" rx="5" fill="#f5e8e8" stroke="#c89898" stroke-width="1"/>
      <text x="538" y="34" font-family="IBM Plex Mono,monospace" font-size="9.5" fill="#8f2a2a" text-anchor="middle" font-weight="500">Pattern match</text>
      <text x="538" y="50" font-family="DM Sans,sans-serif" font-size="9" fill="#a06060" text-anchor="middle">Motif in string?</text>
      <text x="538" y="63" font-family="IBM Plex Mono,monospace" font-size="8.5" fill="#c89898" text-anchor="middle">any(match)  — 1 line</text>

      <!-- Arrows down to SGD failure -->
      <line x1="74"  y1="68" x2="74"  y2="100" stroke="#d8d2c6" stroke-width="1" marker-end="url(#da)"/>
      <line x1="226" y1="68" x2="226" y2="100" stroke="#d8d2c6" stroke-width="1" marker-end="url(#da)"/>
      <line x1="378" y1="68" x2="378" y2="100" stroke="#d8d2c6" stroke-width="1" marker-end="url(#da)"/>
      <line x1="538" y1="68" x2="538" y2="100" stroke="#d8d2c6" stroke-width="1" marker-end="url(#da)"/>

      <!-- SGD outcome -->
      <rect x="8" y="104" width="604" height="30" rx="5" fill="#ede9e0" stroke="#d8d2c6" stroke-width="1"/>
      <text x="310" y="116" font-family="DM Sans,sans-serif" font-size="10" fill="#7a7060" text-anchor="middle">SGD: fits training data perfectly →</text>
      <text x="310" y="128" font-family="IBM Plex Mono,monospace" font-size="10" fill="#8f2a2a" text-anchor="middle">test accuracy ≈ 50%  (near chance)</text>
    </svg>
    <p class="diagram-caption">Fig. 1 — Tasks with short program descriptions are compact as code but gradient-opaque. Across 1B-scale models, test accuracy remains near chance even after perfect training-set fit.</p>
  </div>

  <h3>The failure mode</h3>

  <p>Across several 1B-scale language models, training on a few hundred labeled examples yields near-perfect <em>training</em> accuracy on tasks such as parity, Dyck-2, and cellular automata parity. Test accuracy, however, often remains near chance — and this persists even when the amount of training data is substantially increased.</p>

  <h3>Why SGD struggles</h3>

  <p>The statistical query perspective gives a clean explanation. For planted $k$-parity over $n$ variables, mini-batch coordinate SGD requires at least:</p>

  <div class="eq-highlight">
    $$q = \Omega\!\left(\frac{\sqrt{\binom{n}{k}}}{2^b}\right)$$
  </div>

  <p>fresh examples to achieve nontrivial population error. The target rule is simple as a program, but <strong>SGD is the wrong search procedure for this hypothesis class</strong>. The difficulty is statistical and fundamental, not a matter of model capacity or hyperparameter tuning.</p>

  <hr>

  <h2>Part II — ERM over short programs is statistically attractive</h2>

  <h3>Think of the target as code</h3>

  <p>Suppose the target rule can be expressed as a program of length $L$ over an alphabet $\Sigma$. The relevant hypothesis class is the set of valid programs of length at most $L$, with $|\mathcal{H}_L| \le |\Sigma|^L$. This immediately yields a classical PAC-style guarantee:</p>

  <div class="eq-highlight">
    $$\text{test error} \;\le\; \frac{L \log|\Sigma| + \log(2L^2/\delta)}{m}$$
  </div>

  <p>The sample complexity depends on <strong>description length</strong>, not on raw input dimension. A compact parity program can therefore generalize from surprisingly few examples — the number of samples needed grows with $k \log n$, not with $n^{k/2}$.</p>

  <h3>The central tension</h3>

  <div class="table-wrap fade-in">
    <table class="tension-table">
      <thead>
        <tr><th></th><th>SGD</th><th>Length-first ERM</th></tr>
      </thead>
      <tbody>
        <tr>
          <td>Samples for low error</td>
          <td class="td-red">$\Omega(n^{k/2})$ — exponential</td>
          <td class="td-green">$O(k \log n)$ — compact</td>
        </tr>
        <tr>
          <td>Per-sample compute</td>
          <td class="td-green">$O(1)$ — cheap</td>
          <td class="td-red">$\Omega(n^{\Theta(k)})$ — intractable</td>
        </tr>
      </tbody>
    </table>
  </div>

  <p>SGD is computationally cheap but statistically wasteful on these tasks. Program ERM is statistically efficient but computationally intractable under uniform search. The real question is whether one can keep ERM's statistical advantages while replacing uniform search with something more structured.</p>

  <hr>

  <h2>Part III — LLM-PV makes ERM searchable</h2>

  <h3>From uniform search to proposal priors</h3>

  <p>The real bottleneck in program ERM is not verification — given a candidate program, checking whether it fits the data is easy. The difficult part is <strong>proposing promising candidates</strong>. Uniform search over programs of length $L$ assigns probability roughly $|\Sigma|^{-L}$ to any fixed target. A pretrained LLM changes this: conditioned on labeled examples, it places probability mass on short, structured, plausible rules suggested by the data.</p>

  <div class="pull-quote">&ldquo;The LLM does not replace ERM — it makes a previously impractical ERM procedure searchable.&rdquo;</div>

  <h3>The LLM-PV pipeline</h3>

  <div class="explorer fade-in" id="pipeline">
    <div class="explorer-header">
      <span class="explorer-title">LLM-PV — propose and verify</span>
      <span class="explorer-subtitle">— click each stage for details</span>
    </div>
    <div class="explorer-body">
      <div class="pipeline-steps">
        <div class="pipe-step" style="background:var(--gold-soft);" onclick="showPipe(0)" id="ps0">
          <div class="pipe-step-num" style="color:var(--gold);">Step 1</div>
          <div class="pipe-step-title" style="color:var(--text);">Prompt</div>
          <div class="pipe-step-desc">Format examples as input-output pairs</div>
        </div>
        <div class="pipe-arrow">→</div>
        <div class="pipe-step" style="background:var(--accent-xs);" onclick="showPipe(1)" id="ps1">
          <div class="pipe-step-num" style="color:var(--accent);">Step 2</div>
          <div class="pipe-step-title" style="color:var(--text);">Sample</div>
          <div class="pipe-step-desc">Draw $k$ candidate programs from LLM</div>
        </div>
        <div class="pipe-arrow">→</div>
        <div class="pipe-step" style="background:var(--surface);" onclick="showPipe(2)" id="ps2">
          <div class="pipe-step-num" style="color:var(--muted);">Step 3</div>
          <div class="pipe-step-title" style="color:var(--text);">Execute</div>
          <div class="pipe-step-desc">Compile and run in sandbox</div>
        </div>
        <div class="pipe-arrow">→</div>
        <div class="pipe-step" style="background:var(--teal-soft);" onclick="showPipe(3)" id="ps3">
          <div class="pipe-step-num" style="color:var(--teal);">Step 4</div>
          <div class="pipe-step-title" style="color:var(--text);">Select</div>
          <div class="pipe-step-desc">Pick lowest validation error</div>
        </div>
      </div>
      <div class="pipe-detail" id="pipe-detail">Click a step above to see details.</div>
    </div>
  </div>

  <h3>The formal guarantee</h3>

  <p>The guarantee cleanly separates the statistical role of validation from the search role of the LLM. Let $p_\epsilon(S_{\text{tr}})$ denote the probability that a fresh LLM proposal has population error at most $\epsilon$. Then after $k$ trials:</p>

  <div class="eq-highlight">
    $$\text{err}_D(h^\star) \;\le\; \epsilon \;+\; 2\sqrt{\frac{\log(4k/\delta)}{2m_{\text{val}}}}$$
  </div>

  <p>The LLM enters only through $p_\epsilon$ — the probability that it proposes a good program. It does not need to be trusted as the final predictor. The effective search size becomes roughly $1/p_\epsilon(S_{\text{tr}})$ instead of $|\Sigma|^L$.</p>

  <h3>Watching candidates evolve: reasoning trace simulator</h3>

  <div class="explorer fade-in" id="trace-sim">
    <div class="explorer-header">
      <span class="explorer-title">Reasoning trace simulator</span>
      <span class="explorer-subtitle">— candidates sharpen from heuristics to correct solutions</span>
    </div>
    <div class="explorer-body">
      <div style="display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:10px;margin-bottom:14px;">
        <div style="display:flex;align-items:center;gap:8px;flex-wrap:wrap;">
          <span style="font-family:var(--mono);font-size:10.5px;color:var(--muted);">Task:</span>
          <select id="trace-task" onchange="traceReset()" style="font-family:var(--mono);font-size:11px;padding:4px 8px;border-radius:4px;border:1px solid var(--border);background:var(--bg);color:var(--text);cursor:pointer;">
            <option value="prime">IsPrime</option>
            <option value="parity">Parity</option>
            <option value="palindrome">IsPalindrome</option>
            <option value="dyck">Dyck-2</option>
          </select>
        </div>
        <div style="display:flex;gap:6px;align-items:center;">
          <button class="play-btn active" id="trace-play-btn" onclick="traceTogglePlay()">▶ Play</button>
          <button class="play-btn" onclick="traceStep()">Next round</button>
          <button class="play-btn" onclick="traceReset()">Reset</button>
          <span id="trace-round-label" style="font-family:var(--mono);font-size:10.5px;color:var(--muted-lt);min-width:80px;text-align:right;">Round 0 / 2</span>
        </div>
      </div>

      <div id="trace-candidates" style="display:flex;flex-direction:column;gap:8px;margin-bottom:12px;">
        <div style="text-align:center;padding:1.5rem;color:var(--muted-lt);font-family:var(--mono);font-size:11px;">Press Play or Next round to begin</div>
      </div>

      <div style="background:var(--bg);border:1px solid var(--border-lt);border-radius:7px;padding:10px 12px;">
        <div style="font-family:var(--mono);font-size:9.5px;font-weight:500;color:var(--muted-lt);letter-spacing:.06em;text-transform:uppercase;margin-bottom:8px;">Best validation accuracy over rounds</div>
        <div id="trace-evo"></div>
      </div>

      <div id="trace-insight" style="display:none;margin-top:10px;font-family:var(--sans);font-size:12.5px;line-height:1.6;padding:9px 13px;background:var(--accent-xs);border:1px solid #c0d9ef;border-radius:6px;color:var(--accent);"></div>
    </div>
  </div>

  <p class="figcaption"><strong>Fig. 2.</strong> Simulated reasoning trace for LLM-PV. On IsPrime, proposals evolve from "check if odd" (58%) to trial division with √n bound (100%) in just two rounds. On parity, the correct solution appears in round 1. The LLM does not need to be perfect — it only needs to assign enough mass to the right program for ERM verification to find it.</p>

  <hr>

  <h2>Part IV — Results</h2>

  <h3>Recovering exact rules from a handful of examples</h3>

  <p>Across 13 algorithmic tasks at input length $n = 100$, LLM-PV recovers exact or near-exact rules from only 200 labeled examples:</p>

  <div class="bar-chart fade-in">
    <div class="bar-chart-title">Test accuracy (%) — 200 training examples, input length 100</div>
    <div class="filter-tabs">
      <button class="filter-tab active" onclick="filterBars(this,'all')">All tasks</button>
      <button class="filter-tab" onclick="filterBars(this,'perfect')">LLM-PV perfect</button>
      <button class="filter-tab" onclick="filterBars(this,'hard')">Challenging</button>
    </div>
    <div id="bars-container"></div>
  </div>

  <p class="figcaption"><strong>Fig. 3.</strong> LLM-PV achieves perfect accuracy on 10 of 13 tasks. On SHA-256 parity — intentionally pseudorandom with no exploitable short structure — it fails, confirming the method's dependence on compressible hypotheses.</p>

  <p>The full comparison with baselines:</p>

  <div class="table-wrap fade-in">
    <table>
      <thead>
        <tr>
          <th>Task</th>
          <th>XGBoost</th>
          <th>SGD (1B)</th>
          <th>Fine-tune</th>
          <th>ICL (30B)</th>
          <th>TabPFN</th>
          <th class="col-llmpv">LLM-PV</th>
        </tr>
      </thead>
      <tbody>
        <tr><td>Full parity</td><td class="td-chance">49.9</td><td class="td-chance">49.3</td><td class="td-chance">50.4</td><td class="td-chance">53.0</td><td class="td-chance">50.1</td><td class="td-llmpv td-best">100</td></tr>
        <tr><td>First-half parity</td><td class="td-chance">50.0</td><td class="td-chance">50.6</td><td class="td-chance">51.3</td><td class="td-chance">54.0</td><td class="td-chance">50.5</td><td class="td-llmpv td-best">100</td></tr>
        <tr><td>Pattern 1</td><td class="td-chance">50.6</td><td class="td-chance">51.5</td><td>61.5</td><td class="td-chance">56.0</td><td class="td-chance">49.2</td><td class="td-llmpv td-best">100</td></tr>
        <tr><td>Pattern 2</td><td class="td-chance">52.3</td><td class="td-chance">53.6</td><td>57.6</td><td class="td-chance">51.0</td><td class="td-chance">51.2</td><td class="td-llmpv td-best">100</td></tr>
        <tr><td>3-parity</td><td class="td-chance">49.9</td><td class="td-chance">49.7</td><td class="td-chance">51.0</td><td class="td-chance">50.0</td><td class="td-chance">49.3</td><td class="td-llmpv td-best">100</td></tr>
        <tr><td>10-parity</td><td class="td-chance">49.3</td><td class="td-chance">50.3</td><td class="td-chance">50.5</td><td class="td-chance">50.0</td><td class="td-chance">50.5</td><td class="td-llmpv td-best">100</td></tr>
        <tr><td>IsPalindrome</td><td>83.6</td><td class="td-chance">49.2</td><td class="td-chance">49.6</td><td class="td-chance">47.0</td><td class="td-chance">49.4</td><td class="td-llmpv td-best">100</td></tr>
        <tr><td>Dyck-2</td><td class="td-chance">49.7</td><td class="td-chance">51.4</td><td class="td-chance">52.7</td><td class="td-chance">48.0</td><td class="td-chance">50.5</td><td class="td-llmpv td-best">100</td></tr>
        <tr><td>CA parity</td><td class="td-chance">50.4</td><td class="td-chance">49.4</td><td class="td-chance">50.7</td><td class="td-chance">49.0</td><td class="td-chance">48.0</td><td class="td-llmpv td-best">100</td></tr>
        <tr><td>IsPrime</td><td>61.8</td><td>58.8</td><td>57.2</td><td class="td-chance">50.0</td><td>57.1</td><td class="td-llmpv td-best">100</td></tr>
        <tr><td>IsPrime+47</td><td>59.3</td><td class="td-chance">53.6</td><td>58.7</td><td>58.0</td><td>65.4</td><td class="td-llmpv td-best">80.6</td></tr>
        <tr><td>CycleCount</td><td class="td-chance">51.1</td><td class="td-chance">53.5</td><td>65.7</td><td class="td-chance">46.0</td><td class="td-chance">51.3</td><td class="td-llmpv td-best">96.9</td></tr>
        <tr><td>SHA-256</td><td class="td-chance">50.3</td><td class="td-chance">49.8</td><td class="td-chance">50.8</td><td class="td-chance">54.0</td><td class="td-chance">50.6</td><td class="td-llmpv td-chance">50.1</td></tr>
      </tbody>
    </table>
  </div>

  <h3>More data does not rescue SGD</h3>

  <p>Even with up to 100,000 training examples, SGD-trained models can remain near chance on parity-style tasks while fitting the training data perfectly. These tasks are not difficult because they require huge datasets — they are difficult because the search procedure is poorly matched to the hypothesis class.</p>

  <h3>Length generalization emerges naturally</h3>

  <p>A particularly striking property of LLM-PV is that it often synthesizes <strong>dimension-invariant programs</strong>. When trained on short inputs ($n = 10$) and tested on much longer ones ($n = 100$), it can maintain perfect accuracy. This follows naturally from representing the hypothesis as code — a loop or invariant-checking procedure extends cleanly beyond the training input size, whereas a fixed-dimensional parametric map cannot.</p>

  <div class="finding-green">
    <div class="finding-label">Auditable output</div>
    The output is executable code and the search trace is logged. The learned hypothesis can be read, tested, modified, and verified directly — a major conceptual difference from opaque neural predictors.
  </div>

  <div class="finding">
    <div class="finding-label">Beyond algorithmic tasks</div>
    On standard tabular datasets with only 100 training samples, LLM-PV is competitive with XGBoost, Random Forest, and TabPFN — the propose-and-verify view extends beyond exact program recovery.
  </div>

  <hr>

  <h2>What this does and does not say</h2>

  <p>This argument does <strong>not</strong> say that LLM-PV replaces deep learning on standard vision, language, or audio tasks. In those domains, the usual pipeline remains extremely effective. The picture is narrower and cleaner.</p>

  <p>Classical ERM over programs is statistically attractive but computationally inaccessible under uniform search. A pretrained LLM changes the proposal distribution — making some short, structured hypotheses much easier to find. Verification and final selection still come from the data. If the target does not admit a short exploitable program, or if the LLM assigns negligible mass to useful candidates, the method fails. The SHA-256 result confirms exactly this regime.</p>

  <div class="steps">
    <div class="step">
      <div class="step-num" style="background:var(--accent);">✓</div>
      <div class="step-body">
        <div class="step-title">The LLM proposes.</div>
        <div class="step-desc">Conditioned on examples, it generates candidate programs from a structured distribution over code — vastly more efficient than uniform enumeration.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num" style="background:var(--teal);">✓</div>
      <div class="step-body">
        <div class="step-title">The data verifies.</div>
        <div class="step-desc">Held-out validation selects the best candidate. The LLM is not trusted as the final predictor — it is a search engine. ERM is the selection rule.</div>
      </div>
    </div>
  </div>

  <div class="takeaway">
    <h3>Takeaway</h3>
    <p>Pretrained LLMs can make program-based ERM practical by replacing brute-force search with guided search. The mechanism has four parts.</p>
    <p><strong>Short programs generalize.</strong> If the target has a length-$L$ description, ERM needs only $O(L \log|\Sigma|)$ samples — independent of raw input dimension.</p>
    <p><strong>SGD can still fail badly.</strong> On SQ-hard families such as parity, gradient-based learners may require exponentially many samples even when the target is simple as code.</p>
    <p><strong>Brute-force ERM is computationally intractable.</strong> Uniform search over programs scales like $|\Sigma|^L$ — impractical even for short targets.</p>
    <p><strong>LLM-PV changes the search distribution.</strong> A pretrained LLM proposes plausible candidates; held-out verification selects the best one. The ERM principle is preserved; only the proposal mechanism changes.</p>
    <p>The resulting paradigm recovers exact algorithmic rules from a handful of examples, generalizes beyond the training distribution, and produces executable hypotheses that can be inspected and verified directly.</p>
  </div>

</article>

<div class="post-footer">
  <p>Published on <a href="https://dlfundamentals.github.io/blog/">Theory/Simplified</a> &nbsp;&middot;&nbsp; Based on <a href="#">Singhal, Mishra, Malach, Galanti — arXiv 2025</a></p>
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

  /* ── PIPELINE ── */
  var pipeDetails = [
    '<strong>Step 1 — Prompt construction.</strong> The training examples are formatted as input-output pairs and placed into a prompt asking the LLM to write a Python function implementing the underlying rule. No gradient updates, no fine-tuning — just prompting.',
    '<strong>Step 2 — Sampling.</strong> The LLM generates $k$ candidate programs (typically $k=64$ to $256$). Each is a complete, executable Python function. The LLM acts purely as a proposal distribution — it does not optimize the learning objective.',
    '<strong>Step 3 — Sandbox execution.</strong> Each candidate program is compiled and executed against training and validation examples in an isolated sandbox. Programs that crash, time out, or produce malformed output are discarded automatically.',
    '<strong>Step 4 — ERM selection.</strong> The program with the lowest error on held-out validation data is selected. This is classical empirical risk minimization — the LLM proposes, the data decides.'
  ];

  window.showPipe = function(i){
    root.querySelectorAll('.pipe-step').forEach(function(el){el.classList.remove('active');});
    var s = document.getElementById('ps'+i); if(s) s.classList.add('active');
    var d = document.getElementById('pipe-detail'); if(!d) return;
    d.innerHTML = pipeDetails[i];
    if(typeof renderMathInElement !== 'undefined') renderMathInElement(d,{delimiters:[{left:'$',right:'$',display:false}],throwOnError:false});
  };

  /* ── BAR CHART ── */
  var tasks = [
    {name:'Full parity',     llmpv:100,  best_base:53.0, cat:'perfect'},
    {name:'First-half parity',llmpv:100, best_base:54.0, cat:'perfect'},
    {name:'Pattern 1',       llmpv:100,  best_base:61.5, cat:'perfect'},
    {name:'Pattern 2',       llmpv:100,  best_base:57.6, cat:'perfect'},
    {name:'3-parity',        llmpv:100,  best_base:51.0, cat:'perfect'},
    {name:'10-parity',       llmpv:100,  best_base:50.5, cat:'perfect'},
    {name:'IsPalindrome',    llmpv:100,  best_base:83.6, cat:'perfect'},
    {name:'Dyck-2',          llmpv:100,  best_base:52.7, cat:'perfect'},
    {name:'CA parity',       llmpv:100,  best_base:50.7, cat:'perfect'},
    {name:'IsPrime',         llmpv:100,  best_base:61.8, cat:'perfect'},
    {name:'IsPrime+47',      llmpv:80.6, best_base:65.4, cat:'hard'},
    {name:'CycleCount',      llmpv:96.9, best_base:65.7, cat:'hard'},
    {name:'SHA-256',         llmpv:50.1, best_base:54.0, cat:'hard'}
  ];

  function renderBars(filter){
    var c = document.getElementById('bars-container'); if(!c) return;
    c.innerHTML = '';
    var filtered = filter==='all' ? tasks : tasks.filter(function(t){return t.cat===filter;});
    filtered.forEach(function(t){
      var barColor = t.llmpv >= 100 ? 'var(--teal)' : (t.llmpv > 60 ? 'var(--accent-mid)' : 'var(--muted)');
      var r1 = document.createElement('div'); r1.className = 'bar-row';
      r1.innerHTML = '<div class="bar-label">'+t.name+'</div><div class="bar-track"><div class="bar-fill" style="width:'+t.llmpv+'%;background:'+barColor+'">'+(t.llmpv>12?'<span class="bar-value">'+t.llmpv+'</span>':'')+'</div></div>'+(t.llmpv<=12?'<span class="bar-value-out">'+t.llmpv+'</span>':'');
      var r2 = document.createElement('div'); r2.className = 'bar-row'; r2.style.marginBottom='12px';
      r2.innerHTML = '<div class="bar-label" style="font-size:9.5px;color:var(--muted-lt);">best baseline</div><div class="bar-track"><div class="bar-fill" style="width:'+t.best_base+'%;background:var(--muted-lt);opacity:.5">'+(t.best_base>12?'<span class="bar-value">'+t.best_base+'</span>':'')+'</div></div>'+(t.best_base<=12?'<span class="bar-value-out">'+t.best_base+'</span>':'');
      c.appendChild(r1); c.appendChild(r2);
    });
  }

  window.filterBars = function(btn, filter){
    root.querySelectorAll('.filter-tab').forEach(function(t){t.classList.remove('active');});
    btn.classList.add('active');
    renderBars(filter);
  };
  renderBars('all');

  /* ── TRACE SIMULATOR ── */
  var traceTasks = {
    prime:{name:'IsPrime',rounds:[
      {candidates:[
        {code:'def predict(x):\n  return x % 2 != 0',score:58,label:'Check if odd',status:'partial'},
        {code:'def predict(x):\n  return len(str(x)) > 1',score:52,label:'Digit count heuristic',status:'fail'},
        {code:'def predict(x):\n  s = sum(int(d) for d in str(x))\n  return s % 3 != 0',score:55,label:'Digit sum rule',status:'partial'},
        {code:'def predict(x):\n  return x > 1 and x % 2 != 0 and x % 3 != 0',score:72,label:'Check 2 and 3',status:'partial'}
      ],best:3,insight:'Round 1: The LLM proposes simple heuristics. Checking divisibility by 2 and 3 is the best so far — but it wrongly classifies composites like 25 and 35 as prime.'},
      {candidates:[
        {code:'def predict(x):\n  if x < 2: return False\n  for d in [2,3,5,7,11,13]:\n    if x > d and x % d == 0:\n      return False\n  return True',score:88,label:'Check small primes',status:'partial'},
        {code:'def predict(x):\n  return x in [2,3,5,7,11,13,17,19,23,29]',score:61,label:'Hardcoded list',status:'fail'},
        {code:'def predict(x):\n  if x < 2: return False\n  for i in range(2, min(x, 20)):\n    if x % i == 0: return False\n  return True',score:91,label:'Trial division (cap 20)',status:'partial'},
        {code:'def predict(x):\n  return x > 1 and all(x % i != 0\n    for i in range(2, int(x**.5)+1))',score:100,label:'Trial division (√n)',status:'pass'}
      ],best:3,insight:'Round 2: The LLM now proposes trial division with different bounds. Only the √n version is correct for all inputs. Validation selects it immediately.'}
    ]},
    parity:{name:'Parity',rounds:[
      {candidates:[
        {code:'def predict(x):\n  return x[0] ^ x[1]',score:52,label:'XOR first two bits',status:'fail'},
        {code:'def predict(x):\n  return sum(x) % 2',score:100,label:'Sum mod 2',status:'pass'},
        {code:'def predict(x):\n  return x[-1]',score:51,label:'Last bit',status:'fail'},
        {code:'def predict(x):\n  c = 0\n  for b in x: c += b\n  return c > len(x)//2',score:54,label:'Majority vote',status:'fail'}
      ],best:1,insight:'Round 1: Full parity has a one-line solution — sum all bits mod 2. The LLM finds it on the first round. ERM verification confirms 100% accuracy immediately.'}
    ]},
    palindrome:{name:'IsPalindrome',rounds:[
      {candidates:[
        {code:'def predict(x):\n  return x[0] == x[-1]',score:68,label:'Match first/last',status:'partial'},
        {code:'def predict(x):\n  return len(set(x)) < len(x)//2',score:55,label:'Low unique count',status:'fail'},
        {code:'def predict(x):\n  n = len(x)\n  return all(x[i]==x[n-1-i]\n    for i in range(n//2))',score:100,label:'Full palindrome check',status:'pass'},
        {code:'def predict(x):\n  return x[:3] == x[-3:][::-1]',score:72,label:'Match first/last 3',status:'partial'}
      ],best:2,insight:'Round 1: The correct solution — comparing characters from both ends — appears alongside partial heuristics. Validation picks the 100% candidate immediately.'}
    ]},
    dyck:{name:'Dyck-2',rounds:[
      {candidates:[
        {code:'def predict(x):\n  return x.count("(")==x.count(")")',score:62,label:'Count parens only',status:'partial'},
        {code:'def predict(x):\n  return len(x) % 2 == 0',score:53,label:'Even length',status:'fail'},
        {code:'def predict(x):\n  s=[]\n  for c in x:\n    if c in "([": s.append(c)\n    elif not s: return False\n    elif c==")" and s[-1]!="(": return False\n    elif c=="]" and s[-1]!="[": return False\n    else: s.pop()\n  return len(s)==0',score:95,label:'Stack-based check',status:'partial'},
        {code:'def predict(x):\n  d=0\n  for c in x:\n    d += 1 if c=="(" else -1\n    if d < 0: return False\n  return d == 0',score:74,label:'Depth counter (1 type)',status:'partial'}
      ],best:2,insight:'Round 1: Dyck-2 requires tracking two bracket types. The stack-based solution reaches 95% but has an edge case on mixed nesting.'},
      {candidates:[
        {code:'def predict(x):\n  m={"(":")", "[":"]"}\n  s=[]\n  for c in x:\n    if c in m: s.append(m[c])\n    elif not s or s.pop()!=c: return False\n  return not s',score:100,label:'Stack with map',status:'pass'},
        {code:'def predict(x):\n  s=[]\n  for c in x:\n    if c in "([": s.append(c)\n    elif not s: return False\n    elif c==")" and s[-1]=="(": s.pop()\n    elif c=="]" and s[-1]=="[": s.pop()\n    else: return False\n  return len(s)==0',score:100,label:'Explicit stack match',status:'pass'},
        {code:'def predict(x):\n  while "()" in x or "[]" in x:\n    x=x.replace("()","").replace("[]","")\n  return x == ""',score:100,label:'Reduction method',status:'pass'},
        {code:'def predict(x):\n  d1=d2=0\n  for c in x:\n    if c=="(": d1+=1\n    elif c==")": d1-=1\n    elif c=="[": d2+=1\n    else: d2-=1\n    if d1<0 or d2<0: return 0\n  return d1==0 and d2==0',score:82,label:'Dual counters',status:'partial'}
      ],best:0,insight:'Round 2: Three candidates achieve 100% — stack-with-map, explicit matching, and reduction all solve Dyck-2. The dual-counter fails on interleaved brackets like "([)]".'}
    ]}
  };

  var traceRound=0, traceTask='prime', tracePlaying=false, traceTimer=null, traceBestHistory=[];

  function traceUpdateLabel(){
    var total=traceTasks[traceTask].rounds.length;
    var lbl=document.getElementById('trace-round-label');
    if(lbl) lbl.textContent='Round '+traceRound+' / '+total;
  }

  window.traceReset=function(){
    if(tracePlaying) window.traceTogglePlay();
    var sel=document.getElementById('trace-task');
    traceTask=sel?sel.value:'prime';
    traceRound=0; traceBestHistory=[];
    var c=document.getElementById('trace-candidates');
    var e=document.getElementById('trace-evo');
    var i=document.getElementById('trace-insight');
    if(c) c.innerHTML='<div style="text-align:center;padding:1.5rem;color:var(--muted-lt);font-family:var(--mono);font-size:11px;">Press Play or Next round to begin</div>';
    if(e) e.innerHTML='';
    if(i){i.style.display='none';}
    traceUpdateLabel();
  };

  window.traceStep=function(){
    var t=traceTasks[traceTask];
    if(!t||traceRound>=t.rounds.length) return;
    var round=t.rounds[traceRound]; traceRound++;
    var container=document.getElementById('trace-candidates'); if(!container) return;
    container.innerHTML='';

    round.candidates.forEach(function(c,i){
      var div=document.createElement('div');
      div.className='trace-cand'+(i===round.best?' best':(c.status==='fail'?' eliminated':''));
      div.style.opacity='0'; div.style.transform='translateY(8px)';
      var bCls=c.status==='pass'?'trace-badge-pass':(c.status==='fail'?'trace-badge-fail':'trace-badge-partial');
      var bTxt=c.status==='pass'?'100% — selected':(c.status==='fail'?'eliminated':c.score+'%');
      if(i===round.best&&c.status!=='pass'){bTxt=c.score+'% — best so far';bCls='trace-badge-best';}
      if(i===round.best&&c.status==='pass') bCls='trace-badge-pass';
      var barColor=c.status==='pass'?'var(--teal)':(c.status==='fail'?'var(--red)':'var(--amber)');
      if(i===round.best) barColor=c.status==='pass'?'var(--teal)':'var(--accent)';
      div.innerHTML='<div class="trace-cand-header"><span class="trace-cand-label">Candidate '+(i+1)+' — '+c.label+'</span><span class="trace-badge '+bCls+'">'+bTxt+'</span></div><div class="trace-code">'+c.code+'</div><div class="trace-footer"><span class="trace-score">Validation: '+c.score+'%</span><div class="trace-bar-track"><div class="trace-bar-fill" style="width:0%;background:'+barColor+'"></div></div></div>';
      container.appendChild(div);
      setTimeout(function(){
        div.style.transition='opacity .4s ease,transform .4s ease';
        div.style.opacity='1'; div.style.transform='translateY(0)';
        var fill=div.querySelector('.trace-bar-fill');
        if(fill) fill.style.width=c.score+'%';
      },i*150+50);
    });

    traceBestHistory.push(round.candidates[round.best].score);
    var evo=document.getElementById('trace-evo');
    if(evo){
      evo.innerHTML='';
      traceBestHistory.forEach(function(score,i){
        var row=document.createElement('div');
        row.style.cssText='display:flex;align-items:center;gap:8px;margin-bottom:4px';
        var bc=score>=100?'var(--teal)':(score>=80?'var(--accent-mid)':'var(--amber)');
        row.innerHTML='<span style="font-family:var(--mono);font-size:10px;color:var(--muted-lt);min-width:24px">R'+(i+1)+'</span><div style="flex:1;height:5px;background:var(--surface-2);border-radius:3px"><div style="height:100%;border-radius:3px;width:'+score+'%;background:'+bc+';transition:width .6s ease"></div></div><span style="font-family:var(--mono);font-size:10px;color:var(--muted-lt);min-width:36px;text-align:right">'+score+'%</span>';
        evo.appendChild(row);
      });
    }

    var ins=document.getElementById('trace-insight');
    if(ins){ins.style.display='block';ins.textContent=round.insight;}
    traceUpdateLabel();
    if(traceRound>=t.rounds.length&&tracePlaying) window.traceTogglePlay();
  };

  window.traceTogglePlay=function(){
    tracePlaying=!tracePlaying;
    var btn=document.getElementById('trace-play-btn');
    if(tracePlaying){
      if(btn){btn.textContent='⏸ Pause';btn.classList.add('active');}
      if(traceRound===0||traceRound>=traceTasks[traceTask].rounds.length) window.traceReset();
      window.traceStep();
      traceTimer=setInterval(function(){
        if(traceRound>=traceTasks[traceTask].rounds.length){window.traceTogglePlay();return;}
        window.traceStep();
      },3500);
    } else {
      if(btn){btn.textContent='▶ Play';btn.classList.remove('active');}
      clearInterval(traceTimer);
    }
  };

  if('IntersectionObserver' in window){
    var obs=new IntersectionObserver(function(entries){entries.forEach(function(e){if(e.isIntersecting)e.target.classList.add('visible');});},{threshold:0.1});
    root.querySelectorAll('.fade-in').forEach(function(el){obs.observe(el);});
  }

  window.traceReset();
})();
</script>
