---

layout: post
typo_id: 3860
title: Spaces 'Application Assignments' and Applescript
---

&lt;div style="float:left;margin:10px;"&gt;
&lt;script type="text/javascript"&gt;&lt;!--
google_ad_client = "pub-5165033129816339";
//250x250, created 11/22/07
google_ad_slot = "4463239324";
google_ad_width = 250;
google_ad_height = 250;
//--&gt;&lt;/script&gt;
&lt;script type="text/javascript" src="http://pagead2.googlesyndication.com/pagead/show_ads.js"&gt;
&lt;/script&gt;
&lt;/div&gt;

Let's face it -
[Spaces](http://www.apple.com/macosx/features/spaces.html),
<a href="http://www.amazon.com/gp/redirect.html?ie=UTF8&location=http%3A%2F%2Fwww.amazon.com%2FApple-Mac-Version-10-5-Leopard%2Fdp%2FB000FK88JK&tag=jnewlandcom0a-20&linkCode=ur2&camp=1789&creative=9325">Leopard's</a><img src="http://www.assoc-amazon.com/e/ir?t=jnewlandcom0a-20&amp;l=ur2&amp;o=1" width="1" height="1" border="0" alt="" style="border:none !important; margin:0px !important;" />
new [virtual desktop](http://en.wikipedia.org/wiki/Virtual_desktop)
implementation, isn't as polished as many of us would like it to be. It
has more than it's share of
[undocumented](http://twitter.com/jacksonfox/statuses/418554032)
[features](http://twitter.com/dydimustk/statuses/368923792),
[bugs](http://twitter.com/jnewland/statuses/393275612), and
[annoyances](http://www.pascal.com/diary/?p=183).

One of my personal gripes with spaces it's lack of keyboard shortcuts
for managing what Spaces calls "Application Assignments". I'd like to be
able to quickly assign an application to all Spaces with a quick
keypress. Also - I often find myself hunting through my Spaces for 3 or
4 Safari windows I've left in various places - it'd be nice if there was
an easy way to collect all windows of a given app on the current Space.

So, this morning, I sat down and started hacking at some Applescripts to
do just that. After wading through the [bizarre
way](http://bbs.applescript.net/viewtopic.php?id=23070&action=new) that
Application Assignments are stored, I ended up with 4 Applescripts:

-   **Assign to All Spaces** - assigns the frontmost window to
    all spaces.
-   **Assign to Space X** - opens an input dialog asking you which space
    to assign the frontmost window to.
-   **Collect on Current Space** - brings all windows from the frontmost
    appliation to the current space.
-   **Remove Assignments** - remove any appliaction assignments the
    frontmost window may have.

Here's a zip file of all 4:

> [Spaces Applescripts](http://files.jnewland.com/Spaces.zip)

These scripts are designed to be invoked via a keyboard shortcut via
[Quicksilver](http://blacktree.com/?quicksilver) or
[FastScripts](http://www.red-sweater.com/fastscripts/).

If you have any corrects / additions / suggestions as to how to improve
these scripts, drop 'em in the comments!
