---
layout: default
title: "Home"
order: 1
display-title: "This day’s portion"
is_home: true
is_wide: true
sub: 'Notebooks out! This is the blog of Leon Paternoster. If you like what you’re reading, do <a href="/feed/index.xml">Subscribe to the RSS feed</a> and/or <a href="https://micro.blog/leonp/">follow me on micro.blog</a>. You can also <a href="/contact">contact me</a> directly.'
hide-title: true
pagination:
   enabled: false
   collection: posts, links, notes
---

## Posts

<div class="mt3">

{% for post in site.posts limit:10 %}

<div class="mb3">

   <time class="db f6" datetime="{{ post.date | date: "%Y-%m-%d" }}">{{ post.date | date: "%-d %b, %Y" }}</time>

   <div><a href="{{ post.url }}" class="db">{{ post.title }}</a></div>

</div>

{% endfor %}

</div>

**[All posts](/posts)**

## Links

<div class="mt3">

{% assign links = site.links | reverse %}

{% for link in links limit:10 %}

<div class="mb3">

   <time class="db f6" datetime="{{ link.date | date: "%Y-%m-%d" }}">{{ link.date | date: "%-d %b, %Y" }}</time>

   <div><a href="{{ link.url }}" class="db">{{ link.title }}</a></div>

</div>

{% endfor %}

</div>

**[All links](/links)**

## Notes

<div class="mt3">

{% assign notes = site.notes | reverse %}

{% for note in notes limit:10 %}

<div><a href="{{ note.url }}" class="db pv1 f6">{{ note.content | strip_html | truncatewords: 10 }}</a></div>

{% endfor %}

</div>

**[All notes](/notes)**


