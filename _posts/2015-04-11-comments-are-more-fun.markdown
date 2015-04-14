---
layout: post
title:  "comments are more fun"
date:   2015-04-11 14:21:30
categories: jekyll disqus
comments: true
---
Hooray for adding comments to my blog!

Today I learned how to add the ability for users to comment on blog posts using [Disqus](https://disqus.com/).

First, create a Disqus account.

Second, grab the Universal Embed Code that Disqus generates for you.  You want to copy that code to a new file that you need to create in the _includes directory.  I called it comments.html.

Theoretically, you add `<% if page.comments %>` before this code, and `<% endif %>` after per [this page](https://help.disqus.com/customer/portal/articles/472138-jekyll-installation-instructions). but for some reason that did not work for me - it showed that literal text before and after the comment area.  Also, I can't be bothered to fix it as I don't have a desire to limit comments to only certain posts at this time.

Next, add `comments: true` to the front matter of your posts to allow for comments (if your "ifs" work).

Finally, add `{% raw %}{% include comments.html %}{% endraw %}` to the post layout file in the location that you want the comments to show.

BONUS!!  Add the comment count Universal Embed Code to the bottom of your index.html file.  Then, inside your li for each post, add some code like this:
`<a class="comment-count" href="{{ post.url | prepend: site.baseurl }}#disqus_thread"></a>`.
