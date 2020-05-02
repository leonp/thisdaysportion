---
title: "Using Staticman for comments on a Jekyll site"
category: web
layout: post
---
Table of contents:

* TOC
{:toc}

## Why use Staticman?

When you move from a "dynamic" CMS (such as WordPress) to a static site generator (like Jekyll) you lose comments. You can use [Disqus](https://disqus.com/) or similar instead, but hosted, javascript-powered systems have disadvantages:

- You have to login to a service such as Google or Facebook (or Disqus itself) to make a comment
- The comments don't live on your website, but on Disqus's servers. If Disqus goes, so do your comments.
- The comments don't exist on your site until they're called by javascript when the page is loaded, so they don't exist to search engines when they crawl your site
- No javascript, no comments

Now, if we're looking to move our discussions from Facebook, Twitter <i>et al</i> back to our own websites (and we should be), this is a sad state of affairs. We might consider why we moved from WordPress in the first place when it does blogging so well. But there are solutions to this seemingly intractable problem. The foremost being [Staticman](https://staticman.net).

In this post I'll provide an overview of what Staticman does and take you through some of the pitfalls you need to avoid in order to get it working properly. I refer you to [Michael Rose's excellent, comprehensive Staticman and Jekyll guide](https://mademistakes.com/articles/improving-jekyll-static-comments/) for more detailed instructions that'll help you get more "advanced" features working.

## Files/code to copy

If you just want to copy some code and files:

- [My comment form include](https://github.com/leonp/leon2/blob/master/_includes/comment-form.html)
- [My comments include](https://github.com/leonp/leon2/blob/master/_includes/comments.html)
- [My staticman config file](https://github.com/leonp/leon2/blob/master/staticman.yml)

## What you'll need

Staticman is smart. This is how it works:

1. A user submits a comment from your website through a standard HTML form (no javascript required)
2. Staticman receives the comment
3. If you've turned off moderation, Staticman pushes the comment to a Github repository. If you've hooked up your website to a Github repository (if you're using a service like Github Pages, Netlify or CloudCannon, for example) this will normally fire a site build, meaning the comment will appear within seconds or minutes.
4. If you haven't turned off moderation, Staticman makes a pull request, which you can choose to accept and merge into your production branch. Again, this will normally fire a site build.

All these moving parts mean you'll need:

- The know how to code an HTML form (although you could always copy and paste something)
- Your website hosted in a Github repository
- Automated site builds
- The know how to handle relatively complex Liquid templates and Jekyll data files (or collections), and a Staticman config file. Again, you may be able to copy and paste something.

Assuming you have all these, or you're willing to copy and paste and experiment, you should be able to get comments working well fairly easily. Especially if you follow these tips:

## Get the Staticman URL right

The Staticman docs provide an incorrect URL for your comment form to submit data to. It should be `{% raw %}https://api.staticman.net/v2/entry/{your github name}/{the github repo}/{the branch}/comments{% endraw %}`. The `comments` bit is important.

This means your `form` element would look something like:

{% highlight html %}
<form method="post" action="https://api.staticman.net/v2/entry/leonp/leon2/master/comments">
{% endhighlight %}

(Obviously, you've entered your Github username, repo and branch, right?)

## Check whether you have any comments before trying to sort them

In all likelihood, you'll create a `comments.html` include to handle displaying comments. You'll then add your include to whatever layout file you're using for posts.

I made a mistake which had me banging my head for several hours. My code did this:

1. Created an object that contained all the page's comments and sorted it by date
2. Checked whether there was anything in this object
3. If there was, looped through each comment to display it

While this generated a list of comments, I couldn't sort them. This is because Jekyll's templating language Liquid won't let you sort empty objects, so if the object contained no comments and you tried to add a `sort` filter, it threw an error.

So your code should:

1. Check whether the page has any comments
2. If it does, create an object from the comments using `assign` and apply a `sort` filter. By default this will sort by filename, which, if you're following my code, will consist of a timestamp. In effect, you'll be sorting by date and time, which is probably what you want.
3. Loop through each comment

## Use Jekyll's inbuilt text filters for formatting and sanitising

Jekyll comes with a few filters you can apply when it outputs text. My `comments.html` include makes use of `markdownify` and `smartify`, which means it'll convert any markdown to HTML and make 'dumb' quotes smart, curly quotes. Most usefully, it ensures paragraph breaks are rendered.

Also bear in mind Staticman doesn't sanitise form inputs, which means visitors could hotlink to javascript from your comments form. The simplest way to mitigate this threat is to strip any html from comments _and_ the name field using the `strip_html` filter. This does mean commenters won't be able to enter HTML, even if it's wrapped in Markdown back ticks. Markdown formatting is retained though:

`{% raw %}{{ comment.message strip_html | markdownify | smartify }}{% endraw %}`

`{% raw %}<h3 class="f5 lh-title mt0 mb1">{{ comment.name | strip_html }}</h3>{% endraw %}`

## Add a fragment to comments so you can link to them

Make use of each comment's automatically generated `_id` and add it to a link to the comment. I've used WordPress's convention of making the comment timestamp a link back to the comment:

Generated HTML:

{% highlight html %}
<a href="/posts/evening-edition-is-boring/#b029aec0-a9fa-11e8-88c0-ef9d7cca50b9">Aug 27, 2018, 13:11</a>
{% endhighlight %}

Liquid:

{% highlight html %}
{% raw %}
<a href="{{ page.url }}#{{ comment._id}}">{{ comment.date | date: "%b %-d, %Y, %H:%M" }}</a>
{% endraw %}
{% endhighlight %}

## Set up anti-spam with a simple honey pot field

In your `staticman.yml` file, you can specify which fields commenters are allowed to submit. If they submit a value in any other field, it'll stop processing the comment and display a `json` error.

As spambots tend to complete every field in a form, this will normally stop any spam getting to your site.

Often, developers hide these "honey pot" fields. It's actually simpler and [arguably more accessible to display the field](https://ux.stackexchange.com/questions/52916/what-is-the-best-way-to-hide-a-honeypot-captcha) and attach a label that clearly discourages users from entering anything, such as <q>Only fill this in if you're trying to spam me</q>.

`staticman.yml` code:

{% highlight yaml %}

* Make sure you don't enter your honey pot field name here!
allowedFields: ["name", "email", "message"]

{% endhighlight %}

Form HTML (with classes removed):

{% highlight html %}
{% raw %}

<label for="hp">Only fill this in if you're trying to spam me</label>
<input name="fields[hp]" id="hp" type="text">

{% endraw %}
{% endhighlight %}

## Conclusion

This should give you the code to set up a robust, simple commenting system on your Jekyll-generated site. You can also add more advanced features like email notifications and threaded comments, but I'm saving that for another piece of work.

And feel free to leave a comment ✍️
