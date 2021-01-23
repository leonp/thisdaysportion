---
title: Creating a comments system on a Jekyll website
category: web
sub: "Comments on a “static” website should be impossible as there’s no database to store them in and no scripting to put them on a server. But with some “headless” options and Zapier to knit it all together, I managed to rig a system up."
---

**Note: If you’re setting up a new website and want comments you can get up and running on WordPress.com in about 10 minutes. You get all this and more out of the box.**

## Introduction

[Traditional static sites](/posts/static/) are a collection of pre-compiled files and assets, so they don’t offer dynamic features such as instant responses to form input.

Consider how a website with a back end controller and a database handles comments. With this architecture, the site can display user-generated content such as a comment as soon as it’s submitted:

1. User enters comment into an HTML form
2. The HTML form sends the comment to the database
3. The back end creates a new page and emails the submitter and website owner a notification
4. The current page is updated and displayed with relevant changes whenever a user visits the page

We’re going to build a system that works in a different way:

1. User enters comment into an HTML form
2. The HTML form sends the comment to a database hosted by a third party
3. A third party task automator will add the comment to another third party database that offers an API
4. The third party task automator emails the submitter and website owner a notification
5. The third party task automator fires a new site build, which takes place on the static site host
6. During the build process, the static site generator fetches any new comments from the database API and adds them to the relevant page
7. The completed, new static site includes the new comments

As noted above, this system isn’t as good as that offered by WordPress.com out of the box. It doesn’t include the following features:

- Automatic email notifications when comments have been accepted and published
- An easy way to subscribe to further comments (although there is a bodged way of doing this)

You’ll also need to bear in mind that this system will incur costs if you handle a large number of comments. This will be down to generating more build minutes (300) or form submissions (100) than Netlify allows in its free tiers.

## What you’ll need

- A [Jekyll](https://jekyllrb.com) generated website hosted on [Netlify](https://netlify.com)
- The [jekyll-get-json](https://github.com/brockfanning/jekyll-get-json) plugin installed. This will handle fetching comments from Airtable and displaying them on your site.
- A free [Zapier](https://zapier.com) account
- A free [Airtable](https://airtable.com) account with a table and a [read-only API set up](https://airtable.com/api) (you’ll need the API key)

I’m going to assume you’ve got these set up – all have good documentation. In this how-to I’m going to show you how to configure your Jekyll layouts and `_config.yml` file so your site will accept and display comments when it’s built.

## Configure the jekyll-get-json plugin in `_config.yml`

jekyll-get-json is a fantastic plugin that enables Jekyll to grab data from json APIs and make it available to site developers as [data files](https://jekyllrb.com/docs/datafiles/). You’ll access this data in the normal way, through using `site.data.[data name]`. Every time you build your site the plugin will consult the API and create a new data collection.

Configuration is relatively simple. You’re going to provide a name for your data files that you can refer to in `site.data.[name]`, an API endpoint and a `cache` flag. When you set the `cache` to true it’ll speed up site builds (thereby saving you potential costs).

You configuration will look like this:

{% highlight yaml %}
jekyll_get_json:
  - data: airtable_comments
    json: '[Your Airtable API endpoint URL]'
    cache: true
{% endhighlight %}

Assuming your API is working, you’ll now be able to access comments using `site.data.airtable_comments`.

## Add an include that contains your comment form and code for displaying comments

You can either add comments code directly to your `post` layout, or you can write a separate include that the layout calls.

We’re going to use [Netlify’s inbuilt forms](https://www.netlify.com/products/forms/) to store submissions and fire a Zapier zap that sends their contents to Airtable. The nice thing about Netlify’s forms is that they’re completely agnostic over the code you use to build the form, so I’m using vanilla HTML with no javascript (note, I’ve stripped out all classes, but you can style it however you like):

{% highlight html %}
<h2 id="commentary">Add a comment</h2>

<form name="comments" method="POST" netlify-honeypot="bot-field" data-netlify="true" action="/thanks/">

  <p class="lh-title f7"><strong>Required fields marked <span>*</span></strong>. I won’t publish or share your email address – I just need it to get in touch to clarify anything.</p>

  <div>
    <label for="bot-field">Add something interesting only if you’re not a human</label>
    <input name="bot-field">
  </div>

  <label for="name">Name <span>*</span></label>
  <input autocorrect="off" required type="text" name="name" id="name">

  <label for="email">Email <span>*</span></label>
  <input required autocapitalize="none" type="email" name="email" id="email">

  <label for="website">Your website</label>
  <input autocapitalize="none" type="text" name="website" id="website">

  <label for="comment">Comment <span class="dark-red">*</span> (use <a href="https://www.markdownguide.org/cheat-sheet/">Markdown</a> to format text)</label>
  <textarea required name="comment" id="comment"></textarea>

  <input name="slug" hidden value="{% raw %}{{ page.slug }}{% endraw %}">

  <input name="uri" hidden value="{% raw %}{{ site.url }}{{ page.url }}{% endraw %}">
  
  <button type="submit">Submit comment</button>

</form>
{% endhighlight %}

### Notes

- You’ll probably hide the `bot-field` `label` and `input` from the screen using some CSS.
- We need to send some information about the comment so we can link to the page in any notification emails and, more importantly, link comments to specific pages.










