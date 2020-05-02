---
title: A few notes on moving from WordPress to Jekyll

category: web
---

Last night I migrated my blog from WordPress to [Jekyll][2]. As it doesn&#8217;t really make much difference to readers (apart from in one major way, which I&#8217;ll discuss in a bit), I wasn&#8217;t planning to write about it. But the change elicited a few Twitter comments, so here&#8217;s a rough and ready explanation/guide.

## What&#8217;s Jekyll?

Jekyll is a static site generator, which means you write posts on your PC in [Markdown][3], which Jekyll converts into a bunch of HTML pages. Once it&#8217;s done that, you upload your site to your web server.

## Why use Jekyll?

**Speed**, mainly. WordPress builds HTML pages *on your web server* by grabbing information from a database and feeding it through a template. Jekyll looks at Markdown files within a folder, puts them through various [Liquid][4] templates and generates HTML pages *on your PC*. You can view these pages before uploading them to your server (and copy and paste them – there&#8217;s no extracting your content from a database).

Because a Jekyll–generated site consists of flat HTML files it&#8217;s also a lot **simpler and therefore more robust** than a WordPress install. There&#8217;s no database, which means no `500 internal server error` messages.

For the same reason, Jekyll is **more secure** than WordPress. A database can provide access to your website. No database means no way in.

Finally, the Jekyll **writing workflow** is simpler and more flexible than WordPress&#8217;s. When I used WordPress I&#8217;d write posts in Markdown, copy the HTML it generated and post it into the WordPress editor. Jekyll converts the Markdown into posts for me, which I then upload to the server. No copying and pasting, logging in and reformatting.

## Disadvantages

Initially, Jekyll is daunting, especially if you&#8217;re not used to the **command line**. You can&#8217;t open a program with an icon and windows and buttons. This is what you&#8217;ll be using.

To get everything up and running you&#8217;ll need to install Ruby and the Jekyll gems, and write in Markdown. You&#8217;ll also have to use an FTP client (or even run the site through Github).

Jekyll, Ruby, Markdown, Liquid, FTP… It all sounds frankly geeky. And it is, to a certain extent, but once the system is set up it&#8217;s easy to use. **Markdown is easier to write than HTML** and gives you far more freedom and control over what your website outputs than a WYSIWYG editor. If you can hack around WordPress template tags, you won&#8217;t struggle with Liquid.

Similarly, the command line is efficient, and the only things you&#8217;ll need to type are:

*   `cd [path to your site's folder on your PC]`
*   `jekyll build --watch`
*   `jekyll serve`

There are, however, a few additional problems. The biggest is **there are no comments**, because there&#8217;s no database to store them in. Unlike many bloggers who made the move to Jekyll, I like comments. Getting rid of them is a big thing.

I weighed up the advantages of Jekyll against losing comments and decided to take the plunge anyway. If you have a lot of comments you may feel differently.

If you *do* want comments you can use a third party system like Disqus. Personally, I don&#8217;t like Disqus, but it is possible to export all your existing WordPress comments into it.

Another big advantage to WordPress is that it lets you publish anywhere with an internet connection. All you need is a browser or the relevant app. With Jekyll you need a PC with Ruby and Jekyll installed on it. You *can* store a local site across different PCs using Dropbox, but it&#8217;s a still **a long way from being able to publish a post on a public PC or a smartphone**. If you&#8217;re blogging about a trip abroad, you&#8217;re not going to use Jekyll.

Finally, you might miss **WordPress&#8217;s plugins**.

## How to plan the migration

You&#8217;ll need to think about:

1.  setting up Ruby
2.  setting up Jekyll
3.  moving your existing posts from WordPress into Jekyll
4.  getting your permalink and image URLs to match up with your existing install
5.  creating a sitemap
6.  creating an RSS feed

### Installing Ruby and Jekyll

Remember – **you don&#8217;t need to know any Ruby to run Jekyll**. You just need to install it.

You won&#8217;t need to set up Ruby on a Mac as it comes pre–installed. Use the [official Ruby guidelines][6] if you&#8217;re on Ubuntu or similar, and the [Jekyll docs][7] if you&#8217;re on Ubuntu or Mac.

I have Jekyll installed on my **Windows** work laptop. [Running Jekyll on Windows][8] is the best guide I found, although I did a few things differently:

*   I installed the Ruby devkit from the same page as the Windows Ruby installer (just make sure you get the right devkit for the right version of Ruby)
*   I didn&#8217;t need to edit my `config.yml` file as it already contained the correct path to my Ruby installation
*   I didn&#8217;t bother installing pygments

It&#8217;s also worth remembering you can run a special Ruby command line from Windows. To find this I simply enter `command` into the start button search box, which brings up a choice of a standard command line or the Ruby version.

### Moving your existing posts from WordPress to Ruby

I couldn&#8217;t get the ‘official’ WordPress importer to work, but [exitwp][9] was excellent. Just make sure you follow *all* the instructions carefully.

Unfortunately, you won&#8217;t just be able to publish your exported markdown posts as is. **They&#8217;ll need *some* editing**. For example, exitwp didn&#8217;t handle WordPress&#8217;s quotes very well. I found that a normal post will take around two–five minutes to edit, depending on how many images it contains, which is why I&#8217;ve only published 10 at the time of writing (check your analytics to see what&#8217;s popular).

You&#8217;ll save yourself a lot of heartache if you can **keep your existing permalink and image path settings**. It&#8217;s easy to configure pretty URLs in Jekyll (and I published a post on [keeping the standard YY/MM/post-name structure][10]).

WordPress stores images and other assets in its `wp-content/uploads` folder and organises it according to your chosen permalink structure. exitwp extracts all your assets from your `wordpress.xml` file and puts them in a similarly structured folder. So all you need to get images working on your Jekyll site is to copy the `uploads` folder to your project&#8217;s folder.

### Creating a sitemap and RSS feed

Again, this isn&#8217;t as daunting as it seems. Both these methods worked perfectly:

*   Vito Bottas&#8217;s guide to [creating an RSS feed][11] (just remember to replace all the existing site references if you copy and paste the code)
*   Tobiass Josten&#8217;s guide to [creating a sitemap XML file][12]

## Conclusion

And that&#8217;s all I did. I now have a website that&#8217;s generated on my laptop then uploaded to my server. I&#8217;ve found it easy to publish posts and everything is a lot quicker.

If you know the basics of WordPress theme creation then you should know enough to start using Jekyll. It all depends on how important comments and plugins are to you. WordPress isn&#8217;t ‘bloated’–it&#8217;s just more than you need for a simple blog.

(Incidentally, you may ask *why Jekyll?* Well, Mr Hyde is Dr Jekyll&#8217;s ugly, evil alter ego. Jekyll lets you present your civilised face to the world while keeping all your ugly, evil stuff on your PC.)

 [1]: http://upload.wikimedia.org/wikipedia/commons/thumb/7/78/Dr_Jekyll_and_Mr_Hyde_poster_edit2.jpg/1280px-Dr_Jekyll_and_Mr_Hyde_poster_edit2.jpg
 [2]: http://jekyllrb.com/
 [3]: http://daringfireball.net/projects/markdown/
 [4]: http://liquidmarkup.org/
 [5]: https://lh3.googleusercontent.com/-k8NAPsBc5Cw/Ucc0YEhoc6I/AAAAAAAAB7Y/X_eVVYvNI7E/w600-h457-no/terminal.jpg
 [6]: http://www.ruby-lang.org/en/downloads/
 [7]: http://jekyllrb.com/docs/installation/
 [8]: http://www.madhur.co.in/blog/2011/09/01/runningjekyllwindows.html
 [9]: https://github.com/thomasf/exitwp
 [10]: http://leonpaternoster.com/2013/06/replicating-year-month-wordpress-urls-in-jekyll/
 [11]: http://vitobotta.com/how-to-migrate-from-wordpress-to-jekyll/#atom-rss-feed
 [12]: http://vvv.tobiassjosten.net/jekyll/jekyll-sitemap-without-plugins/
 [13]: https://lh6.googleusercontent.com/-T8befFQMJaI/UcctGFRlmwI/AAAAAAAAB60/FN_9adEUxEQ/w761-h480-no/pingdom.jpg

 *[HTML]: HyperText Markup Language
 *[FTP]: File Transfer Protocol
 *[WYSIWYG]: What you see is what you get
 *[RSS]: Really Simple Syndication
 *[XML]: Extensible Markup Langauge
