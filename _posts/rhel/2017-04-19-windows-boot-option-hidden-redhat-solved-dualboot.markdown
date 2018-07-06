---
layout: post
title:  Windows boot option missing after installing redhat in dualboot SOLVED
date:   2017-04-19 17:01:02 +0545
categories: rhel
description: Windows boot option missing after installing redhat/ centos in dualboot on Redhat Enterprise Linux | Redhat Enterpise Linux Blog , How to
---


Windows boot option missing after installing redhat/ centos in dualboot

Before starting, make sure that your windows drive(NTFS) is mounted in rhel system. Otherwise you won't see windows OS in steps following below.

To mount windows ntfs drive, please check <a href="" target="blank"> this</a> quick tutorial post for RHEL 7.

Check that windows is detected. Run following command:

	grub2-mkconfig

If Windows was listed anywhere, lets save the new configuration file by first making a backup first, just in case.

backup:

	sudo cp /boot/grub2/grub.cfg /boot/grub2/grub.cfg.old
 
save the config file:

	sudo grub2-mkconfig -o /boot/grub2/grub.cfg   

Reboot your system, now you must see Windows option in boot menu.

