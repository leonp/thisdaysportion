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

<h2 class="mt4 mt5-ns f5 ttl small-caps tracked c-lh-title normal c-secondary-foreground">Latest post</h2>

{% for post in site.posts limit:1 %}

<article>

  <header class="mb4 flex flex-column-reverse">

    <h3 class="f4 f3-ns ma0 p-name"><a href="{{ post.url }}" class="c-link no-underline">{{ post.title }}</a></h3>

    <p class="f6 mb2"><time class="dt-published" datetime="{{ post.date | date: "%Y-%m-%d" }}">{{ post.date | date: "%-d %b, %Y" }}</time></p>

  </header>

  <div class="e-content c-headings c-hyphens">

  {% if post.sub %}

  {{ post.sub }}

  {% else %}

  {{ post.excerpt }}

  {% endif %}

  </div>

  <footer>

    <p><a href="{{ post.url }}" class="b" aria-label="Continue reading {{ post.title }}">Continue reading &rarr;</a></p>

  </footer>

</article>

{% endfor %}
