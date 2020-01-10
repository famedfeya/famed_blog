---
layout: post
title: CCNP Wireless CUWSS 642-732 Summary Notes 9 - Mesh Networks
date: 2014-11-13 09:13
author: tnotez
comments: true
categories: [642-732, CCNP Wireless, CCNP Wireless Summary Notes, CUWSS]
---
<h2>Indoor Mesh Networks</h2>

This is an excellent way of providing coverage in hard to wire environments or where cables cannot be used or if cable length is too long (&gt; 100 m).

Indoor mesh access points:

<ul>
    <li>Cisco Aironet 1130 Series - controller based</li>
    <li>Cisco Aironet 1240 Series - controller based</li>
</ul>

The APs deliver network access to users over the 2.4-GHz frequency and use the 5-GHz band to backhaul traffic.

The APs use AWPP (Adaptive Wireless Path Protocol) which is Cisco Proprietary for communication. Because it dynamically learns the best way to route traffic wirelessly across multiple hops back to the wired network, the AWPP ensures maximum network availability.<!--more-->

Benefits of Mesh Network include:

<ul>
    <li>Coverage to places where coverage had not been possible due to wiring restrictions.</li>
    <li>With AWPP , mesh-enabled access points automatically
find the nearest path to the core network, and the controller supports zero-configuration deployment, automatically detecting and configuring the access points when connected.</li>
    <li>Centrally managed hence simplifies WLAN design, administration and operation.</li>
    <li>AWPP provides self-healing from and resiliency to interference and network outages, reducing management costs.</li>
    <li>Universal port capability enables enterprises to leverage the unused Ethernet port to configure access points within the mesh network to function as wireless bridges.The mesh access point attaches to the device or switch via the unused Ethernet port and backhauls the traffic to the rest of the wireless network.</li>
    <li>Unified indoor and outdoor mesh enables clients to roam seamlessly between indoor and outdoor networks, making it possible for users to continue using services and applications while they move from the indoor areas of a facility to its outdoor areas.</li>
</ul>

APs should be set to bridge mode

There will be MAPs and RAPs. RAPs are the wired networks backhaul connection whereas the MAPs have no wired connection.

Adding MAPs decreases the total available bandwidth

<h2><strong>Outdoor</strong> Coverage</h2>

<ul>
    <li>Often Mesh networks but can be inter building bridges.
<ul>
    <li>For Mesh, only subsets of the nodes need to be connected to the wired network (root access points). The RAPs then offer radio links to other APs Mesh Access Points (MAPS). MAPS then also offer radio connectivity for other APs etc etc. For Cisco, MAP is default. An AP can be MAP or RAP. Traffic takes the best path from any MAP to the RAP, based on best path  determined with a Cisco proprietary protocol, Adaptive Wireless Path Protocol (AWPP).</li>
    <li>Mesh networks are a tradeoff between performance and investment.
<ul>
    <li>Single radio APs are cheap but client communication prevents AP from sending or receiving on the backhaul and the AP will also need to use the same radio channel to communicate. This type of deployment offers limited
performance and cannot scale easily. QoS cannot be deployed. Should only be used where only 2.4 and one channel is possible.</li>
    <li>Dual radio APs use one radio (5) for backhaul communication and the other (2.4) for client access. Backhaul is usually a bottleneck for RAP. To increase backhaul performance you can use 802.11an radios, use 40-MHz channels on the backhaul, add more RAPs, or use RAPs and MAPS that have 2 802.11a
radio modules. Also limit your network to 10 to 20 MAPs max per RAP, and 2 to 3 hops max to the RAP, although the controller code limit is 32 MAPs
per RAP and 8 hops.</li>
    <li>RAP Starts:
<ul>
    <li>From Config, it  Discovers and associates to the controller</li>
    <li>broadcasts every 500 ms on its backhaul radio a Neighbor Update message saying it  can be used to reach controller</li>
    <li>bridge group name (BGN) on the RAP groups APs.</li>
</ul>
</li>
    <li>MAP starts:
<ul>
    <li>Tries to use Cable to reach controller first,</li>
    <li>If fails, it enables the backhaul radio and scans 5GHz radio several times looking for APs with same BGN if configured.</li>
    <li>MAP selects AP with best path to wired network and joins controller.ThisisdeterminedusingAdaptiveWirelessPathProtocolAWPP which is a combination of Signal to Noise Ratio and hop count.SNR and hop count is the ease value. The higher the ease value (higherSNRandlowerhopcount ) the prefered the route.
<ul>
    <li>AWPP is a Cisco proprietary protocol. IEEE has 802.11s Hybrid Wireless Mesh Protocol (HWMP) for mesh network inter AP routing. The HWMP has up to 6 MAC addresses in the mesh frame: Original source, Point of entry in the mesh cloud,  Sending mesh AP, Receiving mesh AP, Point of exit from the mesh cloud, Final destination</li>
</ul>
</li>
    <li>MAP sends network updates for other APs to use it as relay. Neighbour updates have the ease values included. When an AP chooses a path, it adds a 20 percent bonus to the chosen path ease value to increase path  stability.</li>
    <li>MAPs require a good SNR (&gt;20 dB) to use another AP as a next hop to the wired network then choses the one with the highest ease.  AP considers SNR &gt; 10dB. If only links &lt; 20 dB SNR are found, the AP tries to use the link that has the highest SNR above 12 dB and higher ease but flags those links with a Poor SNR tag.</li>
</ul>
</li>
</ul>
</li>
    <li>Mesh APs usually have higher power levels and antennas than indoor APs. Signal travels and reflects farther therefore delay is higher and can be affected by humidity. As the frequency increases, propagation issues due to rain attenuation also increase and is worse for 5 GHz band. MAPs should be 13 to 30 feet (4 to 10 m) above street. If link length is &gt; 11 km, earth curvature should be taken in account. 40% of the frensel zone should be free from obstacles.</li>
</ul>
</li>
</ul>

<strong>References:</strong>

<ol>
    <li>CCNP Wireless  (642-732 CUWSS) Quick Reference Guide by Jerome Henry</li>
    <li>IPexpert's CCNP CUWSS Wireless Voice on Demand (642-731)</li>
    <li>CUWSS Student Guide v1.0</li>
</ol>
