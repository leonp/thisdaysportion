---
date: 2021-06-05 15:48:25 +0000
title: " CSS System Colors"
link-published: 2021-06-02 23:00:00 +0000
link-url: https://blog.jim-nielsen.com/2021/css-system-colors/
link-author: Jim Nielsen
mb-cat: ''
hide-from-twitter: false
is_reply: true
is_like: true

---
I’m really enjoying Jim Neilsen’s blog at the moment, where he’s exploring what HTML is really for, and what it can do. It’s quite inspiring, and has got me reaching for a “purer” approach that focuses on accessibility and interoperability rather than decoration (not that I’ve ever gone in for decoration, of course).

I’d not heard of CSS system colors and I’ve been looking at implementing them on my site this afternoon. Alas, there are a few problems which I haven’t been able to fathom. This is a shame as it would leave light and dark mode settings to the browser, which in turn would mimic the OS’s colour choices. Apart from being very cool, it’d save a fair few `prefers-color-scheme` declarations in my stylesheet.

Firstly, I couldn’t actually get `color-scheme: light dark;` to work in Firefox 89.0, but it was fine in Safari 14.1.1. Secondly, Safari only seems to have a single set of link colours, so if you’re in dark mode you’ll struggle to see links as they’ll render in the default blue you see on white backgrounds. [The spec says](https://drafts.csswg.org/css-color/#css-system-colors):

> To maintain legibility, the [<system-color>](https://drafts.csswg.org/css-color/#typedef-system-color "Expands to: activetext | buttonborder | buttonface | buttontext | canvas | canvastext | field | fieldtext | graytext | highlight | highlighttext | linktext | mark | marktext | visitedtext") keywords also respond to light mode or dark mode changes... the browser should ensure that [matching foreground/background pairs](https://drafts.csswg.org/css-color/#system-color-pairs) have a minimum of WCAG AA contrast.

So I guess it’s just not been fully implemented yet.