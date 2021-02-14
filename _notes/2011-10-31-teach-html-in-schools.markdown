---

title: Web writers should know HTML so teach it in school
category: web
---

If you write long form texts for the web you should know HTML.

If you don't know HTML and you're publishing web stuff you're screwed for several reasons:

* you'll paste documents from Word into a CMS and generate markup that makes no sense. Your article may look OK, but Google won't understand it.
* in an effort to make a sentence stand out more you'll make it an `h1`. Again, it may well create the desired visual effect, but it won't make **sense**.
* when someone else comes to edit your work they'll hate you for it. Why is this sentence a top level heading?
* your content isn't portable. Want to move it from your current CMS to a new one? Suddenly, you've got a bunch of `h1`s everywhere.
* your content isn't accessible. Screen readers will interpret your big bold text as a heading.


This may seem quite obvious (and most web editor/manager jobs demand knowledge of HTML). But you'd (perhaps) be surprised at how difficult this is to explain to non–web types. And how often the people responsible for putting documents online **don't** understand this.

If you've only used Word to write documents there's no reason why you'd know there's a distinction between content and its presentation. If you want to make something stand out you select it and increase the point size.

And while your office may have an HTML–savvy editor, there may be some places where s/he isn't responsible for adding online content.


## Making web content meaningful


One solution to this problem is to lock down your editor so you can only format text semantically. No colour, underline or indentation options.

Cleverer systems could offer meaningful alternatives to large red text, such as _call to action_, _warning_ or _information_ and apply CSS classes to the selected text.

This approach would enforce some kind of semantic order, but there's still nothing to stop editors from applying _Heading 1_ to any text they want, or trying to shift a block of text to the right by adding lots of spaces.


## Teach HTML in school


The only real way to overcome this problem is to learn the concept of markup.

The best way to do this would be to teach it at school. Not in IT lessons with Dreamweaver, but in English.

I'm not saying students should learn about `doctype` or how to link to a stylesheet. But understanding the difference between content and its presentation is going to be a useful workplace skill.

And using headings, sections and other elements is going to teach them how to structure certain types of texts regardless of the publication medium.

After all, if students are learning how to use an old fashioned word–processor why not teach them very basic markup?
  *[HTML]: HyperText Markup Language
