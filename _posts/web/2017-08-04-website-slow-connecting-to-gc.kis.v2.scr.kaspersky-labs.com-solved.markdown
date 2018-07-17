---
title: Solved - Website loading slow because of connecting to gc.kis.v2.scr.kaspersky-labs.com...
date: 2017-08-04 04:06:47 Z
categories:
- web
layout: post
description: Because of some reasons, your website might be slower than it should be. Here is how to fix connecting to gc.kis.v2.scr.kaspersky-labs.com js request injection.
image: /assets/kaspersky.png
---

My story is : 

I updated a website's content through a windows computer with Kaspersky antivirus enabled on it, I didn't care much. I accessed that site's cpanel and was updating through the file manager. And later, my website was unexpectedly slower, yeah slower than slowest. At the bottom of browser it showed `connecting to gc.kis.v2.scr.kaspersky-labs.com` and it would take more than a minute to load page. 

<img src="/assets/kaspersky.png" alt="connecting to gc.kis.v2.scr.kaspersky-labs.com solved"> <br>

I googled about connecting to gc.kis.v2.scr.kaspersky-labs.com and found out that it was because of Kaspersky Antivirus Internet Protection enabled that was making it slow. 

Kaspersky did a Javascript injection on my homepage, possibly! not sure though! 

And when I viewed loaded website's source through view source option than I found that the page was calling to this file(`<script type="text/javascript" src="http://gc.kis.v2.scr.kaspersky-labs.com/.../main.js" charset="UTF-8"></script>`)

This website wasn't slow on that Kaspersky enabled windows computer only but in every computer's browser accessed. Even in my linux computer, it said connecting to gc.kis.v2.scr.kaspersky-labs.com when no Kaspersky was in my machine. This made me to dig the story.

If this problem is only on particular Kaspersky enabled windows computer that you can easily solve this by disabling following option from Kaspersky's setting:

	Settings -> Additional -> Network -> Inject scripts into web traffic to interact with web pages.

Else, if your problem is like mine than,

go to your website's cpanel or source code from where you update your site. Look for code something like this: 

	<script type="text/javascript" src="http://gc.kis.v2.scr.kaspersky-labs.com/.../main.js" charset="UTF-8"></script>

then just remove this from your file, now believe me, your website will be faster. Yeah faster!

