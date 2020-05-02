---

title: An aside really isn’t a sidebar
category: web
---

One of HTML5's structural tags is `aside`. I must admit to liking this one as soon as I found out about it; it seemed to promise a way of adding a little writerliness to blog posts, even a little depth. On a practical level, it could help authors supply supplementary or tangential information within their documents. One of the best uses of asides (not the actual tag itself) can be found on [Jon Tan's site](http://jontangerine.com/log/2008/02/designer-php-a-dynamic-menu-with-if-and-else).

At least that's what I thought an aside was. And the dictionary agrees with me:


> a temporary departure from a main theme or topic, esp. a parenthetical comment or remark; short digression [Dictionary.com](http://dictionary.reference.com/browse/aside)


However. Here's the HTML5 spec:


> The aside element represents a section of a page that consists of content that is tangentially related to the content around the aside element, and which could be considered separate from that content. Such sections are often represented as sidebars in printed typography.

The element can be used for typographical effects like pull quotes or sidebars, for advertising, for groups of nav elements, and for other content that is considered separate from the main content of the page.

It's not appropriate to use the aside element just for parentheticals, since those are part of the main flow of the document. [HTML5 specification](http://dev.w3.org/html5/spec/Overview.html#the-aside-element)


The problem here is that the spec stretches the natural interpretation of what an aside is, i.e. a _short, temporary digression_. Blogrolls and other side content on a blog are not short or temporary, or even necessarily tangentially related to the main content.

An aside is a conversational digression, and belongs solely within an `article` or `section` tag, not independent of it. Without a surrounding `article` or `section` there's nothing to digress from.

A sidebar could easily be represented by an, erm, `sidebar` tag. If we allow equally presentational tags such as `header` and `footer`, then it makes no sense to disallow `sidebar`. All of these tags serve a semantic function, even if their names are rooted in their appearance on the page (especially when they're so prevalent on web pages). A sidebar simply serves as a container for content outside of the main article.

![A Guardian story about Tony Blair with a sidebar containing a related account of a parliamentary session](http://s3.amazonaws.com/giles/newspaper_041309/guard.png)

For me this represents a problem with HTML5. The meaning of most HTML 4 tags is not really open to interpretation, so it's pretty easy to start marking up documents with just a list of tags. When a tag's purpose is not self-evident (from its natural language meaning), or the reasoning behind the naming and usage of tags is inconsistent, then this will cause problems.
