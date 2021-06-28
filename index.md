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

<p class="f6">There are <a href="/posts">posts</a>, <a href="/links">links</a> and <a href="/notes">notes</a>.</p>

<h2 class="mt4 mt5-ns f5 ttl small-caps tracked c-lh-title normal c-secondary-foreground">Latest posts</h2>

<ul class="list ph0 mb4">

{% for post in site.posts limit:10 %}

   <li class="mb3">
      <a href="{{ post.url }}" class="no-underline underline-hover db">{{ post.title }}</a>
      <time class="c-sans-serif db c-secondary-foreground f6" datetime="{{ post.date | date: "%Y-%m-%d" }}">{{ post.date | date: "%-d %b, %Y" }}</time>
   </li>

{% endfor %}

</ul>

**[All posts &rarr;](/posts)**
