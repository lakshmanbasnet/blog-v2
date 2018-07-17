---
title: Blog posts in Random
permalink: "/random/"
layout: category
---

<ul class="post-list">
{% for post in site.categories.random %}
<li>
      <span class="post-meta">{{ post.date | date: '%Y %b %d'}}</span> &raquo; <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
    </li>
  {% endfor %}

  </ul>

<div class="abc">
<iframe width="560" height="315" src="https://www.youtube.com/embed/1cStUjjGXOs?rel=0&amp;controls=0" frameborder="0" allowfullscreen></iframe>
</div>