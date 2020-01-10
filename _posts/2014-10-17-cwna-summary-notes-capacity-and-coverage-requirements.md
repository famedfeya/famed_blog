---
layout: post
title: CWNA Summary Notes - Capacity and Coverage Requirements
date: 2014-10-17 12:13
author: tnotez
comments: true
categories: [CCNP Wireless, CUWSS, CWNA]
---
<h2>Capacity and Coverage Requirements</h2>

Factors that should be considered when planning for Capacity:

<ul>
    <li>Data applications.
<ul>
    <li>For 802.11b/g network, 12 to 15 data users per AP</li>
    <li>ForVoWiFi
<ul>
    <li>SpectraLink recommends max of 12 calls per 11 Mbps cell (with 1 call needing 4.5 % of AP bandwidth), 7 calls per 2 Mbps (with 1 call needing 12% of AP bandwidth). This can be predicted using the Erlang Formula. Erlang - one hour of telephone traffic in one hour of time.</li>
</ul>
</li>
</ul>
</li>
    <li>User density. A high concentration of human bodies can attenuate the RF signal due to absorbtion.Consider:
<ul>
    <li>How many users currently need wireless access</li>
    <li>How many users many need connectivity in the future</li>
    <li>Where are the users</li>
</ul>
</li>
    <li>Peak on/off use</li>
    <li>Existing transmitters
<ul>
    <li>Previously installed 802.11 network</li>
    <li>Interfering devices
<ul>
    <li>microwaves</li>
    <li>cordless headsets</li>
    <li>cordless phones</li>
    <li>wireless machinery</li>
</ul>
</li>
</ul>
</li>
    <li>Mobile vs Mobility
<ul>
    <li>When one is mobile - disconnect may be ok (moving with the laptop from one desk to another). roaming may not be a requirement.</li>
    <li>For mobility - user must be connected 100% of the time when travelling through the facility eg
<ul>
    <li>VoWiFi</li>
    <li>Warehouse scanning applications</li>
</ul>
</li>
</ul>
</li>
    <li>802.11g protection mechanism. This will always affect throughput due to backward compatibility with 802.11b HR-DSSS clients that support a max data raet e of 11 Mbps as compared to 54 Mbps for the 11g clients.</li>
</ul>

<!--more-->

Issues that may cause performance problems in a WLAN network

<ul>
    <li>Co-channel interference</li>
    <li>multipath interference</li>
</ul>

Issues that may cause roaming problems in a WLAN

<ul>
    <li>Interference</li>
    <li>Lack of adequate coverage</li>
    <li>Lack of proper cell overlap</li>
</ul>

Fctors that should be considered and noted before the site survey

<ul>
    <li>Current WLAN problems
<ul>
    <li>throughput related</li>
    <li>frequent disconnects</li>
    <li>roaming issues</li>
</ul>
</li>
    <li>Known sources of RF interference
<ul>
    <li>microwave ovens</li>
    <li>cordless phones</li>
    <li>bluetooth for keyboards or mouse</li>
</ul>
</li>
    <li>Known coverage dead zones. Too little or too much coverage may cause connectivity and roaming issues.</li>
    <li>Prior site survey data</li>
    <li>Check what equipment is currently installed.</li>
</ul>

Roaming may not be required in some areas. The Role-based access control (RBAC) capabilities of a wireless switch or controller can control and segment roaming. Another roaming considertaion is whether or not layer 3 roaming is required. It may not be optimal for delay sensitive applications like VoWiFi.

<h2>Security Expectations:</h2>

<ul>
    <li>AAA requirements</li>
    <li>Are there plans to implement Wireless Intrusion Detection System (WIDS) against rogue APs and wireless attacks</li>
    <li>Will layer 3 VPNs be used - they increase WLAN overhead.</li>
    <li>EAP authentication may affect VoWiFI and this should be considered.</li>
</ul>

References:

<ol>
    <li>CWNA Certified Wireless Network Administrator Study Guide by David D. Coleman and David A. Wesrcott.</li>
</ol>

&nbsp;
