---
layout: default
title: "Home"
order: 1
in_nav: true
sub: Notebooks out. Blog posts, articles, microblogs, pictures, links.
display-title: "This day’s portion"
nav-title: "Home"
is_home: true
---

## Latest

{% assign notes = site.notes | reverse %}
{% assign links = site.links | reverse %}
{% assign posts = site.posts %}
{% assign everything = notes | concat: links | concat: posts | sort: "date" | reverse %}

<ul class="list mb0 pa0">

{% for entry in everything limit:10 %}

    <li><a class="db pv1" href="{{ entry.url }}">{{ entry.title }}</a><!-- <time class="db mb3 silver f6">{{ entry.date | date: "%-d %b, %Y" }}</time> --></li>

{% endfor %}

</ul>

