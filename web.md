---
title: Blog posts in Web Development and Design
permalink: "/web/"
layout: category
---

<ul class="post-list">
{% for post in site.categories.web %}
<li>
      <span class="post-meta">{{ post.date | date: '%Y %b %d'}}</span> &raquo; <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
    </li>
  {% endfor %}

  </ul>

<div class="abc">
<iframe width="560" height="315" src="https://www.youtube.com/embed/videoseries?list=PLiY4zFbQdWoKkkt4gpYybBmgGFESVC2gf" frameborder="0" allowfullscreen></iframe>
</div>