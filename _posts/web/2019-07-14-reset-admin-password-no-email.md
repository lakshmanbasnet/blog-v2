---
title: Solved - Reset Wordpress admin password no email, no phpmyadmin access
date: 2019-07-14 04:06:47 Z
categories:
- web
layout: post
description: Didn't get reset email to change wordpress password? No access to phypadmin? Follow this one simple step to reset your wordpress admin password.
image: /assets/worddpress-reset-password.png
author: Lakshman Basnet
---

<img src="/assets/worddpress-reset-password.png" alt="reset wordpress password">

<br>
I have a small wordpress blog running live through Digital Ocean server. I don't publish new posts quite often and it had been a while since I had logged in to my wordpress admin panel. I tried logging in but I couldn't. I simply forgot what password I had set, I tried every passwords but didn't work. 

My problem here was:

- I tried **lost password**? link to reset password but I didn't receive any reset emails (may be because I had turned off `mail()` function or for other reasons)

- since I was hosting with digital ocean's wordpress default image, I didn't have phpmyadmin and couldn't change password through phpmyadmin, (there could be other way around accessing database but it tool me some time to find out how to do it and I eventually gave up)

- I couldn't reset password, and following is what I found on the internet and it worked for me.



## Reset Wordpress password through file manager - functions.php ##

For this, you need to have access or get connected to your server. You might need to browse through **FTP**s, **SSH** or any other way.

I did a SSH login via terminal to my digital ocean droplet, and navigated to find where  my wordpress's functions.php file was located.

For me the location was:

	root@myserver:/var/www/html/wp-content/themes/mytheme# 

Generally, you will find your `functions.php` file inside `themes` folder in `wp-content`.

You will need editor to add a line to functions.php. 

To edit with vim, 

	vi functions.php

add this line under the line containing `<?php`

	wp_set_password('new-password', 1);

Save your file, in vim use keys: i to inset, ctrl+o, :wq to write and quit.


`new-password`: password you would like to create
`1`: user id number, if you are unsure about id number, you can use `wp user list` command or if you have few user accounts you can try my way: I have 3 user accounts and I tried resetting password to each account as:

	wp_set_password('new-password', 1);
	wp_set_password('new-password', 2);
	wp_set_password('new-password', 3);

This actually worked for me.

Now goto your wordpress login url, when you try logging in, you will find that you won't be able to login, as this would reset password.

Now, return back to above `functions.php` file and remove the lines that you just added and try logging in, and you will get access into it.

Comment down, if you are confused anywhere. :)