---
title: Projects
permalink: /projects/
section: projects
variant: light
header_style: simple
subtitle: "Selected design, research, and product work"
---

{% assign projects = site.projects | sort: "period.start" | reverse %}
<div class="grid">
  {% for p in projects %}
    <a class="card" href="{{ p.url }}">
      {% if p.thumbnail %}<img src="{{ p.thumbnail }}" alt="">{% endif %}
      {% assign period_display = "" %}
      {% if p.period and p.period.start %}
        {% assign period_display = p.period.start %}
        {% if p.period.end %}
          {% assign period_display = period_display | append: "–" | append: p.period.end %}
        {% endif %}
      {% elsif p.date %}
        {% assign period_display = p.date %}
      {% elsif p.year %}
        {% assign period_display = p.year %}
      {% endif %}
      {% if period_display != "" %}<div class="eyebrow">{{ period_display }}</div>{% endif %}
      <div class="title">{{ p.title }}</div>
      {% if p.summary %}<div class="summary">{{ p.summary }}</div>{% endif %}
      {% if p.category %}
        <div class="meta">{{ p.category | join: ", " }}</div>
      {% endif %}
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
