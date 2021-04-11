---
date: 2021-04-11 09:35:21 +0000
title: Navigation submenus – what’s the best approach? Dropdown, hovers, clicks or
  keeping it flat?
category: web
sub: Let’s say you have a large website with lots of subsections. What’s the best
  way to reflect this in your navigation menu? Do you use dropdowns at all? Are they
  best activated when the user hovers or clicks on a menu item?
mb-cat: ''

---
I agree with this post from Mark Root-Wiley which argues that [dropdown navigation menus are best activiated when a user clicks the link](https://css-tricks.com/in-praise-of-the-unambiguous-click-menu/) (or, correctly speaking, button) rather than hovers over it. Adrian Roselli also writes really well on [how to implement this UI pattern](https://adrianroselli.com/2019/06/link-disclosure-widget-navigation.html) accessibly.

{% include figure.html url="roselli-dropdown.jpg" alt="Screenshot of the Adrian Roselli website navigation menu." caption="Adrian Roselli’s navigation menu item is clearly styled as a button that should be clicked, complete with animated caret control." %}

This problem came up at work recently, where the hover pattern has been implemented on an extranet. I predict it will cause some problems for the normal reasons – afforability, dexterity and annoyance – especially considering the age of the audience using the website. Any testing, or even your own day-to-day experience, will reveal how frustrating it is to hover over a link to reveal a submenu, and then avoid accidentally triggering dropdowns.

But whether you’re using a click or hover pattern, you’re still creating a new set of problems whenever you implement any dropdown menu. That is, _what’s the top level link link for?_

Take Adrian’s menu. It asks two questions:

* Can I click the “Blog” text? Is it a link ot just button text?
* If it does serve as a link to a page, what should appear on that page if all the subpages are listed when you click the button?

Adrian simply makes it a link to the website home page, which I feel is confusing as it’s labelled “Blog”, even if Adrian’s site _is_ a blog.

This lead to me to follow [Heydon Pickering’s advice on accessible menu systems](https://www.smashingmagazine.com/2017/11/building-accessible-menu-systems/) when we developed the work site last year:

> Where a site has a lot of content, a carefully constructed information architecture, expressed through the liberal use of tables of content “menus” is infinitely preferable to a precarious and unwieldy dropdown system. Not only is it easier to make responsive, and requires less code to do so, but it makes things clearer: where dropdown systems hide structure away, tables of content lay it bare.

As you’ll see, the top level menu is eniterly flat. In the spirit of this refusal to hide content behind disclosure widgets, you’ll also see as many navigation items as your screen’s width will allow:

{% include figure.html url="sl-nav-mid.jpg" alt="Screenshot of the Suffolk Libraries website navigation menu." caption="No dropdowns or hamburgers. Note the main content consists of a task menu." %}

Feedback and testing have revealed no problems with this approach – it appears users are happy to burrow into tables of content several levels deep, as long as the trail is clear enough.

{% include figure.html url="sl-table-of-contents.jpg" alt="Screenshot of a signposting page of 3 card options on the Suffolk Libraries website." caption="The “Borrow” page on the Suffolk Libraries website. Users are presented with a table of contents presented as a set of cards." %}

However, I can see possible benefits in implementing dropdown menus well:

* Increased discoverability of subsections of a website
* Confirmation of a website section’s content without having to click through to that section
* Efficiency for users familiar with the navigation menu, where dropdowns serve as a shortcut to the content they’re interested in

I am, on the whole, very happy with using a flat, signposting system for website navigation, but what are your opinions? Do you see a use for dropdowns?