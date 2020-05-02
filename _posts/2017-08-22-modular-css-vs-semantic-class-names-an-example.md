---
title: "Why modular CSS is better than using &#8216;semantic&#8217; class names: An example"
category: web
description: "At the risk of banging on, modular (or functional, or atomic) CSS isn&#8217;t the same as opinionated frameworks such as Bootstrap. By using small CSS class names tied to appearance you&#8217;ll save time and effort, speed up your site and maintain control over its appearance."
article: true
featured: true
---

I recently wrote (another) post on why [using a modular (or atomic) HTML/CSS framework saves time and effort](/2017/08/frameworks-and-methodologies/) when you're building web stuff. Judging from [the response on Twitter](https://mobile.twitter.com/leonpaternoster/status/898558923753619456), some people simply like _handcrafting_ their CSS (I'm coming to dislike that term), rather than &#8216;restricting their creativity&#8217; through using a framework.

I'll repeat: **using a modular framework allows complete control over your styles**. It'll also make your CSS quicker and easier to update than restricting yourself to more &#8216;semantic&#8217; class names. Objections based on creativity are founded on a misunderstanding. **Don't conflate modular CSS with frameworks like Bootstrap and Foundation**, which foist a whole set of styles on you.

## An example

Back in 1824 I wrote a post about [using some newspaper writing techniques on the web](/2008/07/6-newspaper-writing-techniques-for-the-web/). One of the techniques I looked at was using a _standfirst_; a short, summative paragraph at the top of an article. Standfirsts can help readers make a judgement on whether it's worth reading on, and I've started using them again.

In 1824 I would have used a &#8216;semantic&#8217; class name and attached a bunch of styles, like so:

HTML:

<div class="bg-black light-green ph2 ph3-ns pt2 pt3-ns">

    {% highlight html %}
    <p class="standfirst">There are different types of web
    development frameworks. Overly opinionated frameworks
    like Bootstrap and Foundation can prove inflexible,
    “uncreative” and inefficient, but modular efforts such
    as Tachyons make writing manageable code a lot easier
    — and they don’t stifle creativity.</p>
    {% endhighlight %}

</div>

CSS:

<div class="bg-black light-green ph2 ph3-ns pt2 pt3-ns">

    {% highlight CSS %}
    .standfirst {
        font-size: 1.25rem;
        margin: 0;
        font-weight: bold;
    }
    {% endhighlight %}

</div>

Everyone's happy, no? My paragraph has been imbued with meaning through the use of a class name, while I can make changes to the standfirst's appearance through finding its class name in my stylesheet and changing properties and values. Concerns have been separated, creativity maintained.

### Faster (and yet safer) style changes

Except&hellip; this way of changing the appearance of things is pretty inefficient. Let's say someone else comes along and wants to change the block of text at the top of an article. She has to do the following:

- Open the HTML file.
- Open the correct CSS file. What's a _standfirst_? Which SASS file will she find the class name in? `grep` _standfirst_.
- Find the relevant CSS within the CSS file. Make changes and refresh browser. Assume she wants to change all other uses of the `standfirst` class across the website in exactly the same way. Repeat.

The author has made things unnecessarily difficult for future developers (and themselves -- they'll still need to shift back and forth between HTML and CSS files even if they know where everything lives).

Here's how you'd markup the standfirst using a modular framework like Tachyons:

<div class="bg-black light-green ph2 ph3-ns pt2 pt3-ns">

    {% highlight html %}
    <p class="f4 b ma0">There are different types of
    web development frameworks. Overly opinionated
    frameworks like Bootstrap and Foundation can prove
    inflexible, “uncreative” and inefficient, but modular
    efforts such as Tachyons make writing manageable
    code a lot easier — and they don’t stifle creativity.</p>
    {% endhighlight %}

</div>

And if the same developer wants to change the standfirst? Here's the process:

- Open the file and change `f4 b ma0`. Refresh browser and repeat.

That's it. There's no CSS to edit, and the change will only affect this file. Furthermore, she'll have a good idea what `f4 b ma0` means and how to make changes _without referring to any documentation_. Once she knows the basics of the notation, she'll know that removing the `b` will get rid of the bolding, for example. This is a lot quicker than editing a `font-weight` declaration in a separate file.

(Did you play along at home? It's font size 4 in our scale, bold, margin zero, which maps pretty directly to our `.standfirst` CSS.)

Note: I haven't used a standfirst component (or whatever the Foundation or Bootstrap equivalent is), so no-one's imposed _their_ idea of a standfirst on me. I have complete control of its look.

### Drier CSS

When using a semantic class name, we applied the following styles:

<div class="bg-black light-green ph2 ph3-ns pt2 pt3-ns">

    {% highlight CSS %}
    .standfirst {
        font-size: 1.25rem;
        margin: 0;
        font-weight: bold;
    }
    {% endhighlight %}

</div>

Let's say we also want to style important statements. The HTML is similar, and we can use something like an `emphasised-statement` class (semantics are easy to stretch out of shape):

<div class="bg-black light-green ph2 ph3-ns pt2 pt3-ns">

    {% highlight html %}
    <p class="emphasised-statement">I repeat: Opinionated and modular
    frameworks are very different beasts.</p>
    {% endhighlight %}

</div>

And I'll use this CSS:

<div class="bg-black light-green ph2 ph3-ns pt2 pt3-ns">

    {% highlight CSS %}
    .emphasised-statement {
        font-size: 1.25rem;
        margin: 0;
        font-weight: bold;
        padding-left: 1rem;
        border-left: 0.25rem solid purple;
    }
    {% endhighlight %}

</div>

Now, we can achieve the same effect with our modular system (with `<p class="f4 ma0 b pl4 bl b--purple bw3">`, for example) and make our styles a lot easier to update and control.

Then compare the two semantic classes -- you'll see they share several properties:

<div class="bg-black light-green ph2 ph3-ns pt2 pt3-ns">

    {% highlight CSS %}
        font-size: 1.25rem;
        margin: 0;
        font-weight: bold;
    {% endhighlight %}

</div>

This isn't very [DRY](https://code.tutsplus.com/tutorials/3-key-software-principles-you-must-understand--net-25161). On any large scale site, think about the number of times you might write something like `margin-bottom: 1em` even if you're only creating the class names you need for the job in hand. In modular CSS it's written one time only, thereby making your CSS lighter through not repeating the same declarations. I'm willing to bet that on any medium to large size site whole modular CSS frameworks are smaller than any handcrafted stylesheet, even before you start filtering the CSS subsets you don't need.

### But this isn&#8217;t very semantic

Class names aren't meant to be semantic; they mean nothing to machines. They're meant to aid styling. However, as appearance aids meaning&hellip;

If by _semantic_ you mean machine-readable, you should [use a schema](http://schema.org/BlogPosting) instead.

### Conclusion

I'm not telling anyone to do things in a certain way (honest!) On small sites I think you can merrily use semantic class names and keep it manageable -- I did it for about 7 years on this site. On bigger sites with more than one author, probably not.

However, I do think some developers lump Bass CSS and Tachyons with Foundation and Bootstrap, which is a mistake. Modular CSS _does_ provide a way to build web UI quickly and sanely; if you're not already doing so, you should at least look into the idea.
