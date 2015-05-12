---
layout: post
title:  "adding tags and blog post snippets"
date:   2015-04-14 16:58:30
categories: jekyll
comments: true
---
I'm getting fancy now.  Today I added both category tags and post snippets to my blog.  I promise eventually I will post about something other than Jekyll, but I'm still trying to get fancier right now.  :)

First, category tags were pretty easy.  I just added this code to my _layouts/post.html file:<br>
`{% raw %}{{ page.categories | join: ', ' }}{% endraw %}`

And this similar code to my index.html file:<br>
 `{% raw %}{{ post.categories | join: ', ' }}{% endraw %}`.

Snippets were even easier, thanks to [this StackOverflow post](http://stackoverflow.com/questions/19389451/how-can-i-get-a-post-excerpt-in-jekyll).  I just added this line after my comments in the index.html:<br>
`<p>{% raw %}{{ post.content | strip_html | truncatewords: 50 }}{% endraw %}</p>`