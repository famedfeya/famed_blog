---
layout: post
title: CCNP Wireless CUWSS 642-732 Summary Notes 4 - 802.11n hardware
date: 2014-11-04 16:34
author: tnotez
comments: true
categories: [642-732, CCNP Wireless, CCNP Wireless Summary Notes, CUWSS]
---
When performing a survey for 802.11n, signal strength is not an accurate predictor of 802.11n performance. Multipath can actually enhance performance with 802.11n clients.

<h2>802.11n hardware</h2>

Disadvantage of non-802.11 hardware is that they may have 2 antennas per band but they both are connected to the same radio circuit so when they receive a signal, the receiver tests each antenna and uses the one that provides the best signal (diversity) thus limits impact of multipath on the received signal. The same antenna that was used to receive the signal is the same one that is used to send

<!--more-->

802.11n devices use several antennas each connected to an individual circuit and this improves the range for the data and improves throughput. This is done by using the MIMO features described below:

<ul>
    <li>Multi-ratio combining (MRC) - receiver accepts signal on each antenna and circuit, puts the signals in phase and combines them to increase received signal power level</li>
    <li>Transmit beamforming (TXBF) - the emitter sends the same signal in sync  from different circuits and antennas so that when they get to the receiver, they arrive in phase. TxBF works only if the receiver sends 802.11n feedback frames to the sender so that the sender can dynamically synchronize the frames well but Cisco was able to overcome this setback with its ClientLink technology (v1) which enables the AP to use the MRC calcs when receiving frames from a non-802.11n source with a weak signal (&lt;65dBm) and determine when the client signal was received on each of the antennas then uses the difference to send the signals back to the client so that the client receives the signal in phase</li>
    <li>Spatial Multiplexing - The 802.11n emitter sends different signals (streams ) from each antenna, the receiver then collects and combines them together hence more data is sent = higher throughput. Number of supported streams is not always equal to number of antennas and circuits. AP capacity is usually written for example 2*3 (2 circuits for sending by 3 antennas for receiving). 2*3:2, the 2 means that it supports only 2 streams.</li>
</ul>

Other features in 802.11n that improve throughput are:

<ul>
    <li>Channel bonding - using 40 MHz channels</li>
    <li>Block acknowledgements - sending burst frames separate by 2 microseconds reduced interframe space (RIFS) and then sending an acknowledgement.</li>
    <li>AP can be configured to allow for shorter guard intervals SGI of up to 400 ns. OFDM symbols usually have useful bits followed by empty bits (guard interval). The interframe space for OFDM is usually 800ns. Shortening the length might mean increases in loss risk so this should be verified first.</li>
</ul>

The specified data rate is only the speed of the link. Real throughput is usually 50% of that speed. non 802.11n devices usually force 802.11n devices to use protection mechanisms so as to avoid collision and this degrades their performances. Protection mechanisms include:

<ul>
    <li>Ready to Send/Clear to Send (RTS/CTS)</li>
    <li>CTS-to-self-protection</li>
    <li>adding a non-802.11n header to a 802.11n frame</li>
</ul>

Whereas non-802.11 devices were placed to avoid multipath, 802.11n can make use of multipath so having both of them in the same environment is not recommended.

Migration strategies to 802.11n are:

<ul>
    <li>New Survey - Completely new deployment of 802.11n devices independent of non 802.11n APs. Very expensive but best option</li>
    <li>one-to-one replacement - replace non802.11n APs with new 802.11n APs. Easy but less efficient as some APs will not take advantage of multipath</li>
    <li>Phase the migration - replace some APs one to one and move other APs. compromise between cost and performance.</li>
</ul>

<h2><strong>References:</strong></h2>

<ol>
<li><p>CCNP Wireless  (642-732 CUWSS) Quick Reference Guide by Jerome Henry</p></li>
<li><p>IPexpert’s CCNP CUWSS Wireless Voice on Demand (642-731)</p></li>
<li><p>CUWSS v1.0 Student Guide</p></li>
</ol>
