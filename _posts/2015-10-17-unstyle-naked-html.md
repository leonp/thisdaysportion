---
title: Unstyle and looking at naked HTML

excerpt: Unstyle is a browser that strips pages of javascript and styles. How well do websites work without them? Does your site look good naked?
category: web
---

[Unstyle](https://unstyleapp.com/) is an iOS browser that removes all styles and scripts from a page, replacing the original CSS with a minimal stylesheet.

> Unstyle removes the website's original CSS, and replaces it with a much smaller, _better_ [my italics] optimized version. <cite>[Unstyle](https://unstyleapp.com/about/)</cite>

I'm not sure in what ways Unstyle's stylesheet is better than, say, <cite>[The Guardian's](http://guardian.co.uk)</cite> styles. It's certainly smaller, and in a mobile world that really is an important aspect of getting your page to render as quickly as possible. But Unstyle is still a _visual_ browser, where _some_ CSS is necessary to improve the reading experience. For example, it makes sense to hide _Skip to&hellip;_ links when we can see where the navigation and main content areas are. Overriding the default CSS `line-height` value will make prose more readable.

It's a lot easier to scan and interpret <cite>The Guardian's</cite> home page than its Unstyled version.

So Unstyle is slightly misimplemented, but the idea of rendering a meaningful, readable website <i>sans</i> javascript and CSS raises some interesting questions.

[<cite>The Guardian</cite> loads quickly over a 4G connection](http://www.nytimes.com/interactive/2015/10/01/business/cost-of-mobile-ads.html), but how would it perform over something a lot less reliable when it serves up [1MB of images and 444kb of javascript](http://tools.pingdom.com/fpt/#!/dLvXl3/http://www.guardian.co.uk)? What if we need to unstyle it? Does it work naked, exposing its HTML to the world? How accessible is it?

Take a look at the home page using Firefox's _No style_ option. The HTML is messy:

- Some links are repeated one after another
- Some links are oddly labelled
- Some stories are inexplicably placed in nested lists
- There are hundreds of stories to read
- There's no overall heading structure

The page looks like as if the visual design hasn't been translated to well structured HTML (whether we should be designing from HTML outwards is a separate question, but let's assume most people don't do that&hellip;)

Services like Unstyle and websites like [Death to Bullshit](http://deathtobullshit.com/) pose a difficult question. If we are serious about designing progressively for _all_ reading contexts __our pages need to work well as simple HTML first__. That's a restraint in many ways, but if we can load 2MB of images, scripts and styles in 0.8s over a 4G connection, it ought to be possible. The result should be quicker, easier to read pages for everyone.
