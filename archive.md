---
layout: page
title: Archive | Lakshman's all blog posts
permalink: /archive
---


{% for post in site.posts  %}
{% capture this_year %}{{ post.date | date: "%Y" }}{% endcapture %}
{% capture this_month %}{{ post.date | date: "%B" }}{% endcapture %}
{% capture next_year %}{{ post.previous.date | date: "%Y" }}{% endcapture %}
{% capture next_month %}{{ post.previous.date | date: "%B" }}{% endcapture %}

{% if forloop.first %}
{{this_year}}<br>
{{ this_month }}

{% endif %}
<ul class="post-list">

<li><span class="post-meta">{{ post.date | date: '%Y %b %d'}} .. {{ post.categories }} &raquo;</span> <small><a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></small></li>
</ul>


{% if forloop.last %} 
{% else %}

{% if this_year != next_year %}
<hr>
{{next_year}}<br>
{{ next_month }}
<ul class="post-list">
{% else %}    
{% if this_month != next_month %}

{{ next_month }}

{% endif %}
{% endif %}
{% endif %}
{% endfor %}

