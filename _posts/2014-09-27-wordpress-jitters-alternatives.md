---
title: I'd like a friendly Jekyll/Github hybrid to manage websites

category: web
---

Today I updated the work site to WordPress version 4. Updating WordPress work sites is never a pleasant experience.

It actually went OK: the site was only out of action for a few seconds while the update downloaded and installed. The process is simple &#8211; you click a button and wait. I have nothing against WordPress from this point of view &#8211; it's well designed, easy to use software that can do a million and one things. There's just a nagging feeling that something _could_ go wrong with one of the many components that make up a site, and that one thing could bring the site down.

I'm conservative with plugins, but when it comes to maintenance we still have to think about:

- a caching plugin
- an events plugin
- a forms plugin
- a plugin that makes sure javascript is loaded from Google code correctly
- the WordPress core
- a parent theme
- a child theme
- a database
- backing up the database
- backing up the content files
- reinstalling everything should something go wrong

All these bits and pieces affect each other; for example, a few months ago the events plugin created so many pages it messed up the caching plugin, which in turn caused an intermittent fatal error.

It's stressful. Every update represents a round of testing, backing up and finger crossing when the live site is finally changed. 10 plugins means lots of updates.

Having to change things live without being _absolutely_ sure of what's going to happen is a thrill I don't really need at work.

I don't think Jekyll or Hugo can generate easy to edit, complex sites, but a system that did *all* the heavy lifting locally would be ideal. Updates would be a matter of uploading static HTML files to a server, which is about as predictable and stable as you can get.

Here's what I think you'd need:

- A GUI so non&#8211;technical writers could work with content
- A way of accessing that content from different devices
- Extended Markdown
- To generate flat, HTML files
- A way to incorporate common 3rd party alternatives for dynamic functions (such as forms and comments)
- A way of displaying the generated site on a test server

I guess I'm describing a friendlier Jekyll/Github hybrid. Whatever it is, it'd make for a stress free, robust CMS.
