---
title: Responsive Design for Embedded content!
date: 2016-04-19 21:00:46 Z
categories:
- web
layout: post
---

I was trying to embed youtube channel, and google maps into my webpage, and it worked but the problem was it worked well in desktop but didn't fit into screen in small screens, I mean it wasn't responsive.

So, I have found how to make embedded content with iframe responsive.

This is just simple. What you need to do is get the iframe code from any external source you would to embed and place it inside a div in your webpage.

For example ,
to place my youtube channel I would do something like:

	<div class="abc">
	<iframe src="https://www.google.com/maps/d/u/0/embed?mid=1AAOPRci5KHNIyPc4Fq8DHMGzaqQ" width="740" height="400">
	</iframe>
	</div>



here abc is my class name, you can give any.
One more thing to do now, lets add some styling to this abc class in CSS file. So go to your CSS file and add this into your code. Replace "abc" with your class name.


	.abc {
    position: relative;
    padding-bottom: 56.25%;
    padding-top: 35px;
    height: 0;
    overflow: hidden;
	}


Final step is to style the iframe. Add this to your stylesheet :

	.abc iframe {
    position: absolute;
    top:0;
    left: 0;
    width: 100%;
    height: 100%;
	}

That's all, it works!
