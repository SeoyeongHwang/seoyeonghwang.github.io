---
title: Work
permalink: /work/
---

# Work

{% assign projects = site.projects | sort: "year" | reverse %}
<div class="cards">
  {% for p in projects %}
    <a class="card" href="{{ p.url }}">
      {% if p.thumbnail %}<img src="{{ p.thumbnail }}" alt="">{% endif %}
      <div><strong>{{ p.title }}</strong></div>
      <div>{{ p.year }} · {{ p.role }}</div>
    </a>
  {% endfor %}
</div>
