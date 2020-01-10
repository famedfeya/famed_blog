---
layout: post
title: CCNA Wireless Summary Notes- Planning Coverage with Wireless APs
date: 2014-07-28 11:10
author: tnotez
comments: true
categories: [640-722, CCNA Wireless, CCNA Wireless Summary Notes]
---
AP Cell Size is known as the Basic Service Area. Cell size can be controlled by changing the following parameters:
<ul>
	<li>AP Transmit power (Increase signal strength of AP). Most APs are set to transmit within government regulations which limit the effective isotropic radiated  power (EIRP) to a maximum transmit power level of 20 dBm (100 mW). The client should also be able to transmit at the set power level otherwise its signals will not reach the AP and we will have the asymmetric
power problem, where the two communicating devices have differing transmit power levels that might not reach each other.</li>
	<li>Using specific data rates. the higher data rates or more complex modulation and  coding schemes (MCS) offer the greatest throughput but require the best signal conditions (closer to the AP). You can disable the lower data rates like 1-, 2-, and 5.5-Mbps hence forcing the AP to clients to use higher data rates. This effectively reduces the usable size of the AP’s cell, even though the radio  frequency (RF) footprint remains the same.</li>
</ul>
Adding APs to an ESS. Clients will remain connecetd to an AP as long as the following conditions are met:
<ul>
	<li>The client is able to receive the AP’s signal at an acceptable level.</li>
	<li>The AP is able to receive the client’s signal.</li>
	<li>One of the acceptable modulations can be successfully used between the client and the AP.</li>
</ul>
Roaming is  the process of moving an association from one AP to the next, so that the wireless connection  is maintained as the client moves. Adjacent APs should be configured to use different non-overlapping channels. Cisco recommends  15 percent to 20 percent overlap for most applications.The roaming process is driven entirely by the wireless client driver—not by the AP.  Wireless clients decide that it is time to roam based on a variety of conditions eg
<ul>
	<li>received signal strength indicator (RSSI),</li>
	<li>signal-to-noise ratio (SNR),</li>
	<li>a count of missed AP beacons,</li>
	<li>errors due to collisions or interference,</li>
</ul>
<strong>WLAN Channel Layout</strong>

To minimize channel overlap and interference, APs cells should be designed so that adjacent  APs use different channels. Cells should be made to overlap in a honeycomb fashion even when planning deployment when several floors are involved. Alternating channels to avoid overlap is commonly called channel reuse .
