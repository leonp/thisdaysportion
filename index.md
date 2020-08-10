---
layout: default
title: "This day’s portion"
sub: Notebooks out.
display-title: "This day’s portion"
nav-title: "Home"
is_home: true
---

## Latest posts

{% assign posts = site.posts | sort: "date" | reverse | limit:5 %}

<ul class="list mb0 pa0">

{% for post in posts | limit:5 %}

    <li><a class="db no-underline pv1" href="{{ post.url }}">{{ post.title }}</a><!-- <time class="db mb3 silver f6">{{ post.date | date: "%-d %b, %Y" }}</time> --></li>

{% endfor %}

</ul>


## Latest links

{% assign links = site.links | sort: "date" | reverse %}

<ul class="list mb0 pa0">

{% for link in links | limit:5 %}

    <li><a class="db no-underline pv1" href="{{ link.url }}">{{ link.title }}</a><!-- <time class="db mb3 silver f6">{{ post.date | date: "%-d %b, %Y" }}</time> --></li>

{% endfor %}

</ul>

## Latest notes

{% assign notes = site.notes | sort: "date" | reverse %}

<ul class="list mb0 pa0">

{% for note in notes | limit:5 %}

    <li><a class="db no-underline pv1" href="{{ note.url }}">{{ note.title }}</a><!-- <time class="db mb3 silver f6">{{ post.date | date: "%-d %b, %Y" }}</time> --></li>

{% endfor %}

</ul>
