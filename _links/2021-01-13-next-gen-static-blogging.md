---
title: "Next Gen Static Blogging"
link-published: 2021-01-09
link-url: https://inoads.com/articles/2021-01-09-Next-Gen-Static-Blogging
link-author: Maximilian Mackh
---

Harumph. Another zealous approach to (absolutely no)tooling when building a blog. This one removes the need to use `p` tags when you’re handcoding HTML pages by... removing `p` tags altogether. Then use CSS to insert line breaks in your prose. This is the first time I’ve seen the single most common semantic element removed from a document in the name of developer/author convenience.

Just use Markdown. If you want to keep absolutely tool-free when publishing, write your article in a Markdown editor and export the text to HTML. Copy and paste into your HTML document. If all Markdown editors disappear from the face of the earth in 2029, then go back to handcrafting your HTML.

But. I have a seemingly simple set of dependencies for publishing this site – you could describe it as a group of text files that are fed through a compiler that generates static HTML. Yet, when you break it down to a list of Ruby gems, Jekyll itself, Github, Netlify etc. it looks a bit more fragile. I can only imagine the terror some NPM-dependent site owners experience in the middle of the night.


