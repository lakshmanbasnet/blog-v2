---
title: Best screencaster/ recorder for Linux?
date: 2016-06-06 04:06:47 Z
categories:
- linux
layout: post
author: Lakshman Basnet
description: Kazam is the best and most used screencaster/screenrecorder that can
  capture screenshots, videos and have a lot of features. In this post, you will know
  hor to setup Kazam screencaster in Fedora
image: "/assets/kazam.png"
---

Kazam is considered the most loved and liked screen recorder for different operating systems.
It has different features of recording screenshot or screencast and you can choose full screen or particular area.

<figure><img src="/assets/kazam.png" alt="" /> </figure>

To install it in your Fedora device, run the following commands:

    wget http://downloadcontent.opensuse.org/repositories/home:/Kenzy:/packages/Fedora_23/noarch/kazam-1.4.5-3.1.noarch.rpm
    
 and 

    sudo rpm -ivh kazam-1.4.5-3.1.noarch.rpm

 Second command didn't work for me, so I went with third one:

    sudo dnf install kazam-1.4.5-3.1.noarch.rpm

And it will be installed.

Following are some shorcuts for using Kazam that might be useful for you:

    SUPER-CTRL-Q - Quit
	SUPER-CTRL-W - Show/Hide main window
	SUPER-CTRL-R - Start Recording
	SUPER-CTRL-F - Finish Recording

Super generally refers to windows key.