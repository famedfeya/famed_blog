---
layout: post
title: CCNP Wireless CUWSS 642-732 Summary Notes 8 - Bridging Models
date: 2014-11-11 09:10
author: tnotez
comments: true
categories: [642-732, CCNP Wireless, CCNP Wireless Summary Notes, CUWSS, CWNA, Wireless Site Survey, WLAN Site Survey]
---
<strong> Point to Point Wireless Links</strong>

Cisco Aironet 1500 Series Access Point can use its backhaul radio to bridge two wired segments in point to point mode. Its a mesh network with only one MAP and no WLAN clients. If Ethernet bridging is enabled, then wireless client access can be provided but is not recommended if the MAP is too high on the rooftop.<!--more-->

<h2><strong> Point to Multi-Point Wireless Links</strong></h2>

A RAP acts as a root bridge and connects to multiple MAPs as non root bridges with their wired LANs. Feature is disabled by default. Bridging needs to be enabled to support Ethernet bridging.

<a href="https://littlenerdsdiary.files.wordpress.com/2014/11/2014_11_11_17_58_47_nldcbpwlc01.png"><img class="alignnone size-full wp-image-3442" src="https://littlenerdsdiary.files.wordpress.com/2014/11/2014_11_11_17_58_47_nldcbpwlc01.png" alt="2014_11_11_17_58_47_NLDCBPWLC01" width="628" height="192" /></a>

Might or might not support additional wireless clients depending on height of building.

<h2>Site Surveys for Bridges</h2>

<ul>
    <li>The factors that determine how far the mesh link goes:
<ul>
    <li>Fresnel zone</li>
    <li>free space loss</li>
    <li>antenna gain</li>
    <li>cable loss</li>
    <li>data rate</li>
    <li>link distance</li>
    <li>transmitter power</li>
    <li>receiver sensitivity,</li>
</ul>
</li>
</ul>

<ul>
    <li>Most important considerations are:
<ul>
    <li>Line of Sight
<ul>
    <li>This is the free path between the two points</li>
    <li>If distance is greater than 800 m (0.5 miles), you need to consider the earths curvature. Also for such links directional high-gain antenna is recommended and must be aligned so that their main radiated
power lobes are directed at each other. The 17dBi sector antenna can achieve distances of up to 9 miles (14 km) away.</li>
</ul>
</li>
    <li>Determine elevation of structures available for link - the poles, buildings and towers that the equipment will be installed on.</li>
    <li>Determine distance between the sites using GPS.</li>
    <li>Determine Fresnel clearance (F)
<ul>
    <li>This is the elliptical zone surounding the visual Path</li>
    <li>First Fresnel zone should be at least 60 percent clear of obstructions.</li>
    <li>F (feet) = 72.6 * Sq. root of (D/4f)
<ul>
    <li>F - fresnel zone radius in feet</li>
    <li>D - path total in miles</li>
    <li>f - frequency (GHz)</li>
</ul>
</li>
    <li>For 60% clearance: 0.60 F (feet) = 43.3 * Sq. root of (D/4f)</li>
    <li>If more of 40 % of the Fresnel zone is obstructed, you will need to raise antennas or remove the obstacles or build a new structure, cut the trees or find an alternative location.</li>
    <li>Cisco 1500 Mesh Access Point Range Calculation Utility is recommended to calculate the fresnel zone, the distance between bridges, cable loss, required antenna height, and the recommended fade margin</li>
    <li>APs to be used - 1300, 1400 and 1500 that can be used for both the P2P and P2MultiPoint Links. Cisco 1500s can be used for Mesh Networks also</li>
</ul>
</li>
    <li>Determine power and antenna requirements</li>
</ul>
</li>
    <li>Information that you need for the survey
<ul>
    <li>Length of the wireless Link</li>
    <li>Is there a clear Line of Sight (LOS)</li>
    <li>Minimum acceptable data rate for communication</li>
    <li>Antenna type for the link</li>
    <li>Is it P2P or P2Multipoint connectivity</li>
    <li>Can AP area support AP weight</li>
    <li>Do you have access to both ends of the location</li>
    <li>Do you have proper permits required</li>
    <li>Need for a partner (Bridges should always be done with a partner)</li>
</ul>
</li>
</ul>

For outdoor environments, lightening protection should be used.

<ul>
    <li>Install lightening arrestor which dissipates energy induced into the cable from a nearby lightning strike but does not protect against a direct strike.</li>
    <li>Transtector ALPU-TSU allow low-voltage power, such as Power over Ethernet (PoE), to pass, while blocking high-voltage power from static electricity discharges.</li>
    <li>Ground AP  between AP and network before installing power.</li>
    <li>Fiber to copper transeiver should be installed to limit damage to the network connected to AP in the event of a direct lightning strike. Because the conductor in fiber optic cabling is glass, the current cannot travel over the fiber, and the energy is dissipated as heat, melting the fiber optic cabling. To use this method, one meter of fiber optic cabling is needed, and two copper-fiber transceivers which require power. The two transeivers should not be plugged into the same power outlet to avoid creating a path for the current to bypass the fiber optic cabling.<a href="https://littlenerdsdiary.files.wordpress.com/2014/11/2014-11-11-19_03_00-cuwss-v1-0-student-guide_vol1-pdf-adobe-reader.png"><img class="alignnone size-full wp-image-3443" src="https://littlenerdsdiary.files.wordpress.com/2014/11/2014-11-11-19_03_00-cuwss-v1-0-student-guide_vol1-pdf-adobe-reader.png" alt="2014-11-11 19_03_00-CUWSS v1.0 Student Guide_Vol1.pdf - Adobe Reader" width="537" height="272" /></a></li>
</ul>

<strong>References:</strong>

<ol>
    <li>CCNP Wireless  (642-732 CUWSS) Quick Reference Guide by Jerome Henry</li>
    <li>IPexpert's CCNP CUWSS Wireless Voice on Demand (642-731)</li>
    <li>CUWSS Student Guide v1.0</li>
</ol>
