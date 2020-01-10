---
layout: post
title: CCNP Wireless CUWSS 642-732 Summary Notes 21 - Infrastructure requirements Part 2
date: 2014-11-30 12:12
author: tnotez
comments: true
categories: [642-732, CCNP Wireless, CCNP Wireless Summary Notes, CUWSS]
---
802.11n APs with 100% duty cycle:

<ul>
    <li>the 2,4 band when oversubscribed with clients communicating at 144 Mbps may consume up to 70 - 75 Mbps on wired side.</li>
    <li>the 5 GHz band when oversubscribed and using 40 MHz channels with clients communicating at 300 Mbps may consume up to 160 - 170 Mbps on wired side.</li>
    <li>Both bands on the Ethernet Side will consume (75 + 170) = 245 Mbps per AP</li>
</ul>

<!--more-->

Planning:

<ul>
    <li>Limit number of APs per WLC to make sure that overall traffic is less than port bandwidth</li>
    <li>use a 20:1 oversubscription ( 20 APs to 1 Controller)</li>
    <li>At RF level, the distance between the APs should be such that if one goes down, RRM can increase power of surrounding APs and cover the hole.</li>
    <li>Controller redundancy should be in place so that if one controller goes down, APs can join another. Redundancy models:
<ul>
    <li>N+1:
<ul>
    <li>one controller backs up n controllers</li>
    <li>Only 1 additional controller</li>
    <li>Cheap redundancy</li>
    <li>only 1 WLC can fail at a time. the redundant controller could become oversubscribed with access points if there are multiple primary controller failures,</li>
    <li>When a controller reaches the maximum number of joined access points, it accepts no more Lightweight Access Point Protocol (LWAPP) join requests.</li>
    <li>Each access point is configured with a primary controller and all access points point to the next single redundant controller as secondary.</li>
</ul>
</li>
    <li>N+N:
<ul>
    <li>N controllers back up N controllers</li>
    <li>Each WLC loaded to half its license capacity</li>
    <li>More expensive model</li>
    <li>If network fails, all APs  move to the other WLC</li>
</ul>
</li>
    <li>N+N+1:
<ul>
    <li>N controllers back up N controllers as secondary, and
one controller backs up all N controllers as tertiary.</li>
    <li>Intermediate but more common model</li>
    <li>In this design, it is important to load-balance the access point capacity across both controllers. WLC are loaded to a variable perecntage of their licence (eg 66%).</li>
    <li>to logically group access points on controllers to minimize inter-controller roaming events.</li>
    <li>Additional backup is available in NOC</li>
    <li>When one or several WLCs fail, the APs can join the backup or other controllers in the network</li>
    <li>There should be enough access point and bandwidth capacity on each controller to handle a failover situation.</li>
    <li>the plus one controller at the NOC or data center to no longer have to be a member of the same mobility group. It can now be referenced by its IP address versus being part of the same mobility group.</li>
    <li>Most redundant but most expensive</li>
</ul>
</li>
</ul>
</li>
    <li>AP deployment Model
<ul>
    <li>Standard deployment (not advised)
<ul>
    <li>All APs connect to same controller</li>
</ul>
</li>
    <li>Salt and Paper Model
<ul>
    <li>Neighbouring APs connect to different controllers</li>
    <li>In one WLC gets disconnected, only half have to fail over</li>
    <li>Better redundancy than standard model</li>
    <li>Downside: when all controllers are available, interAP roaming leads to intercontroller roaming leading to added delays when roaming</li>
    <li>Recommended only if applicatiosn are not time sensitive</li>
    <li>Determine the roaming paths during the walkthrough visit. deploy APs along the path so that roaming in that path occurs on the same controller</li>
    <li>If WLCs do not connect to same switched network, their WLAN - VLAN mapping may be different which means that we will have local to foreign roaming that increase wired bandwidth consumption</li>
</ul>
</li>
</ul>
</li>
    <li>Controller location
<ul>
    <li>Distributed model
<ul>
    <li>WLCs in each building close to the APs.</li>
    <li>Negatively affects roaming efficiency. Intercontroller roaming even represents 20 ms delay when both controllers are in same subnet and 30 ms when in different subnets</li>
</ul>
</li>
    <li>Centralized model
<ul>
    <li>All WLCs in same location</li>
    <li>Capacity management is simpler</li>
    <li>Simpler to create high availability controller topology</li>
    <li>All packets must be sent to the controller</li>
</ul>
</li>
</ul>
</li>
</ul>

&nbsp;

<h2><strong>References:</strong></h2>

<ol>
<li><p>CCNP Wireless  (642-732 CUWSS) Quick Reference Guide by Jerome Henry</p></li>
<li><p>IPexpert’s CCNP CUWSS Wireless Voice on Demand (642-731)</p></li>
<li><p>CUWSS Student Guide 1.0</p></li>
</ol>
