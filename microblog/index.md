---
layout: default
title: Microblog
footer: true
order: 5
in_nav: true
visited-links: true
prose-headings: true
underlined-links: true
hyphens: true
---

Everything I post to my [micro.blog](https://micro.blog/leonp). Links, notes, Github updates; anything that's not an article.

{% assign microblogs = site.data.microblogs.items %}

<ul class="f6 list pa0 c-columns">

{% for microblog in microblogs %}

	<li><a class="db pv1" href="/microblog/{{ microblog.date_published | remove: ":" | remove: "+" | downcase }}/">{{ microblog.date_published | date: "%-d/%-m/%Y %H:%M" }}</a></li>

{% endfor %}

</ul>
