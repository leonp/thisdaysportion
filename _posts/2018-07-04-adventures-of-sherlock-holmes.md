---
title: 'The Adventures of Sherlock Holmes in HTML'
layout: post
category: work
featured: true
excerpt: "Read the twelve classic Sherlock Holmes stories in perfectly formatted, quick-loading HTML on any device with a web browser. You can also bookmark your place in the text."
---

{% include figure.html url="twisted-lip.jpg" alt="Black and white pen sketch of Holmes sat on some cushions smoking a pipe." caption="Original Sidney Paget illustration from <cite>The Man with the Twisted Lip</cite>" %}

I made a website from the 1892 Sherlock Holmes collection <cite><a href="https://adler.netlify.com">The Adventures of Sherlock Holmes</a></cite>. 12 stories, some of which you may well recognise, originally published in serial form in <cite>The Strand</cite> magazine.

I'm not a huge Holmes fan, but these stories provided a few minutes' Victorian pleasure. It can be fun reading Doyle's character between the lines; protestant, conservative, anti-royalist, a streak perhaps of non-conformism, some romanticism. They _have_ generated some excellent pastiches and adaptations: the best probably being Anthony Burgess' <cite><a href="https://en.wikipedia.org/wiki/The_Devil%27s_Mode">Murder to Music</a></cite>, along with some of the Cumberbatch and Freeman BBC episodes.

So, bearing in mind my slightly _meh_ attitude to the books, and the fact you can easily download them for free, why do this?

## HTML is the best format for online books

What I mean is: I like the idea of navigating to a website and starting to read. You don't need a new device or software; just your browser and a phone, tablet or PC (assuming the text's been responsively styled). Pick up your reading at any time from another device.

The Sherlock Holmes stories seemed just right for this. They're short (most can be read in 15-30 minutes), not too high brow and are freely available in pretty decent HTML on Gutenberg. Victorian readers would have bought the magazine every month; in a better world, you could possibly see modern readers subscribing via RSS, and reading each new episode in their RSS software (another advantage: HTML is infinitely portable). An attentive reader could also start (cross)referencing via the magic of hyperlinks to create all sorts of interesting rabbit holes.

## The technical challenge

Behind the scenes I'm using my normal technical stack: Jekyll, Tachyons, Github and Netlify. The stories are broken down into a chapters collection, which can be used to automatically generate a table of contents, and to split the stories into separate pages. Disappointingly, I discovered only the first story, <cite>A Scandal in Bohemia</cite>, is divided into chapters, so this wasn't really necessary, and reading is actually easier if you _don't_ split the text up into separate pages. Who knew -- scrolling is better on a screen than flipping, although this may not apply if you were HTMLifyimg <cite>War and Peace</cite>.

(The table of contents did mean I got to use my favourite HTML elements, `details` and `summary`: semantic and accessible toggable content in pure HTML, I've no idea why these aren't all over the internet.)

You can bookmark your place in the text by clicking on the `#` sign that appears when you hover over a paragraph. Unfortunately, the (excellent) [anchor.js](https://www.bryanbraun.com/anchorjs/) doesn't work particularly well on mobile; so much so I've decided to hide (as in `display:none`) anchors on narrow screens. I may take [Dmitry Fadeyev's approach](http://leonidandreyev.com/judas-1/) and add a bookmark toggle to the page so that anchors are either visible or not, regardless of the device. If you are reading across devices you'll also need to use a cloud bookmarking service (Firefox has one baked in). This isn't perfect, but it's keeping it no-login-required pure <span role="img" aria-label="Cheery face">☺️</span>.

(Note to self: this could be a good time to look into some sort of AWS integration for generating bookmarks on the fly.)

I've also been using a very simple "framework" I made a few months back. [Jekyll Tachyons](https://github.com/leonp/jekyll-tachyons) creates a basic Jekyll site complete with the Tachyons framework. Most interestingly, you can choose to place styles in the document `head` or in a separate stylesheet, and pick and choose the Tachyons modules it loads. I'm also using it on this site.

There are lots of possibilities here. I could index the text with Algolia to make it searchable and somehow categorised. If only I had the time to look into the potential of plain HTML and text.

- [The Adventures of Sherlock Holmes](https://adler.netlify.com)
- [Jekyll Tachyons framework](https://github.com/leonp/jekyll-tachyons)
