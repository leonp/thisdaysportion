---
layout: default
title: Comments
footer: true
order: 2
in_nav: false
visited-links: true
prose-headings: true
underlined-links: true
hyphens: true
---

Let’s see if comments are retrieved from the WordPress API:

{% assign all_wp_comments = site.data.wp_comments %}

{% for comment in all_wp_comments %}

<article>

	<ul class="mt0 mb3 pa0 list">

		<li>ID: {{ comment.id }}</li>
		<li>Belongs to post no.: {{ comment.post }}</li>
		<li>Name: {{ comment.author_name }}</li>
		<li>Date: {{ comment.date | date: "%d/%m/%Y" }}</li>
		<li>Content: {{ comment.content.rendered }}</li>
		<li>Type: {{ comment.type }}</li>

	</ul>

</article>

{% endfor %}

