---
title: Using Github as a CMS

category: web
---

I saw this idea in the comments on a post somewhere or other, and my immediate reaction was <i>nope</i>. Too technical, too using&#8211;something&#8211;that&#8211;it&#8211;wasn't&#8211;intended&#8211;for.

But then I tried some website edits using Github itself, rather than <a href="/2014/08/my-rig/">writing something locally and pushing them to my website repository</a>, and it worked OK. Now, that doesn't mean it'll work for a site with several non&#8211;techie editors, but I think it'd be great if it could.

## The real world

At work there's me and a couple of web agents who publish events to the website. We use WordPress as our CMS.

I chose WordPress because a) I know it pretty well and b) there's always a plugin to reach for. We use <a href="http://wp-events-plugin.com/">WP Events Manager</a> extensively, which is very good indeed.

That's great, but WordPress does pose some fundamental problems; for a start, it's not actually that good for adding and editing content. The whole *posts* terminology, its blogging roots and the messy <em>New post</em> form can confuse editors. I can see why.

Combine that with a bunch of technical challenges, such as malfunctioning plugins and slow load times, and you can see why a static site appeals.

## Using Github Pages

<a href="/2014/08/my-rig/">I moved this site to Github Pages</a>, so naturally enough I asked myself <i>Could we move the work site? Or at least run it as a group of static pages?</i>. This would provide several benefits:

- *Fast loading pages*. Not only would we get rid of calls to a database, but we'd also retain control of what was loaded and when, and make sure everything was minimised and served properly.
- *Transparent structure*. The work site consists of a child theme of a theme that incorporates the Foundation Framework, built on a WordPress install. It uses 10 plugins. One flat, HTML site would be a joy to maintain.
- *Transparent content*. The whole website would be hosted in a public repository.
- *Some form of CMS*. It's not realistic to expect content editors to to edit files, build sites with Jekyll and push and pull changes using Git.

Of course, it's no trivial matter implementing things like events on a static site, but let's assume it's possible. Can we manage content using Github Pages?

## Managing content

Here's how it'd work:

- I'd do all the local pushing and pulling. I'd have a choice of whether to write content locally and push it to the repo, or write content on Github (which would mean being able to change the site from any PC with an internet connection).
- The agents would publish content on Github. This means setting up Github accounts. Adding content is quite easy &#8211; you just click the + button in the appropriate folder:

<p><img src="https://dl.dropboxusercontent.com/u/6144461/assets/images/github-screenshot.jpg" alt="Screensot of a Github folder" height="386" width="800"></p>

<p class="figcaption">A folder of posts on Github</p>

And then you write your post in Markdown, add front matter and press the Commit button:

<p><img src="https://dl.dropboxusercontent.com/u/6144461/assets/images/github-add-page.jpg" alt="Screensot of a Github add file page" height="478" width="800"></p>

<p class="figcaption">Adding a new file to Github</p>

All of which sounds relatively simple.

## Problems

- *Permissions*. In theory, an agent could delete the `CNAME` file, and completely break your whole website. Or delete whole folders, layouts, *anything*. However, <a href="https://help.github.com/articles/permission-levels-for-an-organization-repository">Github does have permissions</a>.
- *Learning Markdown*. In WordPress you just type into a box and format text by pressing buttons. This is a mixed blessing as you can end up with some pretty cludgy HTML or, worse still, an agent will still paste text directly from Word or Outlook. Markdown is easy to learn, and I'd argue that it's a skill editors should have.
- *File names*. If you're using Jekyll you have to name files in a certain way, i.e. `YYYY-MM-DD-file-name.md` In fact, whole idea of creating files rather than simply writing posts may seem alien.
- *Front matter*. A post often requires just `title` and `layout` fields, but if you were creating an event, you'd need a lot more. Would editors remember what to add, and use the correct format?
- *Previewing content*. In Github you just write the content and commit &#8211; there's no intermediate stage.

There seems to be a lot that could go wrong in this system, but, if you could get it to work, I think it'd be a really simple and secure way to manage a website. And there's <a href="http://prose.io/#about">Prose</a> to perhaps make it all possible.
