---

title: Separating services is preferable to surface integration (or 3 principles for a web strategy)
excerpt: It's a bad idea to make web things look like other things when they're something else altogether. Instead, integrate services to make for better user experiences.
category: web
article: true
---

At work, our approach (or &#8216;strategy&#8217;, if you like) is to incorporate as many services on our own website as possible. So if a customer wants to find a book, CD or download ideally they'd go to `http://suffolklibraries.co.uk`, do a search, browse the results and reserve/download it without leaving the site.

The reasons for this are pretty obvious:

- Customers make no distinction between services. They expect to find everything on the library website &#8211; the idea of a separate searchable catalogue doesn't even occur to them, just as they wouldn't expect to leave Amazon to buy a book.
- Shifting between sites is confusing and a chore. It means we lose customers.

Unfortunately, it's difficult to follow this approach. Library catalogues live separately from library websites, mainly because the library was traditionally a small part of a council's bigger website, and integrating the two would represent a huge amount of work. To be honest, I'm not sure this even occurred to library services. It's easy to buy an off the shelf library management system that shifts all the web work to the supplier.

This is a problem. We shunt customers off to websites that offer miserable search and user experience. I've yet to find a UK library that offers a responsive catalogue and search results sorted by relevancy properly. (Take a few seconds to digest the lunacy of the second part of that sentence.)

Once upon a time, we tried to tackle this problem by making the catalogue _look_ like our website. You can see why this makeover approach would appeal as it might ease the friction of moving between sites. But it soon ran into problems:

- Whenever we wanted to change the appearance or structure of the main website we'd have to update the catalogue.
- We had little control over the catalogue's HTML or scripting.
- There was no local/staging/production workflow.
- The catalogue's code was completely undocumented, poorly structured and liable to change whenever the provider updated the software.
- While the sites looked the same, underneath they weren't, which meant we could confuse customers quite easily. For example, customers would use the site search box to search for titles.

We therefore took the decision to uncouple the site from the catalogue, until we built something that could integrate the two properly. In turn, we added something else to our strategy:

_Don't change things we don't have full control over. Separation is preferable to false integration. Concentrate on integrating things properly._

We apply this to _all_ our web work. It's an important principle as it helps us maintain control of our web experience as much as possible.

Of course, whether other parts of the organisation understand this is a different matter. It's not entirely unknown for someone to approach us to say they've bought a web product from supplier _x_ and they'd like us to make it look like our website. Unfortunately, the answer is _no_ (and you really should involve the web department when you're buying things for the web!)

Which leads to another principle:

_We're always helpful, but we decide how we implement things on the web as bodged solutions are impossible to manage and result in poor customer experiences._
