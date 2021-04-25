---
date: 2021-04-24T15:45:00.000+00:00
title: Edit your RSS feed to control your site’s output to micro.blog
category: web
sub: "One advantage to building a static site is complete control over its output, including your RSS feed(s). Fine tune your feed to make sure you output exactly what you want to micro.blog."
comments_enabled: true
---

If you’re an [indieweb](https://indieweb.org/) purist you publish everything – novels, essays, images, links, thoughts, jokes and tweet-length notes – to your website _before_ syndicating them to social media such as Twitter, Facebook and micro.blog.

RSS will power your syndication. The better social media services work out of the box with RSS, monitoring your feed and retrieving content whenever it’s published. The older, closed networks will require some API wrangling, normally performed by a third party automator such as IFTTT or Zapier.

{% include figure.html url="engine-2.jpg" alt="Diagram of a complicated Victorian engine." caption="RSS is the engine of the indieweb." %}

Most static site generators automatically create an RSS feed, which micro.blog uses to publish new posts:

{% include figure.html url="mb-post.jpg" alt="A micro.blog post." caption="The default RSS-generated micro.blog post." %}

This is good, but means that everything, whether it’s a note, image or 2,000 word essay, looks the same – a title and a link to the post on your website. What if you want to just post the note or the image, rather than a title and link back to your site?

By changing what your RSS feed outputs, you can control what appears on micro.blog. There are three things you need to consider.

Firstly, micro.blog will publish your complete post with no link if you generate an empty `title` node, i.e. `<title></title>`. If the post is more than 280 characters long, it’ll publish those 280 characters followed by an ellipsis and a link back to your site.

Secondly, this means you can post images directly to micro.blog if you use an empty `<title>`. You just need to remember to make image `src`s absolute rather than relative (e.g. use `https://www.thisdaysportion.com/images/engine-2.jpg` rather than `/images/engine-2.jpg`).

Finally, your website can have as many RSS feeds as you like, so you can write a special feed especially for micro.blog, while leaving your ‘main’, complete feed alone. ([See my micro.blog feed](/api/microblog-feed/index.xml).) Static site generators output whatever text files you like from templates, including `xml`, `atom` and `json`, which makes them perfect for generating RSS feeds.

Here’s what [notes I publish to my site first](/notes/dons-better) look like on micro.blog:

{% include figure.html url="mb-note.jpg" alt="A micro.blog note." caption="A website note posted as-is to micro.blog. Note the category emoji, which is set in the note’s front matter." %}

You could create separate feeds for each content type you publish (e.g. one for images, one for essays and one for notes), but that’s maybe a little inefficient. I’ve opted for one micro.blog feed that outputs different entries depending on whether the content is a post, note or link.

You can also do all sorts of clever things when you generate your own feed, such as automatically add a [category emoji](https://help.micro.blog/t/emoji-in-discover/34) you specify in a post’s front matter. Anyway, here’s the Jekyll code for generating my micro.blog feed:

**[See my micro.blog RSS feed code on Github](https://github.com/leonp/thisdaysportion/blob/master/api/microblog-feed/index.xml)**.

Things to note: I’ve created an `everything` array which [concatenates](https://shopify.github.io/liquid/filters/concat/) all site collections into one. I’ve also taken advantage of [Jekyll’s defaults](https://jekyllrb.com/docs/configuration/front-matter-defaults/) to add `is_note`, `is_post` and `is_link` front matter to collection items automatically, so my code can tell what type of item it’s dealing with as it loops through the `everything` array.

