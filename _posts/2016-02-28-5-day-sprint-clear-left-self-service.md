---

title: A 5 day sprint with Clear Left exploring library self-service machine software
category: work
description: An account of running a design sprint in order to plan a web product, in this case library self-service software. Includes a timetable, techniques and overview of the outcomes. The sprint was run by Leon Paternoster and Clearleft for Suffolk Libraries.
subject: Design in libraries
article: true
excerpt: "An account of running a design sprint in order to plan a web product, in this case library self-service software for use across Suffolk’s libraries – and beyond. Includes a timetable, techniques and overview of the outcomes."
cache: true
img: first-wall-poster.jpg
alt: A large poster of a plan on a wall
---

Last week we spent 5 days with digital agency [Clear Left](http://clearleft.com/) exploring how we might develop new self-service machine software for libraries.

Here are a few observations about how Clear Left and a sprint work. It was certainly very useful for me, and you might find it interesting if you do any design work with clients, or you work with external agencies to explore any digital area. If you work in library IT read on to find out about what the future of self-service _might_ look like.

## Background

We're replacing the self-service machines customers use to check out and return books in libraries. The machines were installed about 8 years ago (in this respect libraries are years ahead of supermarkets).

A lot has changed in the last 8 years &#8211; in 2008 there was no such thing as an iPad and the world wasn't quite as connected to the internet as it is now.

<figure>

<img src="/images/self-service-unit.jpg" alt="A current self-service unit" class="bleed">

<figcaption class="figcaption"><p>A current self-service unit</p></figcaption>

</figure>

Over the last few weeks, the IT team has been discussing what a new self-service system might look like. We want something a lot more portable, cheaper, device agnostic and easy to manage than the current system. All this led us to conclude that some sort of web app might be the best approach, rather than, say, a Windows client or an Android app.

As there aren't any software-only providers out there, we'd need to build it ourselves (or rather, get someone to build it for us).

At this stage we felt we needed an expert opinion. Was this really the right approach? If so, what might a web app look like? What problems might we run into? How do we go about this project?

We chose Clear Left because they've done [similar digital strategy work with organisations like the Wellcome Trust](http://clearleft.com/made/wellcome-trust-digitalstories). Most of all, I felt they'd keep accessibility to the fore; not just in areas such as designing for older people, but in keeping the system as open and device agnostic as possible.

There's a longterm business advantage in keeping our hardware, software, library management system (LMS) and software _decoupled_ (a word we used a lot during the week), and in extricating ourselves from [the cosy LMS/self-service provider world](/2015/12/kill-the-lms-future-digital-experience/).

Since one of Clear Left's founders [Jeremy Keith](http://clearleft.com/is/jeremy-keith) has been [writing about the core technologies of the web](http://alistapart.com/article/behavioralseparation) for over a decade, they seemed the right choice.

As you can imagine, I was pretty excited to get Jeremy and James Bates into the library for a weeklong _sprint_. I got a stack of A3 sheets ready for Monday morning.

<figure>

<img src="/images/james-and-jeremy.jpg" alt="James Bates and Jeremy Keith" class="bleed">

<figcaption class="figcaption"><p>Clear Left's James Bates and Jeremy Keith (in thoughtful mode)</p></figcaption>

</figure>

## Making it up as you go along (and visualising it)

Before the sprint we sent Clear Left our own research and thoughts on self-service, including a report from a staff workshop we'd run a couple of weeks beforehand. We'd agreed some basic outputs we wanted from the week; namely, a feasibility report and perhaps some sort of sketch of what a web app could look like.

I'd also arranged for several staff members and volunteers to turn up on the Monday morning. What we were going to do I wasn't sure.

Before the staff workshop, James helped us visualise the sprint by putting a diagram up on the wall. At the start, days 1-5 were pretty empty. That would change over the week.

The workshop helped define our self-service &#8216;problem&#8217; and gave us a rough plan:

<figure>

<img src="/images/first-wall-poster.jpg" alt="A poster planning the week's activities and work" class="bleed">

<figcaption class="figcaption"><p>The work plan poster at an early stage</p></figcaption>

</figure>

You've probably heard terms like _agile_, _lean_ and _sprint_ before: this was, I guess, agile in action. It's a good process as you react to whatever you discover, rather than try to squeeze your findings into a predefined structure. You don't want to simply reinforce your initial ideas, however attached you are to them; instead, you're looking to test them and throw them out if necessary.

And a sprint has a definite end product. It avoids projects getting bogged down.

## Involving everyone

I was surprised at just how much James and Jeremy involved the IT team &#8211; and staff as a whole &#8211; in the work. At one stage we had library information advisors and the finance manager sketching interfaces alongside Jermey Keith and James Bates:

<figure>

<img src="/images/sketching.jpg" alt="Staff at a table sketching self-service ideas" class="bleed">

<figcaption class="figcaption"><p>Staff sketching self-service ideas with Clear Left</p></figcaption>

</figure>

James and Jeremy based their _war room_ in our Lab (a mediumsized room on the top floor of Ipswich County Library). The door was always open and staff and stakeholders were encouraged to pop in whenever they liked to ask questions and get involved. In fact, a lot of the research and testing took place in the library itself; James and Jeremy were very visible throughout the week.

I think there are some very solid reasons for taking this approach. Firstly, it recognises that anybody can have a good idea when it comes to a service they work with and/or use. Secondly, it gets people behind the project; it becomes something they feel a part of.

## A lot of it's actually teaching

Teachers will recognise the skills you need to run a successful sprint. There's the basic organisation, the ability to express and elicit ideas using different learning styles and the knowledge of how to pitch and time activities. There was even a starter/main/plenary structure to some of the work.

James did most the facilitation, using a mix of visual and verbal activities, often strictly timed. For example, we were asked to note down 8 ideas for self-service, which could be as practical or science fiction as we liked (I rather liked my book wayfinding idea &#8211; one for the future, perhaps). We then chose two of these to sketch and got the rest of the group to critique them.

<figure>

<img src="/images/interface-sketches.jpg" alt="Sketches of self-service interfaces" class="bleed">

<figcaption class="figcaption"><p>Some of the interface ideas we came up with</p></figcaption>

</figure>

The final stage involved assigning all the sketched ideas points based on how important we felt they were. This gave us the basis for our proposed product, which Clear Left suggest we divide into minimal viable product (MVP), phase 2 and backlog sections:

<figure>

<img src="/images/mvp.jpg" alt="Features on post-it notes divided into sections" class="bleed">

<figcaption class="figcaption"><p>The final product feature list takes shape</p></figcaption>

</figure>

## Bringing it all together

We did a _lot_ of work over the week (it is a sprint, after all). Jeremy looked into a javascript library that uses a device's camera to recognise barcodes, but found it wasn't _quite_ ready (unfortunately &#8211; getting rid of peripheral devices makes the whole web app approach a lot easier, and reduces our hardware costs). However, we did establish we could use an API rather than the SIP protocol (really good news &#8211; it means we can use simple https to connect to the LMS, while accessing all the data we hold on borrowers and titles). James produced some clickable prototypes that helped everyone picture what our own self-service app might actually look like:

<figure>

<img src="/images/prototype.jpg" alt="A prototype self-service app on a tablet" class="bleed">

<figcaption class="figcaption"><p>An early self-service prototype</p></figcaption>

</figure>

I can't recommend this kind of research sprint enough. We got a report, detailed technical validation of an idea, mock ups and a plan for how to proceed, while getting staff and stakeholders involved in the project &#8211; all in the space of 5 days.

(See [Clear Left's write up of the week](http://clearleft.com/made/suffolk-libraries-design-sprint).)
