---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

title: Home
---

# Hi, I'm Seoyeong

## Latest Writing
<ul>
  {% for post in site.posts limit: 5 %}
    <li><a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

## Latest Work
<ul>
  {% assign projects = site.projects | sort: "year" | reverse %}
  {% for p in projects limit: 5 %}
    <li><a href="{{ p.url }}">{{ p.title }}</a></li>
  {% endfor %}
</ul>
