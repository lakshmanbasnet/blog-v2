---
layout: post
title:  Installing Java in RHEL 7
date:   2017-06-01 12:01:02 +0545
categories: rhel
description: Java installation on Redhat Enterprise Linux | Redhat Enterpise Linux Blog , How to
---

To install Java in Redhat Enterprise Linux follow these steps:

- we are installing from OpenJDK rpm with command line

Run the following command to install the developer version of OpenJDK

	# yum install java-1.7.0-openjdk-devel

- (Optional) It is sometimes required to set the **JAVA_HOME** path variable.

You can know the java path by

	echo $JAVA_HOME

It will give the path where Java is

In my case it was something like : `/usr/lib/jvm/jre-1.8.0-openjdk/bin/java` remember it might be different in your case.

Now,

in `.bashrc` file which is in home directory lets add the java home path as:

I am editing the file in vim editor

	[lx@localhost ~]$ vi .bashrc

at the bottom of file add the java path in following format:

	export JAVA_HOME="/path/to/java/home"

in my case, I added:
	
	#java home path
	export JAVA_HOME="/usr/lib/jvm/jre-1.8.0-openjdk/bin/java"

To save first press te**Ctrl+ O** and then 
	
	:wq


semicolon and then w and q and press enter.

You are done!

You can check the java version installed with:
	
	java -version

My output was:
	
	java version "1.7.0_141"
	OpenJDK Runtime Environment (rhel-2.6.10.1.el7_3-x86_64 u141-b02)
	OpenJDK 64-Bit Server VM (build 24.141-b02, mixed mode)


You can get full documentation <a href="https://access.redhat.com/documentation/en-US/JBoss_Enterprise_Application_Platform/6/html/Installation_Guide/Install_OpenJDK_on_Red_Hat_Enterprise_Linux.html" target="blank">here</a> 