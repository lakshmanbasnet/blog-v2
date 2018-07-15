---
title: Nepal's 360 Photos and Videos by lakshman
permalink: "/nepal-360/"
layout: category
---

<ul class="post-list">
{% for post in site.categories.nepal-360-photo %}
<li>
      <span class="post-meta">{{ post.date | date: '%Y %b %d'}}</span> &raquo; <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
    </li>
  {% endfor %}

  </ul>

<div class="abc">
<iframe width="560" height="315" src="https://www.youtube.com/embed/1cStUjjGXOs?rel=0&amp;controls=0" frameborder="0" allowfullscreen></iframe>
</div>