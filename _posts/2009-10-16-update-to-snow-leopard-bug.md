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

{% highlight javascript %}
**The script**

tell application "System Events"
    tell application "System Preferences"
        activate
        reveal pane id "com.apple.preference.network"
    end tell

    tell window "Network" of process "System Preferences"
        tell pop up button 1
            click
            pick menu item "Wired Reset" of menu 1
        end tell
        delay 1
        click button "Apply"
    end tell
    
    tell window "Network" of process "System Preferences"
        tell pop up button 1
            click
            pick menu item "Automatic" of menu 1
        end tell
        delay 1
        click button "Apply"
    end tell
    quit application "System Preferences"
end tell
{% endhighlight %}