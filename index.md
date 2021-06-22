---
layout: default
title: "Home"
order: 1
display-title: "This day’s portion"
is_home: true
is_wide: false
sub: 'Notebooks out! This is the blog of Leon Paternoster. If you like what you’re reading, do <a href="/feed/index.xml">Subscribe to the RSS feed</a> and/or <a href="https://micro.blog/leonp/">follow me on micro.blog</a>. You can also <a href="/contact">contact me</a> directly.'
hide-title: true
pagination:
   enabled: false
   collection: posts, links, notes
---

<p class="f6">There are also <a href="/links">links</a> and <a href="/notes">notes</a>.</p>

{% for post in site.posts limit:10 %}

<article class="mv4 mv5-ns">

   <header class="mb1 flex flex-column flex-column-reverse">

      <h2 class="f5 c-lh-title ma0"><a href="{{ post.url }}" class="no-underline">{{ post.title }}</a></h2>

      <time class="db c-secondary-foreground f6 mb1" datetime="{{ post.date | date: "%Y-%m-%d" }}">{{ post.date | date: "%-d %b, %Y" }}</time>

   </header>

   {% if post.sub %}

   <p class="ma0">{{ post.sub }}</p>

   {% else %}

   <p class="ma0">{{ post.excerpt | strip_html }}</p>

   {% endif %}

</article>

{% endfor %}

**[All posts &rarr;](/posts)**



