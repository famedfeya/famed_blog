---
layout: post
title: CWNA Summary Notes - Specialized Site Survey Tools
date: 2014-10-15 11:55
author: tnotez
comments: true
categories: [CCNP Wireless, CUWSS, CWNA]
---
These tools include:

<ul>
    <li>dedicated site survey applications</li>
    <li>spectrum analyzers</li>
    <li>protocol analyzers</li>
    <li>documentation tools</li>
    <li>Voice over WiFi (VoWiFi) Tools and Surveys</li>
</ul>

<!--more-->

<h2>Dedicated Applications</h2>

eg. Site Survey Analyzer

These applications can send packets and then analyze both transmitting and receiving data. Settings included in  dedicated applications include:

<ul>
    <li>Destination MAC Address of the AP that will be tested</li>
    <li>Continuous Link Test that starts the active mode test</li>
    <li>Number of Packets to be sent during the test</li>
    <li>Packet Size</li>
    <li>Data Retries - number of retransmissions incase no ACK</li>
    <li>Data Rate</li>
    <li>Delay Between Packets</li>
    <li>Packet Tx Type - unicast or multicast. Multicast does not perform packet retries.</li>
    <li>Percent Success Threshold - baseline for satisfactory performance.</li>
</ul>

<h2>Spectrum Analyzer</h2>

eg. USB spectrum analyzer

It scans the RF spectrum (2.4 GHz or 5 GHz for WLANs) and can locate potential sources of interference. They are passive receivers.

<h2>Protocol Analyzer (Sniffer)</h2>

eg. Sniffer Network Analyzer

This is is hardware or software that captures packets to decode and analyze its contents. They can be used for network troubleshooting and for network traffic characterization.

<h2>Documentation Tools</h2>

The purpose of these tools is to create documentation of the site survey results so they will be available for future reference. The documentation should include:

<ul>
    <li>Purpose of the report</li>
    <li>Survey methods</li>
    <li>RF coverage details (frequency and channel plan)</li>
    <li>Throughput findings</li>
    <li>Sources of interference</li>
    <li>Problem zones</li>
    <li>Marked-up facility drawings with AP placement</li>
    <li>Access point configuration</li>
</ul>

It may be advisable to create a database to store the site survey information and generate reports instead of using a word processor making it much easier to consolidate and then search for and retrieve information.

<h2>Voice over WiFi (VoWiFi) Tools and Surveys</h2>

This type of transmission depends heavily upon each frame arriving in sequence, whereas data transmissions are not as sensitive to time. The  primary tools used when VoWIFI will be incorporated, even if it is mixed with data, should be built-in tools in the VoWiFi handset itself.

Major considerations for Voice over WiFi are:

<ul>
    <li>Packet loss. Should be &lt; 1% of the total packet sent.</li>
    <li>Delay. This may cause an echo. Should be &lt; 50ms</li>
    <li>Jitter. Should be &lt;5ms</li>
</ul>

For indoor implementations the radio signal strength at the cell coverage boundary does not drop below –70 decibel milliwatts (dBm). This means that APs should be positioned so as to overlap their boundaries by approximately 6–10 dB.

<a href="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_15_11_49_42_1133132170_wirele-pdf_adobe_reader.png"><img class="alignnone size-full wp-image-3164" src="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_15_11_49_42_1133132170_wirele-pdf_adobe_reader.png" alt="2014_10_15_11_49_42_1133132170_Wirele.pdf_Adobe_Reader" width="471" height="300" /></a>

Many VoWiFi handsets do not support 802.11n and do not have multiple antennas because of space consolidation but some VoWiFi handsets support load balancing of moving a new call to an alternate channel that is less congested.

It is recommended that the network be designed to support a maximum of 10 simultaneous active calls per AP at any given time.

<h2>References:</h2>

<ol>
    <li>CWNA Guide to Wireless LANs – 3rd Edition (Chapter 8) by Mark Ciampa, Ph.D.</li>
</ol>
