---
title: How to install Android Studio on Ubuntu?
date: 2016-04-06 04:06:47 Z
categories:
- linux
layout: post
description: install Android Studio on Ubuntu
---

First Install latest version of Java:
Run following commands in your terminal

{% highlight ruby %}
sudo add-apt-repository ppa:webupd8team/java
sudo apt-get update
sudo apt-get install oracle-java8-installer
{% endhighlight %}
After that

{% highlight ruby %}
sudo apt-get install oracle-java8-set-default
{% endhighlight  %}

Now proceed towards installing Android Studio:
<ul>
<li>Download Android Studio from <a href="https://developer.android.com/sdk/index.html#downloads" target="blank">here</a>
<li>Unzip/Extract the archive file into  location you like,  

<li>To launch Android Studio, navigate to the folder you just extracted, get inside bin directory from android-studio  [ android-studio/bin ]  directory in a terminal and execute {% highlight ruby %}./studio.sh
{% endhighlight  %}

</ul>

And you are done, read  the instructions and continue to setup.
