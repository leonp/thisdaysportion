---
title: "The perfect blogging platform: customising typography rather than theming"
category: web
date: 2021-05-22 15:10:00 +0000
sub: A good blogging platform would allow writers to fine tune their site’s typography, thereby removing the need code themes. Services like Pocket and Firefox Reader show how this approach might work.
---

A few more thoughts on what the perfect blogging platform could look like.

If writers can fine tune their site’s typography they won’t need to code WordPress-like themes. Services like Pocket and Firefox Reader show how this approach might work.

Recently I proposed [a few principles](/posts/some-blogging-platform-principles/), one of which is the freedom to choose a hosted or self-hosted set up. We want our publishers to be able to make the same choice they can with WordPress: either create a site at [wordpress.com](https://wordpress.com) or download the software from [wordpress.org](https://wordpress.org) and install it on their own server.

Unlike WordPress, I think the perfect blogging platform should avoid theming. There are a few reasons for this, the main one being _the platform should be for bloggers, not developers_. Allowing theming blurs the line between blogger and developer, and makes it more difficult to focus the platform’s design. Fewer technical choices will also make the platform easier to use.

(Of course, some of us like the coding part of our blogging platforms, but I’m sure we are in the minority.)

Without theming configuration and self-hosting would be more simple, although it’ll always involve some degree of technical expertise that’s beyond the remit of the platform. I envisage uploading a folder to a PHP-enabled server and visting the website one time to enter a few settings: no control panel or database required, and after this no further configuration to get up and running.

However, we do want authors to have some control over what their blogs look like. This is about more than expressing something through choice of fonts, colour, logo etc. The blog format should influence its typography. For example, a blog consisting of long form essays will perhaps require a different typeface, layout, measure and leading than a photoblog.

Focusing on typography over theming will be a unique feature of our platform. We’re concentrating on getting our text and images right for readers, rather than adding sliders, animations and other “unnecessary” features.

## What will our typography controls look like?

Handily, we already have examples of the UI controls we could use in our blogging platform settings. For example, here are Firefox’s reader mode widgets:

{% include figure.html url="firefox-reader.jpg" alt="Screenshot of the Firefox Reader UI options." caption="You can set colours, typeface, line height, size and column width in Firefox’s reader view." %}

We’d offer more options, but you get the idea. By controlling typography and limiting the site’s purpose to a blog, we can offer all the customisation that normally requires theming. Writers won’t have to code.

## What controls will we offer?

### Typeface

An obvious one. If we’re using freebies from Google Fonts we want to i) load them from our blog rather than Google and ii) limit the selection to the good stuff. So for serifs that would probably be IBM Plex Serif, Source Serif Pro, Libre Baskerville, Literata and Noticia Text. For sans serifs, let’s go for Public Sans, Roboto, Source Sans Pro, Ubuntu, Rubik and Fira Sans. You may like other typefaces, but the point is we want to be opinionated here, demonstrating some form of expertise and judgement.

We also want to offer system fonts for the sake of speed.

Finally, our platform should allow for a body copy typeface and a secondary choice for headings and ancillary text, such as datelines and captions, should the author want one.

### Layout

Fairly simple this, I think. We’ll offer a single column or a content/sidebar combination when the screen width allows it. We’ll be able to place the sidebar to the right or left.

We’re not going to put any WordPress-like widgets in the sidebar, just the site branding, navigation menu and a description.

### Colour

A few options here:

- **Background and foreground colours**. Writers will be able to set light and dark modes, if they want them, which means a couple of choices here. Our platform will alert the writer if the background/foreground contrasts don’t meet WCAG standards.
- **Links, link underlines and visited states**. CSS can be pretty creative when it comes to link styling, so we should allow plenty of options here.
- **Accent and brand colours**. Perhaps apply these to a rule at the top of the page, headings, titles and other configurable options.

### Micro typography

The real nuts of bolts of reading. What’s really powerful here is that we can experiment with typefaces and our micro typography to find the best combination for reading. For example, a typeface’s [x-height](https://en.wikipedia.org/wiki/X-height) should affect its leading and measure – writers can tweak the settings until their site _feels_ right. Again, we’re going to be opinionated and warn authors when their choices may affect the readability of their text (when we have a narrow leading combined with a wide measure and large x-height, for example).

The three main micro typography settings are measure (article column width), leading (the space between lines of text) and size. Note, size provides a base value we use to calculate all element proportions, from captions to subheadings and titles. We could perhaps offer a choice of type scales – the [whole lingo of majors, minors, thirds, fifths etc.](https://type-scale.com/) perhaps suits the platform brand that’s beginning to form.

I think the perfect blogging platform should focus on writing rather than coding, even if it’s fun tinkering with the inner workings of your website. But writers should be able to control the appearance of their blog, if they want to – the default settings will be perfectly usable. By allowing lots of typographical customisation, we may have found a way to keep things simple *and* configurable.







