---
layout: post
title:  Installing Open Broadcaster Software OBS in Redhat Enterprise Linux 7
date:   2017-05-13 
categories: rhel
description: OBS on Redhat Enterprise Linux | Redhat Enterpise Linux Blog , How to
---

Recently, I installed OBS studio in my RHEL 7. This is how you do:

- Get RPM fusion at [http://rpmfusion.org/Configuration/](http://rpmfusion.org/Configuration/)


- set up build environment

	sudo yum install gcc gcc-c++ gcc-objc cmake git
- install required packages 

	sudo yum install libX11-devel mesa-libGL-devel libv4l-devel \
          pulseaudio-libs-devel x264-devel freetype-devel \
          fontconfig-devel libXcomposite-devel libXinerama-devel \
          qt5-qtbase-devel qt5-qtx11extras-devel libcurl-devel \
          systemd-devel ffmpeg