---
layout: post
title:  Installing VLC media player in Redhat Enterprise Linux 7
date:   2017-04-26 
categories: rhel
description: Installing VLC media player in RHEL is so easy than you thought on Redhat Enterprise Linux | Redhat Enterpise Linux Blog , How to
---
Installing VLC media player in Redhat Enterprise Linux editios can be done in following ways:

1. You can directly download from VLC's official [site](http://www.videolan.org/vlc/download-redhat.html) and proceed.

2. Or follow the following steps:
	

First install Epel and Nux repositories

	# rpm -Uvh https://dl.fedoraproject.org/pub/epel/7/x86_64/e/epel-release-7-8.noarch.rpm
	# rpm -Uvh http://li.nux.ro/download/nux/dextop/el7/x86_64/nux-dextop-release-0-5.el7.nux.noarch.rpm


Check if vlc is available

	# yum info vlc


sample output:

	Loaded plugins: langpacks, product-id, search-disabled-repos, subscription-
              : manager
	nux-dextop                                               | 2.9 kB     00:00     
	nux-dextop/x86_64/primary_db                               | 1.7 MB   00:08     
	Available Packages
	Name        : vlc
	Arch        : x86_64
	Epoch       : 1
	Version     : 2.2.4
	Release     : 1.el7.nux
	Size        : 1.5 M
	Repo        : nux-dextop/x86_64
	Summary     : The cross-platform open-source multimedia framework, player and
	            : server
	URL         : http://www.videolan.org
	License     : GPLv2+
	Description : VLC is a free and open source cross-platform multimedia player and
	            : framework that plays most multimedia files as well as DVDs, Audio
	            : CDs, VCDs, and various streaming protocols.


Now, install with

	# yum install vlc

VLC media player can be opened with following command
	
	$ vlc