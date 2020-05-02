---

title: A guide to using Markdown to write blog posts
excerpt: Markdown is quick, easy and portable. If you're writing for websites, you really should learn it.
article: true
category: web
---

## Introduction: What is Markdown?

Markdown makes it possible for anybody to structure their text and publish it in an electronic format. The most common electronic format is <abbr title="HyperText Markup Language">HTML</abbr>, but you can also use Markdown to produce other formats, such as <abbr title="Portable Document Format">PDF</abbr>.

For the purposes of this guide we'll stick to HTML.

Markdown is simple, quick, portable and efficient. To really appreciate why you should use Markdown, it's best to take a look at the old fashioned way of publishing websites.

## Publishing HTML the old fashioned way: WYSIWYG editors

If you publish a web page you publish HTML. This may come as a surprise &#8211; when you wrote that blog post you didn't write this:

<pre>
<code>&lt;h1&gt;Why writers should use Markdown&lt;/h1&gt;
&lt;p&gt;Markdown is quick, simple and portable. It's also extremely elegant and very cool. You need to know Markdown.&lt;/p&gt;
&lt;p&gt;WYSIWYGs are the past. They're slow and bloated.&lt;/p&gt;</code>
</pre>

But that's what you ended up publishing.

What happened?

Let's say you use WordPress. When you write a post in WordPress you use a _What you see is what you get_ (WYSIWYG) editor, which is like a simple word processor. You write text, select bits of it and then make those bits a heading, list or quote.

WordPress then takes your text and converts it to HTML. Why? Because browsers need HTML to understand the structure of your article. HTML is the _language_ of web pages.

### Why use WYSIWYG editors?

HTML isn't code. Anyone can look at HTML and understand what it's doing.

Take our example. The text between the &lt;h1&gt; &lt;/h1&gt; _tags_ is a first level heading, which the browser will display in a large, bold style. The text between the &lt;p&gt; &lt;/p&gt; _tags_ is a parapgraph (_p_ for _paragraph_, see) which the browser will display in a normal style.

There are 5 or so commonly used tags. Once you know these you can pretty much write HTML.

However, writing HTML _is_ laborious. As most people have some experience of using a word processor, it makes sense to replicate the Word experience online.

### Problems with WYSIWYG editors

#### WYSIWYG makes it easy to write poor HTML

Writing HTML is simple, but it is important to follow the rules.

When you use a WYSIWYG editor, it's easy to get hung up on the text's appearance rather than its structure.

In order to make their text _look_ right, writers can misuse headings, quotes and blockquotes. A first level heading not only looks bigger than a paragraph, it has a different _meaning_ to a browser.

This might not seem a huge problem, but think about who &#8211; and what &#8211; might read your web page.

If it's a visitor using a screen reader a misplaced &lt;h1&gt; will make your page confusing. If it's a search engine trying to figure out what your page is actually about, it may get the wrong idea, making your page hard to find.

#### WYSIWYG isn't portable

Let's say you have to move to a new blogging system, or you want publish some of your blog posts in another format, such as PDF or ePub.

If you've used the WordPress WYSIWYG editor all your posts are in WordPress's own format.

Now, WordPress is a good web citizen. It makes it easy to export your posts in an open XML format. But you'll still need to find a tool that can convert this complex XML into your new system's format, or into another file format.

It's far easier to move plain text, Markdown or HTML between systems and formats.

You can also store all your content on a USB or in a Dropbox folder.

#### WYSIWYG isn't that quick

If you write a lot chances are you've got used to using your keyboard to select bits of text and copy and paste.

Although WYSIWYG editors are quicker than writing HTML, you still have to navigate your way round a web page and select formatting options from a dropdown menu. You'll be switching between keyboard and mouse a lot.

The more you keep to the keyboard, the more efficient your writing.

## Enter Markdown: A quicker, more efficient way to publish web texts

You write Markdown in a text editor. Think of it as an easy to use shorthand for HTML.

Take our HTML example. In Markdown, it would look like this:

<pre><code># Why writers should use Markdown

Markdown is quick, simple and portable. It's also extremely elegant and very cool. You need to know Markdown.

WYSIWYGs are the past. They're slow and bloated.</code></pre>

Note the `#` we used. That tells the Markdown editor (or programme you're using to convert Markdown to HTML) to wrap to the following line in &lt;h1&gt; &lt;/h1&gt; tags.

Markdown knows you're writing a paragraph when you leave a line between blocks of text.

To make a second level heading, we use 2 `##`s:

<pre><code>## This is a subheading</code></pre>

There are lots of little characters we use to structure our text. For example:

<pre><code>> This makes a blockquote. A blockquote is a long piece of quoted text. Blockquotes are often indented and occasionally italicised.</code></pre>

Which a browser will make look something like this:

> This makes a blockquote. A blockquote is a long piece of quoted text. Blockquotes are often indented and occasionally italicised.

### Why write in Markdown

Once you understand Markdown's _syntax_ it's easy &#8211; and quick &#8211; to write web documents. Using a WYSIWYG editor will seem cumbersome.

Markdown mirrors HTML. When you write in Markdown you're thinking about structure and meaning, not appearance. Quality control is easier in Markdown than WYSIWYG.

### From Markdown to your blog

OK, so that all sounds grand. You've written your first blog post in Markdown in record time. How do you actually convert it to HTML and get it on the internet?

You've got a few options. You can either do the conversion _before_ you open your blogging software, or you can do it _in_ your blogging software.

Let's take a look at WordPress again.

#### Converting Markdown to HTML before opening WordPress

You can write Markdown in any text editor, but you'll need some software to convert it to HTML.

The best way to do this is to use a Markdown editor, which'll let you edit and convert in one program. Lots of editors will show you what your HTML will look like as you write Markdown.

There are lots of good Markdown editors out there. I use:

- [haroopad](http://pad.haroopress.com/user.html) in Ubuntu/Debian Linux, Windows or Mac OS X
- [iA Writer](http://www.iawriter.com/mac/) in Mac OS X/iOS
- [Markdown Pad](http://www.markdownpad.com/) in Windows

The process is simple. Write in Markdown then choose _Export_ from your file menu. At the very least you'll get the option to export HTML. Some editors also let you export to a PDF file.

Once you have some HTML to work with, login to your website, select _New post_ and paste your HTML into the _Text_ tab in the WYSIWYG editor pane. Press _Publish_ and you're done.

#### Writing Markdown in WordPress

You _can_ bypass Markdown editors altogether. This will make for a more streamlined workflow, but you won't have any local copies of your blog posts. Remember, one of the weaknesses of WYSIWYG editors was the lack of portability.

You'll still write better quality posts more quickly.

However, if exporting and copying and pasting HTML is too time consuming, then it makes sense to use Markdown _in_ WordPress. To do that, you'll need a plugin. You could try [wp-markdown](https://wordpress.org/plugins/wp-markdown/).

This time, you'll login to your website and select _New post_. Instead of using the WYSIWYG editor you'll chose the _Text_ editor and write in Markdown.

#### Using an app like Blogeasy

[Blogeasy](http://blogeasyapp.com/) offers the best of both worlds. Write local Markdown files and hit the _Publish_ button to send them straight to your WordPress powered website.

## The future

As you've probably figured out, the Markdown/WordPress workflow isn't perfect at the moment. Although there are some advantages to using a Markdown editor you may well find the whole export/copy/login/paste process too time consuming.

There are some desktop apps out there that let you write Wordpress posts in a WYSIWYG editor on your computer _before_ uploading to your site. A few (such as Blogeasy) let you write in Markdown. This is ideal.

We need more Markdown editors that connect directly to websites, whether they're built on WordPress, Blogger or Drupal.

Alternatively, you could try a different blogging engine. There are lots of static site generators out there which take Markdown files and convert them to complete websites. The likes of Jekyll (which runs this site) are super fast, secure and portable, but they do take quite a bit of technical know how.
