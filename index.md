<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>{% if page.title %}{{ page.title }} | {% endif %}Theory/Simplified</title>
<link href="https://fonts.googleapis.com/css2?family=Newsreader:ital,wght@0,300;0,400;0,500;0,600;1,300;1,400&family=DM+Sans:wght@400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
:root{--ink:#1a1714;--ink-soft:#4a4640;--ink-muted:#8a8680;--cream:#faf8f4;--paper:#ffffff;--rule:#e0dcd6;--accent:#c45028;--accent-soft:#f0e6df;--teal:#1a7a5c;--teal-soft:#e4f2ec;--purple:#5a4ab8;--purple-soft:#eeedfe;--amber:#a06810;--amber-soft:#faf0da;--coral:#d85a30;--serif:'Newsreader',Georgia,serif;--sans:'DM Sans',-apple-system,sans-serif;--mono:'JetBrains Mono',monospace}
*{margin:0;padding:0;box-sizing:border-box}
body{font-family:var(--serif);background:var(--cream);color:var(--ink);line-height:1.72;-webkit-font-smoothing:antialiased}

/* Masthead */
.masthead{max-width:900px;margin:0 auto;padding:2rem 2rem 0}
.logo{display:flex;align-items:center;gap:14px;text-decoration:none;color:var(--ink)}
.logo-mark{width:36px;height:36px;flex-shrink:0}
.logo-mark svg{width:100%;height:100%}
.logo-text{display:flex;flex-direction:column}
.logo-title{font-family:var(--serif);font-size:1.4rem;font-weight:500;letter-spacing:-0.02em;line-height:1.2}
.logo-title span{font-weight:300;color:var(--ink-muted)}
.logo-sub{font-family:var(--sans);font-size:11px;font-weight:500;letter-spacing:1.5px;text-transform:uppercase;color:var(--ink-muted);margin-top:1px}

/* Index hero */
.index-hero{max-width:900px;margin:0 auto;padding:3rem 2rem 2.5rem;border-bottom:1px solid var(--rule)}
.index-hero p{font-size:1.1rem;color:var(--ink-soft);max-width:600px;line-height:1.65}

/* Post list */
.post-list{max-width:900px;margin:0 auto;padding:0 2rem 4rem}
.post-item{display:block;padding:2rem 0;border-bottom:1px solid var(--rule);text-decoration:none;color:var(--ink);transition:background .15s}
.post-item:hover .post-title{color:var(--accent)}
.post-meta{font-family:var(--sans);font-size:12px;color:var(--ink-muted);margin-bottom:.5rem;display:flex;gap:1rem;align-items:center;flex-wrap:wrap}
.post-tag{font-size:11px;padding:2px 8px;border-radius:12px;border:.5px solid var(--rule);color:var(--ink-muted);font-weight:500}
.post-title{font-family:var(--serif);font-size:1.45rem;font-weight:500;line-height:1.3;margin-bottom:.5rem;transition:color .15s}
.post-excerpt{font-size:.98rem;color:var(--ink-soft);line-height:1.6;max-width:640px}

/* Footer */
.index-footer{max-width:900px;margin:0 auto;padding:2rem;text-align:center;border-top:1px solid var(--rule)}
.index-footer p{font-family:var(--sans);font-size:13px;color:var(--ink-muted)}
.index-footer a{color:var(--accent);text-decoration:none}
</style>
</head>
<body>

<div class="masthead">
  <a href="{{ '/' | relative_url }}" class="logo">
    <div class="logo-mark">
      <svg viewBox="0 0 36 36" fill="none" xmlns="http://www.w3.org/2000/svg">
        <rect x="1" y="1" width="34" height="34" rx="8" fill="none" stroke="#1a1714" stroke-width="1.5"/>
        <text x="8" y="14" font-family="Newsreader, Georgia, serif" font-size="10" font-weight="600" fill="#1a1714">T</text>
        <line x1="6" y1="18" x2="30" y2="18" stroke="#e0dcd6" stroke-width="0.75"/>
        <text x="13" y="28" font-family="Newsreader, Georgia, serif" font-size="10" font-weight="300" fill="#8a8680">S</text>
        <circle cx="28" cy="10" r="3" fill="#c45028" opacity="0.85"/>
      </svg>
    </div>
    <div class="logo-text">
      <div class="logo-title">Theory<span>/Simplified</span></div>
      <div class="logo-sub">DL Fundamentals Lab</div>
    </div>
  </a>
</div>

<div class="index-hero">
  <p>Clear, principled explanations of deep learning theory — with interactive visualizations, verified claims, and the math that matters.</p>
</div>

<div class="post-list">
  {% for post in site.posts %}
  <a href="{{ post.url | relative_url }}" class="post-item">
    <div class="post-meta">
      <span>{{ post.date | date: "%B %-d, %Y" }}</span>
      {% for tag in post.tags limit:2 %}
      <span class="post-tag">{{ tag }}</span>
      {% endfor %}
    </div>
    <div class="post-title">{{ post.title }}</div>
    {% if post.excerpt %}
    <div class="post-excerpt">{{ post.excerpt | strip_html | truncate: 200 }}</div>
    {% endif %}
  </a>
  {% endfor %}
</div>

<div class="index-footer">
  <p><a href="{{ '/' | relative_url }}">Theory/Simplified</a> &middot; <a href="https://github.com/DLFundamentals">DL Fundamentals Lab</a></p>
</div>

</body>
</html>
