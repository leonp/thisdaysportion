---
title: Getting data from APIs with Jekyll
category: web
sub: "Find out how to get information from another website, convert it to Jekyll data and create pages from this data. Although Jekyll is a static site generator, you can access APIs at build time, and even build interactive functions, such as comment forms."
---

## What are APIs?

Application programming interfaces (APIs) allow us to access data from sources external to our website.

Consider <cite>The Guardian</cite>. The website creates web pages from a database of articles, images, videos and authors. The [Guardian API](https://open-platform.theguardian.com/) allows _anybody_ to access this database in order to build their own apps and websites.

I use the Guardian API to create [Skinny Guardian](https://www.skinnyguardian.xyz), a site built with Jekyll. There are millions of APIs out there. You can even access all the posts from my “professional” website using [the leonpaternoster.com API](https://www.leonpaternoster.com/api/posts.json).

We can access data at API _endpoints_. An endpoint is simply a URL where a service will present data in the form of a file. This file can be in any format, but it’s often either `XML` or, more commonly, `json`. The data can be static (as it is at [https://www.leonpaternoster.com/api/posts.json](https://www.leonpaternoster.com/api/posts.json)), or it can be changed using a query, usually appended to the endpoint URL. For example, this URL will return the content, author, a shortened URL and word count of the last 50 published UK articles:

`https://content.guardianapis.com/search?show-fields=body,byline,shortUrl,wordcount&page-size=50&production-office=UK&type=article`

You could get the last 30 articles by changing the `page-size=50` part of the query to `page-size=30`.

## Why use APIs, especially with Jekyll?

Think about <cite>The Guardian</cite> again. The website is a well designed architecture of components, pages, images and fonts that serve to publish articles while conveying the paper’s brand and selling membership.

However, sometimes you might just want to read an article on an old mobile phone, without the branding or attempts to sell membership. A website could grab articles from the database via the API and build [very simple pages that load quickly on any device](https://www.skinnyguardian.xyz).