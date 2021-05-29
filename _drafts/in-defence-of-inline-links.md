---
date: 2021-05-29 06:14:24 +0000
title: Some thoughts on why inline hyperlinks are better than print style references
category: web
sub: ''
mb-cat: "\U0001F58B"
hide-from-twitter: false
in_reply_to: https://daringfireball.net/linked/2021/05/28/quinn-devforums-markdown

---
Daring Fireball [argues that reference hyperlinks are more readable than traditional, inline hyperlinks](https://daringfireball.net/linked/2021/05/28/quinn-devforums-markdown).

Note, this article is about _writing_ links in Markdown, not reading a Markdown authored web page, and I don’t have any strong opinions on this – I’ve always used the inline method myself 🤷🏻‍♂️

However, the post reminded me that it’s possible to _render_ links in a Markdown document as what I’ll call _reference hyperlinks_. You don’t them in the wild very often. They mimic academic footnotes – a number in brackets after some text which links to a footnote at the bottom of your web page, which in turn will link to a source.

[This is an inline hyperlink](https://en.wikipedia.org/wiki/Hyperlink). You see hundreds of them every day. They’re more usable – and readable – than reference links, an epochal development in the construction of texts, possibly the main reason hypertext is more powerful than print.

Why? Well...

**Most web reading consists of skimming and scanning.** And links provide [good information scent](https://www.nngroup.com/articles/information-scent/). A well turned inline link provides more information to a scanner than a small number in a bracket.

But even if you are reading a longform text in a traditionally linear way, inline links are better.

**Inline links are more accessible.** Not only do they provide more information about what you’re linking to, they’re also easier to click/tap because they simply offer a bigger target.

**They’re easier to use.** With a reference link the reader has to click/tap a small area, find the relevant link at the bottom of the page and then follow it to its destination. That’s an extra couple of steps.

True, [you can create links within pages](http://www.echoecho.com/htmllinks08.htm), but these are problematic for a couple of reasons. Firstly, they’re counterintuitive – the expected behaviour of a hyperlink is to take you to another web page. Secondly, linking within pages is imprecise, unless the page author styles the target link carefully. The reader will most likely be sent to the footnote link’s general area, rather than to the link itself.

**Reference links belong in print.** We know exactly where the bottom of a print page is, but web pages are fluid and intangible. I can create a mental _model_ of a web page and its components by looking at the text and the scrollbar, but I don’t _know_ where the bottom of that page is. It might even move based on my actions, such as clicking on a [disclosure widget](https://adrianroselli.com/2020/05/disclosure-widgets.html).

More fundamentally, reference links belong in age where it’s unlikely I can simply check the reference immediately. Even if I do have the referenced text to hand, I’ll need to find the relevant page and paragraph. It makes sense to place them out of the way as footnotes, where they can be taken on trust, or checked another time.

Linked hypertexts are available immediately.