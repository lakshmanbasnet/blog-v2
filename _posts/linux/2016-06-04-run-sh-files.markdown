---
title: How to run .sh files in Linux?
date: 2016-06-04 04:06:47 Z
categories:
- linux
layout: post
author: Lakshman Basnet
description: run .sh files in Linux
---

Even though I have posted this in fedora category, it works for all linux distros.
To execute/run any .sh files.

run the followig comands:

* first give execute permission to script file :

      chmod +x /path/to/scriptfile.sh

* and to run the script:

      /path/to/scriptfile.sh

* if scriptfile.sh is in current directory then you do it with:

      ./scriptfile.sh

as ./ refers to current directory

after doing this it must be running, if still not then 

* browse to the script file with file manager 
* right click to properties
* open permissions 
* make sure: Allow executing file as program is checked on.
