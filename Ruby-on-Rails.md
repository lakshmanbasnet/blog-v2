---
title: Blog posts in Ruby on Rails
permalink: "/Ruby-on-Rails/"
layout: category
---

<ul class="post-list">
{% for post in site.categories.Ruby-on-Rails %}
<li>
      <span class="post-meta">{{ post.date | date: '%Y %b %d'}}</span> &raquo; <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
    </li>
  {% endfor %}

  </ul>

