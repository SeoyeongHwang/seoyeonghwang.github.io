---
title: Projects
permalink: /projects/
section: projects
variant: light
header_style: simple
subtitle: "Selected design, research, and product work"
---

{% assign projects = site.projects | sort: "year" | reverse %}
<div class="grid">
  {% for p in projects %}
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
