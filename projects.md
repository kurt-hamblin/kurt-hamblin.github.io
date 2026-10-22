---
layout: page
title: Projects
---

<!-- Each project is a file in _projects/. Set `order` to control the list order. -->
{% assign projects = site.projects | sort: "order" %}
<ul class="entry-list">
  {%- for project in projects %}
  <li>
    <a href="{{ project.url | relative_url }}">{{ project.title }}</a><br>
    <span class="entry-meta">{{ project.summary }}</span>
  </li>
  {%- endfor %}
</ul>
