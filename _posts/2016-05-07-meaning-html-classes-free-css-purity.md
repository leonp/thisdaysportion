---
title: Meaning, separation and using lots of classes freely
category: web
---

[This article feels like the end of an era](https://alistapart.com/article/meaningful-css-style-like-you-mean-it), the last hurrah for a flawed way of thinking about how we should build websites. Those of us who remember the <abbr title="Cascading Style Sheets">CSS</abbr>/tables wars perhaps feel a nostalgic tug towards something more "semantic" than presentational classes. Perhaps we feel all those divs and classes are somehow polluting our markup. But that misunderstands the whole point of keeping everything separate and therefore more organised, manageable and, yes, semantic.

<hr>

A standard <abbr title="HyperText Markup Language">HTML</abbr> element can do three discrete things. Take this example:

`<header role="banner" class="pa2 bg--light-grey f3">Some content</header>`

- The `header` element tells the user agent that the content between the `<header>` tags will contain some introductory information _about_ the following content  (e.g. a logo indicating ownership, some navigation or time of publication)
- The `role` attribute tells the user agent that _this_ `<header>` relates to the whole website rather than the content just on this page. It also serves as a navigational landmark to a screenreader.
- The `class` attribute refers to classes we define in some related CSS or javascript. In this case it's telling any user agent to apply some padding, a background colour and a defined font size when this `<header>` element is displayed on a screen.

This combination of elements and attributes gives our content meaning and structure in different contexts. Once we start using the wrong element for the wrong purpose we risk breaking each element's intended purpose. By leaving the `role` attribute out of our CSS we make sure we don't start using <abbr title="Accessible Rich Internet Applications">ARIA</abbr> roles to change the colour of things rather than aid accessibility.

Conversely, we don't have to start wrangling our CSS when we want to style elements with the same ARIA role differently. Classes offer by far the most flexible, easy to manage way to control appearance.

This separation of concerns is at the heart of CSS. We like "semantic" and "meaningful", but we we place "presentational" in false opposition. Of the three elements of meaning in our HTML, appearance is as important as the others &#8211; most users will be accessing our content with a visual browser.

## But all those divs and classes are messy

Yes, they can be. But that's not an objection <i>per se</i>. Messiness is a consequence of poorly organised CSS. That's why I'm starting to use frameworks that tie class names directly to CSS properties. Once you normalise your HTML and use fewer abstract constructions (panel, card etc.) the less `divs` you need: you can go ahead and add classes to `sections`, `articles`, `uls`, `lis` and `footers` with no problems at all. Take this (admittedly simple) site. The only time I use a `div` is to wrap post content after the post header &#8211; and you _could_ argue there should be an HTML element for that.
