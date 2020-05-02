---

title: Coding one off and recurrent events in Jekyll
category: web
article: true
excerpt: How do you make events appear and disappear at the right time on a static website, while linking them to specific locations? This article contains a detailed explanation.
img: events-ss.jpg
alt: Screenshot of events listing on the Suffolk Libraries website
---

Suffolk Libraries puts on thousands of events and activities over a year, ranging from regular song and rhyme sessions for babies to one off Raspberry Jams, gigs and author talks. (Didn't know that? Libraries don't just lend books, you know&hellip;)

We recently moved the website from WordPress to Jekyll, a static site generator. As events and event lists are inherently dynamic they pose several problems for any static site. How do you:

- get your site to understand when now is?
- keep event lists up to date without building the site manually?
- make recurring events?
- link events to locations?

A library website is the perfect place to figure out these problems. Here's how we went about it.

## How soon is now?

Without knowing when now is you can't determine whether an event is in the future or the past. Without that, you can't keep an event list up to date.

Jekyll uses the Liquid templating language, which has a `now` filter. To Liquid, `now` is how much time has passed since Jan 1 1970; feed this through a seconds filter and you have the current time since a fixed point in time expressed as a number:

<pre><code>

&lbrace;&percnt; capture now-unix-seconds &percnt;&rbrace;&lbrace;&lbrace; 'now' | date: '&percnt;s' &rbrace;&rbrace;&lbrace;&percnt; endcapture &percnt;&rbrace;

</code></pre>

Good. If we can convert an event start date in the same way we can determine whether it's taking place in the past or future.

To do that in Jekyll we can add properly formatted event start and end times to event YAML. For example, if we set `event-start-date: 2016-08-18` it'll start on 18 Aug 2016. Feed the date through the `%s` date filter again to get a time in seconds since Jan 1 1970:

<pre><code>
&lbrace;&percnt; capture event-time-seconds &percnt;&rbrace;&lbrace;&lbrace;event.event-start-date | date: '&percnt;s' &rbrace;&rbrace;&lbrace;&percnt; endcapture &percnt;&rbrace;
</code></pre>

### Converting seconds to days

Finally, we need to convert our seconds to days so we can make an easy comparison between now and the event's start date. Handily, the Liquid `divided_by` filter rounds down by default, so dividing our times by the number of seconds in a day gives us a number of days:

<pre><code>
&lbrace;&percnt; capture event-time &percnt;&rbrace;&lbrace;&lbrace; event-time-seconds | divided_by: 86400&rbrace;&rbrace;&lbrace;&percnt; endcapture &percnt;&rbrace;
</code></pre>

and

<pre><code>
&lbrace;&percnt; capture event-time &percnt;&rbrace;&lbrace;&lbrace; event-time-seconds | divided_by: 86400&rbrace;&rbrace;&lbrace;&percnt; endcapture &percnt;&rbrace;
</code></pre>

With these days, we can use a simple conditional statement to build current and future event lists:

<pre><code>
&lbrace;&percnt; if now-unix <= event-time &percnt;&rbrace; ... &lbrace;&percnt; endif &percnt;&rbrace; // if now is equal to or less than the event start time
</code></pre>

## Updating event lists automatically

Unlike WordPress based sites, static sites don't change unless you rebuild them. Therefore, now remains the same until a new build.

You could rely on someone rebuilding the site every day, but this is obviously far from ideal (what happens at weekends, for example).

You'll need to turn to your hosting for a solution to this problem. We use Netlify to set up a post hook URL and Zapier to send a post request to that URL at 1am every morning. When the URL receives the request Netlify runs `jekyll build`, thereby recalculating now and running the event list code again.

## Recurring events

We handle the bread and butter, week in, week out events differently. They're actually a lot more simple: we just use a `recurrents` collection where each event has plain text YAML that's outputted on library pages. The YAML includes `recurrent-day`, `recurrent-times` and `recurrent-category`.

## Attaching events to locations

The final piece of the jigsaw. To link one off and recurring events to locations we need to add a key to events that matches a key in library YAML.

Each library has a `branch-unique-id` such as `beccles-library`. If we add some YAML that uses this text to an event we can start matching events to libraries:

`location: beccles-library`

Here's how we use the code on a library page (in our `library.html` layout file):

<pre><code>
&lbrace;&percnt; assign current = page.branch-unique-id &rbrace;&percnt;

&lbrace;&percnt; assign events = site.events | sort: 'event-start-date'&rbrace;&percnt;

&lbrace;&percnt; for event in events &rbrace;&percnt;

    &lbrace;&percnt; if event.location == current &rbrace;&percnt;

    // some stuff, could probably use where filter

    &lbrace;&percnt; endif &rbrace;&percnt;

&lbrace;&percnt; endfor &rbrace;&percnt;
</code></pre>

And that's it: we have  one off and recurrent events linked to specific locations on the Suffolk Libraries website, and they'll disappear from events listings once their start date passes. This may seem quite a lot of work, but Jekyll's flexibility makes it really easy to attach any data to events and create all sorts of lists (based on category, for example).

[See our repo](https://github.com/suffolklibraries/sljekyll) for all the code.
