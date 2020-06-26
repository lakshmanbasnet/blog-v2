---
title: Blog posts in Internet of Things
permalink: "/iot/"
layout: category
---

<ul class="post-list">
{% for post in site.categories.iot %}
<li>
      <span class="post-meta">{{ post.date | date: '%Y %b %d'}}</span> &raquo; <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
    </li>
  {% endfor %}

  </ul>



<div class="abc">
	<iframe width="560" height="315" src="https://www.youtube.com/embed/n3A7tfcL-J8?rel=0&amp;controls=0" frameborder="0" allowfullscreen></iframe>
</div>
