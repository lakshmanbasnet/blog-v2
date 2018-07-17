---
title: Displaying post count in jekyll
date: 2016-05-04 04:06:47 Z
categories:
- jekyll
layout: post
---

We can display the total number all posts or in particular with following code , I have used only one curly brace, make sure there are two {{ code}}
    
    {% raw %}
    {{ site.posts | size }}
    {% endraw %} 


To display count number for particular categories:
    
    {% raw %}
    {{ site.categories.CAT | size }}
    {% endraw %} 


