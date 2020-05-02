---

title: Kill the LMS – what a modern library digital presence should look like
excerpt: "Libraries do digital badly. Replace the LMS with an open, queryable database that can talk to other apps that do one job well. Disperse and distribute services through APIs: Kill the LMS or be killed."
article: true
category: libraries
description: An exploration of what libraries should do in order to modernise their digital and web presences. Suggests getting rid of library management systems that fulfil all digital functions and using a more modular, API-based approach.
subject: Digital strategy in libraries
cache: true
img: db-connect.jpg
alt: Database and icons
featured: true
---

## Summary

Libraries do digital badly. Replace the LMS with an open, queryable database that can talk to other apps that do one job well. Kill the LMS or be killed.

## What's a digital presence?

The term _digital presence_ encompasses any point at which a customer or member of staff performs an activity that affects the library's stock (which will include things like physical books, DVDs, eBooks and collections) and/or the customer's account _remotely_. This will include:

- The library website
- Self-service machines
- Apps

What all of these points have in common is a screen that someone interacts with and a connection to a database. Most customer interactions with the library therefore involve some digital element.

## What's wrong with LMSs?

For many years, and for many reasons, library services have bought a single piece of software that controls nearly all the library's digital presence. This software is called a Library Management System (LMS).

LMSs make for poor customer experiences:

- They don't do search well, so library assets can be hard to find
- They can't compete with competitors such as Google and Amazon when it comes to discovering and borrowing resources
- They make for a fractured customer experience: The catalogue of library assets sits separately from the customer website, as do the ebook and eaudio collections
- They don't do CRM well
- They look and feel outdated
- They require customers to learn how to use them

There are many reasons for this set of problems, some of them cultural:

### The wrong staff skills and structure

Library staff are skilled in cataloguing, circulation and categorisation, **rather than fields such as user experience, programming or design**. They therefore often fail to see customer problems and don't know what to look for in a good digital presence.

Furthermore, my experience of library culture is that it's hierarchical, and the people responsible for procuring digital systems are simply the most senior staff, whose skills were more relevant to the pre-Google age.

### One old solution to many modern problems

LMSs offer a single solution to a complex array of problems, which makes them attractive to unskilled procurers.

Similarly, a good digital presence requires lots of integration between good quality systems: library services and local authorities have neither the will or expertise to carry out this integration.

### Dysfunctional relationship between providers and procurers

These factors have combined to create an unhealthy ecosystem of providers and procurers. Because there's been no incentive to improve libraries' digital presence, LMSs and the established library equipment providers have been able to peddle essentially the same product for decades for huge amounts of money &#8211; easy government money.

On the procurement side, a **cosy, internal LMS language** and set of protocols have evolved that stifle innovation and discourage new players from entering the market. Take acronyms and terms like LMS, SIP, LCF, circulation, enquiry and OPAC. These are more often than not symptoms of problems such as proprietary protocols (SIP) and fractured user experiences (OPAC), but that's the <i>lingua franca</i> of the library IT world.

## What a digital presence should look like

In order to solve our customer experience problems, we need to get rid of the LMS altogether. Here's what I think an alternative could look like:

### 1. The core is a database with an open, published API

The heart of any digital library is its inventory of assets and customers. Its digital presence is the sum of its interactions with this database.

In order to enable as many good quality providers as possible to build apps, websites and self service points, we need to make this database easy to query _and_ easy to process the data it returns.

**All modern digital services publish an open API.** Libraries should be no different.

### 2. Use non-proprietary protocols and systems

In order to open our data to providers outside of the existing library ecosytem we need a secure, library-agnostic path. Again, as with all modern APIs, this should be done via `http(s)`.

When we use an API it should also return data in an open, popular format. The most obvious candidate is `json`.

By using agnostic, published APIs we **open up the market to any number of expert providers**, whether they do mobile apps, website design, search or CRM.

### 3. One provider for one job (and millions more to choose from)

A handful of LMS and library equipment vendors currently provide all points of the library digital presence.

It would be difficult for Google to provide good quality CMS, CRM and email marketing, let alone an LMS provider that hasn't meaningfully updated their product for decades.

Our open API would allow us to choose **the right tool for the right job** in the library digital experience. For example, we could connect our database with:

- Mailchimp for email marketing
- Google Search Appliance or Amazon A9 for search and suggestion
- Wordpress for our website (and therefore WordPress plugins for things like events)
- A specialist app provider for an Android app that could power self-service machines

### 4. More complex, but better and cheaper

Dealing with a single LMS provider and its hangers-on has a major advantage: it doesn't require much work or thought. However obtuse and unagile your LMS vendor, they are at least familiar. You'll probably be speaking to the same people if you work for a different library service.

Procuring more, smaller services requires expertise and effort. You'll also need to manage more commercial relationships.

However, the pay-offs should be huge. Let's explore an example.

#### An example: Self-service machines

At the moment, library self-service machines are built by a handful of vendors, most of whom are closely linked to or even owned by the LMS providers.

All the hallmarks of our dysfunctional ecosystem are in place. The machines tend to be old, they use a proprietary SIP protocol to connect to the library database and they're expensive.

Our current 70 or so self-service machines have come to the end of their natural life (they're actually running Windows XP). The device cost (excluding support and installation) was around £5,000 each several years ago.

We can go to an existing provider for any number of options, but what I'd like to do is copy Argos:

<figure><img src="/images/argos-kiosk.jpg" alt="A Samsung tablet in and Argos store"><figcaption class="figcaption"><p>Argos use Samsung Tablets in kiosk mode for customer search.</p></figcaption></figure>

The set up here is:

- A Samsung tablet in kiosk mode
- An app that connects to the Argos database
- Housing for the device
- A wifi connection to the internet

In a library we'd need to attach a barcode scanner to the tablet.

If we had a database with an open API and used `https` to connect to it, we could get any app developer to build a UI that would guide customers through checking library stock in and out. Our tablet would give us several advantages over the current system:

- A top quality user interface
- The portability of a tablet (you could put one in a cafe so customers could get a coffee, grab a book and, if they liked it, check it out)
- Extend its use by adding a search box to search library assets and indicate where they sit in the library, or even enable payments
- Save &pound;000s

If you could get 70 tablets at a cost of around &pound;9000 you're going to be saving hundreds of thousands of pounds, even after you've taken installation, development, project management and testing costs into account. And you'll have a better product.

You can see why the LMS and self-service machine vendors have no interest in opening up their data.

## Libraries are nothing special

Or rather: the nuts and bolts of library systems are essentially the same as any retail operation. You have stock you track, and customers who interact with that stock.

LMS providers and procurers have created a proprietary world that excludes technological developments. The only winners have been the providers and their hangers-on and the unskilled procurers, while customers and frontline staff struggle with creaking, unfriendly systems.

We need to get over ourselves to move forward.

## And if we don't kill the LMS?

I'm an optimist at heart. The purpose and universal appeal of libraries should be stronger than ever in an increasingly commercial and atomised world. Digital experience _could_ help customers from all walks of life take advantage of their library. [We do have advantages over the Googles and Amazons of this world](/2015/11/danger-of-automation/).

Changes are already in the air. The [Libraries Task Force](https://www.gov.uk/government/groups/libraries-taskforce) recently commissioned Canadian company Bibliocommons to write [a report on what a national digital library service would look like](http://www.thebookseller.com/news/lack-of-digital-library-investment-pushing-users-away-312801). Bibliocommons interviewed me (along with several other library folk) while researching their report, and invited a few of us to a workshop at the Department for Culture Media and Sport to present their proposals back in September 2015.

However, at this moment we're failing miserably to provide a good digital experience. In the age of Google and Amazon the competition is fierce: I can get a book on my device for a few quid and a handful of screen taps without leaving my house. If ever an area was ripe for disruption it's library digital.

**If we don't offer a good experience to counter Google and Amazon, customers won't bother with us.** And who could blame them?

That's deadly in an age of austerity. We need to make our case to as many people as possible, not just those who have to use the library service or have used it for years. If most customer interactions with us are digital, we have to make sure their experience is pleasurable and engaging from the off. At the moment digital adds very little to our case beyond some headlines about lending ebooks.
