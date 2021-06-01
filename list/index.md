---
title: Every goddam thing ever
layout: default
noindex: true
---

{% assign notes = site.notes | reverse %}
{% assign links = site.links | reverse %}
{% assign posts = site.posts %}

{% assign everything = notes | concat: links | concat: posts | sort: "date" | reverse %}

<ol class="ma0 pa0">

{% for entry in everything %}

	<li class="f6"><a href="{{ entry.url }}" class="dib pv1">{{ entry.title }}</a> – <time class="pv1">{{ entry.date | date: "%-d %b, %Y" }}</time></li>

{% endfor %}

</ol>

