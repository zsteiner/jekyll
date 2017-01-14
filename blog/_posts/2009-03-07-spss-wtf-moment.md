---
title: What is wrong with the Chart Builder in SPSS?
author: Zach
excerpt: Why do the chart builder and legacy dialogs output radically different scatterplots in SPSS?
layout: post
permalink: /2009/03/spss-wtf-moment/
categories:
  - Psychology
  - UX
---
I am the lab instructor for a graduate psychology statistics course. For my class's homework, they were required to figure out if a linear regression transformation was warranted for a sample data set. When assessing the skewness of a distribution, scatterplots are invaluable. Unfortunately, SPSS does not render them consistently even within itself. The data set is very skewed and requires natural log transformations for both X and Y to not violate assumptions of linear regression.

Consider first the chart editor, the option SPSS prefers by hiding the "legacy dialogs" inside a submenu. I suspect that eventually these will be altogether removed from the menus, leaving the commands available via syntax for backwards compatibility. The following syntax generated this graph:

{% highlight javascript %}
GGRAPH
/GRAPHDATASET NAME="graphdataset" VARIABLES=BODY BRAIN MISSING=LISTWISE REPORTMISSING=NO
/GRAPHSPEC SOURCE=INLINE.
BEGIN GPL

SOURCE: s=userSource(id("graphdataset"))
DATA: BODY=col(source(s), name("BODY"), unit.category())
DATA: BRAIN=col(source(s), name("BRAIN"), unit.category())
GUIDE: axis(dim(1), label("BODY"))
GUIDE: axis(dim(2), label("BRAIN"))
ELEMENT: point(position(BODY*BRAIN))

END GPL.
{% endhighlight %}

<img class="alignnone size-full wp-image-123" title="chartbuilder" src="/images/posts/2009/03/chartbuilder2.png" alt="chartbuilder" width="416" height="329" />

It looks like a linear relationship, right? Wrong! The scale is grossly off. The Body variable actually goes up over 6000. The true relationship is shown through the hidden (supposedly deprecated) legacy dialogs. Which is rendered with much more parsimonious syntax:

{% highlight javascript %}
GRAPH
/SCATTERPLOT(BIVAR)=BODY WITH BRAIN
/MISSING=LISTWISE.
{% endhighlight %}

<img class="alignnone size-full wp-image-124" title="legacy" src="/images/posts/2009/03/legacy2.png" alt="legacy" width="418" height="332" />

Just for yucks, I copied the data in [Numbers][1], a **consumer** spreadsheet app from Apple. It even does a better job of displaying the data than SPSS's chart builder.

<img class="alignnone size-full wp-image-139" title="numbers1" src="/images/posts/2009/03/numbers12.png" alt="numbers1" width="420" height="313" />

I am left with a lot of questions and few answers. Why did the chart builder cut off those points at the upper range that radically skew the data set? Why is the syntax for the chart builder 4 times as long as the old charting syntax? Why can't the chart builder do as accurate a graph as a "baby" spreadsheet app? What is going on here?

 [1]: http://www.apple.com/iwork/numbers/