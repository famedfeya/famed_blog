---
layout: post
title: CWNA Summary Notes - Coverage Analysis Methods
date: 2014-10-23 11:16
author: tnotez
comments: true
categories: [CCNP Wireless, CUWSS, CWNA]
---
<h2>Manual Site Survey</h2>

Passive manual survey - The radio card collects RF measurements but the client adapter is not associated to the access point during the survey, and all information is received from radio signals that exist at layer 1.

Active manual survey - the radio card is associated to the access point and has layer 2 connectively, allowing for low-level frame transmissions. If layer 3 connectivity is also established, ping traffic is sent in 802.11 data frame transmissions. RF measurements, packet loss and re-transmission percentage recorded.

Moth types of survey are recommended.<!--more-->

<h3>Measurement tools</h3>

<ul>
    <li>NetStumbler</li>
    <li>Microsoft Wireless Zero Configuration (WZC) service</li>
    <li>AirMagnet Survey</li>
</ul>

<h2>Assisted Site Survey</h2>

This involves using a wireless management system application to scan the access point radio cards and collect the RF information, which is then used for visualization of coverage cells and for optimizing AP configurations such as channel and power settings.

<h2>Predictive Site Survey</h2>

Uses applications that provide RF simulations and modeling design capabilities. The software creates forecast models using the predictive algorithms and the attenuation information. The modeling forecast can include the following:

<ul>
    <li>Channel reuse patterns</li>
    <li>Coverage cell boundaries</li>
    <li>Access point placement</li>
    <li>Access point power settings</li>
    <li>Number of access points</li>
    <li>Data rates</li>
</ul>

Predictive coverage analysis software can be a valuable tool, but a manual site survey is still necessary to confirm the coverage simulations.

<h3>Measurement tools</h3>

<ul>
    <li>Ekahau Site Survey</li>
</ul>

<h2>Eliminating Manual Site Survey (self-organizing WLAN technology)</h2>

Radio Frequency Spectrum Management technology where a centralized device can dynamically change the configuration of thin or fat access points based on accumulated RF information gathered from the access points’ radio cards.(RFSM eg transmit power control (TPC) and dynamic frequency selection (DFS)) may have the potential to eliminate the majority of manual site surveys.

Swarm logic - a decentralized approach whereby radio cards establish collective intelligence and decentralize any decision making. A radio card can sense the other radio cards’ RF transmissions and dynamically make adjustments. All client radios and access point radios work together in a collective RF domain. Swarm logic technology can be integrated via software into any 802.11 radio device.

<h2>References:</h2>

<ol>
    <li>CWNA Certified Wireless Network Administrator Study Guide by David D. Coleman and David A. Westcott.</li>
</ol>
