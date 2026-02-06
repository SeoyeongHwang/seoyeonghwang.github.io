---
title: Publications
permalink: /publications/
section: publications
variant: light
header_style: simple
subtitle: " "
---

<div class="grid">
  {% for publication in site.publications %}
    <a class="card publication-card" href="{{ publication.url }}">
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
