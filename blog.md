---
layout: default
title: Blog
permalink: /blog/
---

<div class="prose">
<p>Gedanken zu Forschung, Konferenzen und dem Wissenschaftsalltag.</p>
</div>

<ul class="blog-list">
{% for post in site.posts %}
  <li class="blog-entry">
    <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%-d. %B %Y" }}</time>
    <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
    <p>{{ post.excerpt | strip_html | truncate: 180 }}</p>
  </li>
{% endfor %}
</ul>

{% if site.posts.size == 0 %}
<p><em>Noch keine Beiträge. Lege eine neue Datei in <code>_posts/</code> an, siehe README.</em></p>
{% endif %}
