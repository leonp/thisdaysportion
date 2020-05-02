---
title: "In defence of view page source"
category: web
img: lp-source.jpg
alt: The source code of leonpaternoster.com shown in the Firefox browser
article: true
---

Ever late to the web discussion party, I read [CSS Tricks’ hardline stance on <i>View Source</i>](https://css-tricks.com/view-source/), where Chris argues he’d be happy to get rid of it because you can glean more info about a page from dev tools.

{% include figure.html url="view-source.jpg" alt="The Firefox right-click menu in OS X with View Source highlighted" caption="View page source is just a right-click away" %}

While this is true, I think <i>View page source</i> offers a quick glimpse into the document author’s (or designer's) mind; what they consider important, what they’re good at, what they’re not good at, even their “ethics” (assuming the bastard hasn't inlined and minified everything, although even this suggests something):

{% include figure.html url="skinny-minified.jpg" alt="The source code from the Skinny Guardian website" caption="Skinny Guardian, inlined and minified. You can maybe make out a canonical link in the document head." %}

This is not information you'll get quite as readily from dev tools, which focuses on the page's granular, technical foundations rather than the way it's been authored. When you <i>View page source</i> you can figure out the author's "style" – how they indent their <abbr title="HyperText Markup Language">HTML</abbr>, any comments they've added, how keen they are on `divs`, whether they use classes, whether they overuse IDs and what approach (if any) they take to CSS. That's a lot of information from skimming a page:

{% include figure.html url="lp-source.jpg" alt="The source code from leonpaternoster.com" caption="Is that an unnecessary closing <code>div</code> I can spy?" %}

So, interpreting my page, you could perhaps conclude I generally employ the correct HTML elements (a possibly "proper" `b`, no less), use `divs` sparingly but practically (and erroneously), controversially use `abbr` with a `title`, use Tachyons (or some form of atomic <abbr title="Cascading Style Sheets">CSS</abbr> framework) and use a templating system that messes up indentation slightly. Or that I'm not overparticular about indenting. This _looks_ like a static site. As to what all this says about me, I'll leave up to you, but you can no doubt form a picture.

The document's `head` is always interesting, giving clues as to how <abbr title="Search Engine Optimisation">SEO</abbr>-crazy the author is, what software they use and some of what sort of "ethical" decisions I referred to earlier they've (not) made:

{% include figure.html url="lp-head.jpg" alt="The source for the head of leonpaternoster.com" caption="All that meta about me and the page" %}

What is my `head` telling you? Well, I'm using an HTML 5 `doctype` (this would have meant a lot more in 2010, admittedly) and I've added a `lang` attribute to the `html` element. This makes me a fairly good web citizen. Perhaps more interestingly, the `html` element also has a class fearlessly attached to it, which would perhaps suggest I'm using `rems` to size stuff, which, in turn, may suggest a certain CSS competency (of course, we're assuming I'm both document and template author).

Sometimes I self-close elements with <code> /&gt;</code>, sometimes <code>&gt;</code>. Again, this would have been contentious in 2010, although there is perhaps some interest in seeing the method authors choose. Actually, this just annoys me, as I hadn't noticed it. It indicates (quite rightly), that I've just been copying and pasting without editing. It's a bit lazy, sloppy even.

And then there's quite a lot of meta data. A [Twitter card](https://developer.twitter.com/en/docs/tweets/optimize-with-cards/overview/abouts-cards.html). There's also some [Dublin Core](https://en.wikipedia.org/wiki/Dublin_Core) stuff – perhaps I'm bothered about semantics, and making my site understandable to machine readers, or maybe I'm worried about its <abbr>SEO</abbr>. Or maybe some combination. I definitely must be a good guy – there's an <abbr title="Really Simple Syndication">RSS</abbr> feed there (several, depending on the page you're reading).

Finally, there's some indie web stuff: [webmention.io](https://webmention.io) and a [micro.blog](https://micro.blog/leonp) link. Does that make me an up to date, independent freethinker, or another middle–aged web bloke? You decide.

It's interesting investigating an author's style and choices from their source code – it's always one of the first things I do when I visit a designer or agency's website. Take a quick look behind the scenes to get an idea of what's really going on and the person (or machine) serving you words, pictures and layout. Although what this says about Twitter, I'm not sure:

{% include figure.html url="twitter-source.jpg" alt="The page source of Mobile Twitter consisting mainly of javascript" caption="This says something, but you'll need dev tools to find out what" %}
