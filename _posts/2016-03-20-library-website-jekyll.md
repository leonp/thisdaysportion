---

category: web
title: Running a library website on Jekyll (maybe)
excerpt: To run a static site or not? Static means faster, more robust and more secure, but you lose plugins, time and easy editing.
---

We're making some changes to our website. Nothing _too_ major from a user's point of view, but I built the site back in 2013 and we do a lot more things on and offline now. Consequently, the <abbr title="Information architecture">IA</abbr> needs rejigging and I want to simplify navigation (by [replacing the universal navigation menu with a more traditional approach](/2016/03/council-toolkit-no-universal-navigation-aberdeenshire/)).

I do want to make big changes to the back end. In 2013 I didn't use <abbr title="Syntatically awesome stylesheets">SASS</abbr> and I hadn't got my head around abstracting <abbr title="Cascading stylesheets">CSS</abbr>, which means the styles are a mess and I've built way too many WordPress templates.

I could improve the CSS structure within WordPress, but I'd also like to make everything a bit more streamlined, quicker and more secure. We currently use 10 plugins, including (excellent) [caching](http://wp-rocket.me/) and [firewall](https://sucuri.net/) services, but the main purpose of these is to implement static website features. Which raises the question <i>why not build a static site</i>?

As I've been using [Jekyll](http://jekyllrb.com) on this site since 2013 it seems the most obvious candidate.

## It's madness using Jekyll (or Hugo, or Octopress, or Pelican)

### Static isn't dynamic

There are many reasons _not_ to build a static site, one of which is its staticness. That means no inbuilt forms, comments or anything interactive.

While there are plenty of third party services that'll fill in the gaps for you, time remains a really thorny problem on a static site because _now_ is when the site's built, not the actual _now_ you're sitting in at this moment in time. Consequently, events are difficult (but not impossible) &#8211; and any library website will need to do events in some form or other.

So Florens is right when he says

> "PHP site generators suck!" *writes a static site generator in Ruby/Node/Rust* "More dynamic pls!" *makes it run like PHP* <cite>[Florens, Twitter](https://twitter.com/fvsch/status/709417111542747136)</cite>

&hellip; which makes something like [Kirby](https://getkirby.com/) pretty attractive.

However, I think if you can crack events you've overcome the main problem static site generators pose, and you'll enjoy the benefits, especially when something like [Jekyll does data so well](https://jekyllrb.com/docs/collections/) (think about all that data you can add to branch pages).

### WordPress has several million plugins

You (maybe) need sliders, events linked to locations, forms with downloads, new custom fields, author images etc. etc. etc. In WordPress, you can get all of these &#8211; and lots more &#8211; in a couple of clicks and some fiddling around with settings. And you get a <abbr title="Grapical User Interface">GUI</abbr>.

### WordPress has user accounts and <abbr title="What you see is what you get">WYSIWYG</abbr> editing wherever there's an internet connection

In theory, anybody within your organisation can add content to your WordPress website; all they need is a username and password. Of course, you don't really want _everybody_ adding content, because that way madness lies.

Your web editors' technical skills pose more of a problem. To add a page to your website they'll need to:

- open a command line
- install Ruby on their PC
- install Jekyll
- build the site
- write Markdown
- know where to put Markdown files
- probably know Git
- upload files to a server using FTP

I'd argue these sorts of skills are pretty useful to _any_ web editor these days, and although it all sounds complicated (_Jekyll, Git, Markdown, command line_ etc.) it's pretty basic stuff.

Unless you're hosting your site on a 3rd party service like [Netlify](https://www.netlify.com/) or [Github Pages](https://pages.github.com/) and [Prose](https://prose.io), you're stuck for editing options when you don't have a PC with Jekyll to hand.

## Static sites are good because&hellip;

So there are lots of things to consider if you're tempted to go static. But there are some advantages that will outweigh the loss of functionality; the sort of things that have a big effect on your user experience.

### They're fast

No page construction and no database calls, just the plain HTML your browser works with. No more of those baffling pauses while WordPress does _something_.

### They're robust

A WordPress site can fail, or at least hang for a while for lots of reasons. Now, you can get yourself a good caching plugin which will largely solve this problem, but you still need to have a database to serve up your static files. There are _no 500 errors_ if you are just serving plain HTML.

### They're simple &amp; transparent

If you're using WordPress your site's data (posts, pages, locations, events etc.) will be stored in a database, while the front end will consist of a set of PHP templates. A static site consists of a set of plain text files in one place: there's no database, which makes backing up and moving your site really easy. Copy the project folder and you're done.

You need a plugin to backup your WordPress site's database, and there's no simple way to add it to a Github repo, for example. Reassembling the site on your PC is an arcane process compared to copying and pasting a folder, opening a terminal and typing `jekyll serve`.

If you're interested in public transparency you can also add the whole site to an open Github repo.

Transparency increases confidence. When you know _everything_ that's happening on your site you're going to feel more confident. There'll be none of that nervy WordPress core and plugin updating.

### They're secure

Hackers can exploit several routes into your WordPress website: the core PHP, forms, the database itself, your FTP account, user logins and, most seriously, poorly coded and infrequently updated plugins.

When you have a static site the only way in is via your FTP and/or Netlify/Github credentials. That makes it far more difficult to inject some malicious code into your site.

## Experimenting

Over the last few days I've been figuring out time, locations and events in Jekyll. Here's what [a library website built using a static site generator](http://dev.suffolklibraries.co.uk) could look like. If I do decide to take the plunge, I'll post how I did it here.
