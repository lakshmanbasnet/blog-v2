---
title: Error installing sqlite3. Ruby on Rails , Fedora
date: 2016-06-02 04:06:47 Z
categories:
- linux
layout: post
---

While creating app in ruby on rails,in Fedors if you face error something like this:

or in other Linux distros, you can use the same way make sure you replace the correct command as per your system.

        ERROR:  Error installing sqlite3:
        ERROR: Failed to build gem native extension.

Then run the command

        sudo dnf install sqlite-devel

after it is successful run

        bundle install
If still not working then, install ruby in developer mode by command:

        sudo dbf install ruby-devel

and run bundle install, it must work.
