---
date: 2021-04-24T14:25:00.000+00:00
title: Edit your RSS feed to control your site’s output to micro.blog
category: web
sub: "One advantage to building a static site is complete control over its output, including your RSS feed(s). Fine tune your feed to make sure you output exactly what you want to micro.blog"
comments_enabled: true
---

If you’re an [indieweb](https://indieweb.org/) purist you publish everything – novels, essays, images, links, thoughts, jokes and tweet-length notes – to your website _before_ syndicating them to social media such as Twitter, Facebook and micro.blog.

RSS will serve as your syndication engine. The better social media networks work out of the box with RSS, monitoring your feed and pushing content to their service whenever it’s updated. The older, closed networks will require some API wrangling, normally performed by a third party automator such as IFTTT or Zapier.

{% include figure.html url="engine-2.jpg" alt="Diagram of a complicated Victorian engine." caption="RSS is the engine of the indieweb." %}

Most static site generators automatically create an RSS feed, which micro.blog uses to publish new posts:

{% include figure.html url="mb-post.jpg" alt="A micro.blog post." caption="The default RSS-generated micro.blog post." %}

This is good, but means that everything, whether it’s a note, image or 2,000 word essay, looks the same in your feed – a title and a link to the post on your website. What if you want to just post the note or the image, rather than a title and link back to your site?

By changing what your RSS feed outputs, you can control what appears on micro.blog. There are three things you need to consider.

Firstly, micro.blog will publish the first 280 characters 