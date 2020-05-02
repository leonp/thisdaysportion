---

title: Setting up WordPress style year and month URLs in Jekyll
category: web
---

Just a quick note to mark my move from WordPress to <a href="http://jekyllrb.com/">Jekyll</a>.

If you were using this common WordPress permalink structure:

`sitename/YY/MM/post-title`

You'll probably want to replicate it in Jekyll so as to keep all your links live. Doing this is really simple. Add the following line to your `_config.yml` file:

`permalink: /:year/:month/:title`
