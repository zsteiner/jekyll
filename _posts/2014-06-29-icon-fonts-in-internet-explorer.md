---
title: Icon Fonts in Internet Explorer
author: Zach
layout: post
permalink: /2014/06/icon-fonts-in-internet-explorer/
categories:
  - UX
---
[Icon fonts are amazing][1]. I wholeheartedly adopted them for our HTML redesign. That is, until I did a client demo that is. None of the icons loaded, strewing Unicode boxes and Unicode fallbacks. It broke layouts. I was embarrassed and confused. "But  IE6 [supports @font-face][2]", I yelled! We tested in IE8, IE9, and even IE7 for yucks! I had set all of the *.eot declarations properly! There is almost nothing written about this in [discussions of icon fonts][3]. After our QA team going through methodically switching security settings one and a time and reloading, we discovered the worst setting in Internet Explorer:

[<img class="aligncenter wp-image-264 size-large" src="/images/posts/2014/06/Screen-Shot-2014-06-25-at-6.05.13-PM-853x1024.png" alt="Screen Shot 2014-06-25 at 6.05.13 PM" width="604" height="725" />][4]

Not only does our government client have this setting enabled as a custom security setting organization wide, but it persists into current versions of Internet Explorer (at least as of IE11). It's a Windows setting. This client does not allow other browsers whatsoever. Chalk this up for another tally in the [SVG icons][5]. There goes are great idea to use icon fonts...

My first idea was to do a progressive enhancement refactor of our CSS. We also needed to detect whether the font was downloaded. Feature detection was out because all of the browsers with this setting enabled actually do support the feature, if their IT administrators would let them. We tried[ detecting the font load][6], which worked fine, but seemed awfully burdensome in that it needs to run on every page load.

What about SVG? My initial reaction to SVG was optimistic, but most of the methods that allow icon font level CSS control require the SVG to be inserted inline on the page and there is all sorts of wonkiness between browsers. Given the number of pages we need to support, I was very nervous about linking to individual SVG files and a big defs file has issues. I really wanted a CSS-based solution.

We finally settled on a variant of Lonely Planet's method of [SVG sprites][7]. SVG are inserted as a background image to :before with background: cover. The height and width of the :before control the size of the icon. There are two draw backs to this method:

  1. Icons need to be the same aspect ratio (basically square) for background:cover to work well
  2. There is no way to color the SVG via CSS as with icon fonts.

We standardized our icons in[ IcoMoon][8] at 32px x 32px. We then standardized colors (helps from a branding perspective) in the sprite. We abstracted naming, inspired by Bootstrap, with .c- prefix. Adding a color only requires adding a line like:

{% highlight html %}
<g fill="#ff7800" class="icon-alert" transform="translate(0 192)">
    <use xlink:href="#icon"</use>
</g>
{% endhighlight %}

Global find and replace makes it easy to add the same line to all SVG files we use. [<img class="aligncenter size-medium wp-image-289" src="/images/posts/2014/06/Screen-Shot-2014-06-29-at-12.40.02-PM1-44x300.png" alt="Calendar Icon" width="44" height="300" />][9] We would have loved to do one big sprite with all icons and multiple colors, but alas Firefox does not support background-position-x and background-position-y separately. Specifying 100 icons x 7 color classes was a non-starter. I would never want to specify something like ".icon-calendar-red" as one of 700+ classes. We settled on icon classes (.icon-calendar chooses the file) and a separate color class (.c-warning changes the background x position across all icons). Adding a new color only adds a single class definition, rather than 100+.  All the classes are built with a Sass partial: a map for the icon and a map + loop with clever division for the colors. This also allows a mixin to add the icon to arbitrary selectors with only:

{% highlight sass %}
@include icon(calendar, warning);
{% endhighlight %}

## What about the rest of the text?

All of this headache with IE made me very sensitive to degrading gracefully when fonts do not download. The default sans-serif doesn't degrade functionality like a icon based button does, but it did break delicate layouts. After some investigation and experimentation, I chose [Segoe UI][10] as a fallback for the text.

{% highlight css%}
font-family: Source Sans Pro, Helvetica Neue, Segoe UI, Arial, sans-serif;
{% endhighlight %}

It has a variety of weights, including light, and bares a passing resemblance to Source Sans Pro (more so than Arial, at least). Best part is that it has come installed in all Office versions since [Office 2007][11] and is installed in [Windows Vista][12] and newer. That leaves out  our Windows XP + Office 2003 users. However, they have to use Firefox or Chrome (we no longer support IE8 and lower), so it's a non-issue: Source Sans Pro should load without trouble.

However, it always bothered me that line heights were very different between Source Sans Pro and Segoe UI. I will address this in a future post.

 [1]: http://css-tricks.com/examples/IconFont/
 [2]: http://caniuse.com/#feat=fontface
 [3]: http://filamentgroup.com/lab/bulletproof_icon_fonts.html
 [4]: /images/posts/2014/06/Screen-Shot-2014-06-25-at-6.05.13-PM.png
 [5]: http://css-tricks.com/icon-fonts-vs-svg/
 [6]: https://github.com/RoelN/font-face-render-check
 [7]: http://ianfeather.co.uk/ten-reasons-we-switched-from-an-icon-font-to-svg/
 [8]: http://icomoon.io
 [9]: /images/posts/2014/06/Screen-Shot-2014-06-29-at-12.40.02-PM1.png
 [10]: http://www.microsoft.com/typography/fonts/family.aspx?FID=331
 [11]: http://www.microsoft.com/typography/fonts/product.aspx?PID=148
 [12]: http://www.microsoft.com/typography/fonts/product.aspx?PID=149