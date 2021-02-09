---
layout: default
title: Search
footer: true
visited-links: true
prose-headings: true
underlined-links: true
hyphens: true
---

<form class="c-sans-serif w-100 pb3 pb0-l relative c-hide-if-no-js">

    <label for="search-input" class="db f7 mb1">Type some words for instant search results:</label>

    <input type="text" role="combobox" autocapitalize="off" name="search-input" id="search-input" class="c-bg c-bg-search c-bg-in-input w-100 c-sans-serif pl4 pr1 pv1 ba b--light-silver c-remove-ios-borders" autofocus>

    <div role="listbox" class="mb2 tl absolute w-100 left-0 top-1 c-sans-serif c-max-vh-10 overflow-x-hidden overflow-y-scroll" id="results-container">

    </div>

</form>

<noscript>

    <form class="c-sans-serif w-100 pb3 pb0-l" method="get" action="https://www.google.com/search">

        <input type="hidden" name="sitesearch" value="thisdaysportion.com">

        <label for="q" class="clip db f7">Search this site with Google:</label>

        <div class="flex border-box w-100">

            <input autofocus type="search" autocapitalize="off" name="q" id="q" class="c-sans-serif pa1 ba b--light-silver c-remove-ios-borders f7 w-80 w-auto-l">

            <button type="submit" class="f6 pa1 ba b--moon-gray bg-dark-blue hover-bg-dark-gray white pointer c-remove-ios-borders f7 w-20 w-auto-l">Search</button>

        </div>

    </form>

</noscript>



