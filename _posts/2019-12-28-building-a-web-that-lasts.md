---
layout: post
title: Building a web that lasts
date: 2019-12-28T15:35:58.562Z
category: web
featured: true
---
<q>How do we make web content that can last and be maintained for at least 10 years?</q> asks Jeff Huang.

[Another back-to-basics post bemoaning the death of the web](https://jeffhuang.com/designed_to_last/). Maybe I sound skeptical? I don’t mean to – I agree with the sentiment, if not all the suggestions; maintaining just one HTML page seems absurd. I sometimes think these blogs are really just an expression of nostalgia, for a time when our limited skills were enough to stay on top of the web.

Yes, we want to generate new pages using a simple, robust templating system, even if that system disappears one day.

Perhaps the answer lies in making sure your CMS creates HTML pages from text files, rather than a database/API. Shifting text files is a lot easier than extracting them from a database. Jekyll, for example, uses Markdown stored in a folder. Copy the folder and you’ve copied your content.

I am all for resisting SPAs and complex build chains. I fit squarely in Jeff’s group of professionals who are able to get a website up and running, but aren’t paid just to do this. The nostalgia, again.

Whatever your approach, this is mainly a matter of will. I’ve used WordPress, Hugo and Jekyll over the years, and you can still find [the first ever post I published](/posts/times-for-print-georgia-for-screen/) over eleven and a half years ago.

I’m very glad I never shifted everything over to a service like Medium, but I am reliant on Github/Netlify at the moment. Netlify’s move to charging for more individual components (such as build minutes) concerns me. I’m therefore thinking of making the next logical step in an indieweb set up: old fashioned, paid for hosting. And if I want to be able to post stuff when and wherever I want, I’ll need an old-fashioned CMS, which won’t have such a complex set of dependencies as Jekyll. [Kirby](https://getkirby.com), probably; I expect PHP is as robust as anything out there, apart from HTML itself, of course.

As we approach the end of the decade, it looks like we’re returning to the set up we had at its beginning. Comforting, if nothing else.
