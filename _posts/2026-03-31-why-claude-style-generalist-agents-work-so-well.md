<link rel="preconnect" href="https://fonts.googleapis.com" crossorigin>
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Lora:ital,wght@0,400;0,500;0,600;1,400;1,500&family=IBM+Plex+Mono:wght@400;500&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&display=swap" rel="stylesheet">

<style>
.ps{--bg:#f6f3ee;--bg-warm:#f0ece4;--surface:#ede9e0;--surface-2:#e8e3d8;--border:#d8d2c6;--border-lt:#e4dfd4;--text:#18160f;--text-soft:#3a3628;--muted:#7a7060;--muted-lt:#a09880;--accent:#1e4f7a;--accent-mid:#2a6199;--accent-soft:#d4e6f5;--accent-xs:#ebf4fc;--gold:#b8860b;--gold-soft:#fdf4d8;--gold-bd:#d4a820;--green:#2a6645;--green-soft:#e4f0ea;--red:#8f2a2a;--red-soft:#f5e8e8;--teal:#1a7a5c;--teal-soft:#e4f2ec;--amber:#a06810;--amber-soft:#faf0da;--serif:'Lora',Georgia,serif;--sans:'DM Sans',-apple-system,sans-serif;--mono:'IBM Plex Mono',monospace;}
.ps,.ps *,.ps *::before,.ps *::after{box-sizing:border-box;}
.ps{width:100%;max-width:100%;background:var(--bg);color:var(--text);font-family:var(--sans);font-weight:300;font-size:17px;line-height:1.78;-webkit-font-smoothing:antialiased;overflow-x:clip;}
.ps ::selection{background:var(--accent-soft);color:var(--text);}
.ps a{color:var(--accent-mid);text-decoration:none;}
.ps a:hover{text-decoration:underline;}

/* ── TOP BAR ── */
.ps .top-bar{height:3px;background:linear-gradient(90deg,#1e4f7a 0%,#2a6199 55%,#b8860b 100%);}

/* ── HERO ── */
.ps .hero{max-width:820px;margin:0 auto;padding:3.5rem 2.5rem 2.5rem;border-bottom:1px solid var(--border);}
.ps .hero-eyebrow{font-family:var(--mono);font-size:10.5px;font-weight:500;letter-spacing:.12em;text-transform:uppercase;color:var(--muted);margin-bottom:1.1rem;display:flex;align-items:center;gap:.5rem;}
.ps .hero-eyebrow::before{content:'';display:inline-block;width:18px;height:2px;background:var(--gold);flex-shrink:0;}
.ps .hero h1{font-family:var(--serif);font-size:clamp(1.9rem,4.5vw,2.9rem);font-weight:600;line-height:1.13;letter-spacing:-.025em;color:var(--text);margin:0 0 1.3rem;max-width:680px;}
.ps .hero h1 em{font-style:italic;font-weight:400;color:var(--accent);}
.ps .hero-subtitle{font-size:1.08rem;color:var(--muted);font-style:italic;font-weight:300;max-width:600px;line-height:1.68;border-left:2px solid var(--border);padding-left:1.1rem;margin:0 0 1.6rem;}
.ps .hero-meta{font-family:var(--mono);font-size:11px;color:var(--muted-lt);display:flex;gap:1.25rem;flex-wrap:wrap;align-items:center;}
.ps .verified-badge{display:inline-flex;align-items:center;gap:5px;background:var(--green-soft);color:var(--green);border:1px solid #9fd4b4;padding:3px 10px;border-radius:20px;font-weight:500;font-size:10.5px;}

/* ── ARTICLE ── */
.ps article{max-width:820px;margin:0 auto;padding:2.5rem 2.5rem 6rem;}
.ps article p{margin:0 0 1.15rem;font-size:1.02rem;}
.ps article p.lead::first-letter{font-family:var(--serif);font-size:3.6em;font-weight:600;line-height:.75;float:left;margin:.06em .1em 0 0;color:var(--accent);}
.ps article h2{font-family:var(--serif);font-size:1.48rem;font-weight:500;line-height:1.22;letter-spacing:-.01em;margin:2.75rem 0 1rem;padding-top:2rem;border-top:1px solid var(--border);color:var(--text);}
.ps article h2:first-child{border-top:none;padding-top:0;margin-top:0;}
.ps article h3{font-family:var(--mono);font-size:.73rem;font-weight:500;letter-spacing:.1em;text-transform:uppercase;color:var(--muted);margin:2rem 0 .65rem;}
.ps strong{font-weight:500;}
.ps code{font-family:var(--mono);font-size:.85em;background:var(--surface);border:1px solid var(--border-lt);padding:1px 6px;border-radius:3px;color:var(--text-soft);}

/* ── CALLOUT (gold) ── */
.ps .callout{background:var(--gold-soft);border-left:3px solid var(--gold-bd);padding:1.05rem 1.3rem;border-radius:0 7px 7px 0;margin:1.75rem 0;font-size:.98rem;line-height:1.68;color:var(--text-soft);}
.ps .callout strong{display:block;margin-bottom:.3rem;font-weight:500;color:var(--text);}

/* ── SOURCE NOTE (green) ── */
.ps .source-note{font-family:var(--mono);font-size:.76rem;color:var(--teal);background:var(--teal-soft);border:1px solid #9fd4b4;padding:.8rem 1rem .8rem 2.1rem;border-radius:5px;margin:1.1rem 0 1.6rem;line-height:1.7;position:relative;}
.ps .source-note::before{content:"⬢";position:absolute;left:.8rem;top:.82rem;font-size:9px;}
.ps .source-note code{background:rgba(26,122,92,.12);color:#0f5e42;border:none;padding:1px 4px;}

/* ── FINDING (blue) ── */
.ps .finding{background:var(--accent-xs);border:1px solid #c0d9ef;border-left:3px solid var(--accent-mid);border-radius:0 7px 7px 0;padding:1rem 1.3rem;margin:1.6rem 0;font-size:.95rem;color:var(--text-soft);}
.ps .finding-label{font-family:var(--mono);font-size:.68rem;font-weight:500;letter-spacing:.1em;text-transform:uppercase;color:var(--accent);margin-bottom:.4rem;}

/* ── MATH BLOCK ── */
.ps .math-block{text-align:center;font-family:var(--serif);font-style:italic;font-size:1.05rem;color:var(--text-soft);padding:1.35rem 1.75rem;margin:1.6rem 0;background:var(--surface);border:1px solid var(--border);border-radius:8px;letter-spacing:.02em;overflow-x:auto;}

/* ── LOOP VISUALIZATION ── */
.ps .loop-viz{margin:2rem 0;}
.ps .loop-step{display:grid;grid-template-columns:46px 1fr;gap:0 18px;margin-bottom:0;position:relative;cursor:default;}
.ps .loop-step::before{content:'';position:absolute;left:22px;top:46px;bottom:-1px;width:2px;background:var(--border-lt);}
.ps .loop-step:last-child::before{display:none;}
.ps .loop-icon{width:46px;height:46px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-family:var(--mono);font-weight:500;font-size:13px;flex-shrink:0;position:relative;z-index:1;transition:transform .2s;box-shadow:0 1px 6px rgba(0,0,0,.08);}
.ps .loop-step:hover .loop-icon{transform:scale(1.08);}
.ps .loop-content{padding-bottom:1.6rem;min-width:0;}
.ps .loop-tool-tag{font-family:var(--mono);font-size:10px;font-weight:500;letter-spacing:.06em;padding:2px 8px;border-radius:3px;display:inline-block;margin-bottom:5px;text-transform:uppercase;}
.ps .loop-label{font-family:var(--sans);font-weight:500;font-size:15px;color:var(--text);margin-bottom:4px;}
.ps .loop-desc{font-size:13.5px;color:var(--muted);line-height:1.62;font-weight:300;}

/* ── UNCERTAINTY METER ── */
.ps .uncertainty-meter{margin:.85rem 0 0;}
.ps .meter-label{font-family:var(--mono);font-size:10px;color:var(--muted-lt);margin-bottom:5px;display:flex;justify-content:space-between;letter-spacing:.04em;}
.ps .meter-track{height:4px;background:var(--surface-2);border-radius:2px;overflow:hidden;}
.ps .meter-fill{height:100%;border-radius:2px;transition:width .8s cubic-bezier(.4,0,.2,1);}

/* ── STEPS ── */
.ps .steps{margin:1.5rem 0;}
.ps .step{display:flex;gap:1rem;margin-bottom:1.15rem;align-items:flex-start;}
.ps .step-num{background:var(--accent);color:white;width:26px;height:26px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-family:var(--mono);font-size:.7rem;font-weight:500;flex-shrink:0;margin-top:.12rem;box-shadow:0 1px 5px rgba(30,79,122,.22);}
.ps .step-body{flex:1;}
.ps .step-title{font-weight:500;margin-bottom:.12rem;font-size:.97rem;}
.ps .step-desc{font-size:.9rem;color:var(--muted);line-height:1.62;font-weight:300;}

/* ── DIAGRAM WRAP ── */
.ps .diagram-wrap{background:var(--bg-warm);border:1px solid var(--border);border-radius:10px;padding:1.6rem 1.5rem 1.2rem;margin:2rem 0;overflow-x:auto;}
.ps .diagram-caption{font-family:var(--mono);font-size:10.5px;color:var(--muted-lt);margin-top:.85rem;text-align:center;line-height:1.55;}

/* ── PULL QUOTE ── */
.ps .pull-quote{font-family:var(--serif);font-size:1.2rem;font-style:italic;color:var(--accent);border-top:2px solid var(--accent-soft);border-bottom:2px solid var(--accent-soft);padding:1.1rem 0;margin:2rem 0;line-height:1.55;text-align:center;}

/* ── TOOL TABLE ── */
.ps .table-wrap{margin:1.5rem 0;overflow-x:auto;border-radius:8px;border:1px solid var(--border);}
.ps table{width:100%;border-collapse:collapse;font-family:var(--sans);font-size:13px;background:var(--bg-warm);}
.ps table th{text-align:left;font-weight:500;padding:9px 12px;border-bottom:2px solid var(--border);color:var(--muted);font-family:var(--mono);font-size:10px;letter-spacing:.06em;text-transform:uppercase;white-space:nowrap;background:var(--surface);}
.ps table td{padding:7px 12px;border-bottom:1px solid var(--border-lt);vertical-align:top;}
.ps table tr:last-child td{border-bottom:none;}
.ps table td:first-child{font-family:var(--mono);font-size:12px;color:var(--accent);white-space:nowrap;}

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

@media(max-width:700px){.ps .hero,.ps article,.ps .post-footer{padding-left:1.25rem;padding-right:1.25rem;}.ps .hero h1{font-size:1.8rem;}}
</style>

<div class="ps">

<div class="top-bar"></div>

<div class="hero">
  <div class="hero-eyebrow">Agents &middot; LLMs &middot; Claude</div>
  <h1>Why Claude-Style <em>Generalist Agents</em> Work So Well</h1>
  <p class="hero-subtitle">Claude-style agents work because they repeatedly choose the next useful action, execute it through tools, observe the result, and continue. This post explains why — and verifies every claim against real source code.</p>
  <div class="hero-meta">
    <span>By Tomer Galanti</span>
    <span>&middot;</span>
    <span>March 31, 2026</span>
    <span>&middot;</span>
    <span>15 min read</span>
    <span>&middot;</span>
    <span class="verified-badge">&#9670; Source-verified against leaked Claude Code architecture</span>
  </div>
</div>

<article>

  <h2>Introduction</h2>

  <p class="lead">Why do Claude-style generalist agents feel so effective in practice? At first glance, it is tempting to imagine a large hand-written controller somewhere inside the system: first inspect the code, then run tests, then edit the file, then verify, then summarize. But the real picture is both simpler and more interesting.</p>

  <p>A Claude-style agent works by combining a strong language model with a <strong>tool loop</strong>, project context, and runtime structure. The model is not handed a fixed script for each task. Instead, it repeatedly answers a more local question:</p>

  <div class="callout">
    <strong>The core question</strong>
    Given the user request, the current context, and the result of the last action, what is the best next step?
  </div>

  <p>That simple pattern turns out to be surprisingly powerful. This post explains the mechanism concretely — and cross-references every claim against the actual Claude Code source architecture, publicly leaked on March 31, 2026 via a source map file in Anthropic's npm registry.</p>

  <div class="source-note">
    All architectural claims have been verified against the leaked <code>src/</code> directory: ~1,900 TypeScript files, 512K+ lines, built on Bun + React/Ink. Key files: <code>QueryEngine.ts</code> (~46K lines), <code>Tool.ts</code> (~29K lines), <code>context.ts</code>, and the <code>src/tools/</code> directory with ~40 tool implementations.
  </div>

  <p>This post focuses on four ideas:</p>

  <div class="steps">
    <div class="step">
      <div class="step-num">1</div>
      <div class="step-body">
        <div class="step-title">The agent is a loop, not a monolithic planner.</div>
        <div class="step-desc">It repeatedly chooses the next useful action. There is no fixed script per task type.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num">2</div>
      <div class="step-body">
        <div class="step-title">Tools turn reasoning into real operations.</div>
        <div class="step-desc">Reading files, editing code, running commands, and searching the web are executable actions, not metaphors.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num">3</div>
      <div class="step-body">
        <div class="step-title">Context tells the agent what is plausible.</div>
        <div class="step-desc">Project instructions, memory, tool descriptions, and previous outputs all shape what the model does next.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num">4</div>
      <div class="step-body">
        <div class="step-title">Verification makes the loop robust.</div>
        <div class="step-desc">The agent does not need to be right immediately if it can test, observe failure, and recover.</div>
      </div>
    </div>
  </div>

  <hr>

  <h2>A useful mental model</h2>

  <div class="math-block">
    User request &rarr; model chooses next action &rarr; tool runs &rarr; result returns &rarr; model chooses again
  </div>

  <p>This is the core of the agent. The model usually does <em>not</em> write code to implement file reading or shell execution. Instead, it emits a structured request — read this file, search for that pattern, run this command, edit that function — and the runtime executes it. The result returns, and the model continues from the updated state.</p>

  <p>The agent is best understood not as a giant fixed workflow, but as a <strong>repeated decision process over an evolving workspace</strong>.</p>

  <div class="source-note">
    In the source, <code>QueryEngine.ts</code> handles this loop explicitly: streaming API responses, detecting tool-call requests, dispatching to the right tool, collecting results, and feeding them back as context for the next inference pass.
  </div>

  <hr>

  <h2>Part I — The core loop</h2>

  <p>Suppose the user says: <code>Fix the bug in auth.py</code>. A common misconception is that the system has a hard-coded bug-fixing pipeline hidden inside it. In reality, the behavior is a repeated decision: see the context, choose the best next action, execute, observe, repeat. Here is a plausible trajectory — mapped to real tool implementations, with uncertainty dropping at each step:</p>

  <div class="loop-viz fade-in">

    <div class="loop-step">
      <div class="loop-icon" style="background:var(--accent-soft);color:var(--accent);">1</div>
      <div class="loop-content">
        <span class="loop-tool-tag" style="background:var(--accent-soft);color:var(--accent);">FileReadTool</span>
        <div class="loop-label">Read auth.py</div>
        <div class="loop-desc">The request names a file. Reading is the cheapest way to reduce uncertainty. The model does not guess — it looks.</div>
        <div class="uncertainty-meter">
          <div class="meter-label"><span>Uncertainty</span><span>85%</span></div>
          <div class="meter-track"><div class="meter-fill" style="width:85%;background:var(--red);"></div></div>
        </div>
      </div>
    </div>

    <div class="loop-step">
      <div class="loop-icon" style="background:var(--teal-soft);color:var(--teal);">2</div>
      <div class="loop-content">
        <span class="loop-tool-tag" style="background:var(--teal-soft);color:var(--teal);">GrepTool</span>
        <div class="loop-label">Search for related tests</div>
        <div class="loop-desc">Tests reveal intended behavior. The agent uses ripgrep to search for existing coverage before committing to an edit.</div>
        <div class="uncertainty-meter">
          <div class="meter-label"><span>Uncertainty</span><span>65%</span></div>
          <div class="meter-track"><div class="meter-fill" style="width:65%;background:var(--amber);"></div></div>
        </div>
      </div>
    </div>

    <div class="loop-step">
      <div class="loop-icon" style="background:var(--gold-soft);color:var(--gold);">3</div>
      <div class="loop-content">
        <span class="loop-tool-tag" style="background:var(--gold-soft);color:var(--gold);">BashTool</span>
        <div class="loop-label">Run pytest tests/test_auth.py -q</div>
        <div class="loop-desc">Running tests exposes actual behavior, not guessed behavior. The model selects this command from project context — <code>pyproject.toml</code>, CI config, or persistent memory.</div>
        <div class="uncertainty-meter">
          <div class="meter-label"><span>Uncertainty</span><span>40%</span></div>
          <div class="meter-track"><div class="meter-fill" style="width:40%;background:var(--amber);"></div></div>
        </div>
      </div>
    </div>

    <div class="loop-step">
      <div class="loop-icon" style="background:var(--surface-2);color:var(--muted);">4</div>
      <div class="loop-content">
        <span class="loop-tool-tag" style="background:var(--surface-2);color:var(--muted);">Feedback</span>
        <div class="loop-label">Observe the failure</div>
        <div class="loop-desc">The test output narrows "something is wrong" to a specific assertion failure. Errors are information, not dead ends — they make the next step much easier.</div>
        <div class="uncertainty-meter">
          <div class="meter-label"><span>Uncertainty</span><span>20%</span></div>
          <div class="meter-track"><div class="meter-fill" style="width:20%;background:var(--gold);"></div></div>
        </div>
      </div>
    </div>

    <div class="loop-step">
      <div class="loop-icon" style="background:var(--accent-soft);color:var(--accent);">5</div>
      <div class="loop-content">
        <span class="loop-tool-tag" style="background:var(--accent-soft);color:var(--accent);">FileEditTool</span>
        <div class="loop-label">Edit auth.py</div>
        <div class="loop-desc">With the file read, tests found, and failure mode identified, the edit is a narrow, well-informed operation. String replacement — precise, not a wholesale rewrite.</div>
        <div class="uncertainty-meter">
          <div class="meter-label"><span>Uncertainty</span><span>10%</span></div>
          <div class="meter-track"><div class="meter-fill" style="width:10%;background:var(--green);"></div></div>
        </div>
      </div>
    </div>

    <div class="loop-step">
      <div class="loop-icon" style="background:var(--green-soft);color:var(--green);">6</div>
      <div class="loop-content">
        <span class="loop-tool-tag" style="background:var(--green-soft);color:var(--green);">BashTool</span>
        <div class="loop-label">Verify — re-run tests</div>
        <div class="loop-desc">The loop closes. If tests pass, confidence rises. If they fail differently, the loop continues. The agent is not powerful because it never errs — it is powerful because it can close the loop between action and feedback.</div>
        <div class="uncertainty-meter">
          <div class="meter-label"><span>Uncertainty</span><span>2%</span></div>
          <div class="meter-track"><div class="meter-fill" style="width:2%;background:var(--green);"></div></div>
        </div>
      </div>
    </div>

  </div>

  <p>Notice what is happening. The agent is not solving the whole task in one shot. It is repeatedly asking: <em>What should I do next, given everything I know right now?</em> Each step reduces uncertainty. That decomposition is one of the main reasons these systems work well.</p>

  <hr>

  <h2>Part II — Why the next-step decomposition works</h2>

  <p>Many real tasks are too large, too uncertain, or too stateful to solve in one forward pass. If the user says "fix the bug in auth.py," the model may not yet know what the bug is, whether tests exist, which test command the repository uses, or whether the file has hidden dependencies. A one-shot answer would force the model to guess too much.</p>

  <p>The agent loop avoids that. Software tasks have a natural causal structure that maps cleanly to discrete tool invocations:</p>

  <!-- Causal structure diagram -->
  <div class="diagram-wrap fade-in">
    <svg viewBox="0 0 600 100" xmlns="http://www.w3.org/2000/svg" style="width:100%;max-width:600px;display:block;margin:auto">
      <defs>
        <marker id="da" markerWidth="6" markerHeight="6" refX="5" refY="3" orient="auto"><path d="M0,0 L6,3 L0,6 Z" fill="#a09880"/></marker>
      </defs>
      <!-- boxes -->
      <rect x="4"   y="20" width="102" height="52" rx="5" fill="#ebf4fc" stroke="#b5cfe6" stroke-width="1"/>
      <text x="55"  y="43" font-family="IBM Plex Mono,monospace" font-size="9" fill="#1e4f7a" text-anchor="middle" font-weight="500">Read</text>
      <text x="55"  y="56" font-family="DM Sans,sans-serif" font-size="8.5" fill="#2a6199" text-anchor="middle">FileReadTool</text>
      <text x="55"  y="66" font-family="DM Sans,sans-serif" font-size="8" fill="#7a7060" text-anchor="middle">reduces uncertainty</text>

      <rect x="128" y="20" width="102" height="52" rx="5" fill="#e4f0ea" stroke="#9fd4b4" stroke-width="1"/>
      <text x="179" y="43" font-family="IBM Plex Mono,monospace" font-size="9" fill="#1a7a5c" text-anchor="middle" font-weight="500">Search</text>
      <text x="179" y="56" font-family="DM Sans,sans-serif" font-size="8.5" fill="#2a6645" text-anchor="middle">GrepTool · GlobTool</text>
      <text x="179" y="66" font-family="DM Sans,sans-serif" font-size="8" fill="#7a7060" text-anchor="middle">reveals dependencies</text>

      <rect x="252" y="20" width="102" height="52" rx="5" fill="#fdf4d8" stroke="#d4a820" stroke-width="1"/>
      <text x="303" y="43" font-family="IBM Plex Mono,monospace" font-size="9" fill="#b8860b" text-anchor="middle" font-weight="500">Run</text>
      <text x="303" y="56" font-family="DM Sans,sans-serif" font-size="8.5" fill="#a06810" text-anchor="middle">BashTool</text>
      <text x="303" y="66" font-family="DM Sans,sans-serif" font-size="8" fill="#7a7060" text-anchor="middle">exposes real behavior</text>

      <rect x="376" y="20" width="102" height="52" rx="5" fill="#ebf4fc" stroke="#b5cfe6" stroke-width="1"/>
      <text x="427" y="43" font-family="IBM Plex Mono,monospace" font-size="9" fill="#1e4f7a" text-anchor="middle" font-weight="500">Edit</text>
      <text x="427" y="56" font-family="DM Sans,sans-serif" font-size="8.5" fill="#2a6199" text-anchor="middle">FileEditTool</text>
      <text x="427" y="66" font-family="DM Sans,sans-serif" font-size="8" fill="#7a7060" text-anchor="middle">applies candidate fix</text>

      <rect x="500" y="20" width="96" height="52" rx="5" fill="#e4f0ea" stroke="#9fd4b4" stroke-width="1"/>
      <text x="548" y="43" font-family="IBM Plex Mono,monospace" font-size="9" fill="#1a7a5c" text-anchor="middle" font-weight="500">Verify</text>
      <text x="548" y="56" font-family="DM Sans,sans-serif" font-size="8.5" fill="#2a6645" text-anchor="middle">BashTool</text>
      <text x="548" y="66" font-family="DM Sans,sans-serif" font-size="8" fill="#7a7060" text-anchor="middle">closes the loop</text>

      <!-- arrows -->
      <line x1="108" y1="46" x2="126" y2="46" stroke="#a09880" stroke-width="1.2" marker-end="url(#da)"/>
      <line x1="232" y1="46" x2="250" y2="46" stroke="#a09880" stroke-width="1.2" marker-end="url(#da)"/>
      <line x1="356" y1="46" x2="374" y2="46" stroke="#a09880" stroke-width="1.2" marker-end="url(#da)"/>
      <line x1="480" y1="46" x2="498" y2="46" stroke="#a09880" stroke-width="1.2" marker-end="url(#da)"/>
    </svg>
    <p class="diagram-caption">Fig. 1 — The causal structure of a software task maps cleanly to tool invocations. Each step reduces a different kind of uncertainty.</p>
  </div>

  <hr>

  <h2>Part III — What shapes the next action?</h2>

  <p>Why does the agent decide to read a file before editing it? Why does it run tests? The next action is shaped by four sources of information simultaneously.</p>

  <h3>1. The user request</h3>
  <p>The prompt gives the agent a goal. If the user says "fix the bug," the model has learned that editing without inspection is risky. Reading first is the safer move.</p>

  <h3>2. Tool descriptions</h3>
  <p>The model knows what tools exist and what each does. Tool descriptions are part of the reasoning environment — they help map an abstract intention like "inspect the code" into a concrete action like "invoke <code>FileReadTool</code> on auth.py."</p>

  <div class="source-note">
    In the source, <code>tools.ts</code> serves as the central tool registry, and <code>Tool.ts</code> (~29K lines) defines base types, input schemas, permission models, and progress state types for all tools.
  </div>

  <h3>3. Project context and memory</h3>
  <p>If the project includes instructions — build commands, test commands, conventions, or warnings — the model uses them. Context narrows the space of plausible actions from "everything" to "the sensible things for this codebase."</p>

  <div class="source-note">
    <code>context.ts</code> collects system and user context. The <code>memdir/</code> system provides persistent memory across sessions. The service layer includes <code>extractMemories/</code> for automatic memory extraction and <code>teamMemorySync/</code> for team-level memory synchronization.
  </div>

  <h3>4. The result of the previous action</h3>
  <p>This is what makes the process adaptive. If the agent runs <code>pytest</code> and the output says the repository uses <code>tox</code>, that failure is new information. The next action can be better than the previous one. The agent does not need to know everything at the start — it only needs a good next move and the ability to update.</p>

  <hr>

  <h2>Part IV — The real tool inventory</h2>

  <p>The basic description — read, search, run, edit — captures the essence but understates the full picture. The leaked source reveals roughly 40 discrete tools:</p>

  <div class="table-wrap fade-in">
    <table>
      <thead>
        <tr><th>Tool</th><th>What it does</th></tr>
      </thead>
      <tbody>
        <tr><td>BashTool</td><td>Shell command execution with permission checks</td></tr>
        <tr><td>FileReadTool</td><td>Reads files — images, PDFs, notebooks, plain text</td></tr>
        <tr><td>FileWriteTool</td><td>Creates or overwrites files</td></tr>
        <tr><td>FileEditTool</td><td>Partial modification via string replacement</td></tr>
        <tr><td>GrepTool</td><td>Content search via ripgrep</td></tr>
        <tr><td>GlobTool</td><td>File pattern matching</td></tr>
        <tr><td>WebFetchTool</td><td>Fetches URL content</td></tr>
        <tr><td>WebSearchTool</td><td>Web search</td></tr>
        <tr><td>AgentTool</td><td>Spawns sub-agents for parallel work</td></tr>
        <tr><td>MCPTool</td><td>Model Context Protocol server invocation</td></tr>
        <tr><td>LSPTool</td><td>Language Server Protocol integration</td></tr>
        <tr><td>NotebookEditTool</td><td>Jupyter notebook editing</td></tr>
        <tr><td>SkillTool</td><td>Reusable workflow execution</td></tr>
        <tr><td>EnterPlanModeTool</td><td>Switches to planning mode</td></tr>
        <tr><td>EnterWorktreeTool</td><td>Git worktree isolation</td></tr>
        <tr><td>TeamCreateTool</td><td>Team-level parallel agent management</td></tr>
      </tbody>
    </table>
  </div>

  <p>Several tools — <code>AgentTool</code>, <code>TeamCreateTool</code>, <code>EnterPlanModeTool</code> — reveal capabilities beyond a simple reactive loop. The system can spawn sub-agents, coordinate team-level parallel work, and switch between planning and execution modes. The "next-step" model remains the core, but it operates within a richer infrastructure than the basic description suggests.</p>

  <hr>

  <h2>Part V — Why generalist agents work across tasks</h2>

  <p>A Claude-style agent is often called a <strong>generalist</strong>. That does not mean it knows a perfect workflow for every domain. It means it has one reusable control pattern — understand, choose, execute, observe, repeat — that transfers across tasks.</p>

  <div class="pull-quote">&ldquo;The generalism is not in the tools. It is in the loop.&rdquo;</div>

  <p>Bug fixing, refactoring, writing tests, updating documentation, searching the web for missing information, preparing a pull request summary — the tools change, the local decisions change, but the outer control loop stays nearly the same. The source code confirms this: the same <code>QueryEngine.ts</code> handles every task type.</p>

  <hr>

  <h2>Part VI — The gap between chatbot and agent</h2>

  <p>A plain chatbot without tools must answer from its internal text distribution alone. It can explain what it <em>thinks</em> might be wrong in <code>auth.py</code>, but it cannot inspect your repository, run your tests, or verify the result.</p>

  <p>A tool-using agent is fundamentally different. The gap is not about abstract reasoning ability — it is about the ability to <strong>interact with the environment and correct course using real feedback</strong>.</p>

  <div class="steps">
    <div class="step">
      <div class="step-num" style="background:var(--teal);">✓</div>
      <div class="step-body">
        <div class="step-title">Look instead of guess.</div>
        <div class="step-desc">Read the actual file, search the actual codebase, fetch the actual URL.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num" style="background:var(--teal);">✓</div>
      <div class="step-body">
        <div class="step-title">Test instead of speculate.</div>
        <div class="step-desc">Run the actual command and observe the actual output.</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num" style="background:var(--teal);">✓</div>
      <div class="step-body">
        <div class="step-title">Edit instead of merely suggest.</div>
        <div class="step-desc">Apply a concrete change with <code>FileEditTool</code>, then verify the result.</div>
      </div>
    </div>
  </div>

  <hr>

  <h2>Part VII — What the blog got right, and what it missed</h2>

  <p>Cross-referencing the original post against the leaked source reveals a nuanced picture. The core thesis — that Claude Code operates as a next-step decision loop — is accurate and well-supported. The four sources of action-shaping information all have clear counterparts in the codebase. But the blog describes the runtime as having "a small amount of runtime structure." The reality is 1,900 files and 512K+ lines of TypeScript.</p>

  <p>The blog also omits several significant architectural features:</p>

  <div class="finding">
    <div class="finding-label">Multi-agent coordination</div>
    <code>AgentTool</code> spawns sub-agents. The <code>coordinator/</code> directory handles orchestration. <code>TeamCreateTool</code> enables parallel work across team agents. The system runs multiple loops concurrently.
  </div>

  <div class="finding">
    <div class="finding-label">Permission system</div>
    Every tool invocation passes through a permission check that prompts the user or auto-resolves. This layer sits between "model chooses" and "tool executes" — a critical safety boundary not mentioned in the original post.
  </div>

  <div class="finding">
    <div class="finding-label">Plan mode</div>
    <code>EnterPlanModeTool</code> and <code>ExitPlanModeTool</code> allow the agent to switch between planning and execution modes. The control pattern has more structure than a single undifferentiated loop.
  </div>

  <div class="finding">
    <div class="finding-label">Skills and plugins</div>
    Reusable workflows in <code>skills/</code> and third-party plugins in <code>plugins/</code> extend the agent beyond its built-in tools. Users can add custom skills — making the "generalist" claim even stronger in practice.
  </div>

  <p>These omissions don't invalidate the thesis. They reveal that the "simple" loop is the conceptual core of a much larger system — and that the engineering required to make that loop reliable, safe, and extensible is itself a substantial achievement.</p>

  <div class="takeaway">
    <h3>Takeaway</h3>
    <p>Claude-style generalist agents work because they combine reasoning, action, and feedback in one loop.</p>
    <p><strong>The model chooses the next useful step.</strong> It does not need a full plan from the start. <strong>Tools make the step real</strong> — the agent can read, search, run, edit, and verify through ~40 discrete tool implementations. <strong>Context makes the step grounded</strong> — tool descriptions, project instructions, persistent memory, and previous outputs shape every decision. <strong>Feedback makes the loop robust</strong> — even imperfect choices get corrected when the agent sees real results.</p>
    <p>What looks like mysterious general intelligence is often something more concrete: a system that keeps asking, very effectively, <em>"what is the best next action now?"</em> — backed by 512K lines of engineering to make that question answerable.</p>
  </div>

  <h2>Epilogue</h2>

  <p>Once you see the pattern this way, many apparently sophisticated behaviors become easier to understand. The agent does not need a separate "debugging brain," "refactoring brain," and "documentation brain." It needs a strong enough model to choose sensible local actions, good enough tools to make those actions real, and enough feedback to keep improving its trajectory.</p>

  <p>That is a much simpler recipe than it first appears. It also helps explain why this style of agent has become so influential — not because it solves everything in one shot, but because it usually does the next thing well enough to keep moving forward.</p>

</article>

<div class="post-footer">
  <p>Published on <a href="https://dlfundamentals.github.io/blog/">Theory/Simplified</a> &nbsp;&middot;&nbsp; Source-verified against <a href="https://github.com/nirholas/claude-code">nirholas/claude-code</a></p>
</div>

</div>

<script>
(function(){
  var root = document.querySelector('.ps');
  if(!root) return;
  if('IntersectionObserver' in window){
    var obs = new IntersectionObserver(function(entries){
      entries.forEach(function(e){ if(e.isIntersecting) e.target.classList.add('visible'); });
    },{threshold:0.1});
    root.querySelectorAll('.fade-in').forEach(function(el){ obs.observe(el); });
  }
})();
</script>
