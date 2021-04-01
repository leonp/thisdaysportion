---
date: 2021-03-31T14:49:53.000+00:00
title: Adding webmentions to Jekyll (an overview)
category: ''
sub: A summary of how I got the webmentions service – which collects mentions to your
  website in one place – to work on a version 4 Jekyll site.
mb-cat: ''

---
I have [webmentions working on a Jekyll site](https://www.thisdaysportion.com/notes/netnewswire-6-has-a-twitter-feed-feature#1096440) (they even get their own anchor link).

Here’s an overview of what I did (this explanation assumes knowledge of what an API is and some general programming concepts):

* I set up [webmentions](https://webmention.io/) and [Bridgy](https://brid.gy/)
* I installed the `jekyll-get-json` plugin to parse my [webmention endpoint](https://webmention.io/api/mentions?token=l0rDXZZ2YinbbSQ8KQ_HAA)
* `jekyll-get-json` makes each webmention object available in a Jekyll array, which you loop through as you would any other array
* I added some code to my `comment-form.html` include that  looked for the post URL slug in the webmention source URL. If it got a match, it added the webmention object to a new array.
* The code loops through the new array, outputting the mention author, source, date and content
* I subscribe to my webmention RSS feed to get a notification whenever there’s a new mention. I _could_ get this to fire a site build on Netlify, so the mention would appear minutes after the mention was made (but there’s not much point, really).

[See the code](https://github.com/leonp/thisdaysportion/blob/master/_includes/comment-form.html) (from line `68`).

There is a [semi-official webmention plugin](https://github.com/aarongustafson/jekyll-webmention_io) from Aaron Gustafsson, but this has a `<4.0` Jekyll dependency. So, I am _half_ tempted to try and build my first Jekyll plugin. After all, Jekyll is popular blogging software, and I’m guessing its users would be quite receptive to hooking into the indieweb.