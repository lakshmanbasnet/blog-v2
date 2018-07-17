---
title: How to embed a youtube channel into a webpage?
date: 2016-04-09 20:15:07 Z
categories:
- web
layout: post
---

Embedding a youtube channel  is lot easier and simpler. Youtube provides iframe to embed youtube channel to any webpages or posts.

Just replace YOURCHANNELNAME with name of your channel.
{% highlight ruby %}
<iframe src="http://www.youtube.com/embed/?listType=user_uploads&list=YOURCHANNELNAME" width="480" height="400"></iframe>  
{% endhighlight %}

for instance, to embed my channel I would place this code in my webpage.
{% highlight ruby %}
<iframe src="http://www.youtube.com/embed/?listType=user_uploads&list=galkotbaglung1" width="480" height="400"></iframe>  
{% endhighlight  %}

To embed a playlist

<ul>
	<li>open the playlist in youtube</li>
	<li>click share</li>
	<li>click on embed</li>
	<li>copy paste the link given into your webpage</li>

</ul>

To embed a particular video ,
<ul>
	<li>open the video and do same as the steps mentioned above in embedding a playlist section</li>
</ul>