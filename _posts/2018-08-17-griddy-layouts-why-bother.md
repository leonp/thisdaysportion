---
title: "If users aren’t bothered about griddy layouts, why are we?"
category: web
layout: post
article: true
featured: true
---

Hidde de Vries posted some excellent thoughts on [not bothering with complex CSS fallbacks for older browsers](https://hiddedevries.nl/en/blog/2018-08-11-lets-serve-everyone-good-looking-content) (in this case when using CSS grid):

> I don’t think we owe it to any users to make it all exactly the same. Therefore we can get away with keeping fallbacks very simple. My hypothesis: users don’t mind, they’ve come for the content.

Granted, what we mean by "content" is vague. A blog post is different from a list of trainers, which _may_ require a more complex layout than a single column. But what always strikes me about these types of posts (which have been [written for years](https://jonikorpi.com/leaving-old-IE-behind)) is that they don't take the obvious next step and recommend ditching complex layouts altogether.

**If users don't care about a complex layout then why should the people making web pages? Why do we bother creating griddy layouts at all when it means more work and more code?**

(Actually, [a few designers have argued just this](http://www.heydonworks.com/article/on-writing-less-damn-code).)

Hidde acknowledges the main reason for implementing grids is to keep on-brand: <q>Some brand design guidelines come with specific grids that content needs to be layed [<i>sic</i>] out in.</q> In other words, it's not users who demand grids, but marketing departments.

But that's not a good reason, and something designers should resist. You _could_ argue for making things look fancy for their own sake by referring to [the world of advertising](https://www.newstatesman.com/science-tech/internet/2018/07/death-don-draper). Companies still pay for display adverts and TV spots because they communicate something about the the "brand" beyond its content and price. They don't want to look cheap, and nor does your website:

> &hellip; an ad can emit a powerful signal about a brand, regardless of information content. Online ads are cheap and easy to make, but the problem is, they look it.

But this is by the by. Even if we accept the Don Draper logic, a simple layout doesn't have to look cheap. If your user is happier with plainer then that's a good business reason for keeping it simple. Online, the interface is the brand, and your testing and feedback should dictate the layout you implement.

<hr>

Note: That's not a reason to discard CSS grid <span role="img" aria-label="A saintly smile">😇</span> – I don't mean to conflate a CSS technique with a type of layout. _Any_ layout is quicker and easier to implement in CSS grid than by using floats, an age old CSS hack.
