---
title: Latest YouTube Videos from Knowledge Server Plus 
permalink: "/knowledgeserverplus/"
layout: category
---

<div class="row">
<div class="col-md-3">
	
</div>


<div class="col-md-6 ba" style="text-align: center;margin:12px;">
<a href="https://www.youtube.com/knowledgeserverplus?sub_confirmation=1">

<i class="fa fa-firefox fa-2x" aria-hidden="true"></i> &nbsp;
<div class="g-ytsubscribe" data-channelid="UC3cOZUVV5FZ5v3niIgSukMw" data-layout="full" data-theme="default" data-count="default"></div>&nbsp;<i class="fa fa-hand-pointer-o fa-2x" aria-hidden="true"></i></a>
</div>


<div class="col-md-3">
	
</div>
</div>

<ul class="post-list">
  {% for post in site.categories.knowledgeserverplus limit:16 %}


<div class="col-md-6">
<div class="postf">
    
<div class="pimage">
     <a class="post-link" href="{{ post.url | prepend: site.baseurl }}"><img data-src="{% if post.image %} {{ post.image | escape }} {% else %} /assets/lb-th.png {% endif %}" class="lazyload" alt="{{ post.title }}" style="padding-bottom: 2px;"></a>
</div>


<h3>
            <a class="post-link" style="color: #000;" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
</h3>


<p class="post-meta"><hr class="hre"><small> <i class="fa fa-clock-o" aria-hidden="true"></i> {{ post.duration}} &nbsp;&nbsp;<i class="fa fa-folder-open-o" aria-hidden="true"></i>
 {{ post.topic}}<br><i class="fa fa-calendar" aria-hidden="true"></i>
<time datetime="{{ page.date | date_to_xmlschema }}" itemprop="datePublished">{{ post.date | date: "%b %-d, %Y" }}</time></small></p>



  </div>

</div>
  {% endfor %}

  </ul>



<!-- Pagination Links -->


<script src="https://apis.google.com/js/platform.js"></script>