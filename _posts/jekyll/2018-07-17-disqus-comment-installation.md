---
title: Disqus Comments on Jekyll Site
date: 2018-07-17 04:06:47 Z
categories:
- jekyll
layout: post
author: Lakshman Basnet
description: A simple walkaround on how easily you can set up Disqus Comment Management System in your Jekyll site!
image: /assets/lb-th.png
---
Few hours before writing this article, I was trying to setup DISQUS Comment System in this Jekyll site. I went through Disqus' official site's documentation and did exactly same what was told there but for some reasons the comment system didn't load at all. I looked over the internet, but still no luck .. and later, I started playing around and the comment section just loaded! :D Here is how I did it!
<br>

<div class="row">
<div class="col-md-6 sm-5 xs-5 tableofcontent">
	<h3 class="rhre">This post is about</h3>
	<li class="hre"><a href="#1"><h4>1. What Disqus is</h4></a></li>
	<li class="hre"><a href="#2"><h4>2. Disqus Comment vs Facebook Comment</h4></a></li>
	<li class="hre"><a href="#3"><h4>3. Disqus Installation in Jekyll site</h4></a></li>
	<a href="#4"><h4>4. Quick Notes</h4></a>

</div>

</div>

<a name="1"></a>
<br>
<br>

First, if you are new to DISQUS comment, let me tell you what Disqus is all about. It comes from the word <b>discussion</b>. It is a very popular Comment Management System, remember it somehow differs from Content Management System even though comment is also a content in itself. It is kind of social network of comment that can be embedded into any webpages. Comment management is really easier and smoother with Disqus.
<br>
<br>
Wikipedia defines Disqus as: 
<div class="thumbnail">
Disqus (/dɪsˈkʌs/) is a worldwide blog comment hosting service for web sites and online communities that use a networked platform. The company's platform includes various features, such as social integration, social networking, user profiles, spam and moderation tools, analytics, email notifications, and mobile commenting. 
</div>
<a name="2"></a>
<br>
<br>
<h2>DISQUS Comment vs Facebook Comment</h2>
From 2016 to the time writing this post, I was using facebook comment plugin for managing comments in this blog site. And now I am switching to Disqus comments primarily for following reasons:

- not all visitors are willing to comment through their personal facebook account
- setting up facebook developer app and making comment plugin work takes little more time than setting up Disqus
- Disqus has a very outstanding dashboard for comment management
- apart from comments there are several other features like ads, newsletter subscriptions, and more in different plans in Disqus

<a name="3"></a>
<br><br>
<h2>Setting up Disqus in Jekyll site</h2>
Now lets quickly dive into setting up Disqus Comment System in our Jekyll site. 

For this, please follow the instructions followed below:
- Sign Up and login to <a href="https://disqus.com" target="blank">Disqus</a>
- create a new site from <a href="https://disqus.com/admin/create/">`New`</a>  tab
- fil in the details and appropriate category that best fits your site
- next page will take you to select appropriate platform where we can select the platforms our site is made on

- choose jekyll
- in step <i class="ba">**1**</i>, it says us to setup in YAML front matter.
<div class="thumbnail">
<b>note</b>: if you want comment section to appear in every posts, or you don't want to define `comments: true` than you don't need to declare it in YAML. You can skip the step below:
</div>

YAML front matter is something thats inside:

	---
	sth goes here
	---

The instruction is to add `comments: true` in the front matter of every post where we need to load Disqus comment as below:

	---
	layout: default
	comments: true
	# other options
	---

	post content

- in step <i class="ba"><b>2</b></i>,<br>

Disqus instructs us to put the universal code inside, lets create a new file `disqus.html` in `_includes` where we will keep our disqus comment code. The general syntax is:

	{% raw %}
    {% if page.comments %}
	universal code here
	{% endif %}
	{% endraw %}

Here is how my `disqus.html` file looks like:

{% highlight javascript %}
{% raw %}
<div id="disqus_thread"></div>
<script>

/**
*  RECOMMENDED CONFIGURATION VARIABLES: EDIT AND UNCOMMENT THE SECTION BELOW TO INSERT DYNAMIC VALUES FROM YOUR PLATFORM OR CMS.
*  LEARN WHY DEFINING THESE VARIABLES IS IMPORTANT: https://disqus.com/admin/universalcode/#configuration-variables*/

var disqus_config = function () {
this.page.url = '{{ page.url }}';  // Replace PAGE_URL with your page's canonical URL variable
this.page.identifier = '{{ page.url }}' // Replace PAGE_IDENTIFIER with your page's unique identifier variable
};

(function() { // DON'T EDIT BELOW THIS LINE
var d = document, s = d.createElement('script');
s.src = 'https://Shortname.disqus.com/embed.js';
s.setAttribute('data-timestamp', +new Date());
(d.head || d.body).appendChild(s);
})();
</script>

                            
<script src="https://Shortname.disqus.com/embed.js"></script>
{% endraw %}
{% endhighlight %}


replace **shortname** with your from the one you created one previously in disqus

since the js code didn't work, so I added script source manually at the end and it works well. :)

<br><br>
<div class="thumbnail">
<b>note</b>: if you want comment to be displayed in every posts, then you don't need to put universal code inside as above.  
</div>

<br><br>
- Now, in `post.html` file located in `_layouts`,

lets add the disquss comment code from `_includes` right above the closing `</article>` tag or anywhere you want the comments to appear

	{% raw %}
	{% if page.comments %}
		{% include disqus.html %}
	{% endif %}
	{% endraw %}

what this code does is, if the post has `comments: true` in YAML front matter than it will load the disqus comment.

<br><br>

- If you want comment to be displayed in every posts, like in mine case,

add just following lines in `post.html`

	{% raw %}
	{% include disqus.html %}
	{% endraw %}

- we are done with setting up Disqus in our jekyll system, remember to put `comments: true` if you have wrapped `{% include disqus.html %}`  inside if page.comments and endif, to display comments in specific posts in `post.html` file

- go ahead and check if the comment system is loading!

- you can return back to diqus.com and complete configuration and enjoy the dashboard!
<a name="4"></a>
<br><br>

<h2>Quick notes:</h2>

1. if you want to load comments in specific defined post only,
	- you need to wrap include disqus.html inside if page.comments ... endif
	- you need to define in which post to load comment by adding `comments: true` in frontmatter
2. if you want comment to load in all posts
	- you don't need to wrap include disqus.html inside anything
	- no need to add any front matters
3. Disqus might slow down your webpage loading speed, for this you can keep all the scripts at the end footer of your jekyll site or do lazy load. 
	
	But remember to at least keep `<div id="disqus_thread"></div>` inside disqus.html
4. you can play around and modify above steps and procedurs as you wish


<br><br>

Do, comment below if this article hepled you or have any confusion!

