---
layout: page
title: Musings
---

Just somewhere to share my thoughts with the world (old man yells at sky).

{% if site.posts.size > 0 %}
<ul class="post-list">
  {%- for post in site.posts %}
  <li>
    <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %-d, %Y" }}</time><br>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
  </li>
  {%- endfor %}
</ul>

<p><a href="{{ '/musings/feed.xml' | relative_url }}">RSS feed</a></p>
{% else %}
<p>Nothing here yet.</p>
{% endif %}
