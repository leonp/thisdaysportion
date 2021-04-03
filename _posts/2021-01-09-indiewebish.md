---
title: "Notes on the “indieweb” #1: Where do I publish and discuss?"
category: web
sub: "2020 was what I’d loosely describe as my year of the “indieweb”. As to what that means, I’m not sure – it’s pleasingly undefined. I can say I stopped using the huge corporate opiniongrinding leviathan known as Twitter, and began publishing to this website first."
---

- [Notes on the “indieweb” #2: Where do I find things to read?](/posts/indiewebish-2/)
- [Notes on the “indieweb” #3: Who’s it for?](/posts/indiewebish-3/)

I stopped using Twitter on a daily (or more accurately, quarterhourly) basis on 24 May 2020. Since then I’ve tinkered with automatically tweeting stuff from this website and I have, on two or three occasions, actually logged in to `twitter.com` and posted something. So while I haven’t gone full woodsman and deleted my account, I have to all intents and purposes, _stopped using Twitter_.

I’ll save the _why_ for another post. Here I’ll just go through where I post updates/thoughts/images, and where any discussion can take place.

## The website

First and foremost I publish pretty much every little update, link, image and longer post to here. One of the principles of the indieweb is _owning_ your content rather than handing it over to the man. Inevitably, there’s an acronymn: [POSSE (Publish on your Own Site, Syndicate Elsewhere)](https://indieweb.org/POSSE).

This is fine, if cumbersome. Tweeting a photo from your phone via the Twitter app takes a couple of seconds and taps. Publishing to a static website like `thisdaysportion.com` involves editing the photo, opening a command line, creating git branches, a text editor, building the site locally, merging and pushing local changes to the remote master branch, waiting for Netlify to build the site... you get the idea.

It’s worth noting it doesn’t have to be this complicated. I could just use `wordpress.com` and get a similar experience to publishing stuff directly to Twitter. Indieweb can be quite hobbyist, disappearing down an [_easier for developers_](https://fvsch.com/static-site-generators) rabbit hole. There’s probably a link between being bothered about the how and where of publishing online and a knowledge of its nuts and bolts.

(Sidenote: 2020 was also a year of tinkering. I did some clever but needlessly complicated work with the WordPress and micro.blog APIs in order to get a frictionless, headless publishing experience on this site.)

## The RSS feed

This site has an RSS feed! [Go subscribe now](/feed/index.xml) and get an update whenever I post a note, link, photo or even a fully fledged blog post.

[I like RSS](/about/what-is-rss) and have used it continually for about 15 years, regardless of my Twitter addiction. I have no idea how many people subscribe to this site or `leonpaternoster.com` these days, but I know it numbered a few hundred back when I was a minor web celebrity.

Humble old RSS – which is central to indieweb – is also invaluable because it enables automatic syndication to pretty much anywhere else (including Twitter) via services such as [IFTTT](https://ifttt.com). That means when I publish anything here, it’ll magically appear on Twitter (after a few minutes).

## Elswehere

Website + RSS feed = a perfectly good indieweb setup. But it’s natural enough to want to reach more people via other services.

In my case, I’ve known a few folk online for over a decade. Ironically enough, these relationships would have started in an indieweb way on my website and its comments sections, but it began moving to Twitter from 2010 onwards. It would be a shame to lose contact with the Nilses, Florenses and Chrises of this world, so anything I post here automatically gets sent to Twitter.

I also autopublish to [micro.blog](https://leonp.micro.blog) because, well, it’s become a solid part of the indiewebverse and a very _nice_ alternative to Twitter: the app and website offer a chronological stream, the design is simple, fast and pretty stylish and there are no neo-Nazis I’m aware of. It offers RSS feed crossposting out of the box, so no IFTTT wrangling required. The general tone is polite. The only problem is that none of my Twitter chums are there, and it’s a little _dull_. Lots of photos of trees, dogs and meals; it feels very [Portland](https://en.wikipedia.org/wiki/Portland,_Oregon), and lacks some of the extreme weirdness and cleverness you can find on Twitter.

## Discussion

None, really. I get the odd reply to an autoposted tweet, nowt through `micro.blog` as I don’t know anyone on there. It’s hard starting a social media ecosystem from scratch and something I haven’t really bothered doing.

I _should_ really host any conversation on my website via good old comment forms; again, this would be a lot simpler with a `wordpress.com` website, and it’s something I did back in 2008-13. I’m planning to use the [Netlify forms API](https://open-api.netlify.com/#tag/form) to implement comments on this static site (yet more tinkering), and then I want to handle _all_ responses via [webmentions](https://indieweb.org/webmention.io), obviating the need to use Twitter at all.

(**Update**: I have rigged up a Netlify forms, Zapier, Airtable comments system. Try it out below!)

I’ve not really been bothered about comments and replies for a while – I locked my Twitter account several years back, which limits any response to posts to your current followers. The _why_ of posting itself is a different question.








