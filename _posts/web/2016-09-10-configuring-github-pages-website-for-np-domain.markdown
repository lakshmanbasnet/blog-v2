---
title: Configuring .np domain for Github page
date: 2016-09-10 04:06:47 Z
categories:
- web
layout: post
description: Pointing .np domain to Github page website, Jekyll Website, gh-pages. register.mos.com.np doesn't allow you to add A records to point to Github so here is the most easiest way how you can do this.
---
In this post, I will share an idea how you can point your `.np` domain website to `Github Pages(gh-pages)` website. It is much easier to point any domain towards gh-pages website by simply adding `A Records` to domain settings and `CNAME` to our `gh-pages` Github repository. But the problem with `.np` domains is that we can't add `A records` as their is no any field to add `A record` to our domain properties. 
To solve this problem, we will make use of `Cloudflare` a CDN(Content Delivery Network) that allows us to manage our domains in easiest and reliable way. And also, it doesn't charge any fees for doing this, and we can manage multiple sites with cloudflare. So follow the steps below:

* first, make sure that you have added `CNAME` file to your github repository
	In my case I would add lakshmanbasnet.com.np in `CNAME` file.
  Remember `CNAME` file has no any extensions and its filename should all be capitalized

* second step is to go to [cloudflare](http://www.cloudflare.com) and make an account (go with free plan)

* at the top click on `Add` site
<figure><img src="/assets/gh/1.png"/></figure>

* add your domain name and begin scan
<figure><img src="/assets/gh/2.png"/></figure>

* after waiting for some time, it scans and suggests you what to do

* after the scan is over, slicck on `Continue Setup`

* since, we want our domain to point to `gh-pages` lets add two `A Records`  for Github Pages

* Now, lets add first `A Record`, in `Name` field add your domain name and in `IPV4 address field` add `gh-pages` address i.e `192.30.252.153`

<figure><img src="/assets/gh/3.png"/></figure>

* similarly for next record `A Record`, do as previous but in `IPV4 address field` add `gh-pages'` address i.e `192.30.252.154`

* for timestamp, you can select the smallest available time, larger time you choose, more time it takes for changes to happen

<figure><img src="/assets/gh/4.png"/><figcaption>Your records will sth like this</figcaption></figure>

* also make sure that you have `CNAME` record to point your domain name with and without `www` to same location

<figure><img src="/assets/gh/5.png"/><figcaption>Your records will sth like this</figcaption></figure>

* now click on `Continue` and after that make sure you choose free plan and tap `Continue`

<figure><img src="/assets/gh/6.png"/></figure>

* after this step Cloudflare automatically suggests you what to do 
	as in my case I have to update the nameservers to what cloudflare has said to.
	for your case also, you need to do as directed

<figure><img src="/assets/gh/5.png"/><figcaption>you get suggestion like this</figcaption></figure>
* now its time to update the `nameservers` provided by cloudflare in your `.np` domain setting.

* goto MOS [site](http://www.register.mos.com.np), login to your account and update the nameserver as said by cloudflare

* after updating the nameserver in mos site, come back to cloudflare setup page and click on `continue`

* it might take some time, wait until it completes and finally you are done!!

This way you can easily point your .np domain to Github sites, gh-pages site or any Jekyll Sites. Hope it was useful
