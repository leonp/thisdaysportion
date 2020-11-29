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

<ul class="list pa0">

{% for microblog in microblogs %}

	<li><a class="dib pv1" href="/microblog/{{ microblog.id }}/">{{ microblog.id }}</a> — <time>{{ microblog.date_published | date: "%-d/%-m/%Y" }}</time></li>

{% endfor %}

</ul>
