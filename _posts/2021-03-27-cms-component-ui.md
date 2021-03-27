---
title: CMSs should allow component-based page creation, but does WordPress Gutenberg
  get it right?
category: web
sub: Allowing web editors to create pages from smaller components such as callouts,
  promos and alerts is a good thing. But what’s the best way to implement these in
  a CMS? Does the WordPress Gutenberg editor take the right approach?

---
My former colleague [Alice was bemoaning the lack of a way of dropping various components into a page](https://twitter.com/alicetheunique/status/1371906984052723716) using her current CMS. She’s right, I think; you’d expect any modern CMS to allow editors to build pages from smaller, self-contained elements, such as alerts, promo boxes, galleries and accordions.

Unless your pages follow a predictable pattern – on a blog, for example – you’re relying on the theme author to code a finite set of templates that will cover a set of requirments you need to predict when the site’s built.

This was one of the main requirements when we rebuilt [the work website](https://www.suffolklibraries.co.uk) using [Statamic](https://statamic.com/) last year. We ended up with a list of around 20 components we could drop into any page, ranging from simple alerts to more complex collection listings:

{% include figure.html url="sl-bard.jpg" alt="Screenshot the Suffolk Libraries page editor." caption="Building a page in Statamic 2" %}

Some simple maths tells us we can create around 400 different page layouts based on shifting these components around. WordPress.com includes around 100 different “blocks” out of the box, giving editors even more possibilities.

## Different approaches to implementing component/block UIs

Statamic and WordPress offer different ways for editors to create components. Statamic takes a more form-based approach, where the editor enters data into clearly styled fields.

{% include figure.html url="bard-z-bar.jpg" alt="Screenshot the Suffolk Libraries page editor z-bar component creator." caption="The z-bar UI consists of a form where editors enter text into fields or use a standard file picker." %}

The editor doesn’t have any visual relationship with what’s rendered on the actual website:

{% include figure.html url="rendered-z-bar.jpg" alt="Screenshot of the Suffolk Libraries website." caption="A typical z-bar on the Suffolk Libraries website." %}

[WordPress’s Gutenberg](https://wordpress.org/gutenberg/), on the other hand, attempts to make the editor look more like what will appear on the website. For example, this is the “cover” block (an image with some text over it):

{% include figure.html url="wp-cover-editor.jpg" alt="Screenshot of the WordPress cover block editor." caption="WordPress doesn’t use traditional form fields. Instead, it attempts to give the editor an idea of what the block will look like on the website." %}

This would _appear_ to be a good idea – tying the editing process to its output saves an element of guesswork and flipping between rendered page and the CMS. But having set up several users on WordPress, and trained a couple of editors in Statamic, I think it poses a few problems.

Firstly, filling in and amending traditional forms is a familiar, predictable process. You enter some text, select an element from a dropdown or complete a file upload dialogue. If you want to the edit the text, you head back to the relevant field and just fill it in again.

In WordPress, this process varies according to the block you’re editing, and can involve experimentation and guesswork. For the cover editor it’s _fairly_ clear, but involves an element of discovery – you click on the image, which reveals a toolbar with a ‘Replace’ option:

{% include figure.html url="edit-wp-cover.jpg" alt="Screenshot of the WordPress cover block editor." caption="You have to click on the picture to reveal the toolbar." %}

The picture slider block works differently. When you click on the block, a different type of toolbar appears, with no ‘Replace’ option:

{% include figure.html url="wp-slider-editor.jpg" alt="Screenshot of the WordPress slider block editor." caption="You have to click on the picture to reveal the toolbar, but this one is a lot different." %}

In my experience, less technically skilled editors find this frustrating, even when they have experience of using different CMSs, including pre-Gutenberg WordPress. In every case, I’ve ended up installing the [the Classic Editor](https://wordpress.org/plugins/classic-editor/).

Secondly, editors can find it difficult to navigate around a page and add new content without the framework of clearly demarcated boxes and forms. Take this example of the verse block followed by a cover. Coming out of the verse block and starting a new paragraph involves a frustrating number of clicks:

{% include figure.html url="wp-full-2.jpg" alt="Screenshot of the WordPress cover page editor." caption="Simply entering a new paragraph on longer, more complex pages can be surprisingly difficult." %}

**I’m a really big fan of WordPress**. It offers a free, fast way to get online and publishing to the indieweb. Half of the features I implement on this site, such as comments, come out of the box. It has a huge range of plugins, and is mature, stable software that handles updates and upgrades fantastically well.

But I think Gutenberg causes problems for editors who won’t be willing to learn how it works. There are some poor UI decisions to overcome. Perhaps more worringly, I think it may be misconceived – keeping content separate from its appearance allows users to focus on creating and editing; let the designer worry about how it ends up looking.

Of course, I could be wrong. My experience is limited to four or five people. Maybe tens of millions are happy with Gutenberg. But it’d be interesting to see how often the Classic Editor is installed.