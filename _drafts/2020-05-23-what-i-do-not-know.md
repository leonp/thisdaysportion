---
title: "What I don’t know"
category: web
---

We’re redoing [the work website](https://www.suffolklibraries.co.uk/). It’s been [static for the last four years](/posts/static/), but we’re moving to a more traditional PHP/server-side set-up, mainly because we want a reliable, flexible CMS that all the digital and marketing team can use. We opted for Statamic because it’s well supported and stores data in files rather than a database, seeming to find a sweet spot between features, speed and security.

I consciously went for a traditional set up – and chose [a sympathetic agency to develop it](https://clearleft.com) – because I have opinions on accessibility and speed. However, this did prompt me to consider what I do and don’t know about what is generally termed _modern web development_. In turn, I learned a few new things, which I’m using on this site. (You may be surprised to learn this bearing in mind how simple this site is.)

So, the things I don’t know about the web:

## SVG

No, that’s not quite true – I do know what SVG _is_, it’s just that I don’t know how to use it to its full potential. So, I’ll more than happily point to an `.svg` file in an `<img>` and in a `background-image` because I know it’ll scale properly and the file size is generally small compared to, say, `jpg` or `png`. I can edit `stroke` and `fill` in a text editor to change colours. But I don’t know about inlining SVGs and using CSS to do more interesting stuff.

## Responsive images

I got stuck at `max-width: 100%` and `height: auto`, which means images don’t extend beyond the edge of a mobile phone screen, causing an annoying horizontal scroll bar to appear. But I’ll serve the same image whether you’re using an iMac or a Moto G4.

##
