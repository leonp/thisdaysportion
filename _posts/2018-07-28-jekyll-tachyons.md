---
title: 'Jekyll Tachyons starter theme for Jekyll'
layout: post
category: work
excerpt: "Jekyll Tachyons is a skeleton theme for Jekyll that makes it easy to get up and running with the Tachyons CSS framework. Prototype layouts quickly while minimising, inlining and selecting the CSS you use."
featured: true
---

[Jekyll Tachyons](https://github.com/leonp/jekyll-tachyons) is a starter theme for Jekyll that makes it easy to:

- get started on a Jekyll project using the Tachyons CSS framework
- remove unwanted Tachyons modules from your project, thereby reducing your CSS payload
- choose to inline your styles in the document `head` or refer to a stylesheet, perhaps saving an additional request for a file and getting your ‘critical’ CSS served as soon as possible
- set custom CSS breakpoints for `-ns`, `-m` and  `-l`

[Get Jekyll Tachyons on Github](https://github.com/leonp/jekyll-tachyons)

## Why use Jekyll Tachyons?

If you use Tachyons and Jekyll a lot it’ll save you time and effort setting up new projects. I’ve used it on a couple of projects (and to tidy up the work website):

- [leonpaternoster.com](https://www.leonpaternoster.com)
- [Adventures of Sherlock Holmes](https://adler.netlify.com)

It’ll also make it easy to remove unnecessary CSS. Tachyons is small (weighing in under 14k gzipped), but it’s still worth removing any CSS you don’t need, especially if you’re not gzipping.

If you’re obsessing over performance you might appreciate putting your CSS in the document `head` rather than referring to an external stylesheet.

As for Why use Jekyll and Tachyons?.. I’ve written about [why I use Tachyons full stop](/posts/modular-css-vs-semantic-class-names-an-example/), but this also provides a really quick and  easy way to prototype HTML pages that share components such as a header and footer. Just edit your header and footer files in the Jekyll `_includes` folder and you’re away. All depends on how you work, of course, but I like getting into the browser as soon as possible.

## Todo

- Update to the latest Tachyons
- Improve the docs

If you’ve got any questions/comments/bugs raise them on Github or contact me via Twitter or at leon.paternoster@zoho.com
