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
.ps tr.row-all td{border-top:2px solid var(--border);font-weight:500;background:var(--surface);}

/* ── STAT STRIP ── */
.ps .stat-strip{display:flex;gap:.75rem;flex-wrap:wrap;margin:1.7rem 0;}
.ps .stat{flex:1;min-width:150px;background:var(--bg-warm);border:1px solid var(--border);border-radius:9px;padding:.95rem 1.05rem;}
.ps .stat-num{font-family:var(--serif);font-size:1.55rem;font-weight:600;color:var(--accent);line-height:1;}
.ps .stat-num.teal{color:var(--teal);}
.ps .stat-num.gold{color:var(--amber);}
.ps .stat-lbl{font-family:var(--mono);font-size:10px;color:var(--muted);letter-spacing:.04em;text-transform:uppercase;margin-top:.45rem;line-height:1.45;}

/* ── BAR CHART ── */
.ps .bar-chart{margin:1.4rem 0;background:var(--bg-warm);border:1px solid var(--border);border-radius:10px;padding:1.1rem 1.25rem;}
.ps .bar-chart-title{font-family:var(--mono);font-size:10px;font-weight:500;color:var(--muted-lt);letter-spacing:.06em;text-transform:uppercase;margin-bottom:14px;}
.ps .bar-row{display:flex;align-items:center;margin-bottom:9px;gap:8px;}
.ps .bar-label{font-family:var(--mono);font-size:10.5px;color:var(--text-soft);width:150px;flex-shrink:0;text-align:right;}
.ps .bar-track{flex:1;height:22px;background:var(--surface-2);border-radius:3px;overflow:hidden;position:relative;}
.ps .bar-fill{height:100%;border-radius:3px;transition:width .6s ease;display:flex;align-items:center;justify-content:flex-end;padding-right:7px;}
.ps .bar-value{font-family:var(--mono);font-size:10px;font-weight:500;color:white;}

/* ── EXPLORER / PIPELINE ── */
.ps .explorer{background:var(--bg-warm);border:1px solid var(--border);border-radius:10px;overflow:hidden;margin:1.75rem 0;}
.ps .explorer-header{background:var(--surface);border-bottom:1px solid var(--border);padding:.8rem 1.25rem;display:flex;align-items:baseline;gap:.75rem;flex-wrap:wrap;}
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

/* ── SIMULATOR ── */
.ps .bd-controls{display:flex;flex-wrap:wrap;gap:.9rem 1.3rem;margin-bottom:1.1rem;}
.ps .bd-ctrl{flex:1;min-width:135px;}
.ps .bd-ctrl label{font-family:var(--mono);font-size:10px;color:var(--muted);display:flex;justify-content:space-between;margin-bottom:5px;}
.ps .bd-ctrl label b{color:var(--accent);font-weight:500;}
.ps .bd-ctrl input[type=range]{width:100%;accent-color:var(--accent);cursor:pointer;}
.ps .bd-bars{margin:.4rem 0 1rem;}
.ps .bd-bar-row{display:flex;align-items:center;gap:8px;margin-bottom:8px;}
.ps .bd-bar-label{font-family:var(--mono);font-size:10px;width:150px;flex-shrink:0;text-align:right;color:var(--text-soft);}
.ps .bd-bar-track{flex:1;height:18px;background:var(--surface-2);border-radius:3px;overflow:hidden;}
.ps .bd-bar-fill{height:100%;border-radius:3px;transition:width .35s ease;min-width:2px;}
.ps .bd-bar-val{font-family:var(--mono);font-size:10px;font-weight:500;color:var(--muted-lt);min-width:96px;flex-shrink:0;}
.ps .bd-result{background:var(--bg);border:1px solid var(--border-lt);border-radius:7px;padding:.85rem 1rem;font-size:13px;color:var(--text-soft);line-height:1.7;}
.ps .bd-result b{color:var(--accent);font-weight:500;}
.ps .bd-result .bd-big{font-family:var(--serif);font-size:1.2rem;color:var(--teal);font-weight:600;}

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
  .ps .bar-label{width:110px;}
}
@media(max-width:600px){.ps table{font-size:11.5px;}}
</style>

<div class="ps">

<div class="top-bar"></div>

<div class="hero">
  <div class="hero-eyebrow">Reasoning Models &middot; Inference-Time Compute &middot; Boosting Theory</div>
  <h1>Agentic Systems as <em>Boosting</em></h1>
  <p class="hero-subtitle">Boosting turns weak learners into strong ones by combining many imperfect signals. Can a committee of weak reasoning-model calls do the same at inference time — reaching the level of much stronger models? And if a correct answer is already hiding in the pool, what does it take to actually pick it out?</p>
  <div class="hero-meta">
    <span>By Tomer Galanti</span>
    <span>&middot;</span>
    <span>May 13, 2026</span>
    <span>&middot;</span>
    <span>15 min read</span>
    <span>&middot;</span>
    <span class="paper-badge">&#9670; Sunkaraneni, Beneventano, Neumarker, Poggio, Galanti — arXiv 2026</span>
  </div>
</div>

<article>

  <h2>Introduction</h2>

  <p class="lead">Classical boosting takes a weak predictor — one that is only slightly better than chance — and, by repeatedly combining imperfect but useful signals, builds a strong predictor. Modern language-model systems lean on a related idea at inference time: sample several candidates, check or compare them, search over partial states, and select a final output.</p>

  <p>But reasoning is not ordinary supervised boosting. In supervised prediction, each weak learner returns a label you can score against training examples. In reasoning, the system has to generate an intermediate <em>move</em>, decide whether that move is useful, and keep small local errors from accumulating into a wrong final answer. The natural question: can a committee of <strong>weak</strong> reasoning-model calls reach the performance of much <strong>stronger</strong> models?</p>

  <p>On SWE-bench Verified, a single call to <code>GPT-5.4 nano</code> resolves 67.0% of tasks. Wrapping that same nano model in a critic&ndash;comparator committee lifts it to 76.4% — matching standalone Gemini 3 Pro and Claude Opus 4.5 Thinking. And an oracle that could always pick the best of 8 nano proposals would reach 79.0%. So most of the correct patches are <em>already in the weak model's pool</em>. The hard part is selecting them.</p>

  <div class="callout">
    <strong>The central reframing</strong>
    Agentic systems are <em>inference-time boosting</em> for reasoning models. The lever is not &ldquo;more agents help.&rdquo; Sampling exposes latent correct solutions; critics and comparators must then <em>recover</em> those solutions without access to the hidden verifier. Generation and recognition are different capabilities — and the gap between them is where most of the design lives.
  </div>

  <p>The analysis separates four quantities. The rest of the post is organized around them:</p>

  <div class="steps">
    <div class="step">
      <div class="step-num purple">1</div>
      <div class="step-body">
        <div class="step-title">Coverage — does a good move appear?</div>
        <div class="step-desc">Whether some proposal in the pool is a progressing-sound next action. Amplified by sampling more candidates.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num" style="background:var(--accent);">2</div>
      <div class="step-body">
        <div class="step-title">Identifiability — can the system recognize it?</div>
        <div class="step-desc">Whether critics and comparators can pick the good move out of the pool. Needs an extra local soundness signal.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num teal">3</div>
      <div class="step-body">
        <div class="step-title">Progress — do local choices compose?</div>
        <div class="step-desc">A rank function ensures each sound action gets strictly closer to a solution, so good steps chain into a terminal answer.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num gold">4</div>
      <div class="step-body">
        <div class="step-title">Diversity — do more calls escape shared failures?</div>
        <div class="step-desc">More calls reduce sampling noise, but cannot fix blind spots that every proposer shares.</div>
      </div>
    </div>
  </div>

  <div class="paper-note">
    Based on: V. Sunkaraneni, P. Beneventano, R. Neumarker, T. Poggio, T. Galanti. &ldquo;Agentic Systems as Boosting Weak Reasoning Models&rdquo;, arXiv:2605.14163, 2026.
  </div>

  <hr>

  <h2>Part I — Boosting, moved to inference time</h2>

  <p>The setting is verifier-backed reasoning: code repair, theorem proving, program synthesis — domains where tests, type checkers, execution, proof checkers, or constraint solvers can supply a local soundness signal. The system is modeled as bounded-depth search over partial reasoning states with local progress.</p>

  <p>Formally, each task induces a state space with a set of valid states (those from which a correct completion is still possible), terminal states accepted by a verifier, and a <strong>rank</strong> function $d_x(s)$ measuring distance to a solution, equal to $0$ at terminal states. An action is <strong>progressing-sound</strong> if it keeps the state valid and strictly decreases the rank:</p>

  <div class="math-display">
    <div class="math-label">Definition &middot; progressing-sound action</div>
    $$s^{*}_a \in \mathrm{Valid}_x \qquad\text{and}\qquad d_x(s^{*}_a) < d_x(s)$$
  </div>

  <p>In the running example — SWE-bench Verified — the state holds the current repo worktree, the issue, and the visible tests; success is judged by <em>hidden</em> tests. A progressing-sound action is a code edit that preserves some hidden-test-passing patch while reducing the remaining work. Visible tests, types, and linters reject many unsound edits, but they don't certify correctness.</p>

  <h3>The committee protocol</h3>

  <p>At each non-terminal state, the committee protocol $\Pi_{k,m,r}$ runs three roles in sequence, then advances and repeats. Click each stage:</p>

  <div class="explorer fade-in" id="pipeline">
    <div class="explorer-header">
      <span class="explorer-title">Committee protocol &Pi;(k, m, r)</span>
      <span class="explorer-subtitle">— one step, repeated up to L times</span>
    </div>
    <div class="explorer-body">
      <div class="pipeline-steps">
        <div class="pipe-step" style="background:var(--purple-soft);" onclick="showPipe(0)" id="ps0">
          <div class="pipe-step-num" style="color:var(--purple);">propose (k)</div>
          <div class="pipe-step-title" style="color:var(--text);">Proposers</div>
          <div class="pipe-step-desc">Sample k candidate moves</div>
        </div>
        <div class="pipe-arrow">&rarr;</div>
        <div class="pipe-step" style="background:var(--accent-xs);" onclick="showPipe(1)" id="ps1">
          <div class="pipe-step-num" style="color:var(--accent);">critique (m)</div>
          <div class="pipe-step-title" style="color:var(--text);">Critics</div>
          <div class="pipe-step-desc">Filter refutable errors</div>
        </div>
        <div class="pipe-arrow">&rarr;</div>
        <div class="pipe-step" style="background:var(--teal-soft);" onclick="showPipe(2)" id="ps2">
          <div class="pipe-step-num" style="color:var(--teal);">compare (r)</div>
          <div class="pipe-step-title" style="color:var(--text);">Comparators</div>
          <div class="pipe-step-desc">Rank the survivors</div>
        </div>
        <div class="pipe-arrow">&rarr;</div>
        <div class="pipe-step" style="background:var(--gold-soft);" onclick="showPipe(3)" id="ps3">
          <div class="pipe-step-num" style="color:var(--amber);">advance</div>
          <div class="pipe-step-title" style="color:var(--text);">Apply &amp; repeat</div>
          <div class="pipe-step-desc">Move to next state</div>
        </div>
      </div>
      <div class="pipe-detail" id="pipe-detail">Click a stage above to see details.</div>
    </div>
  </div>

  <p>Two assumptions name the resources this architecture needs. <strong>Coverage</strong> (Assumption 1) says some proposer in a polynomial-size portfolio outputs a sound action with probability at least $\alpha_0 > 0$. <strong>Identifiability</strong> (Assumption 2) says there exist efficient critics and comparators with an edge: a critic never rejects a sound move but rejects an unsound one with probability $\ge \beta_0$, and a comparator prefers sound over unsound with probability $\ge \tfrac{1}{2}+\sigma_0$. These are different capabilities — and that difference is the whole story.</p>

  <hr>

  <h2>Part II — Coverage is not identifiability</h2>

  <p>It is tempting to think that if good moves appear often enough, the system can simply learn to recognize them from the candidates. The paper proves this is false in general.</p>

  <div class="finding">
    <div class="finding-label">Proposition 1 &middot; a black-box separation</div>
    There is a one-step task family where the proposer is uniform over $M$ actions in every world, the sound set is &ldquo;everything except the hidden bad action $\theta$,&rdquo; and <strong>no</strong> procedure that observes only candidate actions and polynomially many proposer samples has any uniform critic or comparator edge across worlds. Coverage holds; identifiability is impossible.
  </div>

  <p>The intuition: if every world looks statistically identical from the proposal distribution alone, watching proposals tells you nothing about <em>which</em> move is the bad one. Sampling more candidates raises coverage, but it cannot manufacture a critic out of thin air. Recognition has to come from somewhere else — an accessible soundness signal.</p>

  <div class="diagram-wrap fade-in">
    <svg viewBox="0 0 660 232" xmlns="http://www.w3.org/2000/svg" style="width:100%;max-width:660px;display:block;margin:auto">
      <defs>
        <marker id="ab" markerWidth="6" markerHeight="6" refX="5" refY="3" orient="auto"><path d="M0,0 L6,3 L0,6 Z" fill="#2a6199"/></marker>
      </defs>

      <!-- titles -->
      <text x="165" y="22" font-family="DM Sans,sans-serif" font-size="12.5" font-weight="600" fill="#6e48aa" text-anchor="middle">Coverage</text>
      <text x="165" y="38" font-family="IBM Plex Mono,monospace" font-size="9.5" fill="#7a7060" text-anchor="middle">does a good move appear?</text>
      <text x="495" y="22" font-family="DM Sans,sans-serif" font-size="12.5" font-weight="600" fill="#1e4f7a" text-anchor="middle">Identifiability</text>
      <text x="495" y="38" font-family="IBM Plex Mono,monospace" font-size="9.5" fill="#7a7060" text-anchor="middle">can we recognize it?</text>

      <!-- divider -->
      <line x1="330" y1="52" x2="330" y2="214" stroke="#d8d2c6" stroke-dasharray="3 4"/>

      <!-- PANEL A: state node fanning to k candidates, 2 sound -->
      <circle cx="55" cy="130" r="16" fill="#ede9e0" stroke="#7a7060"/>
      <text x="55" y="134" font-family="IBM Plex Mono,monospace" font-size="10" fill="#3a3628" text-anchor="middle">s_t</text>
      <!-- candidate dots -->
      <g>
        <line x1="71" y1="130" x2="150" y2="72" stroke="#cfc7b8"/>
        <line x1="71" y1="130" x2="150" y2="102" stroke="#cfc7b8"/>
        <line x1="71" y1="130" x2="150" y2="130" stroke="#cfc7b8"/>
        <line x1="71" y1="130" x2="150" y2="158" stroke="#cfc7b8"/>
        <line x1="71" y1="130" x2="150" y2="188" stroke="#cfc7b8"/>
        <circle cx="158" cy="72"  r="8" fill="#2a6645"/>
        <circle cx="158" cy="102" r="8" fill="#b0a892"/>
        <circle cx="158" cy="130" r="8" fill="#b0a892"/>
        <circle cx="158" cy="158" r="8" fill="#2a6645"/>
        <circle cx="158" cy="188" r="8" fill="#b0a892"/>
      </g>
      <text x="158" y="76" font-family="DM Sans" font-size="9" fill="#fff" text-anchor="middle">&#10003;</text>
      <text x="158" y="162" font-family="DM Sans" font-size="9" fill="#fff" text-anchor="middle">&#10003;</text>
      <text x="210" y="118" font-family="DM Sans,sans-serif" font-size="9.5" fill="#2a6645" text-anchor="middle">sound</text>
      <text x="210" y="148" font-family="DM Sans,sans-serif" font-size="9.5" fill="#a09880" text-anchor="middle">unsound</text>
      <text x="165" y="214" font-family="IBM Plex Mono,monospace" font-size="9" fill="#7a7060" text-anchor="middle">more samples → higher chance one is sound</text>

      <!-- PANEL B: same candidates, indistinguishable (?), verifier reveals -->
      <g>
        <circle cx="408" cy="78"  r="9" fill="#cdc6b6"/>
        <circle cx="408" cy="110" r="9" fill="#cdc6b6"/>
        <circle cx="408" cy="142" r="9" fill="#cdc6b6"/>
        <circle cx="408" cy="174" r="9" fill="#cdc6b6"/>
      </g>
      <text x="408" y="82"  font-family="DM Sans" font-size="11" fill="#6b6453" text-anchor="middle">?</text>
      <text x="408" y="114" font-family="DM Sans" font-size="11" fill="#6b6453" text-anchor="middle">?</text>
      <text x="408" y="146" font-family="DM Sans" font-size="11" fill="#6b6453" text-anchor="middle">?</text>
      <text x="408" y="178" font-family="DM Sans" font-size="11" fill="#6b6453" text-anchor="middle">?</text>
      <text x="408" y="206" font-family="IBM Plex Mono,monospace" font-size="8.5" fill="#a09880" text-anchor="middle">candidates alone</text>

      <!-- verifier box -->
      <rect x="470" y="96" width="92" height="60" rx="7" fill="#ebf4fc" stroke="#2a6199"/>
      <text x="516" y="120" font-family="DM Sans,sans-serif" font-size="10" font-weight="600" fill="#1e4f7a" text-anchor="middle">verifier</text>
      <text x="516" y="136" font-family="IBM Plex Mono,monospace" font-size="8" fill="#2a6199" text-anchor="middle">tests / types</text>
      <text x="516" y="147" font-family="IBM Plex Mono,monospace" font-size="8" fill="#2a6199" text-anchor="middle">exec / proof</text>
      <line x1="427" y1="126" x2="468" y2="126" stroke="#2a6199" marker-end="url(#ab)"/>

      <!-- revealed sound -->
      <circle cx="610" cy="126" r="11" fill="#2a6645"/>
      <text x="610" y="130" font-family="DM Sans" font-size="11" fill="#fff" text-anchor="middle">&#10003;</text>
      <line x1="562" y1="126" x2="597" y2="126" stroke="#2a6199" marker-end="url(#ab)"/>
      <text x="610" y="150" font-family="IBM Plex Mono,monospace" font-size="8.5" fill="#2a6645" text-anchor="middle">recovered</text>
    </svg>
    <p class="diagram-caption">Fig. 1 — Two distinct capabilities. Coverage (left) makes a sound move appear in the pool; identifiability (right) recovers it. Without a soundness signal the candidates are indistinguishable; a one-sided verifier supplies the critic and comparator edges.</p>
  </div>

  <p>When a one-sided local verifier <em>is</em> available — one that always accepts sound moves and rejects unsound ones with probability $\ge 1-\nu$ — it directly supplies the identifiability edges, with $\beta_0 = 1-\nu$ and $\sigma_0 = (1-\nu)/2$. This is stronger than final-answer verification: the task decomposition has to expose useful <em>local</em> checks.</p>

  <div class="pull-quote">&ldquo;Sampling more candidates raises the chance a good move appears. It does not, by itself, tell you which one it is.&rdquo;</div>

  <hr>

  <h2>Part III — Composing local steps into a trajectory</h2>

  <p>Given coverage and identifiability, the bridge theorem shows the committee amplifies them. Round-robin over the proposer portfolio with enough calls makes the chance a sound move appears at a state as high as you like:</p>

  <div class="math-display">
    <div class="math-label">Theorem 1 &middot; coverage amplification</div>
    $$\alpha_{\mathrm{committee}}(s) \;\ge\; 1-(1-\alpha_0)^{\lfloor k/|P_N|\rfloor} \;\ge\; 1-\delta_{\mathrm{prop}}$$
  </div>

  <p>The local committee error then splits cleanly into two failure modes — there was no good proposal, or a bad proposal survived the critics and won the comparison:</p>

  <div class="math-display">
    <div class="math-label">Theorem 2 &middot; local error decomposition</div>
    $$\varepsilon_{\mathrm{loc}}(s) \;\le\; \underbrace{\varepsilon_{\mathrm{prop}}(k;s)}_{\text{no good proposal}} \;+\; \underbrace{k^{2}\,e^{-\beta m - 2r\sigma^{2}}}_{\text{bad proposal survives \& wins}}$$
  </div>

  <p>The proposal term shrinks geometrically in the number of proposals, $\varepsilon_{\mathrm{prop}}(k;s) \le (1-\alpha)^k \le e^{-\alpha k}$. The identification term shrinks exponentially in the critic budget $m$ and comparator budget $r$. Because each progressing-sound action strictly decreases the rank, a trajectory has at most $L_x$ steps, and the errors simply add up along it. Combined with the blind-spot split from Part IV, the global failure bound is:</p>

  <div class="eq-highlight">
    $$\mathrm{err}_x(k,m,r) \;\le\; L_x\Big[\,\underbrace{B}_{\text{blind spots}} + \underbrace{R_k}_{\text{finite sampling}} + \underbrace{k^{2}e^{-\beta m - 2r\sigma^{2}}}_{\text{identifiability}}\,\Big]$$
  </div>

  <p>Three knobs, three terms. The simulator below lets you turn them. Notice what happens: with enough proposals, critic calls, and comparator votes, the sampling and identifiability terms collapse — and the only thing left is the blind-spot floor $B$, which none of these knobs can touch.</p>

  <div class="explorer fade-in" id="amp-sim">
    <div class="explorer-header">
      <span class="explorer-title">Amplification simulator</span>
      <span class="explorer-subtitle">— watch the three error terms respond to the committee budget</span>
    </div>
    <div class="explorer-body">
      <div class="bd-controls">
        <div class="bd-ctrl"><label>proposals <span>k</span> <b><span id="s-k-val">10</span></b></label><input type="range" id="s-k" min="1" max="16" step="1" value="10" oninput="simRender()"></div>
        <div class="bd-ctrl"><label>critic calls <span>m</span> <b><span id="s-m-val">8</span></b></label><input type="range" id="s-m" min="0" max="10" step="1" value="8" oninput="simRender()"></div>
        <div class="bd-ctrl"><label>comparator votes <span>r</span> <b><span id="s-r-val">8</span></b></label><input type="range" id="s-r" min="0" max="10" step="1" value="8" oninput="simRender()"></div>
        <div class="bd-ctrl"><label>coverage/call <span>α</span> <b><span id="s-a-val">0.35</span></b></label><input type="range" id="s-a" min="0.05" max="0.6" step="0.01" value="0.35" oninput="simRender()"></div>
        <div class="bd-ctrl"><label>critic edge <span>β</span> <b><span id="s-b-val">0.80</span></b></label><input type="range" id="s-b" min="0.1" max="0.95" step="0.01" value="0.80" oninput="simRender()"></div>
        <div class="bd-ctrl"><label>comparator edge <span>σ</span> <b><span id="s-sig-val">0.35</span></b></label><input type="range" id="s-sig" min="0.05" max="0.45" step="0.01" value="0.35" oninput="simRender()"></div>
        <div class="bd-ctrl"><label>blind-spot mass <span>B</span> <b><span id="s-bs-val">0.04</span></b></label><input type="range" id="s-bs" min="0" max="0.3" step="0.01" value="0.04" oninput="simRender()"></div>
      </div>

      <div class="bd-bars">
        <div class="bd-bar-row"><div class="bd-bar-label">B — blind spots</div><div class="bd-bar-track"><div class="bd-bar-fill" id="s-bar-B" style="background:var(--red)"></div></div><div class="bd-bar-val" id="s-val-B"></div></div>
        <div class="bd-bar-row"><div class="bd-bar-label">R_k — finite sampling</div><div class="bd-bar-track"><div class="bd-bar-fill" id="s-bar-R" style="background:var(--amber)"></div></div><div class="bd-bar-val" id="s-val-R"></div></div>
        <div class="bd-bar-row"><div class="bd-bar-label">identifiability error</div><div class="bd-bar-track"><div class="bd-bar-fill" id="s-bar-I" style="background:var(--accent)"></div></div><div class="bd-bar-val" id="s-val-I"></div></div>
      </div>

      <div class="bd-result" id="s-result"></div>
    </div>
  </div>

  <p class="figcaption"><strong>Fig. 2.</strong> Illustrative model: the sampling residual is taken as $R_k=(1-B)(1-\alpha)^k$ and the local error as the sum of the three terms (each clamped to $[0,1]$); global success is shown as the per-step product $(1-\varepsilon_{\mathrm{loc}})^{L}$ with $L=3$. The identifiability term is an upper bound and can exceed $1$ when $m$ or $r$ are too small — that is the bound going vacuous, signalling you need more critic or comparator votes.</p>

  <hr>

  <h2>Part IV — The blind-spot ceiling</h2>

  <p>The proposal failure term hides something important. Suppose that, conditional on a latent slice $Z$ of the task, each proposal is sound with probability $q_s(Z)$. Then the chance no proposal is sound factorizes:</p>

  <div class="math-display">
    <div class="math-label">Lemma 2 &middot; oracle miss splits into a floor plus a residual</div>
    $$\varepsilon_{\mathrm{prop}}(k;s) = \mathbb{E}\big[(1-q_s(Z))^k\big] = \underbrace{B_s}_{\;\mathbb{P}(q_s(Z)=0)\;} + \;R_k(s)$$
  </div>

  <p>As you sample more ($k\to\infty$), the residual $R_k(s)$ vanishes, but the floor $B_s$ — the mass of task slices where the proposer assigns <em>zero</em> probability to any sound move — does not. No amount of sampling, critiquing, or comparing can recover a move that was never proposed. This is the formal boostable-capability ceiling: with a perfect oracle selector, best-of-$k$ converges only to $1-B$.</p>

  <div class="finding-green">
    <div class="finding-label">Why this changes evaluation</div>
    <strong>pass@1</strong> measures one-shot capability. <strong>Oracle best-of-$k$</strong> measures the capability latent in the proposal pool under perfect selection. The gap between them diagnoses <em>selection</em>; the gap between oracle best-of-$k$ and a stronger model reflects <em>generation</em> and shared blind spots. A single accuracy number conflates all three.
  </div>

  <p>This motivates a recovery metric: of the gap that oracle selection exposes, how much does the real harness actually recover?</p>

  <div class="math-display">
    <div class="math-label">Oracle-gap recovery</div>
    $$\mathrm{Rec}(k,m,r;P) = \frac{p_{\mathrm{system}} - p_1}{p_{\mathrm{oracle}} - p_1}$$
  </div>

  <p>An average coverage condition can quietly hide blind spots: you can have $\mathbb{E}[q_s(Z)] > 0$ overall while $q_s(Z) = 0$ on a whole subpopulation. Lowering the floor is not a sampling problem — it requires changing the proposal system itself: the model, the prompts, the tools, retrieval, decomposition, or genuine proposer <em>diversity</em>.</p>

  <hr>

  <h2>Part V — Weak to frontier, on SWE-bench Verified</h2>

  <p>The empirical centerpiece puts the theory to work. Using a single weak model, <code>GPT-5.4 nano</code>, the critic&ndash;comparator orchestration climbs from a weak one-shot baseline to the level of substantially stronger standalone models — and lands just short of the oracle ceiling.</p>

  <div class="bar-chart fade-in">
    <div class="bar-chart-title">SWE-bench Verified — resolve rate (k = 8 proposals)</div>
    <div class="bar-row">
      <div class="bar-label">GPT-5.4 nano (1 proposal)</div>
      <div class="bar-track"><div class="bar-fill" style="width:67%;background:var(--muted-lt)"><span class="bar-value">67.0%</span></div></div>
    </div>
    <div class="bar-row">
      <div class="bar-label">nano + orchestration</div>
      <div class="bar-track"><div class="bar-fill" style="width:76.4%;background:var(--teal)"><span class="bar-value">76.4%</span></div></div>
    </div>
    <div class="bar-row">
      <div class="bar-label">oracle best-of-8 (ceiling)</div>
      <div class="bar-track"><div class="bar-fill" style="width:79%;background:var(--accent)"><span class="bar-value">79.0%</span></div></div>
    </div>
  </div>

  <p class="figcaption"><strong>Fig. 3.</strong> The orchestrated nano committee at 76.4% matches standalone Gemini 3 Pro and Claude Opus 4.5 Thinking, and exceeds GPT-5.4 mini. The oracle best-of-8 curve at 79.0% shows correct patches are usually already in the nano pool; the remaining 2.6 points is a pure selection gap.</p>

  <div class="stat-strip fade-in">
    <div class="stat">
      <div class="stat-num gold">+12.0</div>
      <div class="stat-lbl">points of latent capability<br>exposed by 8 proposals (67.0 → 79.0)</div>
    </div>
    <div class="stat">
      <div class="stat-num teal">+9.4</div>
      <div class="stat-lbl">points the harness actually<br>recovers (67.0 → 76.4)</div>
    </div>
    <div class="stat">
      <div class="stat-num">≈78%</div>
      <div class="stat-lbl">of the oracle gap recovered<br>by the real selector</div>
    </div>
  </div>

  <p>The ablations trace the mechanism term by term. Increasing proposer <em>diversity</em> exposes latent correct patches (coverage). Critics <em>filter</em> flawed candidates (the $\beta$ edge). Comparators <em>rank</em> the plausible survivors (the $\sigma$ edge). And the failures that remain are mostly <strong>proposal-coverage failures</strong> — shared blind spots where no nano proposal contained a hidden-test-passing patch, exactly the irreducible floor $B$ that stronger selection alone cannot close.</p>

  <div class="table-wrap fade-in">
    <table>
      <thead>
        <tr><th>Quantity</th><th class="col-llmpv">What it measures</th><th>On SWE-bench</th></tr>
      </thead>
      <tbody>
        <tr><td>pass@1</td><td class="td-llmpv">one-shot capability of the proposer</td><td>67.0%</td></tr>
        <tr><td>System (k=8)</td><td class="td-llmpv">what the real critic&ndash;comparator harness recovers</td><td class="td-best">76.4%</td></tr>
        <tr><td>Oracle best-of-8</td><td class="td-llmpv">latent capability under perfect selection</td><td>79.0%</td></tr>
        <tr><td>Selection gap</td><td class="td-llmpv">oracle &minus; system (recoverable by better selection)</td><td>2.6 pts</td></tr>
        <tr class="row-all"><td>Blind-spot region</td><td class="td-llmpv">$1 -$ oracle (needs a better proposer)</td><td>21.0%</td></tr>
      </tbody>
    </table>
  </div>

  <hr>

  <h2>What this does and does not say</h2>

  <p>The claim is mechanistic, not magical. A committee of weak calls reaches strong-model performance <em>when</em> two separate resources are present: coverage, so a good move appears, and identifiability, so the system can recognize it. The bridge between them is a local soundness signal — tests, execution, types, proofs, constraints, or a learned reviewer. Take that signal away and Proposition 1 says no amount of sampling rebuilds it.</p>

  <p>The ceiling is equally real. Oracle best-of-$k$ converges to $1-B$, so once the harness is recovering most of the oracle gap, the binding constraint is the proposer's blind spots, not the selector. At that point the productive move is not more votes — it is a more diverse or more capable proposal system. The analysis also relies on a rank function and conditional-independence assumptions for the local decomposition; real trajectories are messier, and the bounds are upper bounds that can be loose.</p>

  <div class="steps">
    <div class="step">
      <div class="step-num purple">✓</div>
      <div class="step-body">
        <div class="step-title">Generation and recognition are different.</div>
        <div class="step-desc">Coverage is amplified by sampling; identifiability must come from a soundness signal. Conflating them is the core mistake the framework corrects.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num teal">✓</div>
      <div class="step-body">
        <div class="step-title">Evaluate by role.</div>
        <div class="step-desc">pass@1, oracle best-of-$k$, and the recovery fraction $\mathrm{Rec}$ tell you whether to fix the proposer or the selector — a single accuracy number cannot.</div>
      </div>
    </div>
  </div>

  <div class="takeaway">
    <h3>Takeaway</h3>
    <p>Agentic systems are <strong>inference-time boosting</strong> for reasoning models: weak proposals supply breadth, local checks supply recognition, and a rank function lets sound steps compose into a solution.</p>
    <p><strong>The local error has three sources</strong> — a blind-spot floor $B$, a finite-sampling residual $R_k$, and an identifiability term $k^2 e^{-\beta m - 2r\sigma^2}$. More proposals shrink the second; more critic and comparator votes shrink the third; nothing shrinks the first.</p>
    <p><strong>Coverage does not imply identifiability.</strong> Reliable amplification needs an additional soundness signal — execution, tests, types, proofs, or constraints — without which selection cannot recover what sampling exposes.</p>
    <p><strong>On SWE-bench Verified</strong>, a committee of weak <code>GPT-5.4 nano</code> calls reaches 76.4%, matching frontier standalone models and recovering about 78% of the 67.0&rarr;79.0 oracle gap. The correct patches were mostly already there; the win was learning to pick them — and the remaining failures point at the proposer's blind spots, not the selector.</p>
  </div>

</article>

<div class="post-footer">
  <p>Published on <a href="https://dlfundamentals.github.io/blog/">Theory/Simplified</a> &nbsp;&middot;&nbsp; Based on Sunkaraneni, Beneventano, Neumarker, Poggio &amp; Galanti — arXiv:2605.14163, 2026</p>
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
    '<strong>Proposers — propose(k).</strong> Sample $k$ candidate next-actions from the proposer harness. Diversity is the lever here: different prompts, temperatures, and tools expose different moves, raising the chance that a progressing-sound action appears somewhere in the pool. This is the <em>coverage</em> resource.',
    '<strong>Critics — critique(m).</strong> Run $m$ independent critic calls on each candidate and discard any candidate rejected even once. A one-sided verifier (tests, types, execution, a proof checker) gives the critic its edge $\\beta$: it never rejects a sound move but catches an unsound one with probability $\\ge\\beta$. This filters locally refutable errors.',
    '<strong>Comparators — compare(r).</strong> Among the survivors, hold pairwise comparisons with $r$ comparator votes each and take the Copeland winner. The comparator edge $\\sigma$ lets the system rank plausible alternatives the critic could not reject outright — recovering the good move when several look acceptable.',
    '<strong>Advance &amp; repeat.</strong> Apply the winning action, move to the next state, and repeat — up to $L$ steps. Because every progressing-sound action strictly decreases the rank $d_x$, sound local steps are guaranteed to compose into a terminal solution within $L$ steps. This is the <em>progress</em> resource.'
  ];
  window.showPipe = function(i){
    root.querySelectorAll('.pipe-step').forEach(function(el){el.classList.remove('active');});
    var s = document.getElementById('ps'+i); if(s) s.classList.add('active');
    var d = document.getElementById('pipe-detail'); if(!d) return;
    d.innerHTML = pipeDetails[i];
    if(typeof renderMathInElement !== 'undefined') renderMathInElement(d,{delimiters:[{left:'$',right:'$',display:false}],throwOnError:false});
  };

  /* ── AMPLIFICATION SIMULATOR ── */
  function fmt(v){ return (v<0.001 && v>0) ? v.toExponential(1) : v.toFixed(3); }

  window.simRender = function(){
    var k = +document.getElementById('s-k').value;
    var m = +document.getElementById('s-m').value;
    var r = +document.getElementById('s-r').value;
    var a = +document.getElementById('s-a').value;
    var b = +document.getElementById('s-b').value;
    var sig = +document.getElementById('s-sig').value;
    var B = +document.getElementById('s-bs').value;
    var L = 3;

    document.getElementById('s-k-val').textContent = k;
    document.getElementById('s-m-val').textContent = m;
    document.getElementById('s-r-val').textContent = r;
    document.getElementById('s-a-val').textContent = a.toFixed(2);
    document.getElementById('s-b-val').textContent = b.toFixed(2);
    document.getElementById('s-sig-val').textContent = sig.toFixed(2);
    document.getElementById('s-bs-val').textContent = B.toFixed(2);

    var Rk  = (1-B) * Math.pow(1-a, k);
    var eid = k*k * Math.exp(-b*m - 2*r*sig*sig);
    var eidShown = Math.min(eid, 1);
    var eloc = Math.min(1, B + Rk + eidShown);
    var success = Math.pow(Math.max(0, 1-eloc), L);

    document.getElementById('s-bar-B').style.width = (B*100).toFixed(1)+'%';
    document.getElementById('s-bar-R').style.width = (Rk*100).toFixed(1)+'%';
    document.getElementById('s-bar-I').style.width = (eidShown*100).toFixed(1)+'%';
    document.getElementById('s-val-B').textContent = fmt(B);
    document.getElementById('s-val-R').textContent = fmt(Rk);
    document.getElementById('s-val-I').textContent = (eid>1 ? '≥1 (vacuous)' : fmt(eid));

    // dominant bottleneck
    var note;
    if(eid > 1){
      note = 'The identifiability bound is <b>vacuous</b> — with this few critic ($m$) or comparator ($r$) votes the analysis cannot certify selection. Add votes and watch it drop.';
    } else {
      var mx = Math.max(B, Rk, eidShown);
      if(mx === B && B > 0){
        note = '<b>Blind spots dominate.</b> The floor $B$ is now the bottleneck — more proposals, critics, or comparators will not help. The only fix is a better or more diverse proposer.';
      } else if(mx === eidShown){
        note = '<b>Identification is the bottleneck.</b> Good moves are in the pool, but selection lets bad ones through — add critic ($m$) or comparator ($r$) votes.';
      } else {
        note = '<b>Coverage sampling is the bottleneck.</b> Sound moves are not appearing often enough — raise the number of proposals $k$ (or the per-call coverage $\\alpha$).';
      }
    }

    document.getElementById('s-result').innerHTML =
      'Local error bound &nbsp;<b>ε_loc ≈ '+fmt(eloc)+'</b>&nbsp; → illustrative global success over '+L+' steps: '+
      '<span class="bd-big">'+(success*100).toFixed(1)+'%</span><br>'+note;

    if(typeof renderMathInElement !== 'undefined') renderMathInElement(document.getElementById('s-result'),{delimiters:[{left:'$',right:'$',display:false}],throwOnError:false});
  };

  /* ── INIT ── */
  showPipe(0);
  window.simRender();

  if('IntersectionObserver' in window){
    var obs=new IntersectionObserver(function(entries){entries.forEach(function(e){if(e.isIntersecting)e.target.classList.add('visible');});},{threshold:0.1});
    root.querySelectorAll('.fade-in').forEach(function(el){obs.observe(el);});
  }
})();
</script>
