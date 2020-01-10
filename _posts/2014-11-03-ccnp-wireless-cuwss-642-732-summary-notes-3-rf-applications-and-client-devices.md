---
layout: post
title: CCNP Wireless CUWSS 642-732 Summary Notes 3 - RF Applications and Client Devices
date: 2014-11-03 21:52
author: tnotez
comments: true
categories: [CCNP Wireless, CUWSS, CWNA]
---
<h2>RF Applications</h2>

Data rate is just the link speed and not the throughput (download speed).

<ul>
    <li>802.11b at an 11-Mbps data rate offers on average a 5.5-Mbps throughput. 11b usually degrades performance for other devices in the other bands. Avoid using this band, unless you have old devices.</li>
</ul>

<!--more-->

<ul>
    <li>802.11g at54Mbpsoffersonaveragea20-Mbps throughput butdegradesto6-Mbps throughput as soon as a 802.11b device is in the cell and protection mode is enabled.
<ul>
    <li>Pros:
<ul>
    <li>Higher throughput up to 54 Mb/s.</li>
    <li>OFDM technology reduces multipath issues</li>
</ul>
</li>
    <li>Cons
<ul>
    <li>More interference and noise might be found in the 2.4-GHz band</li>
    <li>Provides only three nonoverlapping channels</li>
    <li>Throughput degraded in the presence of 802.11b clients</li>
</ul>
</li>
</ul>
</li>
    <li>802.11a at54Mbpsoffersonaveragea22-Mbps throughput. Band has more channels (23) and fewer interference. use for time and cell condition-sensitive applications,likeVoWLAN. Has a low market penetration.
<ul>
    <li>Pros
<ul>
    <li>Higher throughput up to 54 Mb/s.</li>
    <li>OFDM technology reduces multipath issues</li>
    <li>Provides FCC 23 nonoverlapping channels</li>
    <li>Recommended for VoWLAN due to the 23 nonoverlapping channels.</li>
</ul>
</li>
    <li>Cons
<ul>
    <li>Lower market penetration</li>
</ul>
</li>
</ul>
</li>
    <li>802.11n commonlyoffersmorethan100-Mbps throughput (depending on channel width, guard interval, and cell conditions). Provides increased range and additional throughput. The benefits of 802.11n are maximized in the 5-GHz band, when you can easily use 40-MHz-wide channels. This is called channel bonding , where a secondary channel is added to a main channel. Not all channels can be bonded together. There are only 11 allowed pairs in the 5-GHz band: 36/40, 44/48, 52/56, 60/64, 100/104, 108/112, 116/120, 124/128, 132/136, 149/153, 157/161. The main channel is usually noted in the pair description, and the secondary mentioned  with +1 or –1. For example, (36,+1) represents main channel 36 and secondary channel 40. (40,-1) is the same pair, but with 40 as the main channel. The main channel is used by non-802.11n stations or 802.11n stations that only support 20-MHz-wide channels. The only downside of 802.11n in the 5-GHz spectrum is that it cannot provide support for devices operating in the 2.4-GHz band. In 2.4 band, channel bonding is very difficult  and not supported by Cisco because there are only 3 non overlapping channels.
<ul>
    <li>802.11n on5GHZ
<ul>
    <li>Pros
<ul>
    <li>Provides 23 nonoverlapping channels</li>
    <li>40-MHz wide channels with channel bonding (11 nonoverlapping channels possible with 40-MHz wide channels)</li>
</ul>
</li>
    <li>Cons
<ul>
    <li>RFID not supported; tags use 2.4-GHz radios</li>
</ul>
</li>
</ul>
</li>
    <li>802.11n on 2.4 GHz
<ul>
    <li>Pros
<ul>
    <li>RFID supported</li>
    <li>Increased speed</li>
</ul>
</li>
    <li>Cons
<ul>
    <li>Only three nonoverlapping channels</li>
    <li>More interference and noise might be found in the 2.4-GHz band.</li>
    <li>40-MHz wide channel bonding not recommended due to only three nonoverlapping channels available</li>
</ul>
</li>
</ul>
</li>
</ul>
</li>
</ul>

<h2> Wireless Applications</h2>

Supported wireless applications:

<ul>
    <li>Wireless data networks</li>
    <li>VoWLAN networks</li>
    <li>Location-based services</li>
</ul>

<h3>Data Only deployment</h3>

When designing a WLAN for data, most important is throughput.

AP should be spaced around 120 to 130 feet (37 to 40 meters) but depends on the environmental conditions.

Normal Cell Overlap is Normally 10 to 15 percent

The frame overhead should be considered when calculating the throughput.

Clients and AP power should match. Maintaining a higher setting on the client does not result in higher performance, and it can cause interference in
nearby cells.

Single floor deployment is simpler than multifloor and should be considered. Avoid installing APs ontop of each other.

2.4 extends farther than 5 GHz cells

Why limit the data rate to the highest rate at which full coverage is obtained:

<ul>
    <li>Broadcast and multicast (if enabled) are sent at the lowest associated data rate (to ensure that all clients can receive the packets)</li>
    <li>Clients that are farther away, and therefore accessing the network at a lower data rate, decrease the overall throughput by causing delays while the lower bit rates are being serviced</li>
    <li>clients at lower rates can associate with the access points that can create a coverage area greater than planned, thereby increasing the security exposure.</li>
</ul>

<h3>Voice Deployment</h3>

Access points are grouped closer together than in data-only installations.

Cell Overlap should be 20 %. Overlapping cell edges should be above –67 dBm  or 11 Mbps which creates greater homogeneity across a single cell and reduces processor load in the handheld phone, which increases link stability and reduces latency.

The AP power level should match the client power level and should be around 20 to 25 mW. Survey should be done at lower power to account for coverage holes.

Between APs, there should be at least 19dBm isolation on same channel.<a href="https://littlenerdsdiary.files.wordpress.com/2014/09/2014_09_02_18_29_25_windows_media_player.png"><img class="alignnone size-full wp-image-2820" src="https://littlenerdsdiary.files.wordpress.com/2014/09/2014_09_02_18_29_25_windows_media_player.png" alt="2014_09_02_18_29_25_Windows_Media_Player" width="660" height="453" /></a>

<h3>location Based Sevices:</h3>

Allows us to track things in real time. It relies on cell coverage and optimal placement of APs. Place access points around the perimeters of the building and in the corners of the perimeters of each floor. the access points are laid out in a staggered pattern. The staggered pattern allows for more accurate estimation of the location of a device.

It can be achieved when

<ul>
    <li>At least 4 APs are deployed</li>
    <li>One AP in the same quadrant as the subject being tracked</li>
    <li>At least one AP in each quadrant is within 21 meters (70 feet) of the subject being tracked.</li>
</ul>

When Installing the APs, mounting locations should be free of obstructions

<h2>Types of Client Devices</h2>

<ul>
    <li>Barcode Scanners -  many use 802.11b only. Barcode scanners often use Telnet protocols to connect and write into a database application.</li>
    <li>Laptops - many are fully 802.11a/b/g/n</li>
    <li>RFID tags - 1 Mbps or 2 Mbps in the 2.4-GHz band. The frame is short, so the impact on the network is usually minimal. However, RFID tags  usually do not perform clear channel assessment (CCA), and they send frames a low data rate (1 Mbps or 2 Mbps, only in the 2.4- GHz band) and high power (100 mW). RFID tags may disturb the cell operation if too many of them are present in a given area.</li>
</ul>

<h2></h2>

<h2><strong>References:</strong></h2>

<ol>
    <li>CCNP Wireless  (642-732 CUWSS) Quick Reference Guide by Jerome Henry</li>
    <li>IPexpert’s CCNP CUWSS Wireless Voice on Demand (642-731)</li>
    <li>CUWSS v1.0 Student Guide</li>
</ol>
