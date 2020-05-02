---
title: Library websites, catalogues and their poor UX

excerpt: Website and catalogue separation and search stuck in the mid-90s result in poor user experiences.
category: libraries
featured: true
---
I started working for [Suffolk Libraries][1] last week. Over the next few months I&#8217;ll be rebuilding our website. If you take a look now, you&#8217;ll see why.

Libraries and the internet seem to share an uncomfortable relationship. I can see a few reasons for this. The main one is that Online Public Access Catalogues (OPACs) are not designed to slot into existing websites. They live as separate entities.

That&#8217;s why you&#8217;re shunted off to a subdomain or even a different website whenever you search for a title, whichever library website you try:

*   [Manchester Central Library][2]
*   [Birmingham Libraries][3]
*   [New York Public Library][4]

This strikes me as exceptionally poor UX. If I go to find a book on a library website I expect to be able to find it on that site. [Navigating across websites is confusing][5]. And isn&#8217;t a library essentially a collection of texts? Why aren&#8217;t they actually housed in the library?

Libraries have tackled this problem in two ways:

*   Some attempt to make the OPAC seem a part of the main site. This is what we&#8217;ve done in the past, and it&#8217;s my least favourite option. The pages are styled in the same way as the rest of the website, and the navigation is replicated. This strikes me as fundamentally *dishonest*. It also makes it a PITA to make simple changes to the website IA, especially when your OPAC isn&#8217;t a CMS.
*   Others apply some light branding to the subdomain, perhaps through adding a logo. I prefer this approach as it doesn&#8217;t try and hide what&#8217;s happening to the user. But hopping between websites is a confusing experience.

In an ideal world users would tap in their query and the website would display a list of search results. You&#8217;d expect this to be easy enough to implement even if the website itself didn&#8217;t store the database records. That&#8217;s what APIs are for.

But here we run into a second problem. Suffolk Libraries is unique in that it is a completely separate entity from its council. But its OPAC still feels like something from the world of local government – it looks dated and is difficult to talk to. If you were able to come up with a library management system with an easy, open API you&#8217;d make a killing (there&#8217;s a business idea for you.)

It seems that providing services across disparate domains and services has become a habit. That&#8217;s why you&#8217;ll see yet more subsites popping up, such as [ebook provider Overdrive][6].

I suspect this will pose the main challenge in my website redesign. Is there anyone out there with experience of dealing with OPACs? I guess screen scraping is an option. Or is there actually a way to do subdomains and separate websites well?

 [1]: http://suffolklibraries.co.uk
 [2]: https://librarycatalogue.manchester.gov.uk
 [3]: https://library-opac.birmingham.gov.uk/cgi-bin/spydus.exe/MSGTRN/OPAC/HOME
 [4]: http://nypl.bibliocommons.com/
 [5]: http://www.nngroup.com/articles/top-10-ia-mistakes/
 [6]: http://manchesterdownload.lib.overdrive.com/
