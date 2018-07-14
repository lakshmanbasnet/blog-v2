---
title: Disabling automatic loading of last session in Sublime Text Editor
date: 2015-01-21 04:06:47 Z
categories:
- technology
layout: post
author: lakshman
description: You might have got irritated everytime seeing two windows of Sublime Text Editor being opened every time you open Sublime. Here is a quick fix to it.
image: "/assets/Sublime_Text_Logo.png"
---

![screenshot sublime](/assets/sublime.png)
Everytime you open Sublime Text Editor even with `subl .` command, it might open two sublime editor windows with one previous session. You can generally stop previous session from being automatically opened by two simple ways:

* before you exit sublime editor each time, from File menu make sure you **Close All Files**

* or, navigate to to this directory :`.config/sublime-text-3/Packages/User` or something similar directory names 

and find file with name **Preferences.sublime-settings**, in this file make sure there doesn't exist `"remember_open_files": true` it should be `false`. Or if you don't see anything follow below:

In this file, add following code inside:

	{
		"hot_exit": false,
		"remember_open_files": false
	}