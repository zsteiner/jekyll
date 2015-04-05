---
title: Fixing iTunes Sync Slowness
author: Zach
layout: post
permalink: /2014/09/fixing-itunes-sync-slowness/
categories:
  - Uncategorized
---
I'm still in the 00s, I admit it. I have a large iTunes library that I manually sync with my music player (iPhone). This is because I have a very large music library. All lossless. So large in fact, I'm way over the limit for iTunes Match by roughly 10k songs. I still selectively sync what music will fit on my iPhone. This will be the case until the probably iPhone 16, which will hopefully have TBs of storage. Or Pied Piper actually gets their compression algorithm to market.

Syncing and using iTunes was pretty annoying for two reasons.

  1. Syncing with my iPhone would take forever. It would take 5 minutes or more on Step 2 just checking which apps to sync. That's without even syncing music.
  2. The few times when iTunes crashes, the restart brings on the dreaded:[<img class="aligncenter size-full wp-image-319" src="http://zachsteiner.com/wp-content/uploads/2014/09/itunes_library_checking.jpg" alt="itunes_library_checking" width="908" height="426" />  
    ][1]which could last for 10 minutes or more.

The culprit for my setup? A bloated (500+ MB) iTunes Genius database. I deleted it and turned off Genius (don't really use it). Now syncs are blazingly fast and iTunes rebounds from crashes with aplomb.

If you have these same symptoms, try the following:

  1. Quit iTunes
  2. Drag "iTunes Library Genius.itdb" to your desktop. It's found in [username]/Music/iTunes.
  3. Restart iTunes. iTunes will recreate the file in a much smaller version (mine is now 41 KB)
  4. Et voilà! You can delete the file on your desktop now.

One note: if you use and like Genius, you will have to let iTunes rebuild information. Eventually your file will get big.

Now if iTunes + iPhone would sync via WiFi, like it's supposed to. A boy can dream...

 [1]: http://zachsteiner.com/wp-content/uploads/2014/09/itunes_library_checking.jpg