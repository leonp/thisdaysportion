---

title: 'Dynamic looping in Liquid to build an advent calendar'
category: web
description: Liquid has some pretty powerful looping options.
published: true
---

Like [24 Ways](https://24ways.org/), we have [an advent calendar on the Suffolk Libraries site](https://www.suffolklibraries.co.uk/new-suggestions/staff-picks/advent-calendar-2016/), consisting of a staff Christmas present suggestion a day. Each new entry appears at 1am.

While it might not seem that spectacular, I like this code and how everything slots together to create a dynamic effect on a static website. Here's the code that generates the calendar:

<script src="https://gist.github.com/leonp/63c81a9d2ee6676671e3bdef09a7afe0.js"></script>

<noscript><p><a href="https://gist.github.com/leonp/63c81a9d2ee6676671e3bdef09a7afe0">Advent calendar code</a></p></noscript>

And here's how it works:

- The advent calendar entries are normal posts tagged `advent-calendar`. The `advent_posts` object consists of all published posts tagged `advent-calendar`,  which we loop through using a standard `for` loop. Naturally enough, there are a maximum of 24 posts in the object (although you won't really need this code unless you put more than 24 entries in the calendar, which would be plain wrong).
- We automate post publication on a day by day basis by triggering a site build using a [Zapier zap](https://zapier.com/). Each advent calendar post has a `date` set in its YAML meta data, so they'll only be published when their day comes round.
- The `reverse` filter orders the posts in the set by date starting with the oldest first, rather than the newest first. This ensures the advent calendar displays entries in order, i.e. Dec 1 then Dec 2 then Dec 3 etc.
- You'll see each entry has its own Christmas icon (an SVG background image). We get a different image a day by applying a different class: `custom-icon-xmas-1`, `custom-icon-xmas-2` etc. To get a different number we use `forloop.index`, which returns the current loop iteration. So when we're iterating through the loop the first pass returns `1`, the second `2` and so on.

This is one of the best things about Jekyll and Liquid. The syntax is easy to learn and [well-documented](https://help.shopify.com/themes/liquid/basics), which means that, with a bit of thought (and Zapier), you can create some dynamic events on a static website.
