---
title: Developing a static library website using Jekyll, Netlify and Zapier
img: ss-slaughter.jpg
alt: A screenshot of events from the Suffolk Libraries website
excerpt: "I migrated the Suffolk Libraries website from a WordPress backend using a theme built on the Foundation framework. We moved to a static website built on Jekyll and hosted by Netlify. The site is faster, more stable and more secure, yet it still handles dynamic features such as events and forms."
summary: "I migrated the Suffolk Libraries website from a WordPress backend using a theme built on the Foundation framework. We moved to a static website built on Jekyll and hosted by Netlify. The site is faster, more stable and more secure, yet it still handles dynamic features such as events and forms."
description: "A static website may sound dull, but it&#8217;s faster, more stable and more secure than a traditional website. The Suffolk Libraries site also does dynamic stuff like events, searchable maps and locations through the power of some smart programming and APIs."
category: work
---

## Overview

I migrated the [Suffolk Libraries website](https://www.suffolklibraries.co.uk) from a WordPress backend using a theme built on the [Foundation framework](http://foundation.zurb.com/). We moved to a static website built on [Jekyll](https://jekyllrb.com) and hosted by [Netlify](https://www.netlify.com). The site is [faster](https://tools.pingdom.com/#!/bKE8SD/https://www.suffolklibraries.co.uk/), more stable and more secure, yet it still handles dynamic features such as events and forms.

## Benefits (the why)

Running a WordPress site had become difficult for a small team. We had to buy, maintain and manage plugins to make the site secure from hackers and fast enough for our users.

At the same time I’d started to use Jekyll, a static site generator that builds your complete website locally for uploading to a server, or, better still, deployment via Github pushes. Jekyll sites are extremely fast because there are no database calls and page builds involved: your pages are served as is. They’re also inherently stable and secure because they’re just HTML, CSS and javascript. There are No SQL or PHP vulnerabilities, no 500 errors.

## Process (the how)

I exported content from WordPress into [Markdown](https://en.wikipedia.org/wiki/Markdown) files using a Jekyll plugin. With our content in an open, convertible format, the work could begin.

### HTML and CSS

Jekyll has a [SASS](http://sass-lang.com/) workflow built in, which I use to write `scss` partials. I use [Bundler](http://bundler.io/) to keep all our Ruby dependencies in shape.

I also moved from the overly-opinionated Foundation framework to a more modular library called [Tachyons](http://bundler.io/). Tachyons just does CSS, and avoids building complex modules such as cards and call-outs. Instead, it takes a low level, ‘atomic’ approach: classes mostly map to single CSS properties, so the `db` class is `display: block`.

This approach results in faster, easier to manage CSS. You can read HTML and tell exactly what the classes are doing. It’s also small and fast, weighing in at around 14k minimised: there's no redundant javascript slowing things down.

Read more:

- [Using presentational classes makes web design easier](/2016/05/presentational-css-efficient-designing/)
- [Why we'll be using a CSS framework like Tachyons to rebuild our website](/2016/04/why-use-tachyons-css-framework/)


### Dynamic features

Most library content doesn’t change over time, and edits are relatively simple. A library might change its opening hours, which we could reflect by editing a Markdown file and pushing it to [Github](https://github.com).

However, some content is more dynamic. For example, our libraries run dozens of events every week, but we don’t want them appearing on the website once they’ve passed. Implementing dynamic features requires some lateral thinking, and some automation on your server.

Read [Coding one off and recurrent events in Jekyll](/2016/07/jekyll-events-static-site-libraries/) to see how I got the site to display events based on time.

The automation is handled by our host, Netlify, which specialises in static sites. Netlify has a smart API which works with [Zapier](https://zapier.com) to do all sorts of clever things, including firing site build requests early in the morning to update all our dynamic content.

The Netlify Zapier connection also offers other features you’d normally only expect from a dynamically hosted site. For example, we can send form submissions to Google Sheets, and automate email replies, without hosting SMTP scripts or databases.

### A sane workflow

The other great benefit of running a static site on Netlify’s servers is its tight integration with Github. This means we can roll back commits and manage the site from a local, Github command line.

This makes it easy (and reliable) to share, stage and publish changes, something that can be difficult in a WordPress workflow. There’s something very satisfying about typing `git push` and seeing your live site update.

Because the site is on Github it’s also automatically backed up and easy to roll back if there are problems. We can also share it with the public, and deploy it locally on any PC within minutes.

## Conclusion

Running a static, Netlify hosted website brings many benefits:

- A fast user experience
- A stable, secure hosting environment
- Zapier powered dynamic features
- Github versioning and back-ups

I’d recommend it for sites that don’t require a huge amount of dynamic content; local and central government organisations, for example. **If you’re interested in building a fast, secure static website with dynamic features, contact me**:

- [@leonpaternoster](https://twitter.com/leonpaternoster)
- [LinkedIn profile](https://uk.linkedin.com/in/leonpaternoster)
- leon.paternoster@zoho.com
