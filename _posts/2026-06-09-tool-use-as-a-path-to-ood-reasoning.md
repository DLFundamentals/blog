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
  <div class="hero-eyebrow">Reasoning &middot; Tool Use &middot; Out-of-Distribution Generalization</div>
  <h1>Tool Use Reduces <em>Depth-Induced Collapse</em></h1>
  <p class="hero-subtitle">Force a model through many out-of-distribution reasoning steps, block the usual shortcuts, and standalone systems lose reliable next-step accuracy as the chain grows. Let them write, run, and revise code, and the collapse largely disappears — even small models begin to rival frontier ones.</p>
  <div class="hero-meta">
    <span>By Tomer Galanti</span>
    <span>&middot;</span>
    <span>2026</span>
    <span>&middot;</span>
    <span>15 min read</span>
    <span>&middot;</span>
    <span class="paper-badge">&#9670; arXiv, 2026</span>
  </div>
</div>

<article>

  <h2>Introduction</h2>

  <p class="lead">A lot of optimism about where AI is heading rests on one assumption: that a language model which has learned relationships on in-distribution data can recombine them to solve genuinely new, out-of-distribution problems. The trouble is that this ability is hard to measure cleanly. On many benchmarks, a model can reach the right final answer by leaning on memorized subproblems, redundant cues, or a small slice of the available evidence. That is still interpolation. Real generalization means using <em>all</em> the relevant evidence, step after step, when no shortcut is available.</p>

  <p>There is an elegant way to frame the stakes. The Diligent Learner framework (Shalev-Shwartz et al. 2025) models reasoning as search over partial solutions, where everything hinges on one number: $\gamma$, the probability that the model proposes a useful next step. If $\gamma$ stays bounded away from zero, search can scale to long horizons. If $\gamma$ decays with depth, even a powerful search procedure becomes brittle. That turns a broad question about generalization into a concrete, testable one:</p>

  <div class="callout">
    <strong>The question</strong>
    Do today's language models preserve a non-trivial next-step success probability on hard problems — or do they look reliable mainly when the task can be solved with memorized pieces, redundant cues, or partial information?
  </div>

  <p>To answer it, you need a benchmark where each step has exactly one correct continuation, and that continuation is recoverable only by combining the revealed history with new evidence. This paper builds one from Boolean reconstruction over GF(2), wraps it in a prefix-conditioned sampling oracle that blocks partial-information shortcuts, and measures $\gamma_g$ as a function of depth. The story has four parts:</p>

  <div class="steps">
    <div class="step">
      <div class="step-num red">I</div>
      <div class="step-body">
        <div class="step-title">Benchmarks reward interpolation.</div>
        <div class="step-desc">Final-answer scoring, many valid paths, and redundant cues can reward memorized subproblems rather than sustained stepwise out-of-distribution reasoning.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num teal">II</div>
      <div class="step-body">
        <div class="step-title">A shortcut-proof benchmark.</div>
        <div class="step-desc">A GF(2) reconstruction game where the revealed prefix acts like a key: without it, new evidence is masked to near-noise; with it, the next term is recoverable in polynomial time.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num amber">III</div>
      <div class="step-body">
        <div class="step-title">Standalone LLMs collapse with depth.</div>
        <div class="step-desc">Small standalone models collapse rapidly, and frontier no-tool models still degrade with depth — even though a polynomial-time recovery procedure exists at every step.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num purple">IV</div>
      <div class="step-body">
        <div class="step-title">Tool synthesis is the remedy.</div>
        <div class="step-desc">When models can generate, execute, and iteratively refine code, even small architectures sustain accurate reasoning over long horizons and approach frontier-level behavior.</div>
      </div>
    </div>
  </div>

  <div class="paper-note">
    Based on: &ldquo;Tool Use Reduces Depth-Induced Collapse in OOD Reasoning&rdquo;, arXiv 2026.
  </div>

  <hr>

  <h2>Part I — Why benchmarks reward interpolation</h2>

  <p>Picture training as a cloud of datapoints in an idea space, linked by the relationships a model learns. At inference, the model walks those relationships from a query to an answer. If the answer sits close to the training cloud, the walk is short and familiar — that is <strong>in-distribution</strong> reasoning. If it sits far away, the model has to extend learned relationships into territory it has never seen — <strong>out-of-distribution</strong> reasoning. Many benchmarks do not force that long walk.</p>

  <div class="diagram-wrap fade-in">
    <svg viewBox="0 0 640 270" xmlns="http://www.w3.org/2000/svg" style="width:100%;max-width:640px;display:block;margin:auto">
      <defs>
        <marker id="rel" markerWidth="7" markerHeight="7" refX="6" refY="3.5" orient="auto"><path d="M0,0 L7,3.5 L0,7 Z" fill="#6e48aa"/></marker>
        <marker id="tool" markerWidth="8" markerHeight="8" refX="7" refY="4" orient="auto"><path d="M0,0 L8,4 L0,8 Z" fill="#9a8fb0"/></marker>
      </defs>
      <!-- training cloud -->
      <circle cx="70" cy="70" r="4" fill="#18160f"/><circle cx="120" cy="50" r="4" fill="#18160f"/><circle cx="100" cy="120" r="4" fill="#18160f"/><circle cx="60" cy="160" r="4" fill="#18160f"/><circle cx="150" cy="150" r="4" fill="#18160f"/><circle cx="130" cy="200" r="4" fill="#18160f"/>
      <line x1="74" y1="68" x2="116" y2="52" stroke="#b88" stroke-width="1.2" marker-end="url(#rel)"/>
      <line x1="104" y1="118" x2="146" y2="148" stroke="#8ab" stroke-width="1.2" marker-end="url(#rel)"/>
      <line x1="64" y1="158" x2="96" y2="124" stroke="#ba8" stroke-width="1.2" marker-end="url(#rel)"/>
      <text x="105" y="240" font-family="IBM Plex Mono,monospace" font-size="10" fill="#7a7060" text-anchor="middle">training: datapoints + relationships</text>
      <!-- ID reasoning region -->
      <circle cx="320" cy="105" r="48" fill="none" stroke="#cfc8ba" stroke-width="1" stroke-dasharray="3 3"/>
      <circle cx="320" cy="105" r="30" fill="none" stroke="#cfc8ba" stroke-width="1" stroke-dasharray="3 3"/>
      <circle cx="320" cy="105" r="4" fill="#18160f"/>
      <circle cx="300" cy="95" r="4" fill="none" stroke="#6e48aa" stroke-width="1.4"/>
      <line x1="303" y1="97" x2="316" y2="103" stroke="#6e48aa" stroke-width="1.4" marker-end="url(#rel)"/>
      <text x="320" y="170" font-family="IBM Plex Mono,monospace" font-size="10" fill="#6e48aa" text-anchor="middle">ID reasoning (near data)</text>
      <!-- OOD target -->
      <text x="470" y="60" font-family="IBM Plex Mono,monospace" font-size="14" fill="#8f2a2a" text-anchor="middle">&#10005;</text>
      <text x="500" y="62" font-family="IBM Plex Mono,monospace" font-size="10" fill="#8f2a2a">OOD target</text>
      <!-- tool synthesis arrow -->
      <line x1="346" y1="100" x2="462" y2="64" stroke="#9a8fb0" stroke-width="2.4" stroke-dasharray="1 4" marker-end="url(#tool)"/>
      <text x="404" y="105" font-family="IBM Plex Mono,monospace" font-size="10" fill="#7a7060" text-anchor="middle">tool synthesis</text>
      <text x="404" y="119" font-family="DM Sans,sans-serif" font-size="9.5" fill="#a09880" text-anchor="middle">extends the reach of reasoning</text>
    </svg>
    <p class="diagram-caption">Fig. 1 — In-distribution reasoning stays inside the dashed neighborhood of the training cloud; out-of-distribution reasoning must reach a target far outside it. A synthesized tool (gray arrow) can extend how far the model travels reliably.</p>
  </div>

  <p>The fix is a benchmark in which ignoring either the history or the new data guarantees failure, so a high score can only mean sustained stepwise reasoning. The catch is that unrestricted Boolean-circuit recovery is the wrong object off the shelf: in its usual form, one tries to recover all terms at once from an enormous example set, and even validating arbitrary intermediate circuits can be intractable. The paper therefore restricts to a structured subclass where every stage has a unique correct continuation and every candidate next step can be checked efficiently.</p>

  <hr>

  <h2>Part II — A shortcut-proof benchmark</h2>

  <p>The targets are Boolean functions written in algebraic normal form over GF(2) — XORs of monomials. Each input splits into address bits $a$ and payload bits $v$. The function is a sum of terms, where each address bit gates one fixed-degree payload conjunction:</p>

  <div class="math-display">
    <div class="math-label">Target in algebraic normal form</div>
    $$f(a,v)=\bigoplus_{j=1}^{n} a_j\,M_j(v), \qquad M_j(v)=\prod_{i\in S_j} v_i, \qquad |S_j| = d-1$$
  </div>

  <p>An instance fixes an ordered list of supports $(S_1,\dots,S_n)$. Reasoning becomes an iterative decoding game: at step $g$, the model is handed the already-recovered prefix $P_g=(t_1,\dots,t_g)$ plus a fresh batch of labeled examples $S_g$, and must name the next monomial $t_{g+1}$. Because the instance commits to an order, there is exactly one correct continuation, so step-success is a clean probability:</p>

  <div class="math-display">
    <div class="math-label">Step-success at depth g</div>
    $$\gamma_g \;:=\; \Pr_{(P_g,\,S_g,\,t_{g+1}),\ \hat t\,\sim\,\pi_\theta(\cdot\,|\,P_g,S_g)}\big[\,\hat t = t_{g+1}\,\big]$$
  </div>

  <p>This is the empirical stand-in for the Diligent Learner's $\gamma$. To make sure it measures reasoning rather than shortcut-spotting, the paper separates solvers by what they can see — the full-information <strong>diligent</strong> solver (prefix + data), a <strong>data-only</strong> solver, a <strong>history-only</strong> solver, and a <strong>partial</strong> solver — then engineers the oracle so only the diligent one can succeed reliably:</p>

  <div class="eq-highlight">
    $$\min_g \gamma^{\mathrm{A}}_g \;\ge\; Q \qquad\text{while}\qquad \gamma^{\mathrm{B}}_g,\ \gamma^{\mathrm{C}}_g,\ \gamma^{\mathrm{D}}_g \;\approx\; \frac{1}{\binom{p}{\,d-1}}$$
  </div>

  <h3>The oracle: history as a key</h3>

  <p>Here is the mechanism that blocks the shortcuts. At step $g$, the oracle turns on the target address bit, zeros out all later address bits, flips the prefix address bits like fair coins, and draws a nearly balanced payload. The resulting label splits cleanly in two:</p>

  <div class="math-display">
    <div class="math-label">Label = prefix mask &oplus; next-term signal</div>
    $$y \;=\; \underbrace{\bigoplus_{j=1}^{g} a_j\,M_j(v)}_{\text{prefix obfuscation mask}} \;\oplus\; \underbrace{M_{g+1}(v)}_{\text{next-term signal}}$$
  </div>

  <p>The mask is computable from the prefix, so a diligent solver subtracts it and reads the signal. To a solver without the prefix, the same mask behaves like a high-entropy scrambler. Its edge over a coin flip from any single example decays geometrically in the number of active prefix bits $m$, which is about $g/2$ at depth $g$:</p>

  <div class="eq-highlight">
    $$\Big|\Pr[\,y = b \mid a,v\,]-\tfrac12\Big| \;=\; \tfrac12\,\big|1-2\rho\big|^{\,m(a)}, \qquad \rho=\frac{\binom{w}{d-1}}{\binom{p}{d-1}}$$
  </div>

  <p>Three guarantees fall out of this design, and together they pin the difficulty to depth. Supports are drawn independently, so the prefix says nothing about the next support — <strong>no history-only shortcut</strong>. The Hamming weight is tuned so each monomial fires with probability near one-half — <strong>no statistical-leakage shortcut</strong>. And the mask drives the data-only Bayes advantage toward zero as depth grows — <strong>no data-only shortcut</strong>. The slider below puts that last guarantee in motion.</p>

  <div class="explorer fade-in" id="mask-sim">
    <div class="explorer-header">
      <span class="explorer-title">The masking oracle</span>
      <span class="explorer-subtitle">— without the prefix, the signal vanishes into noise as depth grows</span>
    </div>
    <div class="explorer-body">
      <div class="bd-controls">
        <div class="bd-ctrl"><label>reasoning depth <span>g</span> <b><span id="mask-g-val">15</span></b></label><input type="range" id="mask-g" min="1" max="127" step="1" value="15" oninput="maskRender()"></div>
        <div class="bd-ctrl"><label>monomial firing rate <span>ρ</span> <b><span id="mask-rho-val">0.55</span></b></label><input type="range" id="mask-rho" min="0.30" max="0.55" step="0.01" value="0.55" oninput="maskRender()"></div>
      </div>
      <div class="bd-bars">
        <div class="bd-bar-row"><div class="bd-bar-label">data-only edge over chance</div><div class="bd-bar-track"><div class="bd-bar-fill" id="mask-bar-data" style="background:var(--red)"></div></div><div class="bd-bar-val" id="mask-val-data"></div></div>
        <div class="bd-bar-row"><div class="bd-bar-label">diligent (prefix + data)</div><div class="bd-bar-track"><div class="bd-bar-fill" id="mask-bar-dil" style="background:var(--teal);width:100%"></div></div><div class="bd-bar-val" id="mask-val-dil">recovers signal</div></div>
      </div>
      <div class="bd-result" id="mask-note"></div>
    </div>
  </div>

  <p class="figcaption"><strong>Fig. 2.</strong> The data-only Bayes advantage is $\tfrac12|1-2\rho|^{m}$ with $m\approx g/2$ active mask bits. As depth climbs — or as $\rho$ approaches the balanced $\tfrac12$ — this advantage collapses toward zero, so new evidence alone becomes uninformative. The diligent solver subtracts the prefix mask and recovers the next term from a small batch, independent of depth. Once unmasked, each step is a single Boolean-conjunction recovery: polynomial-time, and not intrinsically harder at larger $g$.</p>

  <hr>

  <h2>Part III — Depth-induced collapse</h2>

  <p>Run real models on this benchmark and a sharp pattern appears: as depth grows, next-step accuracy falls, even though a polynomial-time recovery procedure exists at every step. The information is present; the difficulty is carrying out the prefix-conditioned computation reliably across a long chain. The estimator simulations confirm the benchmark behaves as designed — only the full-information solver sustains high $\gamma_g$, while data-only and partial solvers decay and history-only stays near chance. Then the language models begin to follow the same script.</p>

  <div class="explorer fade-in" id="collapse-sim">
    <div class="explorer-header">
      <span class="explorer-title">Step-success vs depth</span>
      <span class="explorer-subtitle">— drag the depth marker; watch where each regime sits</span>
    </div>
    <div class="explorer-body">
      <div class="bd-controls">
        <div class="bd-ctrl"><label>reasoning depth <span>g</span> <b><span id="col-g-val">31</span></b></label><input type="range" id="col-g" min="1" max="127" step="1" value="31" oninput="collapseRender()"></div>
      </div>
      <div class="cl-svg" id="col-svg"></div>
      <div class="bd-result" id="col-note"></div>
    </div>
  </div>

  <p class="figcaption"><strong>Fig. 3.</strong> Illustrative curves — the <em>shapes</em> match the paper's measured figures (log-scale $\gamma_g$ versus depth), not exact values. Standalone small models fade toward the chance line $\gamma_{\mathrm{triv}}=1/\binom{12}{3}\approx0.45\%$ by moderate depth; frontier no-tool models delay the fall but still degrade; tool-enabled models stay much flatter across the whole range.</p>

  <h3>How much of the prefix does a model actually use?</h3>

  <p>There is a clean way to quantify the collapse. Take the partial-information solver and give it only the first $k$ prefix terms; ask which $k$ would reproduce a given model's observed accuracy at depth $g$. That $k^\star(g)$ is the <strong>effective prefix</strong> — how much history the model behaves as if it integrated. Full integration is the line $k^\star=g$. The paper's linear fits tell the story: without tools, the slopes usually sit below one, so the gap to full integration widens with depth; with tools, the slopes move back toward one and the error rate becomes far less depth-dependent.</p>

  <div class="explorer fade-in" id="kstar-sim">
    <div class="explorer-header">
      <span class="explorer-title">Effective prefix k&#8902;(g)</span>
      <span class="explorer-subtitle">— slope below 1 means the gap to full integration grows with depth</span>
    </div>
    <div class="explorer-body">
      <div class="bd-controls" style="align-items:center">
        <div style="display:flex;gap:6px;flex-wrap:wrap" id="ks-chips">
          <button onclick="ksSet('30bI')" id="ks-30bI" style="font-family:var(--mono);font-size:11px;padding:4px 9px;border:1px solid var(--border);background:var(--bg);border-radius:6px;cursor:pointer;">30B-Instruct</button>
          <button onclick="ksSet('30bT')" id="ks-30bT" style="font-family:var(--mono);font-size:11px;padding:4px 9px;border:1px solid var(--border);background:var(--bg);border-radius:6px;cursor:pointer;">30B-Thinking</button>
          <button onclick="ksSet('4bT')" id="ks-4bT" style="font-family:var(--mono);font-size:11px;padding:4px 9px;border:1px solid var(--border);background:var(--bg);border-radius:6px;cursor:pointer;">4B-Thinking</button>
          <button onclick="ksSet('4bI')" id="ks-4bI" style="font-family:var(--mono);font-size:11px;padding:4px 9px;border:1px solid var(--border);background:var(--bg);border-radius:6px;cursor:pointer;">4B-Instruct</button>
        </div>
        <div class="bd-ctrl" style="min-width:120px;flex:0"><label>use tools <b><span id="ks-tool-lbl">off</span></b></label><input type="range" id="ks-tool" min="0" max="1" step="1" value="0" oninput="ksRender()"></div>
      </div>
      <div class="cl-svg" id="ks-svg"></div>
      <div class="bd-result" id="ks-note"></div>
    </div>
  </div>

  <p class="figcaption"><strong>Fig. 4.</strong> Exact linear fits $k^\star\approx\max(0,\,f g - a)$ from the paper. Without tools, the 30B variants have $f=0.71$–$0.85$, so the shaded gap to the $k^\star=g$ line opens with depth and accuracy drifts toward the random-guess boundary. With tools, slopes land at $0.96$–$1.08$ and the gap stays nearly flat. (4B-Thinking's no-tool slope of $1.04$ is misleading: partial integration scores by luck at small $g$, then accuracy falls off a cliff once full integration becomes necessary.)</p>

  <p>Frontier systems — GPT-5.2 with extended thinking, Claude Opus 4.5 with maximum thinking, and Gemini 3 Pro — change the magnitude but not the qualitative verdict. They start higher and hold on longer, so where a small standalone model is already guessing, a frontier model can still retain real accuracy. But the valid no-tool frontier runs still degrade as depth grows. <strong>Scale delays the collapse; it does not remove the depth dependence.</strong></p>

  <hr>

  <h2>Part IV — Tools change the computational structure</h2>

  <p>Each step of the game demands two different things: inferring the constraint from the prefix and the new examples, then carrying out the GF(2) computation. A standalone model has to do both token by token. As depth grows, the prefix-conditioned computation gets longer and more fragile, and $\gamma_g$ decays. Tool use splits the two jobs apart: the model specifies the computation in code, hands execution to an interpreter, inspects the result, and revises the procedure when it fails.</p>

  <div class="pull-quote">&ldquo;Tools do not merely add capabilities; they move exact computation out of the token stream.&rdquo;</div>

  <p>The effect is dramatic. Given a sandbox to generate, run, and revise code over up to ten iterations, the small Qwen3-2507 models sustain high accuracy out to depths of $g=127$ — approaching the full-information estimator and, in places, rivaling frontier models. And the <em>iteration</em> is what matters: a 4B model handed a single, unrevised code attempt still fails at large depth; its recovery depends on proposing code, observing how it behaves, and repairing it. Externalizing the deterministic computation is the whole point.</p>

  <div class="stat-strip fade-in">
    <div class="stat">
      <div class="stat-num teal">2 ops</div>
      <div class="stat-lbl">each step = infer the constraint, then execute it — tools split these apart</div>
    </div>
    <div class="stat">
      <div class="stat-num gold">g = 127</div>
      <div class="stat-lbl">deep setting where tool-enabled small models still sustain high accuracy</div>
    </div>
    <div class="stat">
      <div class="stat-num">&le; 10</div>
      <div class="stat-lbl">propose–execute–revise cycles; a single un-revised attempt is not enough</div>
    </div>
  </div>

  <p>The same lift appears for frontier models: once they can run and revise code, $\gamma_g$ remains high even at the deepest settings, far above the $0.45\%$ chance line. By moving exact symbolic execution out of the model and into an executable artifact, tool-enabled systems maintain a much more stable step-success probability over long horizons.</p>

  <hr>

  <h2>What this does and does not say</h2>

  <p>The benchmark is deliberately narrow. Symbolic GF(2) reconstruction was chosen precisely because shortcuts can be controlled and the next step is exactly verifiable — which makes the failure mode easy to measure, but does not by itself establish how often the same collapse appears in messier natural-language or interactive tasks where the carried-forward state is less algebraic. The tool-use results were collected in a sandboxed code-execution setting, so the gains come bundled with practical costs in latency, execution infrastructure, and interface reliability. And the frontier evaluation is a smaller diagnostic — a handful of queries per model, depth, and tool setting — rather than the full protocol used for the small models.</p>

  <p>What survives those caveats is a specific, measurable claim. The Diligent Learner framework assumes a non-vanishing next-step probability; on a benchmark built to demand exactly that, standalone models do not maintain it uniformly as depth grows. Small models drift toward the partial-information regime, and frontier models still show depth dependence. Tool synthesis largely restores the missing stability. That points somewhere slightly against the grain: scalable reasoning may depend less on ever-deeper search inside the model, and more on giving models reliable interfaces for building, executing, and revising their own tools.</p>

  <div class="takeaway">
    <h3>Takeaway</h3>
    <p>On a benchmark engineered so that <strong>every step needs all the evidence</strong> and no partial-information shortcut survives, standalone language models suffer depth-induced collapse: next-step accuracy degrades as the reasoning chain grows.</p>
    <p><strong>The information was never missing.</strong> A polynomial-time recovery procedure exists at every depth; the failure is in carrying a lengthening, prefix-conditioned computation reliably through token-by-token reasoning.</p>
    <p><strong>Scale delays, tools restructure.</strong> Frontier models postpone the collapse but still degrade. Models that generate, execute, and iteratively revise code sustain high step-success over long horizons — and small models start to approach frontier-level behavior.</p>
    <p><strong>The role of tools is sharper than "more capabilities."</strong> By externalizing deterministic computation into an artifact the model can inspect and repair, tool use lowers the effective reasoning depth carried internally — and that may be the key difference between brittle extrapolation and stable out-of-distribution reasoning.</p>
  </div>

</article>

<div class="post-footer">
  <p>Published on <a href="https://dlfundamentals.github.io/blog/">Theory/Simplified</a> &nbsp;&middot;&nbsp; Based on &ldquo;Tool Use Reduces Depth-Induced Collapse in OOD Reasoning&rdquo; — NeurIPS 2026 submission</p>
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

  var CHANCE = 1/220; // 1 / C(12,3) for (p,d)=(12,4)

  /* ── MASKING ORACLE ── */
  window.maskRender = function(){
    var g=+document.getElementById('mask-g').value;
    var rho=+document.getElementById('mask-rho').value;
    document.getElementById('mask-g-val').textContent=g;
    document.getElementById('mask-rho-val').textContent=rho.toFixed(2);
    var m=Math.max(0,Math.round(g/2));
    var adv=0.5*Math.pow(Math.abs(1-2*rho),m); // in [0,0.5]
    document.getElementById('mask-bar-data').style.width=(adv/0.5*100).toFixed(2)+'%';
    var advTxt = adv<1e-4 ? adv.toExponential(1) : adv.toFixed(4);
    document.getElementById('mask-val-data').textContent='±'+advTxt;

    var note;
    if(rho>0.52){
      note='At depth <b>g='+g+'</b>, a typical evidence row carries <b>m&#8776;'+m+'</b> active mask bits. With ρ near the balanced ½, a data-only guesser\u2019s edge over a coin flip is just <b>±'+advTxt+'</b> — essentially noise. ';
    } else {
      note='Pushing ρ away from ½ leaks a little signal: the data-only edge rises to <b>±'+advTxt+'</b>. The benchmark tunes the Hamming weight so ρ stays near ½, closing this gap. ';
    }
    note+='A diligent solver subtracts the prefix mask and reads <b>M<sub>g+1</sub>(v)</b> directly, recovering the next term in O(log p) samples — no matter how deep.';
    document.getElementById('mask-note').innerHTML=note;
  };

  /* ── COLLAPSE CURVES ── */
  (function(){
    var W=560,H=300,ml=46,mr=120,mt=18,mb=34;
    function small(g){return Math.max(CHANCE, CHANCE+(0.90-CHANCE)*Math.exp(-g/8));}
    function frontier(g){return Math.max(CHANCE, CHANCE+(0.95-CHANCE)*Math.exp(-g/45));}
    function tools(g){return 0.86+0.025*Math.sin(g/9);}
    function xpos(g){return ml+(Math.log(g)/Math.log(127))*(W-ml-mr);}
    function ypos(v){var t=Math.log10(v)/Math.log10(CHANCE);return mt+Math.min(1,Math.max(0,t))*(H-mt-mb);}
    function path(fn){var s='';for(var i=0;i<=60;i++){var g=Math.pow(127,i/60);if(g<1)g=1;s+=(i?'L':'M')+xpos(g).toFixed(1)+','+ypos(fn(g)).toFixed(1)+' ';}return s;}
    window.collapseRender=function(){
      var g=+document.getElementById('col-g').value;
      document.getElementById('col-g-val').textContent=g;
      var svg='<svg viewBox="0 0 '+W+' '+H+'" xmlns="http://www.w3.org/2000/svg" style="width:100%;max-width:560px">';
      // gridlines
      var ticks=[1,0.1,0.01,CHANCE];var lbl=['1','0.1','0.01','chance'];
      for(var t=0;t<ticks.length;t++){var y=ypos(ticks[t]);svg+='<line x1="'+ml+'" y1="'+y.toFixed(1)+'" x2="'+(W-mr)+'" y2="'+y.toFixed(1)+'" stroke="#e4dfd4" stroke-width="1"/>';svg+='<text x="'+(ml-6)+'" y="'+(y+3).toFixed(1)+'" font-family="IBM Plex Mono,monospace" font-size="9" fill="#a09880" text-anchor="end">'+lbl[t]+'</text>';}
      // x ticks
      var gx=[1,3,7,15,31,63,127];
      for(var i=0;i<gx.length;i++){svg+='<text x="'+xpos(gx[i]).toFixed(1)+'" y="'+(H-mb+16)+'" font-family="IBM Plex Mono,monospace" font-size="9" fill="#a09880" text-anchor="middle">'+gx[i]+'</text>';}
      svg+='<text x="'+((ml+W-mr)/2)+'" y="'+(H-2)+'" font-family="IBM Plex Mono,monospace" font-size="10" fill="#7a7060" text-anchor="middle">reasoning depth g</text>';
      // chance line
      svg+='<line x1="'+ml+'" y1="'+ypos(CHANCE).toFixed(1)+'" x2="'+(W-mr)+'" y2="'+ypos(CHANCE).toFixed(1)+'" stroke="#a09880" stroke-width="1" stroke-dasharray="4 4"/>';
      // curves
      svg+='<path d="'+path(tools)+'" fill="none" stroke="#1a7a5c" stroke-width="2.4"/>';
      svg+='<path d="'+path(frontier)+'" fill="none" stroke="#a06810" stroke-width="2.4"/>';
      svg+='<path d="'+path(small)+'" fill="none" stroke="#8f2a2a" stroke-width="2.4"/>';
      // marker
      var mx=xpos(g);
      svg+='<line x1="'+mx.toFixed(1)+'" y1="'+mt+'" x2="'+mx.toFixed(1)+'" y2="'+(H-mb)+'" stroke="#6e48aa" stroke-width="1" stroke-dasharray="2 3"/>';
      var fns=[[tools,'#1a7a5c'],[frontier,'#a06810'],[small,'#8f2a2a']];
      for(var k=0;k<3;k++){svg+='<circle cx="'+mx.toFixed(1)+'" cy="'+ypos(fns[k][0](g)).toFixed(1)+'" r="3.5" fill="'+fns[k][1]+'"/>';}
      // legend
      var lx=W-mr+10;
      svg+='<rect x="'+lx+'" y="40" width="10" height="3" fill="#1a7a5c"/><text x="'+(lx+14)+'" y="44" font-family="IBM Plex Mono,monospace" font-size="9" fill="#1a7a5c">with tools</text>';
      svg+='<rect x="'+lx+'" y="58" width="10" height="3" fill="#a06810"/><text x="'+(lx+14)+'" y="62" font-family="IBM Plex Mono,monospace" font-size="9" fill="#a06810">frontier, no tool</text>';
      svg+='<rect x="'+lx+'" y="76" width="10" height="3" fill="#8f2a2a"/><text x="'+(lx+14)+'" y="80" font-family="IBM Plex Mono,monospace" font-size="9" fill="#8f2a2a">small, no tool</text>';
      svg+='</svg>';
      document.getElementById('col-svg').innerHTML=svg;
      function pct(v){return (v*100).toFixed(v<0.01?2:1)+'%';}
      var note='At <b>g='+g+'</b>: tool-enabled &#8776; <b style="color:var(--teal)">'+pct(tools(g))+'</b>, frontier no-tool &#8776; <b style="color:var(--amber)">'+pct(frontier(g))+'</b>, small no-tool &#8776; <b style="color:var(--red)">'+pct(small(g))+'</b> (chance '+pct(CHANCE)+'). ';
      if(g>=31) note+='By this depth the standalone curves have largely collapsed, while tool use holds steady.';
      else note+='The standalone gap to tools widens steadily as you drag g rightward.';
      document.getElementById('col-note').innerHTML=note;
    };
  })();

  /* ── EFFECTIVE PREFIX k*(g) ── */
  (function(){
    var COEF={notool:{'30bI':[0.71,2.79],'30bT':[0.85,1.93],'4bT':[1.04,6.96]},
              tool:{'30bI':[0.96,2.73],'30bT':[1.08,3.42],'4bI':[0.96,1.95],'4bT':[1.00,1.00]}};
    var BND={notool:9.5, tool:9.0};
    var NAME={'30bI':'30B-Instruct','30bT':'30B-Thinking','4bT':'4B-Thinking','4bI':'4B-Instruct'};
    var COL={'30bI':'#1e4f7a','30bT':'#1a7a5c','4bT':'#a06810','4bI':'#6e48aa'};
    var W=560,H=300,ml=42,mr=20,mt=18,mb=34,GM=31;
    var model='30bT';
    function xpos(g){return ml+(g/GM)*(W-ml-mr);}
    function ypos(k){return (H-mb)-(k/GM)*(H-mt-mb);}
    function line(fn,col,wd,dash){var s='';for(var g=0;g<=GM;g++){s+=(g?'L':'M')+xpos(g).toFixed(1)+','+ypos(fn(g)).toFixed(1)+' ';}return '<path d="'+s+'" fill="none" stroke="'+col+'" stroke-width="'+wd+'"'+(dash?' stroke-dasharray="'+dash+'"':'')+'/>';}
    window.ksSet=function(m){model=m;ksRender();};
    window.ksRender=function(){
      var tool=+document.getElementById('ks-tool').value;
      var key=tool?'tool':'notool';
      document.getElementById('ks-tool-lbl').textContent=tool?'on':'off';
      // highlight active chip
      ['30bI','30bT','4bT','4bI'].forEach(function(m){
        var b=document.getElementById('ks-'+m);if(!b)return;
        var avail=!!COEF[key][m];
        var on=(m===model);
        b.style.background=on?(COL[m]):'var(--bg)';
        b.style.color=on?'#fff':(avail?'var(--text-soft)':'var(--muted-lt)');
        b.style.borderColor=on?COL[m]:'var(--border)';
        b.style.opacity=avail?'1':'0.5';
      });
      var off=BND[key];
      function bnd(g){return Math.max(0,g-off);}
      function kg(g){return g;}
      var svg='<svg viewBox="0 0 '+W+' '+H+'" xmlns="http://www.w3.org/2000/svg" style="width:100%;max-width:560px">';
      // grid
      for(var t=0;t<=GM;t+=10){svg+='<line x1="'+xpos(t).toFixed(1)+'" y1="'+mt+'" x2="'+xpos(t).toFixed(1)+'" y2="'+(H-mb)+'" stroke="#eee7db" stroke-width="1"/>';svg+='<text x="'+xpos(t).toFixed(1)+'" y="'+(H-mb+15)+'" font-family="IBM Plex Mono,monospace" font-size="9" fill="#a09880" text-anchor="middle">'+t+'</text>';}
      for(var k=0;k<=GM;k+=10){svg+='<text x="'+(ml-6)+'" y="'+(ypos(k)+3).toFixed(1)+'" font-family="IBM Plex Mono,monospace" font-size="9" fill="#a09880" text-anchor="end">'+k+'</text>';}
      svg+='<text x="'+((ml+W-mr)/2)+'" y="'+(H-2)+'" font-family="IBM Plex Mono,monospace" font-size="10" fill="#7a7060" text-anchor="middle">depth g</text>';
      svg+='<text x="12" y="'+((mt+H-mb)/2)+'" font-family="IBM Plex Mono,monospace" font-size="10" fill="#7a7060" text-anchor="middle" transform="rotate(-90 12 '+((mt+H-mb)/2)+')">effective prefix k&#8902;</text>';
      // k=g line
      svg+=line(kg,'#b0a890',1.4,'5 4');
      svg+='<text x="'+(xpos(GM)-2)+'" y="'+(ypos(GM)+12)+'" font-family="IBM Plex Mono,monospace" font-size="9" fill="#8a8068" text-anchor="end">k = g (full)</text>';
      // boundary
      svg+=line(bnd,'#3a3628',1.2,null);
      svg+='<text x="'+xpos(GM)+'" y="'+(ypos(bnd(GM))-5)+'" font-family="IBM Plex Mono,monospace" font-size="8.5" fill="#3a3628" text-anchor="end">random-guess boundary</text>';
      // model fit
      var c=COEF[key][model];
      if(c){
        var f=c[0],a=c[1];
        function ks(g){return Math.max(0,f*g-a);}
        // shaded gap between ks and k=g
        var sh='M';for(var g=0;g<=GM;g++){sh+=xpos(g).toFixed(1)+','+ypos(ks(g)).toFixed(1)+' L';}
        for(var g2=GM;g2>=0;g2--){sh+=xpos(g2).toFixed(1)+','+ypos(kg(g2)).toFixed(1)+' L';}
        sh=sh.slice(0,-1)+'Z';
        svg+='<path d="'+sh+'" fill="'+COL[model]+'" opacity="0.10"/>';
        svg+=line(ks,COL[model],2.6,null);
        var gapEnd=(GM-ks(GM)).toFixed(1);
        svg+='</svg>';
        document.getElementById('ks-svg').innerHTML=svg;
        var note='<b style="color:'+COL[model]+'">'+NAME[model]+'</b>'+(tool?' (with tools)':' (no tools)')+': k&#8902; &#8776; max(0, <b>'+f.toFixed(2)+'</b>g &minus; '+a.toFixed(2)+'). ';
        if(f<0.95) note+='Slope below 1 — by g=31 the model behaves as if it integrated only <b>'+ks(GM).toFixed(0)+'</b> of 31 prefix terms; the gap to full integration keeps growing and accuracy diverges from the optimum.';
        else note+='Slope &#8776; 1 — the effective prefix tracks the true depth (gap of only '+gapEnd+' at g=31), so the error rate is essentially independent of problem depth.';
        if(model==='4bT'&&!tool) note+=' <em>Caveat: this slope is misleading — partial integration scores by luck at small g, then accuracy collapses once full integration is required.</em>';
        document.getElementById('ks-note').innerHTML=note;
      } else {
        svg+='</svg>';
        document.getElementById('ks-svg').innerHTML=svg;
        document.getElementById('ks-note').innerHTML='<b>'+NAME[model]+'</b> without tools is omitted — its accuracy was indistinguishable from chance at every depth, so an effective prefix can\u2019t be identified. Toggle tools on to see its fit.';
      }
    };
  })();

  /* ── INIT ── */
  maskRender(); collapseRender(); ksRender();

  if('IntersectionObserver' in window){
    var obs=new IntersectionObserver(function(entries){entries.forEach(function(e){if(e.isIntersecting)e.target.classList.add('visible');});},{threshold:0.1});
    root.querySelectorAll('.fade-in').forEach(function(el){obs.observe(el);});
  }
})();
</script>
