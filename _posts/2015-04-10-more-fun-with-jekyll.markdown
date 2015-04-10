---
layout: post
title:  "more fun with jekyll"
date:   2015-04-10 21:45:30
categories: jekyll
comments: true
---
Today I learned three fun things about Jekyll.

First, Github Pages gets confused if your Jekyll blog isn't your Github Portfolio page.  You end up getting a giant Octokitty and some very bad formatting because the page can't find your CSS file:

![My helpful screenshot]({{ site.baseurl }}/images/css-not-found.png)

I love the Octokitty, but that page just isn't going to work.  To fix this, you need to set your base url in your config file to show your repo (i.e., project page) name, like so:  `baseurl: "/blog"`

Once you do that, you will find that your locally hosted version will break.  Oh no!  Don't fret though - you just have to specify to ignore the base url when previewing locally, like so:
`jekyll serve --baseurl ''`

Or, if you have Windows, `bundle exec jekyll serve --baseurl ''`.

Side note, if you do have Windows and don't know how to set up aliases, please please look up how to create them in your bash/terminal/command line.  You don't want to spend your whole life typing in the server command.  You will thank me later.

The second thing I learned was that other things break too - like my navbar logo.  On shared resources, you can't just hard-code the asset or relative page link.  Instead, you have to use the site.url reference.  This is because the Jekyll magic to create your blog posts needs a more flexible reference to where an image, for example, is located.  That probably sounded confusing, so to be more clear...

{% highlight html %}
{% raw %}
<!-- Don't do this: -->
<img src="images/keylogo2.png">

<!-- Do this: -->
<img src="{{ site.baseurl }}/images/keylogo2.png">
{% endraw %}
{% endhighlight %}

Finally, I learned how to make that nifty html code box above show the actual code I wrote rather than converting my double-curly braces automatically (which just made the two lines look exactly the same).  I had to add a raw tag to my html, like described in [this post](http://stackoverflow.com/questions/24102498/escaping-double-curly-braces-inside-a-markdown-code-block-in-jekyll).

Hope that helps at least one person out there!