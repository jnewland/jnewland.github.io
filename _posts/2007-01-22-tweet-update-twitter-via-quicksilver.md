---

layout: post
typo_id: 3615
title: Tweet - Update Twitter via Quicksilver
---
[Tweet](http://www.sauria.com/blog/2007/01/18/growlified-tweet/), a
Twitter Quicksilver Action, is my favorite [Twitter](http://twitter.com)
updating vehicle as of late - except for one thing. It uses Keychain
Scripting to access your saved
[Twitterrific](http://iconfactory.com/software/twitterrific) username
and password - which, for some ungodly reason, takes about 30 seconds on
my Mac Book Pro.

I've made some updates to
[Tweet.scpt](http://files.jnewland.com/tweet.scpt.zip) to fix the
slowness:

-   Now uses the [Twitter Rubygem](http://twitter.rubyforge.org/) to
    talk to Twitter
-   Uses the username and password stored in `~/.twitter`, via the
    Twitter Gem
-   Uses
    <a href="http://iconfactory.com/software/twitterrific">Twitterrific</a>'s
    icon, if you have it installed.

### Requirements

-   [Growl](http://growl.info/)
-   [Rubygems](http://rubygems.org/read/chapter/3)
-   [Twitter Rubygem](http://twitter.rubyforge.org/)
    -   `sudo gem install twitter`

### Installation Directions

1.  Download [Tweet.scpt](http://files.jnewland.com/tweet.scpt.zip)
2.  Move `Tweet.scpt` to
    `~/Library/Application Support/Quicksilver/Actions`
3.  Restart Quicksilver (Cmd+Ctrl+Q)
4.  Setup a Trigger - I use Cmd+Opt+Ctrl+T
    :<br /><br />![](http://files.jnewland.com/tweet.png)

This, combined with [Twitter Monitor](http://al3x.net/entries/766), is
the way I'm using Twitter most often these days. Like it [or
not](http://meyerweb.com/eric/thoughts/2007/01/21/the-twitters/), I
think [Twitter](http://twitter.com) has a lot of
[potential](http://twitter.com/blog/2006/08/have-your-quake-and-twitter-it-too.html).
I'd love to throw some AI at the trends of public twitters - you'd see
the string "coffee" grow in popularity in the AM and wane in the PM. Add
Geocoding support - a way to set your 'Location' as well as your status
- and Twitter becomes useful in another dimension. I'm interested to see
what Twitter has in it's future.
