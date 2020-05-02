---
title: "Hiding accessibility on web pages"
category: web
---

I've unhidden my [skip link](https://www.nomensa.com/blog/2004/what-are-skip-links) (as you may be able to see in the top right hand corner of the page). Why? Well, if you hide a link and neglect to reveal it on focus, keyboard navigators experience a weird jump when they tab to it. It seems as if something's broken.

[Whether you still need skip links](https://webaim.org/techniques/skipnav/#headings) is perhaps a moot point.

You can get round this problem by hiding the link with CSS and revealing it when the user tabs to it. Lots of sites do this, including the [New York Times](https://www.nytimes.com/) (try pressing the tab key a couple of times and you'll see what I mean).

This strikes me as an odd approach. The link won't appear until you discover it accidentally, and then disappears when you tab on through the page. It's confusing. As a developer, you're also hacking CSS, writing extra code.

But there's another question we should perhaps ask: _Why hide it in the first place?_

What harm does it do? If the majority of our visitors are using a screen and mouse to navigate around a web page, clicking the link will simply move them to the page content. This is expected behaviour, assuming the link's been labelled logically (probably hard to argue with _Skip to main content_). Granted, users may pause for a second to wonder why it's there – it's perhaps something to interpret.

If some visitors use a keyboard to navigate, having a visible skip link is helpful.

The only other argument I can think of is that it doesn't look good, or it's inelegant, not minimal etc.

There's a pattern when it comes to hiding accessibility features. On this page, most websites wouldn't show you:

- The skip link
- The navigation menu on a narrow screen, replacing it with a hamburger icon, or a _Menu_ button
- The [comment form honey pot field](/posts/staticman-jekyll-comments/#set-up-anti-spam-with-a-simple-honey-pot-field)

It seems as if accessibility features are something to be hidden. Accessibility detracts from the ideal, default experience of a web page.

## Don't hide accessibility

There's something dishonest about hiding things. It's like the developer is ashamed of what they've placed on the page. We don't _really_ think our beautiful, primarily _visual_ page is better than a usable, accessible design (that can still be beautiful)?

Rather than concentrating on how we hide and reveal page elements, it perhaps makes more sense to put our efforts into making pages accessible in the first place. In the same way that genuinely building mobile first should make our pages quicker and easier to use for everyone, building visible accessible elements will [help make them more inclusive](/posts/inclusive-design/).
