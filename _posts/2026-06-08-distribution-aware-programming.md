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

/* ── TENSION TABLE ── */
.ps .tension-table{width:100%;border-collapse:collapse;font-family:var(--sans);font-size:13px;margin:1.4rem 0;background:var(--bg-warm);border:1px solid var(--border);border-radius:8px;overflow:hidden;}
.ps .tension-table th{padding:9px 14px;border-bottom:2px solid var(--border);font-weight:500;font-family:var(--mono);font-size:10px;letter-spacing:.06em;text-transform:uppercase;color:var(--muted);text-align:left;background:var(--surface);}
.ps .tension-table td{padding:10px 14px;border-bottom:1px solid var(--border-lt);vertical-align:middle;}
.ps .tension-table tr:last-child td{border-bottom:none;}
.ps .tension-table td:first-child{font-weight:500;color:var(--text);}
.ps .td-red{color:var(--red);}
.ps .td-green{color:var(--teal);}

/* ── STAT STRIP ── */
.ps .stat-strip{display:flex;gap:.75rem;flex-wrap:wrap;margin:1.7rem 0;}
.ps .stat{flex:1;min-width:150px;background:var(--bg-warm);border:1px solid var(--border);border-radius:9px;padding:.95rem 1.05rem;}
.ps .stat-num{font-family:var(--serif);font-size:1.55rem;font-weight:600;color:var(--accent);line-height:1;}
.ps .stat-num.teal{color:var(--teal);}
.ps .stat-lbl{font-family:var(--mono);font-size:10px;color:var(--muted);letter-spacing:.04em;text-transform:uppercase;margin-top:.45rem;line-height:1.45;}

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

/* ── BACKDOOR SIM ── */
.ps .bd-controls{display:flex;flex-wrap:wrap;gap:1.1rem 1.4rem;margin-bottom:1.1rem;}
.ps .bd-ctrl{flex:1;min-width:150px;}
.ps .bd-ctrl label{font-family:var(--mono);font-size:10.5px;color:var(--muted);display:flex;justify-content:space-between;margin-bottom:5px;}
.ps .bd-ctrl label b{color:var(--accent);font-weight:500;}
.ps .bd-ctrl input[type=range]{width:100%;accent-color:var(--accent);cursor:pointer;}
.ps .bd-bars{margin:.4rem 0 1rem;}
.ps .bd-bar-row{display:flex;align-items:center;gap:8px;margin-bottom:8px;}
.ps .bd-bar-label{font-family:var(--mono);font-size:10.5px;width:128px;flex-shrink:0;text-align:right;color:var(--text-soft);}
.ps .bd-bar-track{flex:1;height:20px;background:var(--surface-2);border-radius:3px;overflow:hidden;}
.ps .bd-bar-fill{height:100%;border-radius:3px;transition:width .4s ease;min-width:3px;}
.ps .bd-bar-val{font-family:var(--mono);font-size:10px;font-weight:500;color:var(--muted-lt);min-width:120px;flex-shrink:0;}
.ps .bd-result{background:var(--bg);border:1px solid var(--border-lt);border-radius:7px;padding:.85rem 1rem;font-size:13px;color:var(--text-soft);line-height:1.7;}
.ps .bd-result b{color:var(--accent);font-weight:500;}
.ps .bd-result .bd-big{font-family:var(--serif);font-size:1.15rem;color:var(--teal);font-weight:600;}

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
  <div class="hero-eyebrow">Algorithm Design &middot; Program Synthesis &middot; LLM Agents</div>
  <h1>Distribution-Aware <em>Programming</em></h1>
  <p class="hero-subtitle">A program is usually one fixed recipe meant to work on every possible input. But the inputs you actually run on are not worst-case — they have structure. What if you learned a solver for the distribution you'll really see, and judged it not just by whether it's correct, but by how fast it runs?</p>
  <div class="hero-meta">
    <span>By Tomer Galanti</span>
    <span>&middot;</span>
    <span>June 8, 2026</span>
    <span>&middot;</span>
    <span>15 min read</span>
    <span>&middot;</span>
    <span class="paper-badge">&#9670; Koganti, Mishra, Beneventano, Galanti — 2026</span>
  </div>
</div>

<article>

  <h2>Introduction</h2>

  <p class="lead">Classical learning theory is organized around correctness. A hypothesis is good if it predicts well on fresh draws from the distribution, and generalization is measured by accuracy. But when the object you are learning is an <strong>executable procedure</strong> — an algorithm, a solver, a piece of code — correctness is only half the story.</p>

  <p>Two solvers can both return valid answers on every instance you will ever see, and still be wildly different. One finishes in microseconds; the other grinds for seconds. By the usual accuracy yardstick they are tied. By any honest standard they have not learned equally well. When the learned object is code, the algorithm must generalize not only in <em>quality</em>, but in <em>computation</em>.</p>

  <p>This is the question behind <strong>distribution-aware program learning</strong>: from samples of an unknown deployment distribution, a learner returns solver code that is then evaluated on fresh instances by <em>both</em> solution quality and runtime. The goal is not to solve the ambient problem class in the worst case, but to learn an algorithm whose execution is specialized to the regime you actually operate in.</p>

  <div class="callout">
    <strong>The central claim</strong>
    Samples can improve <em>computation</em>, not just accuracy. The mechanism is a <strong>solver hint</strong> — reusable structure inferred from samples and compiled into specialized solver code — and a pretrained LLM agent can discover and compile these hints automatically.
  </div>

  <p>The story has four parts:</p>

  <div class="steps">
    <div class="step">
      <div class="step-num" style="background:var(--red);">I</div>
      <div class="step-body">
        <div class="step-title">Runtime is part of generalization.</div>
        <div class="step-desc">When the learned object is code, two correct solvers can differ arbitrarily in runtime. Correctness is a feasibility constraint; the real objective is fast, correct computation on the deployment distribution.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num gold">II</div>
      <div class="step-body">
        <div class="step-title">Three ways to design against a distribution.</div>
        <div class="step-desc">Worst-case design assumes nothing about $D$. Average-case complexity assumes an analytic $D$. We study the regime in between: $D$ is accessible only through samples.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num amber">III</div>
      <div class="step-body">
        <div class="step-title">Solver hints make samples actionable.</div>
        <div class="step-desc">The sample-to-solver map factors through a hint: $S \mapsto \widehat h_S \mapsto \widehat c_S = \mathrm{Comp}(\widehat h_S)$. Identifiable hints are recoverable from polynomially many samples and compiled into fast solvers — with a complete fallback for correctness.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num" style="background:var(--accent);">IV</div>
      <div class="step-body">
        <div class="step-title">LLM agents synthesize them.</div>
        <div class="step-desc">Across 21 structured optimization distributions, synthesized solvers reach mean quality 0.971 and run hundreds of times faster than strong heuristics and exact backends — by changing the computational scale.</div>
      </div>
    </div>
  </div>

  <div class="paper-note">
    Based on: S. Koganti, P. Mishra, P. Beneventano, T. Galanti. &ldquo;Distribution-Aware Algorithm Design with LLM Agents&rdquo;, 2026.
  </div>

  <hr>

  <h2>Part I — When you learn code, runtime is part of generalization</h2>

  <h3>&ldquo;Correct on every input&rdquo; means worst-case</h3>

  <p>Asking a program to be correct on <em>all</em> inputs forces us to design for the hardest one — an instance we may never actually encounter. We engineer the procedure for inputs we never see. Yet real workloads are not adversarial: they are drawn from some distribution with exploitable structure. The instances we run on are usually far easier than the worst case, and a procedure tuned to them can be dramatically cheaper.</p>

  <h3>Two students, same answer, different learning</h3>

  <p>A small analogy makes the point. Ask two students to compute $17 \times 24$. Student A computes it as repeated addition — twenty-four copies of seventeen — and reaches $408$. Student B decomposes by place value, $(10+7)(20+4) = 200+40+140+28 = 408$, and reaches the same answer. Both are correct. But only one learned <em>how to compute</em>: repeated addition scales with the magnitude of the numbers, while place-value multiplication scales with the number of digits.</p>

  <div class="finding-green">
    <div class="finding-label">The point of the analogy</div>
    Both students learned <strong>correctness</strong>. Only one learned a <strong>better computation</strong>. If correctness is the only thing we measure, we cannot tell them apart — which is exactly the blind spot of accuracy-only generalization for learned code.
  </div>

  <h3>The objective, made precise</h3>

  <p>Let $\mathrm{V}(x,z)\in\{0,1\}$ say whether $z$ is a valid solution for instance $x$, and let a solver $c$ run in time $\mathrm{T}(c,x)$. We evaluate a solver by its deployment error $\mathrm{Err}_D(c)=\Pr_{x\sim D}[\mathrm{V}(x,c(x))=0]$ and its expected deployment runtime $\mathrm{Run}_D(c)=\mathbb{E}_{x\sim D}[\mathrm{T}(c,x)]$. Correctness is a feasibility constraint: among solvers with $\mathrm{Err}_D(c)=0$, runtime can still vary arbitrarily. The quantity we actually want is the best runtime achievable by a <em>correct</em> solver in the class:</p>

  <div class="eq-highlight">
    $$\mathrm{Run}_D^\star(\mathcal{C}) \;:=\; \inf_{c\in\mathcal{C}\,:\,\mathrm{Err}_D(c)=0}\; \mathrm{Run}_D(c)$$
  </div>

  <p>Unlike worst-case runtime, this depends on $D$. The role of the sample is to discover which fast, correct solver the present $D$ admits.</p>

  <hr>

  <h2>Part II — Three ways to design against a distribution</h2>

  <p>This places the problem cleanly between two classical traditions. Worst-case algorithm design assumes no distributional information at all. Average-case complexity assumes an <em>analytic</em> specification of $D$ before analysis can begin. In practice, deployment distributions rarely come with a closed form — but they do come with examples. We study that intermediate, sample-access regime.</p>

  <div class="diagram-wrap fade-in">
    <svg viewBox="0 0 660 196" xmlns="http://www.w3.org/2000/svg" style="width:100%;max-width:660px;display:block;margin:auto">
      <defs>
        <marker id="da" markerWidth="6" markerHeight="6" refX="5" refY="3" orient="auto"><path d="M0,0 L6,3 L0,6 Z" fill="#a09880"/></marker>
        <marker id="db" markerWidth="6" markerHeight="6" refX="5" refY="3" orient="auto"><path d="M0,0 L6,3 L0,6 Z" fill="#2a6199"/></marker>
      </defs>

      <!-- row labels -->
      <text x="4" y="56" font-family="IBM Plex Mono,monospace" font-size="8.5" fill="#a09880">access to D</text>
      <text x="4" y="104" font-family="IBM Plex Mono,monospace" font-size="8.5" fill="#a09880">learned rep.</text>
      <text x="4" y="158" font-family="IBM Plex Mono,monospace" font-size="8.5" fill="#a09880">deployed solver</text>

      <!-- highlight panel behind column C -->
      <rect x="468" y="14" width="186" height="174" rx="9" fill="#ebf4fc"/>

      <!-- titles -->
      <text x="150" y="26" font-family="DM Sans,sans-serif" font-size="11" font-weight="600" fill="#3a3628" text-anchor="middle">Worst-case</text>
      <text x="350" y="26" font-family="DM Sans,sans-serif" font-size="11" font-weight="600" fill="#3a3628" text-anchor="middle">Average-case</text>
      <text x="561" y="26" font-family="DM Sans,sans-serif" font-size="11" font-weight="600" fill="#1e4f7a" text-anchor="middle">This paper</text>

      <!-- Column A -->
      <rect x="78" y="40" width="144" height="32" rx="5" fill="#ede9e0" stroke="#d8d2c6"/>
      <text x="150" y="60" font-family="DM Sans,sans-serif" font-size="9" fill="#7a7060" text-anchor="middle">none — worst over D</text>
      <line x1="150" y1="72" x2="150" y2="138" stroke="#d8d2c6" marker-end="url(#da)"/>
      <rect x="78" y="140" width="144" height="38" rx="5" fill="#ede9e0" stroke="#d8d2c6"/>
      <text x="150" y="156" font-family="DM Sans,sans-serif" font-size="9" fill="#3a3628" text-anchor="middle">algorithm with</text>
      <text x="150" y="168" font-family="DM Sans,sans-serif" font-size="9" fill="#3a3628" text-anchor="middle">worst-case guarantee</text>

      <!-- Column B -->
      <rect x="278" y="40" width="144" height="32" rx="5" fill="#ede9e0" stroke="#d8d2c6"/>
      <text x="350" y="60" font-family="DM Sans,sans-serif" font-size="9" fill="#7a7060" text-anchor="middle">D specified analytically</text>
      <line x1="350" y1="72" x2="350" y2="138" stroke="#d8d2c6" marker-end="url(#da)"/>
      <rect x="278" y="140" width="144" height="38" rx="5" fill="#ede9e0" stroke="#d8d2c6"/>
      <text x="350" y="163" font-family="DM Sans,sans-serif" font-size="9" fill="#3a3628" text-anchor="middle">algorithm tuned to D</text>

      <!-- Column C -->
      <rect x="489" y="40" width="144" height="30" rx="5" fill="#ffffff" stroke="#7fb0db"/>
      <text x="561" y="59" font-family="IBM Plex Mono,monospace" font-size="9.5" fill="#1e4f7a" text-anchor="middle">sample  S ~ Dⁿ</text>
      <line x1="561" y1="70" x2="561" y2="86" stroke="#2a6199" marker-end="url(#db)"/>
      <rect x="489" y="88" width="144" height="30" rx="5" fill="#d4e6f5" stroke="#2a6199"/>
      <text x="561" y="107" font-family="IBM Plex Mono,monospace" font-size="9.5" fill="#1e4f7a" text-anchor="middle">hint  ĥ_S ∈ H</text>
      <line x1="561" y1="118" x2="561" y2="138" stroke="#2a6199" marker-end="url(#db)"/>
      <rect x="489" y="140" width="144" height="38" rx="5" fill="#ffffff" stroke="#7fb0db"/>
      <text x="561" y="156" font-family="IBM Plex Mono,monospace" font-size="9" fill="#1e4f7a" text-anchor="middle">solver  ĉ_S =</text>
      <text x="561" y="168" font-family="IBM Plex Mono,monospace" font-size="9" fill="#1e4f7a" text-anchor="middle">Comp(ĥ_S)</text>
    </svg>
    <p class="diagram-caption">Fig. 1 — Three access models for designing a solver against a distribution $D$. We study the sample-access regime: infer a hint from $S\sim D^n$, then compile it into a deployed solver. The effective search space becomes the structured subfamily $\mathrm{Comp}(\mathcal{H})\subseteq\mathcal{C}$.</p>
  </div>

  <hr>

  <h2>Part III — Solver hints: sample &rarr; hint &rarr; solver</h2>

  <h3>What a hint is</h3>

  <p>The central abstraction is a <strong>solver hint</strong>: reusable structure inferred from samples and compiled into solver code. The sample-to-solver map factors as</p>

  <div class="eq-highlight">
    $$S \;\longmapsto\; \widehat h_S \;\longmapsto\; \widehat c_S = \mathrm{Comp}(\widehat h_S)$$
  </div>

  <p>A hint might be a backdoor set in SAT, a latent decomposition in a graph problem, an active-resource pattern in packing, or geometric structure in routing. Crucially, <strong>correctness need not be learned</strong>: the compiled solver can always fall back to a generic complete routine. What the sample learns is which <em>shortcut</em> to compile so that future instances are solved faster.</p>

  <div class="pull-quote">&ldquo;A solver hint is not a solution to one instance — it is information that changes the algorithm used for many.&rdquo;</div>

  <h3>The concrete case: hidden SAT backdoors</h3>

  <p>SAT illustrates the mechanism cleanly because correctness never requires learning — a complete solver is always available. The value of learning is purely computational. Suppose there is an unknown <em>backdoor</em> set $B$ of $k$ variables: once you fix the values of those $k$ variables, every clause becomes easy (e.g., Horn), solvable by fast propagation with no further branching. Brute force tries $2^{d}$ assignments over all $d$ variables; if you know $B$, you only enumerate $2^{k}$ settings and let the rest follow.</p>

  <p>The hint is which variables form $B$. If membership in $B$ is identifiable from a bounded salience statistic with margin $\gamma$, then a handful of samples recovers it — and the search collapses. Drag the sliders below to see the effect.</p>

  <div class="explorer fade-in" id="bd-sim">
    <div class="explorer-header">
      <span class="explorer-title">SAT backdoor — search collapse</span>
      <span class="explorer-subtitle">— fix the hint, shrink the search</span>
    </div>
    <div class="explorer-body">
      <div class="bd-controls">
        <div class="bd-ctrl">
          <label>variables <span>d</span> <b><span id="bd-d-val">40</span></b></label>
          <input type="range" id="bd-d" min="8" max="60" step="1" value="40" oninput="bdRender()">
        </div>
        <div class="bd-ctrl">
          <label>backdoor size <span>k</span> <b><span id="bd-k-val">5</span></b></label>
          <input type="range" id="bd-k" min="2" max="12" step="1" value="5" oninput="bdRender()">
        </div>
        <div class="bd-ctrl">
          <label>salience margin <span>γ</span> <b><span id="bd-g-val">0.20</span></b></label>
          <input type="range" id="bd-g" min="0.05" max="0.5" step="0.01" value="0.20" oninput="bdRender()">
        </div>
      </div>

      <div class="bd-bars">
        <div class="bd-bar-row">
          <div class="bd-bar-label">brute force 2<sup>d</sup></div>
          <div class="bd-bar-track"><div class="bd-bar-fill" id="bd-bar-d" style="background:var(--red)"></div></div>
          <div class="bd-bar-val" id="bd-val-d"></div>
        </div>
        <div class="bd-bar-row">
          <div class="bd-bar-label">with hint 2<sup>k</sup></div>
          <div class="bd-bar-track"><div class="bd-bar-fill" id="bd-bar-k" style="background:var(--teal)"></div></div>
          <div class="bd-bar-val" id="bd-val-k"></div>
        </div>
      </div>

      <div class="bd-result" id="bd-result"></div>
    </div>
  </div>

  <p class="figcaption"><strong>Fig. 2.</strong> Fixing the $k$ backdoor variables leaves an easy residual problem, so the solver searches $2^{k}$ cases instead of $2^{d}$. The sample is only needed to <em>identify</em> the backdoor — a cost logarithmic in the number of variables — after which the per-instance speedup is exponential.</p>

  <h3>The guarantees</h3>

  <p>Two results formalize when sample-conditioned design generalizes. First, when the solver library is fixed, runtime-aware empirical risk minimization works: keep the sample-consistent solvers and pick the fastest. With description length $L(c)$, runtime cap $B$, and $m$ samples, the empirically fastest sample-consistent solver $\widehat c$ satisfies, with high probability,</p>

  <div class="math-display">
    <div class="math-label">Correctness &middot; Occam bound</div>
    $$\mathrm{Err}_D(\widehat c) \;\le\; \frac{L(\widehat c) + \log(2/\delta)}{m}$$
  </div>

  <div class="math-display">
    <div class="math-label">Runtime &middot; competitive with any correct solver</div>
    $$\mathrm{Run}_D(\widehat c) \;\le\; \mathrm{Run}_D(c) \;+\; 2B\sqrt{\frac{L(c)+L(\widehat c)+\log(4/\delta)}{2m}}$$
  </div>

  <p>So runtime-aware ERM is not merely picking a solver that looked fast on the sample — it estimates the best correct distribution-specialized solver available in the class. The guarantee is class-relative: it does not promise the right specialization is present, only that if it is, samples can find it.</p>

  <p>Second, when the useful specialization is not enumerated in advance, the learner must <em>recover</em> a hint. If the hints induce score functions separated by a margin $\gamma$, then identifying the true hint among $N$ candidates needs only</p>

  <div class="eq-highlight">
    $$n \;\ge\; \frac{2}{\gamma^2}\,\log\frac{2N}{\delta}\qquad\text{samples}$$
  </div>

  <p>— logarithmic in the number of candidate hints. For the SAT backdoor over $d$ variables, this specializes to $m \ge 8\gamma^{-2}\log(2d/\delta)$ samples to recover $B$ exactly, after which the compiled solver runs in $O(2^{k}\,\mathrm{poly}(|F|))$ on the deployment distribution.</p>

  <div class="callout">
    <strong>The honest caveat</strong>
    The hard part in practice is not estimating a hint for a <em>known</em> score family. It is <em>discovering</em> what the hint should be, what statistic reveals it, and how to compile it into code. That discovery problem is exactly what the LLM agent approximates.
  </div>

  <hr>

  <h2>Part IV — Synthesizing solvers with an LLM agent</h2>

  <p>The synthesis procedure implements the sample&nbsp;&rarr;&nbsp;hint&nbsp;&rarr;&nbsp;solver factorization directly. Each candidate is not a one-shot guess at a solver; it is a triple — a distributional <em>hypothesis</em>, a train-time <em>analysis program</em> that estimates the hint from samples, and a <em>deployment solver</em> conditioned on the recovered hint. Click through the stages:</p>

  <div class="explorer fade-in" id="pipeline">
    <div class="explorer-header">
      <span class="explorer-title">Synthesis pipeline — propose, compile, verify</span>
      <span class="explorer-subtitle">— click each stage for details</span>
    </div>
    <div class="explorer-body">
      <div class="pipeline-steps">
        <div class="pipe-step" style="background:var(--purple-soft);" onclick="showPipe(0)" id="ps0">
          <div class="pipe-step-num" style="color:var(--purple);">Stage 1</div>
          <div class="pipe-step-title" style="color:var(--text);">Hypothesize</div>
          <div class="pipe-step-desc">Guess the reusable structure</div>
        </div>
        <div class="pipe-arrow">&rarr;</div>
        <div class="pipe-step" style="background:var(--accent-xs);" onclick="showPipe(1)" id="ps1">
          <div class="pipe-step-num" style="color:var(--accent);">Stage 2</div>
          <div class="pipe-step-title" style="color:var(--text);">Analyze &rarr; hint</div>
          <div class="pipe-step-desc">Measure it once over the sample</div>
        </div>
        <div class="pipe-arrow">&rarr;</div>
        <div class="pipe-step" style="background:var(--surface);" onclick="showPipe(2)" id="ps2">
          <div class="pipe-step-num" style="color:var(--muted);">Stage 3</div>
          <div class="pipe-step-title" style="color:var(--text);">Compile</div>
          <div class="pipe-step-desc">Write a solver using the hint</div>
        </div>
        <div class="pipe-arrow">&rarr;</div>
        <div class="pipe-step" style="background:var(--teal-soft);" onclick="showPipe(3)" id="ps3">
          <div class="pipe-step-num" style="color:var(--teal);">Stage 4</div>
          <div class="pipe-step-title" style="color:var(--text);">Verify &amp; select</div>
          <div class="pipe-step-desc">Rank on held-out data</div>
        </div>
      </div>
      <div class="pipe-detail" id="pipe-detail">Click a stage above to see details.</div>
    </div>
  </div>

  <p>The key discipline is the separation between train-time inference and deployment. The analysis program may spend computation <em>once</em> on the public sample to estimate the hint $a_c = A_c(S_{\mathrm{tr}})$; the deployed solver then uses that cheap summary on each new instance. This is amortization: pay a one-time synthesis cost against the sample, then deploy a solver whose per-instance cost is much lower.</p>

  <div class="finding">
    <div class="finding-label">The leakage boundary</div>
    The agent sees only public instances, the problem specification, and the scoring rule. It never sees the hidden distribution-family identity, the planted rule, optimum solutions, optimum objective values, or any test performance. This models genuine deployment: you know the problem and the metric, not the generative mechanism.
  </div>

  <hr>

  <h2>Part V — Results</h2>

  <h3>High quality, far lower runtime</h3>

  <p>The benchmark spans 21 structured combinatorial-optimization target distributions across seven problem classes — coloring, MAXSAT, maximum independent set, minimum dominating set, packing LP, multidimensional knapsack, and TSP — each pairing a problem with a hidden distribution family. Aggregated over all 21 targets:</p>

  <div class="stat-strip fade-in">
    <div class="stat">
      <div class="stat-num">0.971</div>
      <div class="stat-lbl">mean normalized quality<br>(1.0 = optimal)</div>
    </div>
    <div class="stat">
      <div class="stat-num">+0.098</div>
      <div class="stat-lbl">quality over the<br>best heuristic</div>
    </div>
    <div class="stat">
      <div class="stat-num teal">336.9&times;</div>
      <div class="stat-lbl">faster than the<br>quality-best heuristic</div>
    </div>
    <div class="stat">
      <div class="stat-num teal">342.8&times;</div>
      <div class="stat-lbl">faster than Gurobi<br>(10s budget)</div>
    </div>
  </div>

  <p>The synthesized solvers also beat the average heuristic pool by $+0.224$ in quality and run $16.1\times$ faster than the selected time-limited exact backend, at a mean per-instance runtime of about $12.8$ ms. Toggle the chart between quality and speedup:</p>

  <div class="bar-chart fade-in">
    <div class="bar-chart-title" id="bars-title">Solution quality (normalized, higher is better)</div>
    <div class="filter-tabs">
      <button class="filter-tab active" onclick="setBars(this,'quality')">Solution quality</button>
      <button class="filter-tab" onclick="setBars(this,'sp_best')">Speedup vs best heuristic</button>
      <button class="filter-tab" onclick="setBars(this,'sp_gur')">Speedup vs Gurobi</button>
    </div>
    <div id="bars-container"></div>
  </div>

  <p class="figcaption"><strong>Fig. 3.</strong> Per-family results. In quality mode, the synthesized solver (teal) is compared against the best heuristic for that family (muted). In speedup modes the bar length is on a log scale; the multiplier is the geometric-mean runtime ratio (above $1\times$ means the synthesized solver is faster).</p>

  <p>The full headline summary:</p>

  <div class="table-wrap fade-in">
    <table>
      <thead>
        <tr>
          <th>Family</th>
          <th class="col-llmpv">Quality</th>
          <th>&Delta;Q vs avg</th>
          <th>&Delta;Q vs best</th>
          <th>Runtime</th>
          <th>vs best heur.</th>
          <th>vs Gurobi</th>
          <th>vs exact</th>
        </tr>
      </thead>
      <tbody>
        <tr><td>Coloring</td><td class="td-llmpv">0.868</td><td class="td-best">+0.217</td><td class="td-best">+0.121</td><td>2.7 ms</td><td>1326.3&times;</td><td>2285.6&times;</td><td>23.1&times;</td></tr>
        <tr><td>MAXSAT</td><td class="td-llmpv td-best">1.000</td><td class="td-best">+0.122</td><td class="td-best">+0.074</td><td>17.1 ms</td><td>217.4&times;</td><td>328.8&times;</td><td>1.0&times;</td></tr>
        <tr><td>MIS</td><td class="td-llmpv">0.992</td><td class="td-best">+0.218</td><td class="td-best">+0.106</td><td>18.8 ms</td><td>530.8&times;</td><td>155.8&times;</td><td>39.7&times;</td></tr>
        <tr><td>MDS</td><td class="td-llmpv">0.973</td><td class="td-best">+0.148</td><td class="td-best">+0.122</td><td>13.3 ms</td><td>718.9&times;</td><td>443.0&times;</td><td>17.4&times;</td></tr>
        <tr><td>Packing LP</td><td class="td-llmpv">0.994</td><td class="td-best">+0.301</td><td class="td-best">+0.259</td><td>3.3 ms</td><td>3004.2&times;</td><td>2829.1&times;</td><td>37.2&times;</td></tr>
        <tr><td>MDKP</td><td class="td-llmpv">0.973</td><td class="td-best">+0.215</td><td class="td-best">+0.009</td><td>94.0 ms</td><td>46.4&times;</td><td>33.8&times;</td><td>12.4&times;</td></tr>
        <tr><td>TSP</td><td class="td-llmpv">0.993</td><td class="td-best">+0.348</td><td class="td-chance">&minus;0.007</td><td>15.3 ms</td><td>32.1&times;</td><td>112.1&times;</td><td>36.6&times;</td></tr>
        <tr class="row-all"><td>All (21)</td><td class="td-llmpv td-best">0.971</td><td class="td-best">+0.224</td><td class="td-best">+0.098</td><td>12.8 ms</td><td>336.9&times;</td><td>342.8&times;</td><td>16.1&times;</td></tr>
      </tbody>
    </table>
  </div>

  <p>The exceptions are informative. On MDKP the solver is faster but trails the quality-best heuristic by a hair, and on TSP it slightly underperforms the best heuristic on quality while still being fast. The method improves the average quality&ndash;runtime frontier; it does not always recover the single cheapest or most accurate specialized procedure.</p>

  <h3>What the agent actually compiled</h3>

  <p>The speedups are not just tighter implementations of the same algorithm. In most cases the selected solver <strong>changes the effective computation</strong>: it replaces an ambient worst-case search or a general-purpose optimizer with a distribution-specific procedure inferred from samples.</p>

  <div class="table-wrap fade-in">
    <table>
      <thead>
        <tr><th>Family &middot; structure</th><th>Ambient computation</th><th>Generated-solver computation</th></tr>
      </thead>
      <tbody>
        <tr><td>MAXSAT &middot; latent Boolean rules</td><td>$O^*(2^v)$</td><td>$O(|F|+R(|F|+B\ell^2\Delta_{\mathrm{occ}}))$</td></tr>
        <tr><td>Coloring &middot; planted palettes</td><td>$O^*(\kappa^n)$</td><td>$O(R(n^2+m+n\kappa)+T_{\mathrm{recolor}})$</td></tr>
        <tr><td>MIS &middot; motif structure</td><td>$O^*(2^n)$</td><td>$O(P(n+m)+T_{\mathrm{local}}+T_{\mathrm{tiny}})$</td></tr>
        <tr><td>MDS &middot; coverage kernels</td><td>$O^*(2^n)$</td><td>$O(n+m+\sum_j c_j 2^{t_j}+T_{\mathrm{prune}})$</td></tr>
        <tr><td>Packing / MDKP &middot; bottlenecks</td><td>$T_{\mathrm{LP}}(N,r,L)$ or $O^*(2^N)$</td><td>$O(P(Nr+N\log N)+T_{\mathrm{repair}})$</td></tr>
        <tr><td>TSP &middot; latent geometry</td><td>$O(n^2 2^n)$</td><td>$O(n^2\log n + B_{\mathrm{tsp}}n^2)$</td></tr>
      </tbody>
    </table>
  </div>

  <p>Coloring becomes template verification plus bounded repair. MAXSAT becomes a distributionally seeded local search. MIS and MDS become greedy construction plus tiny residual enumeration over the few hard pieces. Packing LP becomes density sorting over the active resources instead of a full LP solve. TSP becomes structured candidate generation plus bounded 2-opt rather than exponential tour search. The exponential terms that survive are over tiny residuals — not the whole instance.</p>

  <div class="finding-green">
    <div class="finding-label">The mechanism, confirmed</div>
    Diagnostic traces show the synthesized solvers take a learned fast path on $86.9\%$ of instances on average (and $100\%$ for Packing LP, MDKP, and TSP), with a generic fallback firing on only $3.0\%$. The speedups come from distribution-specific computation, not from quietly calling a backend.
  </div>

  <h3>An external stress test: PACE 2025 Dominating Set</h3>

  <p>To test the procedure outside its own benchmark, the authors evaluate on the released PACE 2025 Dominating Set instances, against highly engineered competition solvers. Trained on the public set and reported on the released private set, the synthesized solver is valid on all 100 graphs and runs about two orders of magnitude faster — at a moderate quality cost.</p>

  <div class="table-wrap fade-in">
    <table>
      <thead>
        <tr><th>Solver</th><th>Valid</th><th>Size vs LLM</th><th>Runtime</th><th>LLM speedup</th></tr>
      </thead>
      <tbody>
        <tr><td>LLM (synthesized)</td><td class="td-best">100/100</td><td>1.000</td><td>2.89 s</td><td class="td-best">1.0&times;</td></tr>
        <tr><td>Fontan&ndash;Verger</td><td>100/100</td><td>1.033</td><td>286.24 s</td><td>98.9&times;</td></tr>
        <tr><td>Root</td><td>100/100</td><td>1.033</td><td>360.42 s</td><td>124.5&times;</td></tr>
        <tr><td>Shadoks</td><td>100/100</td><td>1.032</td><td>316.07 s</td><td>109.2&times;</td></tr>
        <tr><td>AEG Heidelberg</td><td>100/100</td><td>1.034</td><td>350.14 s</td><td>121.0&times;</td></tr>
        <tr><td>Greeduce</td><td>100/100</td><td>1.031</td><td>300.86 s</td><td>104.0&times;</td></tr>
        <tr><td>Swats</td><td class="td-chance">75/100</td><td>1.028&dagger;</td><td>287.61 s&dagger;</td><td>130.3&times;&dagger;</td></tr>
      </tbody>
    </table>
  </div>

  <p class="figcaption"><strong>Fig. 4.</strong> &ldquo;Size vs LLM&rdquo; is the matched total-size ratio; values above $1$ mean the synthesized solver returns a <em>larger</em> (worse) dominating set. The gap is about $3.3\%$ against the top released solvers, while runtime is roughly $99\times$&ndash;$109\times$ lower. &dagger;Computed on the 75 instances Swats solved validly. Not an official PACE score.</p>

  <hr>

  <h2>What this does and does not say</h2>

  <p>This is <strong>not</strong> a claim of new worst-case algorithms for SAT, coloring, knapsack, or TSP. Several of the generated solvers are bounded heuristics with fallback. The faithful claim is distributional and mechanistic: on these deployment distributions, the synthesized programs often replace generic optimization over a large ambient space with a much smaller, distribution-specific computation — and that is exactly the kind of win that accuracy-only generalization cannot see.</p>

  <p>The same lens names the limitations. A one-time synthesis cost only pays off when amortized over enough future instances. The resulting solver is specialized to the sampled regime, so its advantage can degrade under distribution shift — a relabeling perturbation already moves quality on a couple of targets. And because the agent searches a rich program space, different runs may recover different hints, some of them brittle proxies rather than the true structure.</p>

  <div class="steps">
    <div class="step">
      <div class="step-num" style="background:var(--purple);">✓</div>
      <div class="step-body">
        <div class="step-title">The hint encodes the shortcut.</div>
        <div class="step-desc">An analysis program estimates reusable structure from the sample once, producing a compact summary the solver can reuse cheaply per instance.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num" style="background:var(--teal);">✓</div>
      <div class="step-body">
        <div class="step-title">The data verifies.</div>
        <div class="step-desc">Held-out validation selects among candidate hints and solvers by quality, optimality, and runtime. The LLM proposes; execution and validation decide.</div>
      </div>
    </div>
  </div>

  <div class="takeaway">
    <h3>Takeaway</h3>
    <p>When the learned object is code, generalization has two axes — quality <strong>and</strong> computation. Distribution-aware programming targets both.</p>
    <p><strong>Runtime is part of the objective.</strong> Among correct solvers, the sample's job is to find the one whose computation is specialized to the distribution you actually deploy on.</p>
    <p><strong>A solver hint is the unit of reuse.</strong> Identifiable structure can be recovered from $O(\log N / \gamma^2)$ samples and compiled into a fast solver, with a complete fallback keeping every answer correct.</p>
    <p><strong>LLM agents can discover hints.</strong> Across 21 structured distributions, synthesized solvers reach $0.971$ mean quality and run hundreds of times faster than strong heuristics and exact backends — by changing the computational scale, not just the implementation.</p>
    <p>The learned object ends up closer to a specialized algorithm for the deployment regime than to a tuned heuristic for isolated instances.</p>
  </div>

</article>

<div class="post-footer">
  <p>Published on <a href="https://dlfundamentals.github.io/blog/">Theory/Simplified</a> &nbsp;&middot;&nbsp; Based on Koganti, Mishra, Beneventano, Galanti — 2026</p>
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
    '<strong>Stage 1 — Hypothesis.</strong> The agent sees only public instances and the scoring rule — never the hidden family, planted rule, or optimal solutions. It proposes a structured guess: a suspected reusable rule, what evidence to measure for it, the solver strategy it implies, and expected failure modes.',
    '<strong>Stage 2 — Analysis → hint.</strong> A train-time program runs once over the public sample and compresses what it finds into a compact summary $a_c = A_c(S_{\\mathrm{tr}})$. This summary <em>is</em> the empirical solver hint — vertex roles, variable salience, active resources, geometric prototypes, whatever the hypothesis says to look for.',
    '<strong>Stage 3 — Compile.</strong> A deployment solver is written conditioned on the recovered hint. It uses the cheap summary on each new instance and falls back to a generic complete routine when the inferred structure is weak — so correctness is preserved regardless of how good the hint is.',
    '<strong>Stage 4 — Verify &amp; select.</strong> Candidates are executed on held-out validation instances and ranked lexicographically by quality, then optimality, then runtime. A diversity-preserving beam keeps competing explanations alive across refinement rounds; the best candidate over all rounds is deployed.'
  ];

  window.showPipe = function(i){
    root.querySelectorAll('.pipe-step').forEach(function(el){el.classList.remove('active');});
    var s = document.getElementById('ps'+i); if(s) s.classList.add('active');
    var d = document.getElementById('pipe-detail'); if(!d) return;
    d.innerHTML = pipeDetails[i];
    if(typeof renderMathInElement !== 'undefined') renderMathInElement(d,{delimiters:[{left:'$',right:'$',display:false}],throwOnError:false});
  };

  /* ── BACKDOOR SIMULATOR ── */
  function pow2Str(e){
    if(e<=33){ return Math.round(Math.pow(2,e)).toLocaleString('en-US'); }
    var log10 = e*Math.LN2/Math.LN10;
    var mant = Math.pow(10, log10 - Math.floor(log10));
    return mant.toFixed(1)+' × 10<sup>'+Math.floor(log10)+'</sup>';
  }

  window.bdRender = function(){
    var d = parseInt(document.getElementById('bd-d').value,10);
    var k = parseInt(document.getElementById('bd-k').value,10);
    var g = parseFloat(document.getElementById('bd-g').value);
    if(k > d-1){ k = d-1; document.getElementById('bd-k').value = k; }

    document.getElementById('bd-d-val').textContent = d;
    document.getElementById('bd-k-val').textContent = k;
    document.getElementById('bd-g-val').textContent = g.toFixed(2);

    var DMAX = 60;
    document.getElementById('bd-bar-d').style.width = (100*d/DMAX)+'%';
    document.getElementById('bd-bar-k').style.width = (100*k/DMAX)+'%';
    document.getElementById('bd-val-d').innerHTML = pow2Str(d);
    document.getElementById('bd-val-k').innerHTML = pow2Str(k);

    var m = Math.ceil(8/(g*g)*Math.log(2*d/0.05));
    document.getElementById('bd-result').innerHTML =
      'Knowing the backdoor shrinks the search by a factor of <span class="bd-big">2<sup>'+(d-k)+'</sup> ≈ '+pow2Str(d-k)+'×</span>. '+
      'And recovering it is cheap: with margin <b>γ='+g.toFixed(2)+'</b> you need only '+
      '<b>m ≥ ⌈8γ⁻² ln(2d/δ)⌉ = '+m.toLocaleString('en-US')+'</b> samples (δ=0.05) to identify the '+k+' backdoor variables — logarithmic in d.';
  };

  /* ── RESULTS BAR CHART ── */
  var fams = [
    {name:'Coloring',   q:0.868, qbest:0.747, sp_best:1326.3, sp_gur:2285.6},
    {name:'MAXSAT',     q:1.000, qbest:0.926, sp_best:217.4,  sp_gur:328.8},
    {name:'MIS',        q:0.992, qbest:0.886, sp_best:530.8,  sp_gur:155.8},
    {name:'MDS',        q:0.973, qbest:0.851, sp_best:718.9,  sp_gur:443.0},
    {name:'Packing LP', q:0.994, qbest:0.735, sp_best:3004.2, sp_gur:2829.1},
    {name:'MDKP',       q:0.973, qbest:0.964, sp_best:46.4,   sp_gur:33.8},
    {name:'TSP',        q:0.993, qbest:1.000, sp_best:32.1,   sp_gur:112.1}
  ];

  function renderBars(mode){
    var c = document.getElementById('bars-container'); if(!c) return;
    c.innerHTML = '';
    var title = document.getElementById('bars-title');

    if(mode==='quality'){
      if(title) title.textContent='Solution quality (normalized, higher is better)';
      fams.forEach(function(t){
        var r1 = document.createElement('div'); r1.className='bar-row';
        var w1 = (t.q*100).toFixed(1);
        r1.innerHTML = '<div class="bar-label">'+t.name+'</div><div class="bar-track"><div class="bar-fill" style="width:'+w1+'%;background:var(--teal)"><span class="bar-value">'+t.q.toFixed(3)+'</span></div></div>';
        var r2 = document.createElement('div'); r2.className='bar-row'; r2.style.marginBottom='12px';
        var w2 = (t.qbest*100).toFixed(1);
        r2.innerHTML = '<div class="bar-label" style="font-size:9.5px;color:var(--muted-lt);">best heuristic</div><div class="bar-track"><div class="bar-fill" style="width:'+w2+'%;background:var(--muted-lt);opacity:.5"><span class="bar-value">'+t.qbest.toFixed(3)+'</span></div></div>';
        c.appendChild(r1); c.appendChild(r2);
      });
    } else {
      var key = mode==='sp_gur' ? 'sp_gur' : 'sp_best';
      if(title) title.textContent = mode==='sp_gur'
        ? 'Runtime speedup vs Gurobi (log scale, higher is faster)'
        : 'Runtime speedup vs best heuristic (log scale, higher is faster)';
      var maxlog = 3.55; // log10(~3500)
      fams.forEach(function(t){
        var v = t[key];
        var w = Math.max(4, 100*Math.log(v)/Math.LN10/maxlog);
        var col = v>=200 ? 'var(--teal)' : (v>=60 ? 'var(--accent-mid)' : 'var(--amber)');
        var r = document.createElement('div'); r.className='bar-row'; r.style.marginBottom='9px';
        r.innerHTML = '<div class="bar-label">'+t.name+'</div><div class="bar-track"><div class="bar-fill" style="width:'+w.toFixed(1)+'%;background:'+col+'"><span class="bar-value">'+v.toFixed(1)+'×</span></div></div>';
        c.appendChild(r);
      });
    }
  }

  window.setBars = function(btn, mode){
    root.querySelectorAll('.filter-tab').forEach(function(t){t.classList.remove('active');});
    btn.classList.add('active');
    renderBars(mode);
  };

  /* ── INIT ── */
  renderBars('quality');
  window.bdRender();
  showPipe(0);

  if('IntersectionObserver' in window){
    var obs=new IntersectionObserver(function(entries){entries.forEach(function(e){if(e.isIntersecting)e.target.classList.add('visible');});},{threshold:0.1});
    root.querySelectorAll('.fade-in').forEach(function(el){obs.observe(el);});
  }
})();
</script>
