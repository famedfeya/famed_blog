---
layout: post
title: CCNP Wireless CUWSS 642-732 Summary Notes 2 - Site Survey Preassessment
date: 2014-11-02 09:39
author: tnotez
comments: true
categories: [CCNP Wireless, CUWSS, CWNA]
---
Site Survey Pre-assessment can be done using a questionnaire that should have most of this information to enable proper design planning for the WLAN.

<ul>
    <li>Customer contact information</li>
    <li>Total number of sites</li>
    <li>Is it a New vs existing deployment</li>
    <li>Band requirements</li>
    <li>Existing devices</li>
    <li>Data coverage type (VoWLAN, Data, Location services)</li>
    <li>Facility information - get maps for those areas
<ul>
    <li>Ceiling heights</li>
    <li>Racking or shelving?</li>
    <li>clearance above storage level</li>
    <li>any hazardous areas</li>
    <li>special safety requirements like safety glasses.</li>
</ul>
</li>
    <li>Number of buildings per site</li>
    <li>Hours of operation</li>
    <li>Current network infrastructure.
<ul>
    <li>Confirm the port capacity.</li>
    <li>Network topology</li>
    <li>Media type</li>
    <li>Confirm power for APs
<ul>
    <li>Most are capable of being powered with 802.11af</li>
    <li>Cisco AP 1250 requires 18.5 power for full power</li>
</ul>
</li>
</ul>
</li>
    <li> RF Coverage information:
<ul>
    <li>RF coverage inside and outside</li>
    <li>Complete or selective RF coverage</li>
    <li>Encryption to be utilized</li>
    <li>Utilizing rate shifting</li>
</ul>
</li>
</ul>

<!--more-->

<h2>Types of Applications</h2>

<ul>
    <li>TCP-Based Applications
<ul>
    <li>resistant to iinterference and Layer 2 losses</li>
    <li>Need to maintain the connection</li>
</ul>
</li>
    <li>UDP-Based Applications
<ul>
    <li>For Voice: Because the voice packet may have to travel very far, it should not take longer than 30 ms to reach the AP from the  moment it is placed into the phone buffer.</li>
    <li>For Video: There could be low bandwidth consumption for still images (or images with little changes) and sudden bandwidth-consumption bursts when the  entire screen needs to be refreshed for a new image.</li>
</ul>
</li>
    <li>Application Network Behavior
<ul>
    <li>Some applications are heavily network oriented</li>
    <li>Cloud applications also increase network consumption.</li>
</ul>
</li>
</ul>

<h2>Guest Access</h2>

<ul>
    <li>Entire area coverage is needed mainly for web browsing at speeds of 128 kbps per user usually.</li>
    <li>Can be free, fee based or corporate-sponsored access.</li>
</ul>

<h2>References:</h2>

<ol>
    <li>CCNP Wireless  (642-732 CUWSS) Quick Reference Guide by Jerome Henry</li>
    <li>IPexpert's CCNP CUWSS Wireless Voice on Demand (642-731)</li>
    <li>CUWSS Student Guide v1.0</li>
</ol>
