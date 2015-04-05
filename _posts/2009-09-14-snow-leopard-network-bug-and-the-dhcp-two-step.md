---
title: Snow Leopard Network Bug and the DHCP Two-step
author: Zach
layout: post
permalink: /2009/09/snow-leopard-network-bug-and-the-dhcp-two-step/
categories:
  - Computers
---
**UPDATE**: [Updated and easier fix here][1].

I updated to OS X 10.6 Snow Leopard the day it came out. For the record, I take full responsibility for the pains of being an early adopter and normally am quite patient with quirks of early releases. I don't want to complain (maybe I do a little bit), but I want to share a workaround (it's not a fix) for the issue I (and 10.6 using colleagues) been experiencing.

It would be charitable to call the wireless connection in my building flaky, so I rely on my ethernet connection to be productive. After updating to 10.6, I found that though getting an IP address, I cannot access the internet. Wired at home (Airport Basestation) and  elsewhere on campus, are no issue. It is just in my office; it is just with Snow Leopard. My officemate also on 10.6 has the same issue; Tiger and Leopard machines have no such difficulty. Simple things like renewing the DHCP lease doesn't work nor does turning off IPv6 (an original suspect) .

After a morning of beating my head against the wall... the workaround, the "DHCP Two-step":

  1. In Network system preference pane, select the Ethernet connection.
  2. Copy the IP address that is displayed.
  3. Switch to "Using DHCP with manual address" under Configure IPv4. Hit Apply.
  4. Switch back to "Using DHCP." Hit Apply again.

The internet should work now. However, when restarting or waking from sleep, be prepared to go back to Step 1. That is why this is not a fix (I see that as permanent), just a workaround. One that I hope will be remedied with a point update. It has not as of 10.6.1.

I have no idea why this happens, but I'm guessing there is a change in how Snow Leopard receives IP addresses that is somehow incompatible with older router hardware used in this part of the building. If any one reading this has a more permanent workaround than the the "DHCP Two-step" I've outlined above or has better understanding of why we are experiencing this problem in the first place, please drop a line in the comments. Here's hoping that Apple fixes this soon!

 [1]: http://zachsteiner.com/2009/10/update-to-snow-leopard-bug/