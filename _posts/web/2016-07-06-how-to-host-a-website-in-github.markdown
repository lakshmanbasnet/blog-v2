---
title: Free website hosting with Github
date: 2016-07-06 06:06:47 Z
categories:
- web
layout: post
description: Save your money and hassle by hosting your websites with Github, no any
  charges, you can host unlimited websites with high bandwidth.
image: "/assets/host.png"
---

<img src="/assets/host.png" alt="">


With Github Pages we can host our sites in Github, it is totally free. You can host as many sites as you want. HTML, CSS, Javascripts and Markdown are supported by github pages.

Basically, static sites and project websites are hosted with github. If you want to host any blog sites then you can do with Jekyll too. Check my other posts for Jekyll.

To host any site, I am explaining here from Linux platform, you can use same method for windows too. follow these steps:
 

You can watch this video or follow the instructions below.

<div class="abc">
	<iframe width="560" height="315" src="https://www.youtube.com/embed/LUbRk2oJQz0?showinfo=0" frameborder="0" allowfullscreen></iframe>
</div>

 * login to your github account and create a new repository
 * in terminal navigate to your website's folder (where index.html is located)
 * run the following github commands:

{% highlight ruby %}
git init
git add .
git commit -m "your message here"

{% endhighlight  %}
  

 * now lets add the remote origin  from github 
{% highlight ruby %}
git remote add origin https://github.com/lakshmanbasnet/test.git
{% endhighlight  %}
  ** replace lakshmanbasnet with your username
  ** replace test.git with your repository name

 *  the default branch is master, for hosting websites with Github we need to push our files to gh-pages branch. Remember you need to push to this branch since any files pushed to master branch won't be generated for websites, if you push to gh-pages branch, github will automatically generate website for you.

 * lets make new branch gh-pages with command:
{% highlight ruby %}
git branch gh-pages
{% endhighlight  %}
 * lets navigate to our gh-pages branch
{% highlight ruby %}
git checkout gh-pages
{% endhighlight  %}
 * now every thing is ready, just hit push command and enter your credentials when asked
{% highlight ruby %}
git push origin gh-pages
{% endhighlight  %}
 * after you have pushed your file to github repo, goto your github repo in your browser 

 * in settings scroll down to find the link for your website, the link will be something like https://lakshmanbasnet.github.io/test/

 * congratulations your site is live now

 * to make any changes to the website, you need to push the files from your computer to github by following commands:
{% highlight ruby %}
git add .
git commit -m "your update message"
git push origin gh-pages
{% endhighlight  %}

 To add custom domain name to replace the default domain name provided by github check my next post.

 Thanks!
 Enjoy free hosting!! ;)

 Like, comment and Share if I worth :P
