---
layout: default
title: "This day’s portion"
sub: Notebooks out.
display-title: "This day’s portion"
nav-title: "Home"
is_home: true
---

## Latest posts

{% assign posts = site.posts | sort: "date" | reverse %}

<ul class="list mb0 pa0">

{% for post in posts limit:5 %}

    <li><a class="db pv1" href="{{ post.url }}">{{ post.title }}</a><!-- <time class="db mb3 silver f6">{{ post.date | date: "%-d %b, %Y" }}</time> --></li>

{% endfor %}

</ul>

**[All posts](/posts/)**

