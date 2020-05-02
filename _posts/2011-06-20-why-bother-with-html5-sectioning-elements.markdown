---

title: An HTML5 challenge (which lead me to think &#8211; Why bother with HTML5 sectioning elements?)
category: web
---

[David asked for suggestions on how to markup a list of albums using HTML5](http://twitter.com/#!/BrightEyesDavid/statuses/82742770497892353). Each album includes the following information:

- album name
- artist name
- cover image

As with all things HTML5, there are several ways to approach this problem (you may think of some more):

## Using article

I had a vague idea that each album entry could be syndicated as it passed [the _would it make sense in an RSS feed_ test](http://html5doctor.com/the-article-element/).

But David specified a list, so I discounted this approach.

## Using dl

David suggested using a description list, which would appear to fit the bill perfectly as the data consists of a collection of names (album titles) and bits of information (or _values_) grouped under these names (artist and cover image).

The HTML5 spec is quite flexible as [the `dt` doesn't have to be a term](http://html5doctor.com/the-dl-element/).


I argued against this on the grounds that titles are better rendered as headings and I wasn't sure that it's ‘valid’ to place images within `dd` tags. (Although I'm no longer convinced that this is the case.)

And the list is ordered, which suggests:

## Using ol


This makes sense in that we can suggest an order to our list. As a bonus, HTML5 allows us to place block level elements within inline elements ([with some caveats](http://dev.w3.org/html5/spec/Overview.html#restrictions-on-content-models-and-on-attribute-values). It's never simple).

I think this is probably the best approach (although you may feel differently).

Now, this is all fun, but it does make me think _what do these new elements actually bring us apart from more to think about?_

After all, we could add some [microdata](http://en.wikipedia.org/wiki/Microdata_(HTML5)) or some such to our markup in order to make it more visible to Google. We could style a microformat to make it more visually meaningful.

I can think of no real world value in using `article` over, say, `<div class="hentry">` when the use of `article` just generates (admittedly interesting) [discussions about semantics](http://html5doctor.com/the-article-element/).

More seriously, [HTML5 makes it difficult to structure documents properly](http://www.456bereastreet.com/archive/201106/on_using_h1_for_all_heading_levels_in_html5/), and, of course, Internet Explorer (pre–version 9) needs a javascript injection to get it playing nicely.

## A sensible approach to HTML5

I've been using HTML5 for a long time now. I like using `article` to mark up articles and dividing articles into headers, content areas and footers.

However there's no practical reason for using HTML5 sectioning elements at the moment, and there are a few reasons for not using them.

I'm thinking about taking the following approach:

* Use the doctype and shortened meta tags
* Take advantage of the looser validation rules (so go ahead and place block level elements in inline elements)
* Use the refactored, previously unfashionable tags such as `i` and `hr`
* Replace `article`, `header`, `aside` _et al_ with `div`
* Make use of microformats, micordata and RDFa

Make sense?
