---
title: Seoyeong
permalink: /
section: home
variant: light
header_style: none
---

<section class="hero">
  <span class="pill">Research · Design · Writing</span>
  <h1>Hi, I’m Seoyeong.</h1>
  <p class="lead">I explore how people and systems shape each other through product design, research, and thoughtful writing. This is a lightweight home for projects and publications.</p>
  <p class="muted">Based in Seoul · Open to collaboration</p>
</section>

<section class="section-block">
  <header>
    <h2>Publications</h2>
    <a class="more" href="/publications/">View all</a>
  </header>
  <div class="grid">
    {% for publication in site.publications limit: 3 %}
      <a class="card" href="{{ publication.url }}">
        {% if publication.thumbnail %}<img src="{{ publication.thumbnail }}" alt="">{% endif %}
        {% if publication.venue %}<div class="eyebrow">{{ publication.venue }} · {{ publication.type | default: "Article" }}</div>{% endif %}
      <div class="title">{{ publication.title }}</div>
      {% if publication.authors %}
          <div class="meta">
            {{ publication.authors | replace: "Seoyeong Hwang", "<span class='author-underline'>Seoyeong Hwang</span>" }}
          </div>
        {% endif %}
      {% if publication.tags %}
        <div class="tags">
          {% for t in publication.tags limit: 4 %}
            <span class="tag">{{ t }}</span>
          {% endfor %}
        </div>
      {% endif %}
      </a>
    {% endfor %}
  </div>
</section>

<section class="section-block">
  <header>
    <h2>Projects</h2>
    <a class="more" href="/projects/">View all</a>
  </header>
  <div class="grid">
    {% assign projects = site.projects | sort: "year" | reverse %}
    {% for p in projects limit: 3 %}
      <a class="card" href="{{ p.url }}">
        {% if p.thumbnail %}<img src="{{ p.thumbnail }}" alt="">{% endif %}
        <div class="eyebrow">{{ p.year }} · {{ p.role }}</div>
        <div class="title">{{ p.title }}</div>
        {% if p.summary %}<div class="summary">{{ p.summary }}</div>{% endif %}
        {% if p.tags %}
          <div class="tags">
            {% for t in p.tags limit: 4 %}
              <span class="tag">{{ t }}</span>
            {% endfor %}
          </div>
        {% endif %}
      </a>
    {% endfor %}
  </div>
</section>
