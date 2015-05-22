---
title: Goodbye, WordPress
author: Zach
layout: post
permalink: /2015/05/goodbye-wordpress/
categories:
  - Computers
---
I've had a WordPress blog since 2008. It originally lived on a very unreliable Ubuntu server that doubled as a media server and lived under my TV. I loved the stereo received shaped case, but hated the upkeep. I quickly moved my WordPress to a hosting site. I tried a number of different themes (ranging from stock to gutted third party themes) over the years, but was always frustrated at the mess that is WordPress theming. I don't really need all of the extra stuff that WordPress offers like commenting, tagging, or elaborate sidebars. WordPress's speed always irked me, as I'm sure it did my occasional visitor.

What I really wanted was a way to create one off HTML pages with custom styles (like my [Projects][1] page), but still have the maintainability of templating. Having heard a bit about [Jekyll][2], I decided to give it a go. It seems to fit my manner of working quite a bit better than WordPress; balancing maintainability with control. It was easy to take over Jekyll's barebones default styling with custom Sass files, as opposed to creating a scratch WordPress theme or hazarding heavy edits to an existing one. I could use SVG where I wanted. I could use custom fonts as I wanted. I can write HTML where it makes sense and Markdown where it's easier. Incremental (or the eventual wholesale) redesigns become much easier. Basically, I get the benefits of a hand coded site without the downsides.

I was able to import my WordPress posts with minimal fuss into Jekyll in about 5 minutes. The URL scheme even matches, so deep links aren't broken. This allowed me to develop to my existing site, not just a lone "Hello Word" post.

I did find a few things challenging, but have been able to figure it out. First was trying to integrate [Autoprefixer][3], an invaluable Post CSS plugin. I found Octopress's port of [Autoprefixer][3], which does the trick. I'm also perplexed by Coda's inability to play nice with Jekyll. Every build seemingly creates a new version of the entire site, so a change to a Sass partial will tell Coda's FTP that every HTML file and image has changed. This is mildly annoying and makes publishing quite a bit more cumbersome. This is likely an artifact of how Coda watches for changes to know what to publish. 

Overall I'm happy with the workflow and it was fun to do a full redesign that I could actually implement. I'm not sure that I would have been to make this happen with WordPress, without some serious cursing and tradeoffs. I'm looking forward to integrating some disparate areas of my site (particularly projects and music) into Jekyll as time permits.

[1]: http://projects.zachsteiner.com
[2]: http://jekyllrb.com
[3]: https://github.com/postcss/autoprefixer
[4]: https://github.com/octopress/autoprefixer
