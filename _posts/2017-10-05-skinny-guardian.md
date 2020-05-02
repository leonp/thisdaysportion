---
title: Skinny Guardian
excerpt: "Skinny Guardian displays the last 50 Guardian articles in a plain, easy to scan and read format. No javascript, no database and a smattering of CSS make it ideal for when you just want something to read on your phone."
summary: "Skinny Guardian displays the last 50 Guardian articles in a plain, easy to scan and read format. No javascript, no database and a smattering of CSS make it ideal for when you just want something to read on your phone."
category: work
description: "Skinny Guardian displays the last 50 Guardian articles in a plain, easy to scan and read format. No javascript, no database and a smattering of CSS make it ideal for when you just want something to read on your phone."
featured: true
---

[Skinny Guardian](https://www.skinnyguardian.xyz) was inspired by sites like [CNN Lite](http://lite.cnn.io/en) and [Thin NPR](http://thin.npr.org/) -- news served with next to no styling. While this may sound (and look) unexciting I find a simple list of headlines an excellent way to get something to read quickly, and because they're just HTML and CSS, articles load instantly. Perfect on a train or bus journey into work with a poor mobile connection, or when you want something quick to read during your lunch.

{% include figure.html url="sg-android.jpg" alt="Screenshot of the Skinny Guardian site on a Nexus smartphone" caption="Skinny Guardian loads quickly on a phone" %}

<cite>The Guardian</cite> has [an excellent, open API](http://open-platform.theguardian.com/), so the project gave me a chance to work with external, queryable data. I'd only used the Google Maps API in the past, copying some pre-defined templates and queries. With Skinny Guardian, I built my own API queries and wrangled the results into layout files.

## The set up

Skinny Guardian uses [Jekyll](https://jekyllrb.com) to generate static HTML files, thereby removing any database requirement. I use [Netlify](https://www.netlify.com) hosting for free SSL and a build hook URL, which means I can automate site builds once every 30m if I use something like a free [Postman](https://www.getpostman.com/) account to send the URL a POST request.

The site simply queries the API whenever it's built, grabbing the 50 most recent articles and converting the <abbr title="Javascript Object Notation">json</abbr> response into Jekyll data files with the [Jekyll Get](https://github.com/18F/jekyll-get) plugin.

I then use the [Jekyll Datapage Generator](https://github.com/avillafiorita/jekyll-datapage_gen) plugin to convert the json into Jekyll pages that I can list and feed through layout files. Throw in the Tachyons CSS framework, and you have a fast, regularly updated list of Guardian articles to peruse and read.

## Making it quick

There's a bit going on under the hood at build time to make sure the site serves as quickly as possible.

I only use the Tachyons CSS modules the site needs -- there are no hover effects, for example. This means the gzipped CSS weighs in at around 7k, half [the magic 14k figure](https://developers.google.com/speed/docs/insights/mobile). So instead of making a separate request for a CSS file, styles are placed directly in the HTML document's head, cutting down on load and display times. I also minimise the HTML and CSS.

All this means Skinny Guardian should load quickly, regardless of the quality of your connection. Ideal if you're stuck between, say, [Ingatestone](https://www.google.co.uk/maps/place/Ingatestone/@51.6777852,0.3328351,13z/data=!3m1!4b1!4m5!3m4!1s0x47d894e193c112ff:0x71fbf17ff37254c6!8m2!3d51.673794!4d0.3899059) and Brentwood on your commute into work 😄
