---
layout: post
title: CCNP Wireless 642-747 IUWMS Summary Notes 3 : Location Tracking Techniques – Lateration (ToA and TDoA)
date: 2015-01-16 12:00
author: tnotez
comments: true
categories: [642-747, CCNP Wireless, CCNP Wireless Summary Notes, IUWMS]
---
<h1>Distance-Based (Lateration) Techniques</h1>

The tracking position is determined based on distance. The distance can be measured in three different ways:

<ul>
    <li>Using Time of Arrival (ToA)</li>
    <li>Using Time Difference of Arrival (TDoA)</li>
    <li>Using Received Signal Strength</li>
</ul>

In ToA and TDoA, localization is based on propagation time, whereas for RSS systems, propagation is based on signal strength.

<!--more-->

<h2> Time of Arrival (ToA)</h2>

Location is based on arrival time of the signal transmitted from the mobile device to several sensors. The distance can then be determined from the elapsed propagation tim because signals are known to travel at approximately the same speed as light (c=~300m/μs).<a href="https://littlenerdsdiary.files.wordpress.com/2015/01/untitled.png"><img class="alignnone size-full wp-image-3665" src="https://littlenerdsdiary.files.wordpress.com/2015/01/untitled.png" alt="Untitled" width="614" height="422" /></a>

Distance (D) between device and sensor:

D (m) = c (m/μs) * t (μs)

ToA from 2 sensors resolves probable position of device. ToA tri-lateration uses 3 sensors and multi-lateration uses four or more sensors.

ToA can resolve location in both 2D and 3D planes, whereby, spheres are used in 3D as opposed to circular models in 2D planes.

All receiving sensors and mobile devices must be accurately synchronized with a precise time source.

<h3>DISADVANTAGES:</h3>

<ol>
    <li>ToA completely relies on time synchronization between all devices and this could be a challenge.</li>
    <li>ToA is challenged in areas with high multipath, interference and noise.</li>
</ol>

<h3>HOW TO IMPROVE THIS TECHNIQUE:</h3>

To avoid the strict requirement for precise time synchronization:

<ol>
    <li>Time adjustments are calculated periodically and can be used to correct offsets from the reference clocks</li>
    <li>Periodic exchange of time packets can be sent between receivers.</li>
</ol>

<h3>WHERE AND WHEN USED:</h3>

<ol>
    <li>Used in Global Positioning Systems (GPS) where time synchronization is achieved by the use of atomic clocks.</li>
    <li>Large-scale outdoor positioning systems / Semi-outdoor (amphitheaters and stadiums)/ Contained outdoor environments(car rental, new car lots , port of entry)</li>
</ol>

<h3>EXAMPLE CALCULATION 1:</h3>

Signal sent by a device was received by Sensor A after 20 nanoseconds. What is the distance between the sensor and the tracked device?

<a href="https://littlenerdsdiary.files.wordpress.com/2015/01/2015-02-06-16_07_34-document1-word.png"><img class="alignnone size-full wp-image-3666" src="https://littlenerdsdiary.files.wordpress.com/2015/01/2015-02-06-16_07_34-document1-word.png" alt="2015-02-06 16_07_34-Document1 - Word" width="442" height="86" /></a>

<h3>EXAMPLE CALCULATION 2:</h3>

Signal sent by a device was received by Sensor A after 100 nanoseconds. What is the distance between the sensor and the tracked device?<a href="https://littlenerdsdiary.files.wordpress.com/2015/01/2015-02-06-16_10_16-document1-word-e1423228293836.png"><img class="alignnone wp-image-3667 size-full" src="https://littlenerdsdiary.files.wordpress.com/2015/01/2015-02-06-16_10_16-document1-word-e1423228293836.png" alt="" width="389" height="70" /></a><!--more-->

<h2>Time Difference of Arrival (TDoA)</h2>

TDoA makes use of relative time instead of absolute time. Only the receivers have to be synchronized. For this technique, a minimum of three devices are required.

Based on Hyperbolic Lateration (Maths). The TDoA between 2 sensors is calculated then the value is used to construct a hyperbols (curve). The focal points of the hyperbola are the respective locations of the sensors.

When a device sends a signal, the signal arrives at A with time Ta, and at B with time Tb

<a href="https://littlenerdsdiary.files.wordpress.com/2015/01/2015-02-06-17_56_41-document1-word.png"><img class="alignnone size-full wp-image-3668" src="https://littlenerdsdiary.files.wordpress.com/2015/01/2015-02-06-17_56_41-document1-word.png" alt="2015-02-06 17_56_41-Document1 - Word" width="332" height="87" /></a>

The hyperbola represents the locus of all the points in the x,y plane, the difference of whose distances from the two foci is equal to k*c meters. All possible locations of device X:

<a href="https://littlenerdsdiary.files.wordpress.com/2015/01/2015-02-06-18_00_15-document1-word.png"><img class="alignnone size-full wp-image-3669" src="https://littlenerdsdiary.files.wordpress.com/2015/01/2015-02-06-18_00_15-document1-word.png" alt="2015-02-06 18_00_15-Document1 - Word" width="257" height="69" /></a>

For the 3rd receiver:

<a href="https://littlenerdsdiary.files.wordpress.com/2015/01/2015-02-06-18_02_24-document1-word.png"><img class="alignnone size-full wp-image-3671" src="https://littlenerdsdiary.files.wordpress.com/2015/01/2015-02-06-18_02_24-document1-word.png" alt="2015-02-06 18_02_24-Document1 - Word" width="200" height="48" /></a>

A second hyperbola is constructed using k1 and it represents all points in the x-y plane, the difference whose distance from the second foci = k1*c (meters)

<a href="https://littlenerdsdiary.files.wordpress.com/2015/01/2015-02-06-18_05_03-document1-word.png"><img class="alignnone size-full wp-image-3672" src="https://littlenerdsdiary.files.wordpress.com/2015/01/2015-02-06-18_05_03-document1-word.png" alt="2015-02-06 18_05_03-Document1 - Word" width="192" height="39" /></a>

<a href="https://littlenerdsdiary.files.wordpress.com/2015/01/untitled1.png"><img class="alignnone size-full wp-image-3673" src="https://littlenerdsdiary.files.wordpress.com/2015/01/untitled1.png" alt="Untitled" width="628" height="290" /></a>

When 3 sensors are used - hyperbolic tri-lateration, whereas when 4 or more are used - hyperbolic multi-lateration. The more the sensors, the better the accuracy.

<h3>ADVANTAGES:</h3>

<ol>
    <li>Does not require the use of synchronized time sources for the mobile devices too.</li>
</ol>

<h3>HOW TO IMPROVE THIS TECHNIQUE:</h3>

To avoid the strict requirement for precise time synchronization:

<ol>
    <li>Time adjustments are calculated periodically and can be used to correct offsets from the reference clocks</li>
    <li>Periodic exchange of time packets can be sent between receivers.</li>
</ol>

<h3>WHERE AND WHEN USED:</h3>

<ol>
    <li>Airport ranging systems</li>
    <li>Enhanced Observed Time Difference (E-OTD) for cellular telephony. (accuracy of 60m in Rural areas and 200m in RF heavy areas)</li>
    <li>Large-scale outdoor positioning systems / Semi-outdoor (amphitheaters and stadiums)/ Contained outdoor environments(car rental, new car lots , port of entry)</li>
    <li>Best in indoor buildings that are large and relatively open with low level of obstruction and high ceilings</li>
</ol>

<h1>References:</h1>

<ol>
    <li>Wi-Fi Location-Based Services 4.1 Design Guide by Cisco Press.</li>
</ol>
