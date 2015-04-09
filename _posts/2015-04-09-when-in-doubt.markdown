---
layout: post
title:  "when in doubt update the PATH"
date:   2015-04-09 20:43:30
categories: environment
---
As any newbie coder will quickly find out, one of the most painful parts of coding isn't coding at all.  It's setting up your environment on your machine.

Case in point, THIS BLOG.  I've been programming in Python for quite a while on this machine, but for some reason, I was getting lots of errors trying to compile the Jekyll code for this blog.  I just saw a lot of nonsense about pygments and python.  I thought, "Surely I have Python installed, so that can't be it."

Well, after doing the standard Google search for all my errors, and finally running across one [blog](http://yizeng.me/2013/05/10/setup-jekyll-on-windows/) in particular, and reinstalling Python, and re-reading their directions which explicitly call out setting the PATH, I finally went to my environment variables.  Lo and behold, there was no path for Python yet.

The moral of the story is, when in doubt, double-check the PATH.