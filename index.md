---
layout: default
title: DL Fundamentals Lab
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Newsreader:ital,opsz,wght@0,6..72,400;0,6..72,500;1,6..72,400;1,6..72,500&family=DM+Sans:ital,wght@0,400;0,500;0,700;1,400&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<link rel="stylesheet" href="{{ '/assets/css/blog.css' | relative_url }}">

<div class="col" style="padding-top:3rem;padding-bottom:4rem">

{% for post in site.posts %}
<div style="margin-bottom:2.5rem">
  <a href="{{ post.url | relative_url }}" style="text-decoration:none;border:none">
    <h2 style="font-family:'Newsreader',Georgia,serif;font-weight:500;font-size:1.6rem;color:#0a1628;letter-spacing:-0.02em;line-height:1.25;margin:0 0 0.4rem 0;border:none;padding:0;transition:color 0.2s">{{ post.title }}</h2>
  </a>
  <div style="font-family:'DM Sans',sans-serif;font-size:0.82rem;color:#9ca3af;margin-bottom:0.6rem;display:flex;align-items:center;gap:0.75rem;flex-wrap:wrap">
    <span>{{ post.date | date: "%B %-d, %Y" }}</span>
    {% if post.read_time %}<span>&middot;</span><span>{{ post.read_time }}</span>{% endif %}
    <a href="{{ post.url | relative_url }}#comments" style="text-decoration:none;border:none;margin-left:auto" class="post-reactions" data-path="{{ post.url | relative_url }}">
      <svg viewBox="0 0 24 24"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"></path></svg>
      <span class="comment-count"></span>
    </a>
  </div>
  <p style="font-family:'Newsreader',Georgia,serif;font-size:1rem;color:#6b7280;line-height:1.65;margin:0">
    {{ post.excerpt | strip_html | truncatewords: 40 }}
  </p>
</div>
{% unless forloop.last %}<hr style="border:none;height:1px;background:#f1f3f5;margin:0 0 2.5rem 0">{% endunless %}
{% endfor %}

</div>
