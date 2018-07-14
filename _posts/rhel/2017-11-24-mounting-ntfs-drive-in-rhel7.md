---
layout: post
title: Mounting NTFS File System Drive in RHEL 7
date: 2017-01-24 12:01:02 +0545
categories: rhel
author: Lakshman Basnet
description: A simple walk through on mounting NTFS drives in Redhat Enterprise Linux | Redhat Enterpise Linux Blog , How to
---
	
NTFS drives can be mounted with `NTFS-3G` Package. There might be several other ways too, but for me this has been the best choice.

To install NTFS-3G

First enable EPEL Repository if not previously enabled.
	
	wget https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm

	rpm -ivh epel-release-latest-7.noarch.rpm

Install NTFS-3G package

	yum install ntfs-3g -y


Doing this, it will automatically mount the NTFS drives, if not mounted you do with:

	mount -t ntfs-3g /dev/sda1 /mnt/windows

just replace sda1 with your drive location




