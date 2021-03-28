---
date: 2021-03-28 20:01:52 +0000
title: Firefox in-page anchor linking oddity
mb-cat: ''

---
Not sure if this is a bug... the [comments link on this page](scroll-behavior: smooth;) should link to the comment form. Instead, it appears to link to an image when I click it in Firefox `86.0.1 Build ID 20210310152336`. There are a few large lazy-loaded images on the page, and the `HTML` element has `scroll-behavior: smooth;` applied in the CSS. Appears fine in Safari in MacOS.