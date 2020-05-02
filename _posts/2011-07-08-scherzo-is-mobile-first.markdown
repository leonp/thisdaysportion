---

title: Scherzo, mobile first (and what that means for you)
category: web
---

You may have heard me describe [my Scherzo theme](http://leonpaternoster.com/wp-themes/) as ‘mobile first’, a phrase that was first used (as far as I'm aware) by [Bryan Rieger](http://yiibu.com/articles/rethinking-the-mobile-web/).

Scherzo has been built on the principles Bryan outlines. By that I mean:

- the layout adapts to the reader's viewport. So if you're using a mobile phone you'll see a one column version of the theme. If you're using a desktop PC (or a tablet in landscape mode) you'll see a two column version.
- you won't have to scroll horizontally to read from Scherzo as images also scale with the viewport
-file sizes have been kept to a minimum. Scherzo loads [a tiny javascript file](http://html5shiv.googlecode.com/svn/trunk/html5.js) to make Internet Explorer understand [HTML5 elements](http://html5doctor.com/element-index/). There are no fancy graphics or effects.
-most importantly **Scherzo works on any mobile device**. Some themes are ‘responsive’ when viewed on certain high–end devices (iPhones, iPads, Android etc.), but bork when viewed on older phones. Scherzo should work on all devices, regardless of age, manufacturer, browser etc., and is, as far as I'm aware, the only WordPress theme in the [official directory](http://wordpress.org/extend/themes/) that is built in this way (feel free to correct me!)

To see how this works visit the [Scherzo demo site](http://leonpaternoster.com/scherzo) and resize your browser window. View it with any mobile device. It _should_ display with no problems at all, shrinking to one column when appropriate.

## What that means for Internet Explorer

Internet Explorer (IE) (pre version 9) doesn't understand the code that tells it to display two columns on a desktop monitor.

<del>It is possible to force older versions of IE to display two columns by using [javascript](http://en.wikipedia.org/wiki/JavaScript). Originally, Scherzo did just this. However, I found that [this javascript](http://code.google.com/p/css3-mediaqueries-js/) caused problems with child themes. (Note: that's not to knock the script in question. It generally works extremely well.)</del>

<del>I therefore decided to remove the javascript. This means that **older versions of IE display one column regardless of viewport size**:</del>
