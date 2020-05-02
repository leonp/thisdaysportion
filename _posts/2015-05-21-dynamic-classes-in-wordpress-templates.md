---

title: Generating page specific classes in WordPress templates to keep code DRY and extensible
excerpt: How to generate page specific class names in a WordPress template, making it easy to extend your code and keep it <abbr title="Do not Repeat Yourself">DRY</abbr>
category: web
---

_How to generate page specific class names in a WordPress template, making it easy to extend your code and keep it <abbr title="Do not Repeat Yourself">DRY</abbr>_.

At work we use WordPress to run our main website. We've built a child theme that includes lots of custom templates so we can build non&#8211;standard of pages.

One such template is `custom-hero.php`. It calls the site header and displays the page excerpt on top of the custom image, should the page author have specified an excerpt and image in the WordPress page editor. You can see it in action on our [Summer Reading Challenge](http://suffolklibraries.co.uk/events-activities/summer-reading-challenge-2015) page.

If you build a new page you'll get some default styling. The hero image caption has a corporate purple background (`#642D91`) and is positioned in the bottom left of its containing `div`. The page title is centred and inherits the default heading `font-weight`.

Sometimes we might want to change these default styles. For example, we might build an event page which calls for a more muted approach, perhaps through a lighter heading `font-weight`, or a less garish caption background colour.

One way we could do this is by creating another WordPress custom template (`custom-hero-tasteful.php`, perhaps), but that's obviously somewhat inefficient. Instead, we can go a bit more <abbr title="Do not Repeat Yourself">DRY</abbr> and extend `custom-hero.php`'s classes.

## Static and dynamic class names in WordPress templates

We want our template to spit out <abbr title="HyperText Markup Language">HTML</abbr> with a static, default set of class names and something dynamically generated that's unique to the page.

Take a look at the `figcaption` classes on the [Summer Reading Challenge](http://suffolklibraries.co.uk/events-activities/summer-reading-challenge-2015) page for an example:

`class="sl-hero-splash-text sl-hero-splash-text-summer-reading-challenge-2015"`

We want all pages built on `custom-hero.php` to use the `sl-hero-splash-text` declarations, but only the Summer Reading Challenge page to use `sl-hero-splash-text-summer-reading-challenge-2015`

How do we do this in one WordPress template?

We basically need to spit out a piece of page specific text in our template. The most obvious page property that does this in a CSS friendly way (i.e. with no non&#8211;standard characters or spaces) is the page slug (`summer-reading-challenge-2015` in our example). We can grab the post slug by querying the `$post` object:

`global $post; echo $post->post_name;`

So if we use this code in our `custom-hero` template we get static and dynamic class names:

{% highlight php %}

<figcaption class="sl-hero-splash-text sl-hero-splash-text-<?php global $post; echo $post->post_name; ?>"><?php the_excerpt(); ?></figcaption>

{% endhighlight %}

By using dynamic class names we don't have to write additional templates whenever we want to make minor styling changes. We make our code a lot more manageable.
