---
title: Blog posts in technology
permalink: "/technology/"
layout: category
---

<ul class="post-list">
{% for post in site.categories.technology %}
<li>
      <span class="post-meta">{{ post.date | date: '%Y %b %d'}}</span> &raquo; <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
    </li>
  {% endfor %}

  </ul>

<div class="abc">
	<iframe width="560" height="315" src="https://www.youtube.com/embed/videoseries?list=PLiY4zFbQdWoLmd-FfhpfYur6SXNMLjikX" frameborder="0" allowfullscreen></iframe>
</div>