---

layout: post
typo_id: 3614
title: TiVoToGo for Mac is Here - for \$99
---
The buzz this morning is that
[TiVoToGo](http://www.tivo.com/4.9.4.1-2_mac.asp)
[for](http://www.wired.com/news/culture/mac/0,72420-0.html?tw=rss.index)
[the](http://www.zatznotfunny.com/2007-01/mac-tivotogo-is-here-by-roxio/)
[Mac](http://crunchgear.com/2007/01/08/roxio-steps-in-to-make-tivotogo-for-mac-a-reality/)
has finally arrived - in the form of software bundled with [Roxio Toast
Titanium
8](http://www.roxio.com/enu/products/toast/titanium/overview.html).
Unfortunately, Toast 8 is \$99 - unlike the official [TiVo Desktop for
Windows](http://www.tivo.com/4.9.4.1-2.asp).

TiVoToGo demoed [almost exactly year
ago](http://www.zatznotfunny.com/2006-01/tivotogo-for-mac-lives/) at CES
as a [standalone
application](http://www.megazone.org/Photos/CES2006/TiVo/SMALL/TTG-Mac-1.JPG)
that [seemed to remove the
DRM](http://www.megazone.org/Photos/CES2006/TiVo/SMALL/TTG-Mac-4.JPG)
from the files it downloaded from the TiVo. It's a shame that it took
TiVo a year to release this software, even more shameful that they
encumbered it with
[DRM](http://en.wikipedia.org/wiki/Digital_Rights_Management), and
unforgivable to charge \$99 for it.

> "This is going to be the only official Mac solution," said Adam
> Fingerman, Roxio's director of product development. "There have been
> some other Mac hacks and shareware things that have popped up, but
> those technically violate the (TiVo) terms of service."

Ironically, the "Mac hack" that Mr, Fingerman is referring to, [TiVo
Decode Manager](http://thebenesch.com/tdm/) (TDM), is a spitting image
of the version of TiVo Desktop demoed at CES last year. TDM was also in
the news this morning: they launched [version
2.1](http://thebenesch.com/tdm/TiVoDecode%20Manager.zip). TDM lacks
support for direct burning of TiVo recordings to DVD, but it makes up
for that by stripping the
[DRM](http://en.wikipedia.org/wiki/Digital_Rights_Management) from the
TivoToGo files, thanks to work by those on the [Ti Vo To
Go](http://alt.org/wiki/index.php/TiVoToGo) page of the alt.org wiki.
Without the TiVo
[DRM](http://en.wikipedia.org/wiki/Digital_Rights_Management), you're
able to do whatever you please with your recordings - re-encode them in
whichever format you prefer, burn them to a DVD with software of your
choice, or transfer them to your iPod or other portable player.

One additional feature that's possible with the "Mac hacks" and not with
TiVo's official software - streaming video from the TiVo without waiting
for it to download first, using curl,
[tivodecode](http://tivodecode.sourceforge.net/), and
[mplayer](http://mplayerosx.sourceforge.net/):

<div class="typocode">
    <code>curl -k --digest -u tivo:{MAK} -c /dev/null "{tivo2go url}" |
    tivodecode -m {MAK} -- - |
    mplayer -vf pp=lb -cache 32768 -</code>

</div>
I have an Applescript application written to do this for me quickly, but
it's not ready for prime time yet. It'd be great if this functionality
made it's way into a future release of [TiVo Decode
Manager](http://thebenesch.com/tdm/). :)
