---
layout: post
title:  Instaling Netbeans in Redhat Linux
date:   2017-05-31 17:01:02 +0545
categories: rhel
description: Netbeans on Redhat Enterprise Linux | Redhat Enterpise Linux Blog , How to
---

To install Netbeans in Redhat Linux follow this step:

Download Netbeans sh file from [http://download.netbeans.org/netbeans/8.2/final/bundles/netbeans-8.2-javase-linux.sh](http://download.netbeans.org/netbeans/8.2/final/bundles/netbeans-8.2-javase-linux.sh)

after downloading, navigate to Downloads folder and give permission to the netbeans sh file with

	chmod -R 777 netbeans-8.2-javase-linux.sh

then execeute following command to run installer

	./netbeans-8.2-javase-linux.sh

It will install netbeans and alert you if any packages are needed like jdk and more.