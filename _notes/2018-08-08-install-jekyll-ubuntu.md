---
title: 'Installing Jekyll in Ubuntu'
layout: post
category: web
---

There's more than one way to skin a cat, but this was easy and quick. My project builds and serves. I last did this about 3 years ago, and used rvm, I think. That may be a better way -- <abbr title="Your mileage may vary">YMMV</abbr>. Using Ubuntu 18.04.

1. `sudo apt-get update`
2. `sudo apt-get install ruby`
3. `sudo apt-get install ruby-dev`
4. `sudo gem install bundler`
5. `sudo gem install jekyll`
6. Move to the project directory
7. `bundle update`
8. `bundle install`
9. `bundle exec jekyll s`

Step 3 will save you tears. Bonus: The (large) project I was working on builds in 45s; it normally takes 120s+ on OS X. It's under 3s with an `--incremental` build switch 😁
