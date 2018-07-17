---
permalink: ae
layout: page
---

<small>Everything I  write and share here were faced by me in some part of my time. Some may be my personal thoughts, and some solutions to the problems I faced. I like writing and sharing here as it would help for anyone who gets into problem and runs for solution.<br>
<b>Like,share and comment </b> boxes are there, make use of them to express what you felt after reading. Any comments are always welcome.</small>
<div>

<ul class="post-list">
  {% for post in site.posts %}
    <li>
      <span class="post-meta">{{ post.date | date: '%Y %b %d'}}</span> &raquo; <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
    </li>
  {% endfor %}

  </ul>

  <p class="rss-subscribe">subscribe <a href="{{ "/feed.xml" | prepend: site.baseurl }}">via RSS</a></p>

</div>


<script>
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','https://www.google-analytics.com/analytics.js','ga');

  ga('create', 'UA-76574913-2', 'auto');
  ga('send', 'pageview');

</script>




<div id="body1">
<div id="page">
    
       <section id="home">
       <div id="grace">Hello, I'm LAKSHMAN.</div>
       <div id="web">I love all things Web.</div>
       <div id="simplicity">Simplicity is my principle.</div>
       </section>

</div>
</div>
</div>