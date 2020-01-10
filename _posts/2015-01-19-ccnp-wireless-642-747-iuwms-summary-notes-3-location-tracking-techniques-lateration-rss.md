---
layout: post
title: CCNP Wireless 642-747 IUWMS Summary Notes 4 - Location Tracking Techniques – Lateration (RSS)
date: 2015-01-19 09:00
author: tnotez
comments: true
categories: [CCNP Wireless]
---
<h2>Received Signal Strength (RSS)</h2>

Localization is based on the received signal strength. The RSS is measured either by the mobile device or by the receiving sensor.

The following information is needed to calculate the distance between the sensor and the device:

<ul>
    <li>Transmitter output power</li>
    <li>Cable losses</li>
    <li>Antenna gain</li>
    <li>Path loss model(PL)</li>
</ul>

<!--more-->

A common PL model used indoors is as below: <a href="https://littlenerdsdiary.files.wordpress.com/2015/02/2015-02-06-19_50_02-document1-word.png"><img class=" size-full wp-image-3690 aligncenter" src="https://littlenerdsdiary.files.wordpress.com/2015/02/2015-02-06-19_50_02-document1-word.png" alt="2015-02-06 19_50_02-Document1 - Word" width="646" height="147" /></a>

<strong>Path loss</strong> - The difference between the Tx signal and the Rx signal measured at the face of both antennas respectively. It is the level of attenuation present in the environment due to the effects of free space propagation, reflection, diffraction and scattering. Common PL values:

<ul>
    <li>=2  - Open Space</li>
    <li>&gt;2  - When there is clutter</li>
    <li>~3.5 - typically for indoor offices</li>
    <li>~4.5 - In dense home environments</li>
</ul>

<strong>Path loss Exponent (n)</strong> - This is the rate at which the path loss increases with distance. It is a factor of:

<ul>
    <li>Frequency</li>
    <li>Environment</li>
    <li>Degree of clutter in the environment (obstruction)</li>
</ul>

<strong>Standard deviation of shadow fading (s)</strong> - Measure of noise (signal strength variability) from the sources not accounted for in the formula:

<ul>
    <li>Attenuation due to number of obstructions present</li>
    <li>Orientation difference between the Tx and Rx antennas</li>
    <li>Reflections due to multipath</li>
</ul>

To reduce the value of s, the use of diversity antennas is recommended. Indoors, s= ~ 3 to 7 dB.

Formula for calculating Received Signal Strength: <a href="https://littlenerdsdiary.files.wordpress.com/2015/02/2015-02-06-21_07_42-document1-word.png"><img class="alignnone size-full wp-image-3692" src="https://littlenerdsdiary.files.wordpress.com/2015/02/2015-02-06-21_07_42-document1-word.png" alt="2015-02-06 21_07_42-Document1 - Word" width="438" height="40" /></a>

Deriving the distance (d) between the Tx and Rx<a href="https://littlenerdsdiary.files.wordpress.com/2015/02/2015-02-06-22_19_53-document1-word.png"><img class=" size-full wp-image-3694 aligncenter" src="https://littlenerdsdiary.files.wordpress.com/2015/02/2015-02-06-22_19_53-document1-word.png" alt="2015-02-06 22_19_53-Document1 - Word" width="596" height="226" /></a>

Using the distance d as radius, a circular area can be drawn to show that the mobile device is somewhere on that circular plot.

When 3 receivers are used, it is considered as RSS tri-lateration, whereas, if 4 or more are used - multi-lateration.

RSS can be calculated from the network side or from the client side:

<ul>
    <li>Network side RSS are usually not dependant on the vendor type hence are better</li>
    <li>Client RSS measurements should make use of a refernce model to avoid inaccuracies</li>
</ul>

<h3>ADVANTAGES:</h3>

<ol>
    <li>Low cost - they do not need specialized hardware for both mobile and network Infrastructure locations</li>
</ol>

<h3>DISADVANTAGES:</h3>

<ol>
    <li>Propagation anomalies brought about by anisotropic conditions in the environment degrade accuracy.</li>
</ol>

<h2>References:</h2>

<ol>
    <li>Wi-Fi Location-Based Services 4.1 Design Guide by Cisco Press.</li>
</ol>
