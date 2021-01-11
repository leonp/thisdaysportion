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

## And let’s see if comments are retrieved from the Airtable API

{% assign all_airtable_comments = site.data.airtable_comments.records %}

Size of Airtable array: {{ all_airtable_comments.size }}

{% for comment in all_airtable_comments %}

<article>

	<ul class="mt0 mb3 pa0 list">

		<li>Name: {{ comment.fields.Name }}</li>
		<li>Commented on slug: {{ comment.fields.slug }}</li>
		<li>Which has a link of: {{ comment.fields.uri }}</li>
		<li>Date: {{ comment.createdTime | date: "%d/%m/%Y" }}</li>
		<li>Comment: {{ comment.fields.comment | strip_html | markdownify  }}</li>

	</ul>

</article>

{% endfor %}

