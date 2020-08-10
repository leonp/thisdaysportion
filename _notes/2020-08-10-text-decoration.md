---
title: Getting browsers to underline links consistently
---

Would like `text-decoration: solid underline 2px #0000FF` to work so the text colour could differ from the (slightly thicker than default) underline. Annoyingly, browsers seem to have patchy support, with Safari and Firefox mobile particularly poor. The “fix” I found was to set individual text-decoration properties, such as `text-decoration-thickness` and `text-decoration-color` as these appear to work consistently across browsers.
