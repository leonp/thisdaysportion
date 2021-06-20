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

<div class="flex-l">

   <div class="w-two-thirds-l pr4-l">

      <h2>Latest posts</h2>

      <div class="mt3">

      {% for post in site.posts limit:10 %}

         <div class="mb3 mb4-l">

            <time class="db f7 mb1" datetime="{{ post.date | date: "%Y-%m-%d" }}">{{ post.date | date: "%-d %b, %Y" }}</time>

            <div class="b c-lh-title mb1"><a href="{{ post.url }}" class="db">{{ post.title }}</a></div>

            {% if post.sub %}

            <p class="f6 ma0">{{ post.sub }}</p>

            {% else %}

            <p class="f6 ma0">{{ post.excerpt | strip_html }}</p>

            {% endif %}

         </div>

      {% endfor %}

      </div>

      <p><strong><a href="/posts">All posts</a></strong></p>

   </div>

   <aside class="w-third-l pl4-l">

      <h2>Links</h2>

      <div class="mt3 f6">

      {% assign links = site.links | reverse %}

      {% for link in links limit:10 %}

         <div class="mb3">

            <time class="db f7" datetime="{{ link.date | date: "%Y-%m-%d" }}">{{ link.date | date: "%-d %b, %Y" }}</time>

            <div><a href="{{ link.url }}" class="db">{{ link.title }}</a></div>

         </div>

      {% endfor %}

      </div>

      <p class="f6"><strong><a href="/links">All links</a></strong></p>

      <h2>Notes</h2>

      <div class="mt3 f6">

      {% assign notes = site.notes | reverse %}

      {% for note in notes limit:10 %}

         <div><a href="{{ note.url }}" class="db pv1">{{ note.content | strip_html | truncatewords: 10 }}</a></div>

      {% endfor %}

      </div>

      <p class="f6"><strong><a href="/notes">All notes</a></strong></p>

   </aside>

</div>


