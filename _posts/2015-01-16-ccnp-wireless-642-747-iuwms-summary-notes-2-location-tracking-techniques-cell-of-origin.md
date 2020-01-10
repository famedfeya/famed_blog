---
layout: post
title: CCNP Wireless 642-747 IUWMS Summary Notes 2 : Location Tracking Techniques - Cell of Origin
date: 2015-01-16 10:00
author: tnotez
comments: true
categories: [642-747, CCNP Wireless, Cell of Origin, IUWMS, measurement technique, pattern recognition, Real Time Location Systems, Tracking systems]
---
Tracking systems are classified by the measurement technique that they use. Real Time Location Systems (RTLS) are grouped into the following:

<ul>
    <li>Cell of Origin ( Nearest Cell)</li>
    <li>Lateration ( depending on Distance)</li>
    <li>Angulation (depending on the angle)</li>
    <li>Location patterning ( pattern recognition)</li>
</ul>

<!--more-->

<h2>Cell of Origin</h2>

The tracking position is based on proximity and is determined by using the associated access point.

<h3>Advantages:</h3>

<ol>
    <li>Very easy to implement. No complicated algorithms used.</li>
    <li>Very fast technique as no complicated algorithms are used.</li>
</ol>

<h3>Disadvantages:</h3>

<ol>
    <li>Lacks granularity, hence may be difficult to locate devices in multi-storied environments, as exact position cannot be calculated.</li>
</ol>

<h3>How to improve this technique:</h3>

<ol>
    <li>Increase granularity by using highest RSSI cell instead of cell of origin.</li>
</ol>

<h3>Where and when used:</h3>

<ol>
    <li>Used when precise location tracking is not needed.</li>
</ol>

<h1>References:</h1>

<ol>
    <li>Wi-Fi Location-Based Services 4.1 Design Guide by Cisco Press.</li>
</ol>
