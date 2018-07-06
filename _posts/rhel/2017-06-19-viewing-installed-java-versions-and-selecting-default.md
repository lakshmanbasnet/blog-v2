---
layout: post
title: Viewing the list of Java version installed and selecting the default one
date: 2017-06-19 12:01:02 +0545
categories: rhel
description: Viewing the list of Java version installed and selecting the default one on Redhat Enterprise Linux | Redhat Enterpise Linux Blog , How to
---
We can view the current java version installed in our system with:
	
	java -version

My java version:
	
	java version "1.7.0_141"
	OpenJDK Runtime Environment (rhel-2.6.10.1.el7_3-x86_64 u141-b02)
	OpenJDK 64-Bit Server VM (build 24.141-b02, mixed mode)



Viewing the list of Java version installed and selecting the default one

	sudo update-alternatives --config java

This command will give you the list of installed Java versions.

My output was:
	
	There are 2 programs which provide 'java'.

	  Selection    Command
	-----------------------------------------------
	*+ 1           java-1.7.0-openjdk.x86_64 (/usr/lib/jvm/java-1.7.0-openjdk-1.7.0.141-2.6.10.1.el7_3.x86_64/jre/bin/java)
	   2           /usr/java/jdk1.8.0_131/jre/bin/java

1 is the selected currently in use, to make use of 2 typing 2 and pressing enter will choose jdk1.8.0_131 for me.

Now, if I do
	
	java -version

The output is:

	java version "1.8.0_131"
	Java(TM) SE Runtime Environment (build 1.8.0_131-b11)
	Java HotSpot(TM) 64-Bit Server VM (build 25.131-b11, mixed mode)

