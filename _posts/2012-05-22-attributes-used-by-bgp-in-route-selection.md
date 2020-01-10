---
layout: post
title: Cisco R&S - Attributes used by BGP in route selection
date: 2012-05-22 23:44
author: tnotez
comments: true
categories: [BGP, Cisco Hub]
---
1) Nexthop - Should be accessible, otherwise, drop.

2) Largest Weight. Not part of the routing update.

3) Largest Local Preference. Prefered path to a remote destination. Part of the routing update. Default is 100. Local to the AS.<!--more-->

4) Originated by BGP running on this computer.

5) Shortest AS-PATH.

6) Lowest origin type. IGP &lt; EGP &lt; Incomplete

7) Lowest MED attribute - Hint to neighbours on which paths to choose to an AS with multiple entry points. Default is 0. Exchanged between AS.

8) External path over Internal Path

9) Closest IGP neighbour

10) Oldest route - for ebgp

11) Lowested BGP router ID

12) Lowest neighbour IP address
