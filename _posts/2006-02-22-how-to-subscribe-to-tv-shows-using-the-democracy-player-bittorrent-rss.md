---

layout: post
typo_id: 160
title: How to Subscribe to TV Shows Using The Democracy Player, Bittorrent, and RSS
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

[The Democracy Player](http://www.getdemocracy.com/) is an amazing open
source Internet TV application that allows you to subscribe to video RSS
feeds from anywhere on the web. The default feeds will keep you supplied
with endless viral and music videos from
[del.icio.us](http://del.icio.us/popular/system:media:video),
[Videobomb](http://videobomb.com/), and
[Telemusicvison](http://telemusicvision.com/), but with a little
hackery, [The Democracy Player](http://www.getdemocracy.com/) will make
you wonder why you're still paying your cable bill.

For quite some time, I've been using [TVRss](http://tvrss.net) to
download episodes of *The Daily Show* that I've missed.
[TVRss](http://tvrss.net) scours a couple Bittorrent sites for TV shows,
and provides RSS feeds of any [search](http://tvrss.net/search/) result.
For example, here's the [RSS feed for recent episodes of *The Daily
Show*](http://tvrss.net/search/?source=all&name=the.daily.show&mode=rss).
I currently subscribe to this feed in
[NetNewsWire](http://ranchero.com/netnewswire/) and download the new
shows as they appear.

These RSS feeds don't work with
[The Democracy Player](http://www.getdemocracy.com/) just yet: the feeds
simply *link* to the bittorrent file, but don't include the critical
[*enclosure*](http://en.wikipedia.org/wiki/RSS_enclosure) element. But
with a little help from [Feedburner](http://www.feedburner.com) 's
[SmartCast](http://forums.feedburner.com/viewtopic.php?t=20) service,
feeds from [TVRss](http://tvrss.net) can be plugged into [The Democracy
Player](http://www.getdemocracy.com/), effectively creating a Internet
PVR.

Now that I've sufficiently bored you with the technical details, here's
the simple step-by-step:

### How to Subscribe to TV Shows Using The Democracy Player & Bittorrent & RSS

1.  Download [The Democracy Player](http://www.getdemocracy.com/)
2.  [Search](http://tvrss.net/search/) for a show of your choice at
    [TVRss](http://tvrss.net)
3.  Right click on the RSS/XML icon link and select *Copy Link URL*
4.  Go to [Feedburner](http://www.feedburner.com), and paste the URL
    into the text field on the home page, check the "I am a Podcaster!"
    box, and click next.
    1.  If you don't already have a
        [Feedburner](http://www.feedburner.com) account, you'll be
        prompted to create one

5.  Click "Next" to activate the feed
6.  Copy the URL of the feed provided by
    [Feedburner](http://www.feedburner.com) (it should start with
    *http://feeds.feedburner.com/*)
7.  Open [The Democracy Player](http://www.getdemocracy.com/), click
    "Add Channel", and paste the URL of the feed into the field that
    appears
8.  Sleep. In the morning, you should have an episode of *The Daily
    Show* to watch!
9.  New episodes will automatically be downloaded as soon as they're
    available on Bittorrent - I've found this to usually be a day after
    the show airs
10. Enjoy!

In my mind, this is the future of video distribution. The technologies
of Bittorrent and RSS perfectly compliment each other: Bittorrent
downloads are much faster when concurrently downloaded by a large swarm.
Notifying software programs of new Bittorrent files via RSS creates a
swarm very quickly, resulting in faster downloads for everyone. [The
Democracy Player](http://www.getdemocracy.com/) combines all of these
technical elements with a pleasant UI, and great video management tools.
The result is nothing short of spectacular.

Now if you'll excuse me, I'm off to watch *The Daily Show*...
