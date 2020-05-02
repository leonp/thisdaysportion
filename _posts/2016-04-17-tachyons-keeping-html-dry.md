---

title: Using Tachyons and keeping your markup dry
category: web
---

I've redone my website. A few years ago, when we styled #content and #sidebar, this would have taken several days. The "relaunch" would have been big news, the subject of blog posts and tweets. Now it takes a few hours at the weekend &#8211; we have tools like Jekyll and SASS to help us stay <abbr>DRY</abbr> and avoid monolithic, bottom up projects.

It looks pretty nice, but I wasn't really interested in appearance this time. The biggest change has been "under the hood". Over the last year or so I've used my own framework, building reusable modules a la [Foundation](https://www.google.co.uk/url?sa=t&rct=j&q=&esrc=s&source=web&cd=4&ved=0ahUKEwiIw5mi2pPMAhWEQBQKHd6fDnsQFghUMAM&url=http%3A%2F%2Ffoundation.zurb.com%2F&usg=AFQjCNF5L0AJwlNs-H8AHm2LAZc7GReA2g) and [Bootstrap](http://getbootstrap.com/). So I'd have something like a _slot_ for title/meta/excerpt patterns and a _title-list_ for a list of titles with meta data.

Recently I've been more interested in lower level frameworks like Tachyons. There are a few reasons for this:

- They weigh far less (the entire Tachyons framework is 7k)
- They're less opinionated than bigger frameworks as they operate at the CSS declaration level
- When it does have opinions, Tachyons does things like type scale well
- I write less CSS to get the look I want
- They apply a strict one class for one job rule

That's all good, but I found one problem, even on a small website like this. Take a look at the classes I use to build a page title:

{% highlight html %}
<h1 class="custom-lh-title custom-green f3 f2 mt2 mt3-ns mb2 mb3-ns">Page title</h1>
{% endhighlight %}

I don't have a problem with using one, five or fifty classes on an element, it's just that I'll use this type of page title in 3 different places. Before, I'd use the same class name (something like _entry-title_), which was easy to remember. Now, I need to remember (or copy and paste) a long string of spaces, letters and numbers.

More problematically, if I want to change the page title's appearance I need to do it in three layout files. Before, I simply changed my _entry-title_ declarations in my SASS file.

Less CSS abstraction means more HTML classes to manage.

It turns out this is _my_ problem, not Tachyons':

> Most web projects will be utilizing some sort of templating system. Just as with any code, templates should be kept DRY. If the markup for something like a modal overlay is defined multiple times across templates, it should be consolidated to a single place. <cite>[Rethinking Variables in CSS](http://jxnblk.com/writing/posts/rethinking-variables-in-css/)</cite>

So there's the answer to my problem: __Define these class chains in one place__.

In Jekyll, you use `include` to call HTML. Normally, you include whole headers, sidebars and footers across all your pages, but there's no reason why you can't include a small list of classes within your templates. For example, you can create a _page-title.html_ file containing:

{% highlight html %}
custom-lh-title custom-green f3 f2 mt2 mt3-ns mb2 mb3-ns
{% endhighlight %}

and then `include` _page-title.html_ to output your string in an element's class attribute. If you want to change any property of your page titles you just edit the _page-title.html_ file.
