---
layout: post
title:  Installing Jekyll on Redhat Enterprise Linux 
date:   2017-04-20 17:01:02 +0545
categories: rhel
description: Know how to install Jekyll static website generator on Redhat Enterprise Linux | Redhat Enterpise Linux Blog , How to
---

I love writing blogs with Jekyll. Before switching to Redhat Enterprise Linux, I used to use Fedora by Redhat. 

To continue writing my blogs, I tried installing Jekyll but I encountered some problems which were not new for me as I have already encountered in Fedora.

Generally, for installing Jekyll we need to have Ruby installed in our system. It can be checked with 

	ruby -v

If it isn't installed, the general command for installing Ruby is

	# yum install ruby

After installing ruby, Jekyll can be installed with:

	gem install jekyll

as Jekyll is a Ruby gem.

But,

you might encounter problem here like `couldn't build native extensions`, similar to this. 

This can be solved by installing the ruby developer package.

If ruby is already installed, lets re install ruby devel packages, (if ruby is already installed, first uninstalling ruby : `yum remove ruby`)

But to install devel packages in RHEL, we need to enable the optional repos.

	subscription-manager repos  --enable rhel-7-server-optional-rpms

Now, install Ruby Devel package by

	yum install ruby-devel

And finally, march ahead to install Jekyll! :D

	gem install jekyl

Oh yeah, installing bundle might be additional too.

	gem install bundle


Enjoy Jekylling! :)
