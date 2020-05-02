---
title: Getting to grips with Contentful and Jekyll

category: web
description: "Contentful is a CMS based on an API, providing a non-technical editing environment for web writers. Here's how it works with Jekyll, a static site generator."
cache: true
article: true
excerpt: "Contentful is a CMS based on an API, providing a non-technical editing environment for web writers. Here's how it works with Jekyll, a static site generator."
---

[Contentful](http://contentful.com), if you're unaware, is a platform agnostic Content Management System (CMS). You use its <abbr title="Application Programming Interface">API</abbr> to pull content into a website or app. There are several reasons for using Contentful instead of/in addition to a CMS:

- With a closed CMS such as WordPress you can only publish content to your website. While you can use <abbr title="Really Simple Syndication">RSS</abbr> to pull that content into something else, the Contentful API gives you access to _all_ content types and fields in easy to read and parse json.
- If you move your website away from WordPress you have to get all the content into a new system. Contentful has your content ready to access via the API, which should make for a less disruptive, long-winded process.
- Contentful has a nice <abbr title="What you see is what you get">WYSIWYG</abbr> editor, a godsend if you're using a system which has no front end, such as [Jekyll](https://jekyllrb.com) or [Middleman](https://middlemanapp.com/). Furthermore, it lets you create well-structured data types easily.

We use Jekyll at work and publish with a text editor, command line and Git. That's OK for our web team of two as we don't need (or want) many other people publishing to our website. However, if you're running a site with lots of distributed writers, editors and publishers, this set up is far from ideal. You'll want something a little less technical.

Even we'd like the option of adding a news story without having to fire up a terminal &#8211; we could publish on a phone or tablet, for example, or the comms manager could post a news story in an emergency. While we can use [Prose](http://prose.io) or even edit files directly in Github, a proper editor would be a lot more useful.

So I decided to test Jekyll and Contentful.

## Setting up Contentful and Jekyll

Setting up content types and using the Contentful editor was great, especially for someone who's been using Markdown for years. Getting Contentful to talk to jekyll was also relatively easy.

I created a simple collection of books for my experiment. The content type `book` consisted of four fields:

- Book title (short text)
- Author surname (short text)
- Summary (long text)
- Picture

Setting up a Contentful account and a book content model took a couple of minutes. I found the UI simple and intuitive:

{% include figure.html url='contentful1.jpg' alt="Screenshot of the Contenful editor" caption="Adding content types and content is easy. The rich text box will be welcome for non-technical editors, and it generates Markdown, perfect for generating HTML or other formats." %}

Happily enough, Contentful provides [Jekyll and Middleman plugins](https://www.contentful.com/ecosystem/jekyll/) for grabbing content and putting it into your project. I installed the Jekyll plugin in a project on my laptop with no problems &#8211; you'll just need a 'space' code and an API access token, which you'll add to your `_config.yml` file. Pull content into your project by running `bundle exec jekyll contentful`. So far so good.

## Displaying pulled in content on the website

Contentful places <abbr title="Yaml Ain't Markup Language">YAML</abbr> files in your Jekyll project's data folder. As you'd expect, the files consist of json name and value pairs:

{% include gist.html code="f163a966aba840af33e877440e97aca2" gh-user="leonp" %}

Now, things got a little trickier here. You'd normally access data in Jekyll with `site.data.[name of folder containing data]`, so in the case of a books data folder you'd use `site.data.books`. You'd then loop through whatever that returned.

Contentful imports complicate your data's namespace in two ways:

- Contentful tucks data away in nested folders. So my books data lives in `_data → contentful → spaces → books.yaml`.
- As you can see from the YAML file, Contentful places `books:` at the top of the file, which implies you could have different data types within `books.yaml`.

All this means `site.data.books` doesn't work. Jekyll changes the namespace to match the folder and data structure, which results in the somewhat verbose `site.data.contentful.spaces.books.book` So, to loop through the collection you could use:

{% include gist.html code="8cc7bc573c2f6740c4d242fad8414beb" gh-user="leonp" %}

Note that Contentful returns Markdown, so using the `markdownify` filter will make sure it also works in HTML files. This is what the code produces with [the Jekyll Poole theme](https://github.com/poole/poole):

{% include figure.html url='books-screenshot-1.jpg' alt="Screenshot of books outputted in a browser" caption="What our code produces. Note the Salinger entry's image is in the summary field while the Sebald image is in the picture field. Unfortunately, Contentful hosted images aren't served via https." %}

Contentful returns complex data with aplomb &#8211; you can put images in long text fields, for example, so you could easily add content models like blog posts.

## The good and the bad

Creating, adding and editing complex data is really easy in Contentful. The thoughtfully implemented WYSIWYG editor gets the balance between editing and producing sane code just right.

However, I think there are two problems:

Firstly, as with all static sites, getting content onto a live site is, by default, a manual process. When you edit in WordPress you press the publish button and it'll appear. In a Contentful/Jekyll workflow the process is:

- Someone visits a Contentful URL
- They log into Contentful
- They write content
- They press publish
- You open the Jekyll project
- You run `bundle exec jekyll contentful`
- You run `bundle exec jekyll s`
- You FTP/push the site to a server

I'm sure there are [ways to automate this process](https://www.contentful.com/developers/docs/ruby/tutorials/automated-rebuild-and-deploy-with-circleci-and-webhooks/), and perhaps you could run Jekyll remotely, but this raises the question of _why run a static site if you need to build all these dynamic features?_

Secondly, by adding data to Jekyll, the Contentful plugin makes it difficult to create web pages for each data item. For example, I can't create a separate page for <cite>Pale Fire</cite> with its own URL &#8211; I can only refer to it in a loop. Normally in Jekyll you'd [make a collection](https://jekyllrb.com/docs/collections/) for this purpose. I'm sure this is possible, but it's not available out of the box.

So the search for a friendly, available-everywhere content editor for Jekyll continues. Prose is OK, but flakey on a mobile, while editing files directly in Github is too technical and makes it too easy to break things. In theory Contentful provides the best method &#8211; I just need to find ways of automating the process.
