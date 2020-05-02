---

category: web
title: Why we'll be using a CSS framework like Tachyons to rebuild our website
---

We're overhauling the work website, something I last did back in 2013. At the moment we use a WordPress theme built on the [Foundation CSS framework](http://foundation.zurb.com).

This has worked pretty well. In 2013 I had 3 main aims, which our set up helped us achieve:

- To rationalise a messy <abbr title="Information Architecture">IA</abbr>
- To make the site responsive
- To make it easy to build new pages and layouts

However, as the library service's needs have changed over the years, a few new problems have arisen:

- The IA needs updating again as we've added lots of new library services since the last rebuild. We're [doing a Liverpool](/2016/04/doing-a-liverpool/) to help solve this problem.
- The whole WordPress, theme, plugin, speed and security ecosystem has become difficult to manage. We'll be using [Jekyll to build the site](/2016/03/library-website-jekyll/) and [Netlify](https://netlify.com) to host it.
- Foundation helps us build pages quickly. However, it's quite an abstracted, opinionated framework with some gaps in its components &#8211; there's no [card pattern](http://tachyons.io/components/collections/text-card/index.html), for example. Because we have to override existing <abbr title="Cacading Style Sheets">CSS</abbr> and add our own components, we end up writing lots of new CSS, some of it documented, other parts not.

We did start to write our own framework, but, as the web team consists of just 2 people doing lots of different things, we decided against it:

- Good, <abbr title="Do not repeat yourself">DRY</abbr>, self-contained CSS is hard to write. Why try when there are lots of options already out there.
- Documenting CSS takes a long time. Obviously, we need good documentation when we build layouts and pages, as will anybody else who works on our website.

So we've opted for [Tachyons](http://tachyons.io), a lightweight CSS framework. We think it'll help us in several ways:

- It's got [good online documentation](http://tachyons.io/docs). Not only that, the class names are designed to be easy to scan and interpret in the <abbr title="HyperText Markup Language">HTML</abbr> &#8211; in other words, they actually form part of the documentation.
- Because it's not abstracted it's largely unopinionated, which means we don't have to write much new CSS. We'll build components like text cards exactly how we want them using the base CSS classes that come with Tachyons. We'll keep DRY by [referring to our component class chains in our HTML includes](/2016/04/tachyons-keeping-html-dry/).

We're adding and changing services at a pretty quick rate in Suffolk. Using Tachyons will help the website keep up, making the service easier to use online. That's the theory at least &#8211; we're in new territory here.
