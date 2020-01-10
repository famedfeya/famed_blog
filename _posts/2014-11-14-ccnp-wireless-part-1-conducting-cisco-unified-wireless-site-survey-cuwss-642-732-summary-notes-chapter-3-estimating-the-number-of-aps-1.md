---
layout: post
title: CCNP Wireless CUWSS 642-732 Summary Notes 11 - Predictive Site Survey
date: 2014-11-14 07:38
author: tnotez
comments: true
categories: [642-732, CCNP Wireless, CCNP Wireless Summary Notes, CUWSS]
---
Site survey could be done in 3 steps:

<ol>
    <li>Virtual site survey using a planning tool for a general overview
<ul>
    <li>ThisisusuallydoneusingtheWLC.
<ul>
    <li>First add the map of the area to be surveyed.</li>
</ul>
</li>
</ul>
</li>
    <li>Layer 1 sweep to discover existing RF</li>
    <li>Actual survey to establish the placing of the APs.</li>
</ol>

<!--more-->

<h2>Predictive Site Survey</h2>

They do not take into account environmental factors. Tool used is Cisco WCS planning mode. You can estimate the number of APs that will be required to provide coverage depending on the type of traffic, the location accuracy needed, number of active users and users per square footage. You need to upload the floor map in order to estimate. You will need to add a Campus &gt; Building &gt; Floor.

To get to Planning Mode: Monitor &gt; Maps &gt; Choose location &gt; Planning mode &gt;Go. Click on Add APs.

<a href="https://littlenerdsdiary.files.wordpress.com/2014/11/2014-11-18-07_04_56-cisco-pi-planning-mode-maps-view-10-44-6-200.png"><img class="alignnone size-full wp-image-3455" src="https://littlenerdsdiary.files.wordpress.com/2014/11/2014-11-18-07_04_56-cisco-pi-planning-mode-maps-view-10-44-6-200.png" alt="2014-11-18 07_04_56-Cisco PI - Planning Mode Maps View - 10.44.6.200" width="222" height="652" /></a>

<ul>
    <li>Choose AP type</li>
    <li>Choose antenna type</li>
    <li>Choose expected throughput</li>
    <li>Choose service type
<ul>
    <li>Data</li>
    <li>Voice</li>
    <li>location - if AP is only providing location services, then it is in monitor mode.</li>
</ul>
</li>
    <li>Advanced options
<ul>
    <li>Demand - specify the number of expected users per AP and the total users on the floor             <a href="https://littlenerdsdiary.files.wordpress.com/2014/11/2014-11-18-07_07_08-cisco-pi-planning-mode-maps-view-10-44-6-200.png"><img class="alignnone size-full wp-image-3456" src="https://littlenerdsdiary.files.wordpress.com/2014/11/2014-11-18-07_07_08-cisco-pi-planning-mode-maps-view-10-44-6-200.png" alt="2014-11-18 07_07_08-Cisco PI - Planning Mode Maps View - 10.44.6.200" width="218" height="76" /></a></li>
    <li>Overide coverage per AP - manually decide AP cell square footage</li>
</ul>
</li>
    <li>SafetymarginparameterforDataandVoceserviceoptions-manuallytunetheRSSIlevelattheedgedependingontheexpectedRSSI levels
<ul>
    <li>Safe - standard RSSI( for voice -75 dBm for all bands)</li>
    <li>Very safe - adds 3 dBm. Has smaller cells but higher RSSI at the edge and maximum overlap between cells ( for voice -72 dBm for all bands)</li>
    <li>Aggressive - minuses 3 dBm. Has larger cells. less intercell overlap and lower client RSSI at the edge ( for voice -78 dBm for all bands)</li>
    <li>7920_enabled ( this one is only for voice -72 dBm for 802.11a/n and -67 dBm foor b/g/n)</li>
</ul>
</li>
    <li>Calculate to determine number of APs needed. Synchronize with deployment to take into account existing APs</li>
    <li>Generate Report - this report can be used to determine the approximate cost of deployment and approximate time needed to perform the survey.</li>
</ul>

Average client throughput is related to 802.11 protocol, AP signal strength, and AP density. IFor 802.11b - 6Mb/s, 802.11a and 802.11g - 20 Mbps, 802.11n - 27Mbps.

There is a point at which a stronger signal does not increase client throughput. For 802.11b - -75dBm, above which average client throughput is 5 to 6.5 Mb/s regardless of an increase in signal strength. For 802.11a networks, this point is typically between –50 dBm and –60 dBm, above which average client throughput is 24 to 30 Mb/s regardless of an increase in signal strength. For 802.11n, this point is typically the same, but the average client throughput is 27 to 33 Mb/s.

Guidelines in the report is based on the following assumptions:

<ul>
    <li>Client Data Terminal Transmit (Tx) Power: &gt;=15 dBm</li>
    <li>Client Data Terminal Antenna Gain: &gt;=0 dBi</li>
    <li>Receiver Sensitivity: = –89 72 dBm @ 11 to 12 Mb/s with ten percent packet error rate</li>
    <li>Environmental Noise Floor: = -85 dBm</li>
    <li>Capacity: up to 15 data client terminals or up to 14 VoIP clients per AP</li>
    <li>Client Data Terminal Tx Power: &gt;=15 dBm</li>
    <li>Handover Times: 37 milliseconds or less for Layer 2 (same controller) handovers, 48 milliseconds or less for Layer 3 (intercontroller and intersubnet) handovers.</li>
    <li>Quality of Service: Assigned on a per-WLAN basis. VoIP clients with Gold quality of service (QoS) take precedence (90+ percent of bandwidth) over clients with Silver or Bronze QoS.</li>
</ul>

<h2></h2>

<h2><strong>References:</strong></h2>

<ol>
    <li>CCNP Wireless  (642-732 CUWSS) Quick Reference Guide by Jerome Henry</li>
    <li>IPexpert’s CCNP CUWSS Wireless Voice on Demand (642-731)</li>
    <li>CUWSS Student Guide v1.0</li>
</ol>

&nbsp;
