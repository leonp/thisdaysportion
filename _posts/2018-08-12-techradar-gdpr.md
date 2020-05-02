---
title: 'Getting round GDPR with dark patterns. A case study: Techradar'
layout: post
category: web
article: true
featured: true
---

Many news and big blog sites have introduced onerous and confusing popovers since the introduction of [GDPR](https://ico.org.uk/for-organisations/guide-to-the-general-data-protection-regulation-gdpr/) in May. Unfortunately, this will no doubt result in GDPR [banner blindness](https://www.nngroup.com/articles/banner-blindness-old-and-new-findings/), where users will simply click 'Accept', thereby allowing websites to install tracking javascript, just as they did before 25 May 2018.

This is not GDPR's fault. [The guidelines are clear](https://ico.org.uk/for-organisations/guide-to-the-general-data-protection-regulation-gdpr/lawful-basis-for-processing/consent/). Websites have to:

- ask users to explicitly opt-in to share their data
- not use legalese or similarly unclear language

It would be _very_ easy to design an unobtrusive banner that did this. Something like:

{% include pull-quote.html text="We can share your anonymised browsing history with advertisers so you get tailored adverts <a href='#'>Share your browsing history &rarr;</a>" %}

Of course, no-one would ever click this link because no-one _wants_ to be served adverts, or share their data with someone they don't know. As a consequence, sites that rely on tracking and identifying visitors are getting round GDPR by the way they know best: <i>obfuscation</i>. They _could_ rephrase this request to collect data by being honest about why they need it:

{% include pull-quote.html text="We can share your anonymised browsing history with advertisers so you get tailored adverts. <strong>We rely on the money we get from tailored adverts to pay our journalists. Please <a href='#'>share your browsing history &rarr;</a></strong>" %}

There are very few examples of sites doing this well. [Smashing Magazine](https://www.smashingmagazine.com) is one, although it recently moved to a part-subscription model for its income, so isn't reliant on installing tracking cookies. The pop up is a minor annoyance which presents a simple binary choice (although you are nudged to accept cookies through the placement, colour and attached image of the <i>Okay</i> option, and the button labels could describe the actions more explicitly):

{% include figure.html url="smashing-mag-consent.jpg" alt="A small pop up in the corner of the screen on the Smashing Magazine website" caption="Smashing Magazine does opting in the right way" %}

But old habits die hard. [Techradar](https://www.techradar.com/uk) writes reviews of electronic things -- it's a useful resource if you're comparing products. Here's the popover they display when you visit their site. I'm sure they're not the only website doing this sort of thing:

{% include figure.html url="techradar.jpg" alt="Popover with small text and confusingly labelled buttons" caption="The Techradar advertising opt-in dialogue" %}

There are a few [dark pattern](https://darkpatterns.org/) techniques at play here that make proceeding without opting-in difficult:

- You only get to access the site immediately by clicking 'I accept' -- the popover makes proceeding any other way impossible. Most users will therefore click 'Accept' without thinking.
- The 'I accept' link is bigger than the link to not opt-in (which isn't labelled clearly, of course). It's labelled 'Show purposes' and set in pale blue, hard to see 12 pixel type. It's easy to ignore. The design implies it's a secondary, perhaps technical action.
- 'Show purposes' is confusing. I don't want to see how Techradar uses cookies. What I want to do is _not_ opt-in. Will clicking this link allow me to not opt in? Will I have to read more stuff in order to proceed without logging in? It should be labelled something like _Don't accept and proceed_. I'm really having to think in order to make my way through this UI.

Unfortunately, clicking 'Show purposes' to not opt-in doesn't end the process. Instead, it reveals the following:

{% include figure.html url="techradar2.jpg" alt="Another popover with small text and confusingly labelled buttons" caption="The second popover. You're not done yet." %}

Another popover to negotiate, using the same dark pattern techniques. The primary action is not to not opt-in (we're in the land of the double negative), but to accept the site's cookies. The secondary, 'technical' option is to _Reject all_. Presumably that'll do the job:

{% include figure.html url="techradar3.jpg" alt="A third popover with small text and confusingly labelled buttons" caption="Another popover. Another small, confusingly labelled link to click." %}

I get the feeling Techradar _really_ don't want us not to opt-in. Again, the primary action leads us to opt-in, and the alternative is very confusingly labelled. Presumably, 'Leave' means _leave the website_? But I do want to read the article. Techradar have put me in a situation where it seems I _have_ to accept cookies in order to use the site. Let's see what happens if you do click 'Leave', though. Ah, success! Sort of:

{% include figure.html url="techradar4.jpg" alt="A third popover asking the user to not use an adblocker" caption="Perhaps unsurprisingly, Techradar don't like adblockers. So they throw a popover at you." %}

At least the text here is clearer, and Techradar are honest about why they don't want you to use an adblocker. Incidentally, we'd need to change our more straightforward banner:

{% include pull-quote.html text="We can share your anonymised browsing history with advertisers so you get tailored adverts. <strong>We rely on the money we get from tailored adverts to pay our journalists. Please <a href='#'>share your data &rarr;</a> and turn off your adblocker.</strong>" %}

This is an easy one. We'll continue with our Adblocker, thank you. And we're there. Of course, this being Techradar, we get a popover for our troubles:

{% include figure.html url="techradar5.jpg" alt="A popover asking users to sign up to an email newsletter" caption="Because I really wanted to sign up for a newsletter at this stage." %}

## Are Techradar complying with GDPR?

Technically speaking Techradar are getting explicit consent to collect visitor data. They're obviously not operating in the spirit of the regulations, but I also think they're in breach in at least two areas:

- They make it seem as if you can't use the site unless you opt-in. [According to the ICO website](https://ico.org.uk/for-organisations/guide-to-the-general-data-protection-regulation-gdpr/lawful-basis-for-processing/consent/), you have to <q>Avoid making consent to processing a precondition of a service</q>.
- On the same page, the ICO says you must <q>Be clear and concise</q>. Although this is a subjective requirement, I can't see how anybody could interpret this process as clear and concise.

Bearing in mind the murky history of online advertising, and some sites' reliance on it as a source of income, it's depressingly inevitable that organisations will find ways to get round the new regulations. The only way GDPR will achieve what it set out to do will be through prosecutions. If they don't prosecute, people will just click or tap 'Accept' and the online advertising industry will carry on as before, while claiming it's doing the right thing. I'm skeptical. If you've any interest in privacy and you'd like to keep websites fast, make sure you're using a browser that puts you in control of trackers and cookies, and use an adblocker. Firefox (or, better still, [Firefox Focus](https://www.mozilla.org/en-GB/firefox/mobile/) on a mobile) is the obvious choice.
