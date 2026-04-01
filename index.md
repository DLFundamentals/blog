---
layout: default
---

<style>
  @import url('https://fonts.googleapis.com/css2?family=Newsreader:wght@300;400;500&display=swap');
  @import url('https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600&display=swap');

  /* Style minima's existing header */
  .site-header { border-top: none; border-bottom: 1px solid #e0dcd6; background: #fff; }
  .site-title, .site-title:visited {
    font-family: 'Newsreader', Georgia, serif !important;
    font-weight: 500 !important;
    font-size: 1.35rem !important;
    letter-spacing: -0.02em;
    color: #1a1714 !important;
  }
  .site-nav { display: none !important; }

  /* Page background */
  body, .page-content { background: #faf8f4; }
  .page-content { padding-top: 0; padding-bottom: 0; }

  /* Intro */
  .index-intro {
    max-width: 680px;
    margin: 0 auto;
    padding: 2.5rem 30px 2rem;
  }
  .index-intro p {
    font-family: 'Newsreader', Georgia, serif;
    font-size: 1.05rem;
    color: #4a4640;
    line-height: 1.65;
    max-width: 560px;
    margin: 0;
  }

  /* Post list */
  .post-list-styled {
    max-width: 680px;
    margin: 0 auto;
    padding: 0 30px 4rem;
  }
  .post-entry {
    display: block;
    padding: 1.5rem 0;
    border-top: 1px solid #e0dcd6;
    text-decoration: none;
    color: #1a1714;
  }
  .post-entry:hover .pe-title { color: #c45028; }
  .pe-date {
    font-family: 'DM Sans', sans-serif;
    font-size: 13px;
    color: #8a8680;
    margin-bottom: 0.3rem;
  }
  .pe-title {
    font-family: 'Newsreader', Georgia, serif;
    font-size: 1.3rem;
    font-weight: 500;
    line-height: 1.3;
    margin-bottom: 0.3rem;
    transition: color 0.15s;
  }
  .pe-excerpt {
    font-family: 'Newsreader', Georgia, serif;
    font-size: 0.95rem;
    color: #4a4640;
    line-height: 1.6;
  }

  /* Footer */
  .site-footer { border-top: 1px solid #e0dcd6; background: #faf8f4; }
</style>

<div class="index-intro">
  <p>Clear, principled explanations of deep learning theory, with the math that matters.</p>
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
