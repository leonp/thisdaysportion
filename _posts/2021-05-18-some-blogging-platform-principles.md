---
title: The perfect blogging platform – some principles
category: web
date: 2021-05-18 20:12:00 +0000
---

What do we want from a blogging platform? Is your current favoured system just right? Or do you want more? Or less?

I use now-fairly-unfashionable [Jekyll](https://jekyllrb.com) to build my own blog and I’m happy enough, although even with [a headless CMS like Forestry](https://forestry.io/) it can prove infuriatingly obtuse to write posts on a phone. And getting comments and webmentions working on a static site is only for the most dedicated tinkerer.

So let’s imagine we’re building a platform primarily for writers rather than developers. We may want _some_ customisation options, but they shouldn’t require any coding knowledge.

What features does it need? I’m going to assume you’re following an [indieweb](https://indieweb.org/) philosophy, so that means hosted comments, [webmentions](https://alistapart.com/article/webmentions-enabling-better-communication-on-the-internet/) and [simple, configurable syndication](/posts/edit-rss-for-micro-blog/) to all the major social networks. We want to be in control of how we tweet even when we’re not on Twitter.

Because this is indieweb we need an RSS feed(s). An email subscription would be grand too (perhaps as a chargeable extra).

Maybe you’re using a few different platforms at the moment. That’s cool, but we want to be able to publish everything from our glorious website. At least in principle. So we need a range of formats – images, notes, asides, quotes, links, videos and, of course, longer form pieces such as blogs and essays.

Categories, tags and archives are maybe a given. Maybe? We should have an option to turn on and off as many of these features as possible. We want to be able to build a simple (paginated?) stream of posts, or a rich taxonomy.

Proper search. The facility to create new pages such as *About*, *Contact*, *Now*.

I wonder if I’m inventing Blogger.

Now, the editing experience is important because you’re not going to stick with a platform that’s horrible to use. This is tricky to define, but I’d say we need a website and native apps for smaller devices (sorry PWA folks). Easy OS integrated sharing so I can publish a picture in two taps. When you are writing it’ll be with a rich text editor and/or Markdown.

This is probably where we should introduce the word “minimal”. We’re not building shops, a brand or an intranet – just a blog. That makes the admin area more focused. [A text box and some form fields](/posts/cms-component-ui/) – no [Gutenberg](https://wordpress.org/gutenberg/); well set words, images and videos are our preferred weapons. Minimalist design, in its purest, not-just-taking-things-away-or-hiding-them sense.

It must be fast. Defensive javascript – no sliders or pop outs but a sprinkling to enhance the UI where necessary. It won’t be a <acronym title='Single Page Application'>SPA</acronym>. Think the Basecamp approach.

We’re nearly there, I think. We _should_ offer self-hosted or hosted options so we can truly own our site, and allow simple importing and exporting to Markdown and `json` (and importing from WordPress’s format). Let’s add an API while we’re at it.

I do want to keep configuration to a minimum, so no theming. That’s odd on a self-hosted system, and probably needs bottoming out. Something like Medium? As for what we can change – logo, author photo, tagline, description, typeface (Google/Adobe fonts integration?), palette. Maybe some other typographical options like font size, measure and leading would be fun and enhance the writerly feel. Two layouts? Single column or content/sidebar?  Inbuilt accessibility warnings. Dark theme.

And that’s it. What do you reckon? _I’d_ go for that, I think. But is there something else it needs? Or should be rid of?



