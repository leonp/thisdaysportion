---
title: 'The perfect blogging platform: crossposting and conversing on social media'
category: web
date: 2021-06-06 16:17:00 +0000
sub: 'How does the perfect blogging platform handle posting to other social media networks and the conversations that take place there? Perhaps the answer also offers a way to make money without tracking or ads.'
---

So far in this series of posts on a never to be built and probably of little interest anyway blogging platform, I’ve established [some principles](/posts/some-blogging-platform-principles/) about what it is and should do, and explored [how users might get to customise their blogs without having to code themes](/posts/perfect-blogging-through-typography/). In this post I want to consider what integration with other social media networks might look like, specifically Twitter (although the ideas could apply to Facebook, Instagram etc.)

One of the main principles of our platform is that we publish to our blog before syndicating posts to other social media networks (a process known as [POSSE](https://indieweb.org/POSSE)); the idea being we, rather than the man, own our content (however trivial or mundane that may be). Personally, I think this is a somewhat dubious theory as once you publish to the Facebooks of this world your content is theirs in perpetuity, whether it’s a copy of the “canonical“ post or not. Still, at least we’re signalling where the content originates from.

Apart from the (supposed) ethical benefit of publishing in this way, there are some practical advantages. For example, should a social media network go under (admittedly unlikely) or decide to remove or lose a post (not impossible), our content still exists on our website, and [wherever else we have our posts backed up](https://github.com/leonp/thisdaysportion/tree/master/_posts). Also, we only have to publish in one place before automatically syndicating across several networks.

## Publishing to Twitter et al

This is the relatively simple part of the process and, in all likelihood, if you’re blogging you’re probably already automatically sending your posts to social media. WordPress offers good, well established plugins that’ll take of wrangling with the Twitter API; in fact, wordpress.com blogs come with this built in, no plugin required.

If you’re foolhardy enough to be using a static site generator such as [Jekyll](https://jekyllrb.com), you’ve got a bit more work on your hands (which should be the motto of static sites). But as long you have an RSS feed you’re probably fine. Sign up for [IFTTT](https://ifttt.com) or [Zapier](https://zapier.com) and connect your RSS feed to your Twitter account. Or work with the Twitter API. Enjoy!

What your website sends to Twitter is important. We want our audience to respond to our posts in a way that’s convenient for them, rather than asking them to jump through hoops by, say, filling in a comment form on our own website. Not only is this polite – they probably have no idea about the indieweb and simply use Twitter like 99% of the rest of the population – it’s also practical: the more difficult you make it to respond the less likely it’ll happen. We should introduce a principle here; namely, that **replying to a post should be as easy as, and feel like, a normal interaction on whatever social media network is hosting the conversation**.

In practice that would mean a few things:

- **By default, Tweets don’t link back to the website.** Although we can add a setting to either override this all of the time or on a per post basis.
- **A post looks like a Tweet on Twitter.** That means it’s sent “as is” – assuming it’s less than 280 characters long. If it’s more than 280 characters long, we get options.
- **Proper “posts” (i.e. anything with a title) or “notes” longer than 280 characters link back to the website.** The platform should allow for simple truncation of a note, a “traditional” title, link and excerpt construction, a handcrafted note and link or any combination of these.
- We should be able to generate **[Twitter cards](https://developer.twitter.com/en/docs/twitter-for-websites/cards/guides/getting-started)**.
- **Images and video are embedded in the tweet.** Our platform should have image and video formats, with optional captions. These get sent straight to Twitter “as is”, just like a note. Images and videos contained within posts and longer notes are treated the same as any other post.

## Conversation

Crossposting itself is _relatively_ simple, but conversation could get tricky.

At this point it may be worth taking a step back and asking _What is the fucking point of all this?_ If we’re so keen to extricate ourselves from the grasp of the social media leviathans, why don’t we just have done with it and _not use Twitter_?

That is an entirely fair enough point, but we’re going to plough on and try and plot a way through not only posting to Twitter, but replying to other people’s posts, and then holding some form of threaded conversation. No-one said this was going to be easy.

### Replying to, retweeting or liking a tweet

Actually, this bit _is_ easy. Webmentions and microformats already allow for `reply` and `like` mentions, which we could add to our post editor along with a field for the tweet URI.

For replies, use the above publishing guidelines to decide how they look in Twitter and have the platform send the reponse. Likes and retweets are even easier – they don’t even need content.

### Replying to a reply to your reply

Things become a bit more complex when we try and deal with Twitter conversation threads (although to be fair Twitter doesn’t deal with Twitter conversation threads particularly well).

Take this scenario: you post a short note that gets sent to Twitter. @leonpaternoster and @paternoster reply. What happens then?

Our platform has three things to deal with:

- Notifying you that @leonpaternoster and @paternoster have replied.
- Displaying the reponses on your blog.
- Allowing you to reply from your blog.

Luckily, we do have a means of dealing with conversations on blogs, and that’s [threaded comments](https://demo.studiopress.com/genesis/threaded-comments.htm), which WordPress has supported for over a decade. In fact, the simple process of indenting replies makes a thread more readable than it is on Twitter. We could even argue that this abstraction and distance might make social media calmer and clearer, allowing for better, more considered conversations. 

Our platform should therefore – in theory – send comments to Twitter and receive replies, rendering them all on the initial post page as a formatted, indented list. Bloggers benefit from a better formatted conversation while readers on social media don’t see any difference.

While this may _work_, we could envisage it soon becoming problematic. What if you’re really active on Twitter, Facebook and Instagram and holding dozens of conversations a day? Are we expecting our platform to handle and mirror three social media networks. To go back to our original question – _what’s the fucking point?_

It’s at this point we might consider how we pay for this platform, how we might _monetize_ (urgh) it. True, it’ll never be built, but here’s the idea for bloggers...

You get to publish and own all your content while on a flexible platform where you control how your blog looks. Your readers don’t have to notice the difference; you can reply, like and retweet just as before, and talk to your audience wherever you please. “Premium” features, such as nested conversations and “advanced” typography,  cost, while the basics – blogging itself, sending replies and limited typographical control – are free. No advertising or tracking, of course.









