---
layout: null
---
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>Theory/Simplified — DL Fundamentals Lab</title>
<link href="https://fonts.googleapis.com/css2?family=Newsreader:ital,wght@0,300;0,400;0,500;0,600;1,300;1,400&family=DM+Sans:wght@400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
:root{--ink:#1a1714;--ink-soft:#4a4640;--ink-muted:#8a8680;--cream:#faf8f4;--paper:#ffffff;--rule:#e0dcd6;--accent:#c45028;--accent-soft:#f0e6df;--teal:#1a7a5c;--teal-soft:#e4f2ec;--purple:#5a4ab8;--purple-soft:#eeedfe;--amber:#a06810;--amber-soft:#faf0da;--coral:#d85a30;--serif:'Newsreader',Georgia,serif;--sans:'DM Sans',-apple-system,sans-serif;--mono:'JetBrains Mono',monospace}
*{margin:0;padding:0;box-sizing:border-box}
body{font-family:var(--serif);background:var(--cream);color:var(--ink);line-height:1.72;-webkit-font-smoothing:antialiased}

/* Same hero as posts */
.hero{max-width:900px;margin:0 auto;padding:4rem 2rem 3rem;border-bottom:1px solid var(--rule)}
.hero-eyebrow{font-family:var(--sans);font-size:12px;font-weight:600;letter-spacing:2px;text-transform:uppercase;color:var(--accent);margin-bottom:1.25rem}
.hero h1{font-family:var(--serif);font-size:clamp(2rem,5vw,3rem);font-weight:500;line-height:1.2;color:var(--ink);margin-bottom:1.5rem;max-width:700px}
.hero h1 span{font-weight:300;color:var(--ink-muted)}
.hero-subtitle{font-size:1.15rem;color:var(--ink-soft);max-width:600px;line-height:1.65}

/* Same article column as posts */
.content{max-width:680px;margin:0 auto;padding:2.5rem 2rem 5rem}

/* Post entries */
.post-entry{display:block;padding:1.75rem 0;border-bottom:1px solid var(--rule);text-decoration:none;color:var(--ink)}
.post-entry:first-child{padding-top:0}
.post-entry:hover .post-entry-title{color:var(--accent)}
.post-entry-meta{font-family:var(--sans);font-size:13px;color:var(--ink-muted);margin-bottom:.4rem}
.post-entry-title{font-family:var(--serif);font-size:1.35rem;font-weight:500;line-height:1.3;margin-bottom:.4rem;transition:color .15s}
.post-entry-excerpt{font-size:1rem;color:var(--ink-soft);line-height:1.6}
.post-entry-paper{font-family:var(--sans);font-size:12px;color:var(--purple);margin-top:.4rem}

/* Footer — same width as article */
.site-footer{max-width:680px;margin:0 auto;padding:0 2rem 4rem}
.site-footer p{font-family:var(--sans);font-size:13px;color:var(--ink-muted);text-align:center}
.site-footer a{color:var(--accent);text-decoration:none}
</style>
</head>
<body>

<div class="hero">
  <div class="hero-eyebrow">DL Fundamentals Lab</div>
  <h1>Theory<span>/Simplified</span></h1>
  <p class="hero-subtitle">Clear, principled explanations of deep learning theory — with interactive visualizations, verified claims, and the math that matters. By Tomer Galanti.</p>
</div>

<div class="content">
  {% for post in site.posts %}
  <a href="{{ post.url | relative_url }}" class="post-entry">
    <div class="post-entry-meta">{{ post.date | date: "%B %-d, %Y" }}</div>
    <div class="post-entry-title">{{ post.title }}</div>
    {% if post.excerpt %}
    <div class="post-entry-excerpt">{{ post.excerpt | strip_html | truncate: 180 }}</div>
    {% endif %}
  </a>
  {% endfor %}
</div>

<div class="site-footer">
  <p><a href="https://github.com/DLFundamentals">DL Fundamentals Lab</a></p>
</div>

</body>
</html>
