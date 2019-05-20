---
title: Blogging like a Hacker - Jekyll Tutorial
date: 2016-09-24 04:06:47 Z
categories:
- web
layout: post
description: Learn to blog like hacker, Jekyll tutorials from basic installation to deployment, and more advanced stuffs too.
image: /assets/jekyll.png
---


<h4>Jekyll</h4> is a simple, blog-aware, static site generator. You can do a lot of things with Jekyll. Here instead of explaining about Jekyll I will write how easily you can make your blog in few minutes with Jekyll. 

I assume that you are doing this on either Linux OS or Mac OS as we will be working on terminal. And also, I am assuming that you have already installed ruby(programming language) in your computer. If you have not installed then please google `installing ruby` or something or follow this [link](https://www.ruby-lang.org/en/documentation/installation/).

After installing you can be sure by checking the ruby version using 

	ruby -v

In my case I get output as:

	$ ruby -v


	ruby 2.2.5p319 (2016-04-26 revision 54774) [x86_64-linux]

Now, lets install Jekyll
	
	gem install jekyll

You can verify by
	
	jekyll -v

now lets create a blog, in my case my blog name is "nepal", replace nepal with you what you want

	jekyll new nepal

let move inside nepal directory 

	cd nepal

if we do `jekyll serve` we will get error, we need to install bundler, so lets do

	gem install bundler

after it completes, 

	bundle install

now lets do

	jekyll serve

it will successfully build our website and gives the localhost address like `http://127.0.0.1:4000/` , lets open up this link in our browser!

Voila !! Our site is up!!


We can see that the basic site is up with one page and one blog post auto genereated by Jekyll. Also, our site is mobile responsive. This is great!

Now lets try pushing it to Github so that we can publish our site live.

in our terminal lets stop the server by `Ctrl+C` command.

now lets initialize Git in this site and do steps as below:

	git init
    git add .
    git commit -m "your message here"

The default branch will be `master`, to host on Github its recommended to use `gh-pages` branch as when pushed to this branch, github will automatically publish our site.

lets create new `gh-pages` branch by
	 
	git branch gh-pages

switch to new branch 
	
	git checkout gh-pages

For this first lets goto [Github](www.github.com) and Sign Up if we don't have account.

* Now lets make a new repository and add the remote to our site by copying as github gives the origin 

* I made a repo with name `huhuhu`, give it an awesome name :D

then move to terminal and run the command to add the remote:

	git remote add origin https://github.com/lakshmanbasnet/huhuhu.git

Finally lets push to this repo by

	git push origin gh-pages

It migh ask for your github username , give your email address and provide your password.

Now if we go to our github account and find our new repo and go to its setting then there will be the deployed link of our site, sth like lakshmanbasnet.github.io/huhuhu click on the link, and your site is live!!

If you want to make this site in your desired domain name then you can easily achieve this by adding a CNAME to your repo. Before I assume that you have a domain name like mine is `www.lakshman.me`, so we can do this by :

in our local computer inside our jekyll site , lets make a new file in the same place as where **index.html** is located 

Inside this file add your domain name , I would write:


	lakshman.me 

and save it under filename <b>CNAME</b> all in capital letters with no any extension.

After adding lets again push it to github, the general procedure for pushing changes is:

	git add .
	git commit -m "CNAME added"
	git push origin gh-pages

Now, your site is live at your desired domain name. 


<h3>Adding a new Page in Jekyll Site</h3>
Nothing is easier than adding a new page in Jekyll site. For this we just need to make a new file with markdown extension.

Also, the best part of Jekyll pages is when we add any pages it will automatically go into navbar, we don't need to add our page to menu link manually.

Here I am trying to make a new page **Contact** for this what I do is make a new file in the same location as where index.html is located and add the following yaml front matters in the head.

	---
	title: Contact
	permalink: "/contact/"
	layout: page
	---

This defines how our page will be, its layout and its title and permalink which are self explanatory. Remember if you don't add this few piece of lines to your pages then they would look so ugly. :D


You can add your desired content below the last `---` lines which will be directly delivered to site. You can use both html and markdown.

For instance I am adding following random contents:

	You can call me directly at 01010101 or send a message in fb.

After this I will save the file with extension `.md`, my filename is `contact.md`

<div class="ab">
If you want certain pages to appear in menu before the other, how can you do?
</div>


Jekyll automatically sorts pages in navbar alphabetically according to their filename. So in our case, about would come first before Contact, to  make Contact come first is you can make it alphabetically come before about to do this I would easily add some letters to the filename. :D So, my new filename is `aaContact.md` . Now, Contact Comes before About :D :D 



### Adding a new Post in Jekyll - Blogging with Jekyll

In Jekyll to add either page or page, we need to create a new file. To add a new post, we create a new file and add front matter to it, the general structure would be:

	---
	title: My New Post
	date: 2014-06-06 04:06:47 Z
	categories: random
	layout: post
	---

Like in page, the content of post will go below `---`, we can use html or markdown or both. For a single post, we need to add a new file.

And while saving the file there is one strict rule that must be followed, we should save the post's file in order : first date and file name

for instance I have saved this blog post as `2016-09-24-blogging-like-a-hacker-jekyll-tutorial.md`

As above, we need to save each post files inside our ** _posts ** folder. 
The general rule is we should start writing with Date and then file name

`YEAR-MONTH-DAY-title.MARKUP`

Some examples of post file names are:

	2011-12-31-new-years-eve-is-awesome.md
	2012-09-12-how-to-write-a-blog.md



The main reason you make blog site is to write blog.

:D

I will write more soon! :) stay tuned.





