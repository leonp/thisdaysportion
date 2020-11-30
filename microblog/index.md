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

Everything I post to [micro.blog](https://micro.blog). That includes links, notes, Github updates; basically anything that's not an article.

{% assign microblogs = site.data.microblogs.items %}

<ul class="flex flex-wrap f6 list pa0">

{% for microblog in microblogs %}

	<li class="w-50 w-third-ns"><a class="db pv1 ph2" href="/microblog/{{ microblog.date_published | remove: ":" | remove: "+" | downcase }}/">{{ microblog.date_published | date: "%-d/%-m/%Y %H:%M" }}</a></li>

{% endfor %}

</ul>
