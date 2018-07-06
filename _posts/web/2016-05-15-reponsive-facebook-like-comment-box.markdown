---
title: Responsive facebook like and comment box
date: 2016-05-15 04:06:47 Z
categories:
- web
layout: post
---

If the plugin code you used for facebook like, comment and share box isn't responsive, then adding following to the CSS file will solve your problem.
Make sure class name matches with the plugin code's class.

        @media only screen and (max-width: 767px)
          {
           .fb-comments {
              width: 100% !important;
             }
          .fb-comments iframe[style]
            {
             width: 100% !important;
            }
          .fb-like
            {
             width: 100% !important;
            }
          .fb-like iframe[style]
            {
             width: 100% !important;
            }
          .fb-comments span
            {
             width: 100% !important;
            }
          .fb-comments iframe span[style]
            {
             width: 100% !important;
            }
          .fb-like span
            {
             width: 100% !important;
            }
          .fb-like iframe span[style]
            {
             width: 100% !important;
            }
          }
