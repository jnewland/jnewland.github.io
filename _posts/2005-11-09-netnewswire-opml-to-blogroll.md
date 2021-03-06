---

layout: post
typo_id: 111
title: NetNewsWire OPML to Blogroll
---
Use [NetNewsWire](http://ranchero.com/netnewswire/) and want a list of
your subscriptions on your blog? Here's how I did it:

-   Export your subscriptions from
    [NetNewsWire](http://ranchero.com/netnewswire/) to a flat OPML file.
    This file contains links to all of your blogs in XML format, we're
    going to use a XSL Transformation to turn this into an unordered
    list (`<ul>`).
-   Download
    [TestXSLT](http://www.entropy.ch/software/macosx/#testxslt), a free
    XSLT Transformation tool for OS X. Open the disk image and drag the
    TestXSTL icon to your Applications folder. Open it, and get ready
    for action.
-   Open `MySubscriptions.opml` from
    [NetNewsWire](http://ranchero.com/netnewswire/) in TextEditor, and
    select all of the text using `apple+a`, then copy it using
    `apple+v`.
-   Paste this into the *XML* tab of
    [TestXSLT](http://www.entropy.ch/software/macosx/#testxslt).
-   Paste the following XSL stylesheet into the *XSL* tab of
    [TestXSLT](http://www.entropy.ch/software/macosx/#testxslt).

{% highlight xml %}
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">
<xsl:output method="html" indent="yes" standalone="no" omit-xml-declaration="yes" />
<xsl:template match="/">

<ul>
<xsl:apply-templates select="//outline" >
<xsl:sort select="@title" data-type="text" />
</xsl:apply-templates>

</ul>
</xsl:template>
<xsl:template match="outline">
<xsl:choose>
<xsl:when test="@type='rss'">

<li>
<a href="{@htmlUrl}"><xsl:value-of select="@title" /></a>

</li>
</xsl:when>
</xsl:choose>
</xsl:template>
</xsl:stylesheet>
{% endhighlight %}

-   Switch to the results tab and press *Process*. Voila! Your blogroll
    as an unordered list (`<ul>`), ready to copy and paste into your
    blog templates. Hope this works for you!

