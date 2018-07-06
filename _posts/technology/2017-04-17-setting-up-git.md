---
title: Setting up git on Linux/Mac
date: 2017-04-17
categories:
- technology
layout: post
description: Setup Git in your computer in few quick steps, be it on Linux (Ubuntu, Fedora, Redhat, Arch etc) or Mac or Windows
image: "/assets/github.JPG"
---

<img src="/assets/github.JPG" alt="Github git setup">

In this blog post, I am writing how you can set up `git` a version control system in your computer system and connect and authenticate it with github.


open terminal and check if git is already installed 

	git --version

if it is already installed, git version will be the output: 

	git version 2.5.0

If not installed Download and install git from https://git-scm.com/download/linux
-you will find the command for your distro accordingly, some common are listed here:

fedora

	yum install git

or

	dnf install git

debian/ubuntu

	apt-get install git

If git is already installed we can get/update latest version of git by git itself

	git clone https://github.com/git/git




## Setting Git username ##

In terminal, lets setup username
	
	git config --global user.name "username"

This will be written in a file `/.gitconfig`

You can check username with

	git config --global user.name



## Setting email address ##

in terminal add your github email address

	git config --global user.email "email@example.com"

confirm by

	git config --global user.email

note: we are adding username and email address for every repository on our computer

## Authenticating with GitHub from Git ##

There are two ways to connect with Github from our computer with git.

1. With HTTPS 
2. With ssh

Here I am explaining about the HTTPS

We can push/commit/pull or do any operations on our github repo. 

* go to github.com
* create a new repository

in terminal,

Initialize git
	
	git init

add the changes
	
	git add .

commit changes

	git commit -m "your message"

add remote by

	git remote add origin https://github.com/username/repository_name.git

we can get origin address in repo's setting too while creating repo

after adding origin,we are ready to push to github

	git push -u origin master










	




