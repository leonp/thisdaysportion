---
title: "Using a sound CSS methodology (you might call it a framework) is a good thing"
category: web
article: true
description: "There are different types of web development frameworks. Overly opinionated frameworks like Bootstrap and Foundation can prove inflexible, &#8220;uncreative&#8221; and inefficient, but modular efforts such as Tachyons make writing manageable code a lot easier &#8212; and they don&#8217;t stifle creativity."
featured: true
---

[Smashing Magazine asked a common question](https://mobile.twitter.com/smashingmag/status/898222789613715463) in web development circles: _Do you use a framework?_ Interestingly enough, I guess, about 60% of respondents do use a framework, and a whopping **42% of all respondents use Bootstrap** (!)

[Sara](https://www.sarasoueidan.com/) tweeted a popular response:

> Never used any frameworks, never will. Writing CSS from scratch is one of the best pleasures of building front-ends in my opinion. ✨ <cite><a href="https://mobile.twitter.com/SaraSoueidan/status/898234232195174400">@SaraSoueidan</a></cite>

I _sort_ of agree with this (it's an opinion about what Sara enjoys, after all, so who am I to disagree anyway -- and she's a far more talented developer than me, to boot), but I would question the efficiency of _never_ using a set of repeatable classes for web projects (let's steer clear of the term <i>framework</i> here).

Something like [Bootstrap](http://getbootstrap.com/), no. I used [Foundation](http://foundation.zurb.com/) for a while on the work website and did find I ended up either overwriting loads of CSS because it was so opinionated, or I had to write new CSS for the components it didn't have. It was a mess.

However, I use [Tachyons](http://tachyons.io) now (this statement always makes me think &#8220;[I drink Yorkshire Tea now](https://www.youtube.com/watch?v=24N7GMk2Byo)&#8221;), and couldn't imagine building web pages without it. Not because it makes it easy for me to style a card or jumbotron predictably; no, **Tachyons saves me time and brainache**. It makes sketching ideas and developing them into finished <abbr title="User interface">UI</abbr> really quick. It's smaller, more efficient and faster than any CSS I could write because it's nearly completely unopinionated and ruthlessly <abbr title="Do not repeat yourself">DRY</abbr> and unspecific.

In fact, Tachyons (or any other modular or atomic framework) isn't really a framework in the way Bootstrap is. **There are no cards, jumbotrons or media components**, just a terse class notation that maps more or less directly to CSS properties and values. I think of it more as a methodology, [a way of implementing and managing HTML and CSS in a fast, sane way](http://mrmrs.github.io/writing/2016/03/24/scalable-css/).

Which is why I'd question anyone who didn't use _some_ sort of framework, even if it's their own. Writing efficient, manageable CSS and HTML is difficult. How can you do this starting with a completely blank canvas on every project? Why would you _want_ to do this?

## But frameworks are uncreative/not fun/stop you learning properly

All these statements are true. The only way to understand concepts such as the cascade and specificity, and to wrangle CSS and HTML into the UI you want, is through coding CSS and HTML. Anyone who started building web pages when I did is at an advantage in this respect: back in 2007 frameworks didn't exist; we had to write millions of lines of <del>unintelligible spaghetti</del> handcrafted markup and styles.

If you use something like Bootstrap you don't need to know how CSS and HTML work together. Just as I can use javascript by installing a jQuery plugin. But my javascript and Bootstrap's output is verbose, inflexible and always looks the same. The moment I want to do something different with it, I'm stymied. So yes, it's not "fun" or particularly creative (but it does work, albeit inefficiently.)

To use Tachyons you still need to know what properties and values do. The `dib` class won't be of any use unless you understand what `display: inline-block` does. Tachyons isn't abstracting away the building blocks of UI; it's just [making them quicker and easier to use](/posts/design-habits/).

Sara is right: each project _may_ demand its own UI. The reason that automated website builders like Squarespace soon become too limiting is that they don't allow for this flexibility. For 90% of simple, brochure sites they're fine; for anything else they're maddening. Bootstrap is the Squarespace of frameworks, but Tachyons is lego. Whatever UI you need it'll help you build it -- quickly. And you'll be able to manage it as it grows.
