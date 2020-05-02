---
title: Improving where filters in Jekyll
category: web
description: "Use Jekyll's where_exp filter to filter for conditions such as falseness. This will speed up build times and make it easier to develop more complex, useful array filters."
---

The Liquid `where` filter selects items from arrays so you don't have to loop through an entire set. In Jekyll this is useful for creating things like category listings, as well as cutting down on site build times.

So you might output a list of all posts in the `web` category like this:

{% include gist.html gh-user="anonymous" code="8d2645653d90a3d913d0f6015b101cbd" %}

That's good, if a little restrictive. `where` only lets you filter for conditions where something equals something else (in this case where the category equals web).

There are times when you might want to filter for all articles _not_ in the `web` category. For this, you need the `where_exp` filter.

`where_exp` lets you use expressions and operators in filters, such as `or`, `and` and `!=`, so you could also use it to filter for all posts in the `web` and `libraries` categories. Here's how you filter for everything not in the `web` category:

{% include gist.html gh-user="leonp" code="cc546c1e83f977aca30767bc68131ded" %}
