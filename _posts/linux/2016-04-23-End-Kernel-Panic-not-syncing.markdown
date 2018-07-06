---
title: 'End Kernel Panic-not syncing: VFS: Unable to mount root fs [solved]'
date: 2016-04-23 04:06:47 Z
categories:
- linux
layout: post
---

Recently while upgrading my ubuntu 15.10 to 16.04 I receieved an error while booting message saying:

	End Kernel Panic-not syncing: VFS: Unable to mount root fs ...


I tried different options going through the diferent forums but couldn't solve.

But I solved it in following way:

<ul>
<li>entered advanced options for ubuntu through grub menu

<li>chose the second last option
{% highlight ruby %}

	Ubuntu, with Linux 4.2.0-16-generic (upstart)
{% endhighlight %}
if above option isn't available in yours than choose similar kind of option.
and when ubuntu logs in


<li>I ran the command:
{% highlight ruby %}
	sudo apt-get install -f
{% endhighlight %}
</li>
and if the wifi or any other drivers aren't working correctly than if the above install succeeds and you restart your computer and login to unbuntu, all the problems will be solved.

It worked for me, It might work for you too. Do try!
