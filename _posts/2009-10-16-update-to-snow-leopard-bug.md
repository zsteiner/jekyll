---
title: Update to Snow Leopard Bug
author: Zach
layout: post
permalink: /2009/10/update-to-snow-leopard-bug/
categories:
  - Computers
---
So it seems that there is an easier way to switch the network settings.

Create a new network location (I called mine "Wired Reset"). Switch location to "Wired Reset." Hit Apply. Switch back to "Automatic." Good news is that this can be accomplished via AppleScript. I know there are more elegant ways to script system preferences, but I tried another and it didn't reliably work.

**The script**

`tell application "System Events"`

&nbsp;

`</p>
<p style="padding-left: 30px;">tell application "System Preferences"</p>
<p style="padding-left: 60px;">activate</p>
<p style="padding-left: 60px;">reveal pane id "com.apple.preference.network"</p>
<p style="padding-left: 30px;">end tell</p>
<p style="padding-left: 30px;">&nbsp;</p>
<p style="padding-left: 30px;">tell window "Network" of process "System Preferences"</p>
<p style="padding-left: 60px;">tell pop up button 1</p>
<p style="padding-left: 60px;">click</p>
<p style="padding-left: 60px;">pick menu item "Wired Reset" of menu 1</p>
<p style="padding-left: 60px;">end tell</p>
<p style="padding-left: 60px;">delay 1</p>
<p style="padding-left: 60px;">click button "Apply"</p>
<p style="padding-left: 30px;">end tell</p>
<p style="padding-left: 30px;">tell window "Network" of process "System Preferences"</p>
<p style="padding-left: 60px;">tell pop up button 1</p>
<p style="padding-left: 60px;">click</p>
<p style="padding-left: 60px;">pick menu item "Automatic" of menu 1</p>
<p style="padding-left: 30px;">end tell</p>
<p style="padding-left: 30px;">delay 1</p>
<p style="padding-left: 30px;">click button "Apply"</p>
<p style="padding-left: 30px;">end tell</p>
<p style="padding-left: 30px;">quit application "System Preferences"</p>
<p>`

&nbsp;

`end tell<br />
`