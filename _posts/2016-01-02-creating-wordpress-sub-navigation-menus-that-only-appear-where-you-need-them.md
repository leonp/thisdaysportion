---

title: Creating WordPress sub navigation menus that only appear where you need them
category: web
---

It's a bit of a mouthful and hard to explain, but if you build a relatively complex work website you'll appreciate this.

At Suffolk Libraries we build microsites that sit within the main site. Often, these will have their own sub navigation. Take <a href="http://suffolklibraries.co.uk/community-services/literacy-books-and-reading-team-for-schools">our schools service</a>:

<figure class="figure">

<img src="/images/lbarts-subnav.jpg" alt="Screenshot of the Suffolk Libraries website" width="800" height="347">

<figcaption class="figcaption"><p>A microsite with a horizontal sub navigation menu</p></figcaption>

</figure>

Apple also uses a sub navigation consisting of icons and labels:

<figure class="figure">

<img src="/images/apple-submenu.jpg" alt="Screenshot of the Apple website" width="800" height="297">

<figcaption class="figcaption"><p>Apple's Mac sub menu</p></figcaption>

</figure>

In the past, we've created a custom menu in our <code>functions.php</code> file for each of these subsites. In order to display this custom menu, we've had to also write new header and template files. Before you know it, you've got 40-odd files in your WordPress theme.

We're currently rebuilding the back end of the website, and one of the things we're trying to do is abstract our layouts so we only use a handful of template files. So instead of creating separate template files for our schools and mental health information services, we want to use, say, one full width template with no additional custom header templates.

The problem lies in only displaying the schools sub navigation menu on the schools pages. How do we achieve this without creating a schools template that calls a schools header and a custom menu in our <code>functions.php</code> file?

The approach we hit on was to:
<ul>
	<li>create a widget area that sits above the main page content area in all our template files</li>
	<li>create custom menus using the WordPress admin area (<em>Appearance </em>&gt; <em>Menus</em>)</li>
	<li>only add the appropriate custom menu when certain conditions are met (for example, add the schools menu to the widget area only when we're on any pages within the schools microsite)</li>
</ul>
Creating a subnav widget area and calling it in our page templates is easy. The difficult part is adding logic that controls when the widget displays anything, and what it displays.

Originally, I considered writing a function that went through all our logical options and displayed a menu accordingly. However, this soon resulted in a <em>lot</em> of <code>if… thens</code>.

And the solution to that problem? This is WordPress, so it's to install a plugin.
<h2>Content Aware Sidebars</h2>
There are several WordPress plugins that allow you to add some logic to your widget areas. The best I've found is <a href="https://en-gb.wordpress.org/plugins/content-aware-sidebars/">Content Aware Sidebars</a> (or CAS).

CAS allows you to create sidebars that only appear on certain types of posts or pages. The amount of control it offers is impressive; for example, you can tell it to display a widget area on archive pages from a certain category as well as single pages within that category, or both even:

<figure class="figure">

<img src="/images/cas.jpg" alt="Screenshot of the WordPress admin area" width="800" height="688" />

<figcaption class="figcaption"><p>A CAS sidebar that appears on just 2 pages</p></figcaption>

</figure>

But the real beauty of CAS is that you tell it to merge or replace an existing widget area with your new widget.

So to create subnavigation menus that sit above the right microsites, we tell our new sidebar to replace the subnav widget area we've created in our <code>functions.php</code> file. Because this widget area is only created on the pages we stipulate, it will appear on the right pages and nowhere else.
<h2>Putting it all together</h2>
Although this process doesn't require a huge amount of technical knowledge, you do need to understand how WordPress displays widget areas, and how you can use CAS in conjunction with WordPress's out of the box functionality.

So, here's a step by step guide (hullo there if you've simply scrolled down here):
<ol>
	<li>Create a new widget area in your <code>functions.php</code> file. Call it something like <em>Sub navigation</em>, or abstract it even more and call it <em>Pre-content widget</em>.</li>
	<li>Call this widget area using <code>dynamic_sidebar</code> in all your templates. You should test whether the sidebar has any content first with <code>is_active_sidebar</code>.</li>
	<li>Install the Content Aware Sidebars plugin.</li>
	<li>Create a new CAS sidebar for the submenu you need on your site. Set its display rules and tell it to replace the widget area you created in <code>functions.php</code> (you can create as many of these CAS sidebars as you like, but you'll only need 1 custom menu in <code>functions.php</code>)</li>
	<li>Create a new custom menu in <em>Appearance</em> &gt; <em>Menus</em></li>
	<li>Go to <em>Appearance</em> &gt; <em>Widgets</em></li>
	<li>Add the custom menu you created in step 5 to the CAS sidebar you created in step 4</li>
	<li>Remember to leave the widget area you created in step 1 empty</li>
</ol>
<h2>Why do this?</h2>
A few reasons:
<ul>
	<li>Cut down on template writing and maintenance</li>
	<li>Ensure consistent layouts and appearance</li>
	<li>Move custom menus from templates to the WordPress admin area (which means editors rather than coders control sub menus)</li>
</ul>
It's an elegant way to control and fine tune website navigation. The only problem I've come across is with building complex display rules in CAS; I can't, for example, combine caetgory and page rules. But that could be me doing something wrong.

What do you think? Are there easier ways to add sub navigation menus to your website?
