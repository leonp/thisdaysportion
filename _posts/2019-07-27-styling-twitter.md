---
title: "Styling Twitter, and HTML with soul"
category: web
---

I’ve been using the mobile Twitter site instead of the OS X app on my laptop for years. So when I got [the “new” Twitter](https://www.ghacks.net/2019/06/26/how-to-disable-twitters-new-interface-design/) it wasn’t anything out of the blue. The main annoyance is the three column, straight-from-2001 layout, and the stupid fixed sidebars and headers; the HTML itself has been a labyrinth of nested divs and esoteric class names for years. For example:

`<div class="css-901oao css-16my406 r-1qd0xha r-ad9z0x r-bcqeeo r-qvutc0">`

[What’s the problem with this type of markup?](https://simulacrum.party/posts/the-mutable-web/) Well, for a start, it’s hard to relate the class names to either the purpose of their element, or its appearance. So it’s neither “semantic” or “presentational” in any recognisable sense -- it doesn't communicate _anything_ to the reader. While I may use functional, "unsemantic" class names&hellip;

`<h1 class="f6 mb4 mb5-ns mb6-l pa2 pv3-ns ph3-ns ph4-l c-lh-title bg-white">`

&hellip; you can at least glean some purpose in them (they set `margin-bottom`, `background-color` etc.) or even [look up what they mean](http://tachyons.io/docs/). The Twitter markup is not saying anything to _humans_ at all -- it's markup for robots by robots, a semaphore that speaks only to itself, a cacophony of whirring signs and impulses. It's rude. _It lacks soul_.

Not that this matters, necessarily.

After all, 99% of the world won't _Inspect element_ or _View page source_; they'll just see or hear the content itself. All of it, including the ads and the sidebar suggestions.

What does matter is that this opaqueness makes the markup very difficult to _control_ through styling. It is what it is. You get what you're given, ads and suggestions included. What you can't understand you can't structure differently, or filter.

There is a principle at stake here. HTML and CSS are inherently meaningful; they exist to aid the distribution and understanding -- and thereby control -- of content. And happily enough, you can make out the odd `article` among the Twitter trees, or a helpful attribute here and there. For example `<div[data-testid="sidebarColumn"] {display: none;}` will remove the suggestions sidebar in one fell swoop.

It's odd that writing the very code we need to _produce_ content on the web is now seen as secondary practice:

> &hellip; in recent years, there's a growing perception of HTML and CSS as a compile target, more akin to bytecode or assembly language than real source code <cite><a href="https://simulacrum.party/posts/the-mutable-web/">The Mutable Web</a></cite>

&hellip; and I wonder whether this indirection is a cause of uncommunicative HTML.
