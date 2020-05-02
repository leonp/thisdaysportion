---

category: web
title: Council Toolkit and non-universal navigation
excerpt: Council Toolkit does complex navigation really well by using an old fashioned, easy to interpret method.
---

Stumbled on [Aberdeenshire Libraries](https://www.aberdeenshire.gov.uk/libraries/) website earlier this week. It's built on [Council Toolkit](http://counciltoolkit.org/), an HTML, CSS and javascript framework that'll help you build a council (or similar) website quickly.

It's not a million miles from gov uk. You get a free set of solidly designed templates (home page, guide, article, signpost etc.) which you can slot pretty easily into your CMS of choice.

One of the things I like about Council Toolkit is the way it handles navigation. On council (and library) websites we often publish _lots_ of sections. Instead of implementing an unwieldy universal navigation, the home page and category templates put navigation in the main content area, while leaving [a few universal actions in the header area &#8211; a good idea](/2015/08/case-against-universal-navigation/):

<figure>

<img src="/images/aberdeenshire1.jpg" alt="Screenshot of the Aberdeenshire Libraries home page navigation area">

<figcaption class="figcaption"><p>The Aberdeenshire Libraries home page simply links to its website sections.</p></figcaption>

</figure>

There's something old fashioned about this approach &#8211; the home page is essentially an index, but I think it has 4 advantages over a traditional navbar:

- _It lightens the user's cognitive load._ As there's only one area to navigate there's no need to choose between a list of links at the top of the page and links to deeper content in the main page area. You're also saving your users working out what happens when they hover over a link, especially if you've added dropdown menus (and they won't accidentally open pop open when the user moves the cursor across the page).
- Similarly, _it's easy to learn._ You click on a link which leads to a page with links styled in exactly the same way. UI wise, there's nothing to work out, and more space means more text to get labels right. A navbar with dropdown menus could result in less clicks, but [the number of clicks don't matter when the route to the goal is clearer](http://uxmyths.com/post/654026581/myth-all-pages-should-be-accessible-in-3-clicks).

<figure>

<img src="/images/aberdeenshire2.jpg" alt="A screenshot of a sub page">

<figcaption class="figcaption"><p>A deeper page within the website. It uses the <em>category</em> template, which uses the same styles as the home page.</p></figcaption>

</figure>

- _It allows space for links to lots of subsections and supplementary text._ The [Aberdeenshire Council home page](https://www.aberdeenshire.gov.uk/) links to 19 sections. While this could be implemented with a vertical navigation menu, you have a lot more space in the main content area.
- _It's more responsive._ It's easy to stack the Aberdeenshire website panels when you shrink the screen. But more importantly, the navigation area is always visible; you won't be hiding it behind a hamburger icon. And [visible navigation is _always_ better than hidden navigation](/2015/05/do-not-fear-the-nav-bar/).

<hr>

We're currently reviewing the Suffolk Libraries website as it's a grown a lot since I rebuilt it in 2013. I'll definitely be taking the Council Toolkit approach to navigation, although I won't be using the toolkit itself &#8211; as for why, that's for a different post.
