---
layout: post
title: CCNP Wireless 642-747 IUWMS Summary Notes 5 - Location Tracking Techniques – Angulation (AoA / DoA)
date: 2015-01-22 09:00
author: tnotez
comments: true
categories: [CCNP Wireless]
---
<h1>Angulation (Angle-Based) Techniques</h1>

Localization is based on the angle of the received signal.

<h2>Angle of Arrival (AoA) / Direction of Arrival (DoA)</h2>

AoA determines the angle of Incidence at which signals arrive at the receiving sensor. This angle is used to estimate the location of the device using the intersection of the two lines of bearing (LoB) formed by a radical line to each receiving sensor. For 2D planes, 2 receivers are needed. When at least 3 receivers are used, this is known as triangulation.<!--more--><a href="https://littlenerdsdiary.files.wordpress.com/2015/01/untitled2.png"><img class=" size-full wp-image-3708 aligncenter" src="https://littlenerdsdiary.files.wordpress.com/2015/01/untitled2.png" alt="Untitled" width="525" height="468" /></a>

Directional antennas at A and B can be adjusted to determine the point of highest RSS. This value is then used to determine the LoB.

Commercially, multiple element antenna arrays are used to sample the RSS eliminating the need for complex antennas. The arrays can be electrically switched and the angle of incidence mathematically determined using the reversed beam forming method (Involves computation of TDoA between elements and converting the value to AoA measurement). This is possible because in beam forming, the signal for each element is phased out (time delayed) to steer the gain of the antenna array.

<h3>DISADVANTAGES:</h3>

<ol>
    <li>Susceptible to multipath and interference</li>
    <li>Works well where there is a direct line of sight but affected with signal reflection from surrounding objects.</li>
</ol>

<h3>WHERE AND WHEN USED:</h3>

<ol>
    <li>VHF omnidirectional range (VOR) for aircraft navigation from 108.1 to 117.95 MHz. VOR beacons transmit multiple VHF signals with each radial at a different angle of incidence. VOR Receiver in the aircraft can determine the radial on which the aircraft is situated as it is approaching the beacon, hence can calculate the angle of incidence with respect to the beacon. With at least 2 beacons, the aircraft navigator can use on-board AoA ranging equipment to determine the aircraft’s position.</li>
    <li>Cellular industry for location tracking during the past for 911 emergency calls. Multiple tower sites calculate the AoA of the signal and perform triangulation. Switching processors can then calculate the users’ position.</li>
</ol>

<h1>References:</h1>

<ol>
    <li>Wi-Fi Location-Based Services 4.1 Design Guide by Cisco Press.</li>
</ol>
