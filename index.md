---
layout: default
---

<style>
@import url('https://fonts.googleapis.com/css2?family=Newsreader:ital,wght@0,300;0,400;0,500;0,600;1,400&family=DM+Sans:wght@400;500;600&display=swap');

/* Override theme header */
.site-header {
  border-top: none;
  border-bottom: 1px solid #e0dcd6;
  background: #fff;
}
.site-title, .site-title:visited {
  font-family: 'Newsreader', Georgia, serif !important;
  font-size: 1.35rem !important;
  font-weight: 500 !important;
  letter-spacing: -0.02em !important;
  color: #1a1714 !important;
}
.site-nav { display: none; }
.page-content { padding: 0; background: #faf8f4; }
.wrapper { max-width: 900px; }

/* Index hero */
.index-hero {
  max-width: 900px;
  margin: 0 auto;
  padding: 3rem 30px 2.5rem;
  border-bottom: 1px solid #e0dcd6;
}
.index-eyebrow {
  font-family: 'DM Sans', sans-serif;
  font-size: 11px;
  font-weight: 500;
  letter-spacing: 1.5px;
  text-transform: uppercase;
  color: #8a8680;
  margin-bottom: 0.75rem;
}
.index-title {
  font-family: 'Newsreader', Georgia, serif;
  font-size: clamp(1.8rem, 4vw, 2.4rem);
  font-weight: 500;
  line-height: 1.2;
  color: #1a1714;
  margin-bottom: 1rem;
}
.index-title span {
  font-weight: 300;
  color: #8a8680;
}
.index-subtitle {
  font-family: 'Newsreader', Georgia, serif;
  font-size: 1.05rem;
  color: #4a4640;
  max-width: 560px;
  line-height: 1.65;
}

/* Post list */
.post-list-styled {
  max-width: 680px;
  margin: 0 auto;
  padding: 0 30px 4rem;
}
.post-entry {
  display: block;
  padding: 1.75rem 0;
  border-bottom: 1px solid #e0dcd6;
  text-decoration: none;
  color: #1a1714;
}
.post-entry:hover .pe-title { color: #c45028; }
.pe-date {
  font-family: 'DM Sans', sans-serif;
  font-size: 13px;
  color: #8a8680;
  margin-bottom: 0.35rem;
}
.pe-title {
  font-family: 'Newsreader', Georgia, serif;
  font-size: 1.3rem;
  font-weight: 500;
  line-height: 1.3;
  margin-bottom: 0.35rem;
  transition: color 0.15s;
}
.pe-excerpt {
  font-family: 'Newsreader', Georgia, serif;
  font-size: 0.98rem;
  color: #4a4640;
  line-height: 1.6;
}

/* Footer */
.site-footer {
  border-top: 1px solid #e0dcd6;
  background: #faf8f4;
}
</style>

<div class="index-hero">
  <div class="index-eyebrow">DL Fundamentals Lab</div>
  <div class="index-title">Theory<span>/Simplified</span></div>
  <p class="index-subtitle">Clear, principled explanations of deep learning theory — with interactive visualizations, verified claims, and the math that matters.</p>
</div>

<div class="post-list-styled">
  {% for post in site.posts %}
  <a href="{{ post.url | relative_url }}" class="post-entry">
    <div class="pe-date">{{ post.date | date: "%B %-d, %Y" }}</div>
    <div class="pe-title">{{ post.title }}</div>
    {% if post.excerpt %}
    <div class="pe-excerpt">{{ post.excerpt | strip_html | truncate: 180 }}</div>
    {% endif %}
  </a>
  {% endfor %}
</div>
