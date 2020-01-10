---
layout: post
title: CCNP Wireless CUWSS 642-732 Summary Notes 17 -  Ekahau Site Survey
date: 2014-11-28 23:39
author: tnotez
comments: true
categories: [642-732, CCNP Wireless, CCNP Wireless Summary Notes, CUWSS]
---
<h2><strong>Ekahau Site Survey Tool </strong></h2>

This tool is used to determine each AP coverage area. It records the signal level, retries, lost packets etc. Ekahau Site Survey comes in a standard version and a Pro version.

<ul>
    <li>Standard</li>
    <li>Pro
<ul>
    <li>adds the predictive survey which allows us to add obstacles to the map so as to predict how many APs will be needed</li>
    <li>adds the simulated AP features that enables us to add a virtual AP so as to check how coverage would be</li>
    <li>This results in a hybrid between onsite survey and planning mode</li>
</ul>
</li>
</ul>

<!--more-->

<h3>Modes:</h3>

<ul>
    <li>Active
<ul>
    <li>You associate to one AP or to one SSID across different APs</li>
    <li>associate to the SSID you want to survey using your windows wireless utility, and Ekahau implements that connection for the survey.</li>
    <li>You do not need to place the APs on the map as Ekahau can autodetect their position during the survey</li>
</ul>
</li>
    <li>Passive
<ul>
    <li>all 802.11 traffic is captured, giving you a good understanding of the existing 802.11 infrastructure.</li>
    <li>Shows all the detected APs, their channel, RSSI, noise values and resulting SNR, APs names and MAC addresses and associated security set identifiers (SSID).</li>
    <li>You cannot associate to any SSID so cannot test the signal quality</li>
    <li>You do not need to place the APs on the map as Ekahau can autodetect their position during the survey</li>
    <li></li>
</ul>
</li>
    <li>Hybrid (both modes)
<ul>
    <li>This mode is useful after the survey if you need to modify minor parameters of the survey without the possibility to return to the facility.</li>
</ul>
</li>
</ul>

<h3>How it works:</h3>

<ul>
    <li>Launch the program</li>
    <li>Create new project</li>
    <li>Import maps of the floors to be surveyed</li>
    <li>Scale the map using the Scale Map tool.
<ul>
    <li>Click the first point, then the second and add the distance.</li>
</ul>
</li>
    <li>Start by creating the building</li>
    <li>Add the floor. Floor map, height, material and background map. The material is used to calculate the absorption between floors.</li>
    <li>The Floor Alignment tool can be used to identify each reference point on floor map.</li>
    <li>Site &gt; Edit Requirements - to enter details about the coverage needed if you know which devices will be in the floor</li>
    <li>Site &gt; Edit Capacity Requirements - input the number and type of devices expected for each cell plus its network behaviour</li>
    <li>click the wireless card and set it to passive mode and choose channels to survey (card is in active by default).</li>
    <li>Walk around the facility and click on the map to show your location.</li>
    <li>Each time you click the Survey button, Ekahau starts recording RF values, and stops when you click
the Survey button a second time.</li>
    <li>Once done, File &gt; Report - generates report and save as RTF or PDF format or export as XML file</li>
</ul>

<h3>Recommendations:</h3>

<ul>
    <li>Always try to use a long object when scaling because an error is of less impact when its on the entire floor</li>
    <li>If you have two cards, set one to Active and the other to Passive, performing both surveys at the same time</li>
    <li>If you have only one card, the first survey would be passive, to provide you a map of the existing coverage. Then pick APs and do the active survey</li>
    <li>place the first AP in a corner of the floor and by moving toward the floor center determine the cell edge then put the AP at your current position knowing that it will cover the corner. Walk along the edge both clockwise and anticlockwise.</li>
</ul>

<h2><strong>References:</strong></h2>

<ol>
<li>CCNP Wireless  (642-732 CUWSS) Quick Reference Guide by Jerome Henry</li>
<li>IPexpert’s CCNP CUWSS Wireless Voice on Demand (642-731)</li>
</ol>

&nbsp;
