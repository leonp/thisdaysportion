---

title: Using presentational classes makes web design easier
category: web
---

I wrote about [how using purely presentational classes in <abbr title="HyperText Markup Language">HTML</abbr> is a good thing](/2016/05/meaning-html-classes-free-css-purity/), how they help align your HTML attributes and tags to their intended purpose.

So what's it like actually using a low level, non-abstracted <abbr title="Cascading Style Sheets">CSS</abbr> framework like [Tachyons](http://tachyons.io)? Does it make designing (i.e. building web pages for a specific purpose) any more efficient?

We've been building the new work site using Tachyons, so we've now got some 'real life' experience. First impressions are good.

Why? Well, the reason's quite subtle: it's to do with the amount of brow-furrowing it removes, or how you _feel_ writing your HTML. It's like when a designer gets font size, line height, measure and white space right to make reading from a screen easier. There's less effort and stress.

When you use presentational classes you're styling the thing on the page in front of you in a predictable way. So typing `mt0` in your HTML has an immediate effect: the thing you're adding it to will have a top margin of 0. There's no translation, reference or counter-intuitiveness; instead, there's a direct relationship between writing and its effect.

When you use an abstraction (such as `panel`) you're removing the predictability as you can't tell what the top margin is without referring to your CSS or by opening an inspector. If you style something like an <abbr title="Accessible Rich Internet Applications">ARIA</abbr> role, or a 'semantic' class like `entry-content`, you're making things difficult in 3 ways:

- Again, you can't tell what the class/attribute actually does to an element
- You're styling things elsewhere, or that don't even exist yet
- You might want to style something else in the same way but which doesn't have the same 'meaning'

We lost this intuitive element of design when we ditched (quite rightly) elements like `font`. We could no longer decide <i>I want to make that text red</i> and make it red straight away. Conversely, if someone looked at our HTML they couldn't tell what the classes actually did.

We decided to try and make classes mimic and augment elements, rather than simply do their more natural job of determining what an element looks like.

_The appearance of your web page is no less important &#8211; or less meaningful &#8211; than its 'semantics'_. In fact, these little, presentational classes define a page's meaning for users with a visual browser.
