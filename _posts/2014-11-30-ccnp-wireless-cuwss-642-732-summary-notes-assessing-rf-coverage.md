---
layout: post
title: CCNP Wireless CUWSS 642-732 Summary Notes 22 - Assessing RF Coverage
date: 2014-11-30 23:16
author: tnotez
comments: true
categories: [642-732, CCNP Wireless, CCNP Wireless Summary Notes, CUWSS]
---
<h2>RF Audit</h2>

The main objective is to verify RF Coverage. The goal is to validate or audit the current WLAN deployment in order to enhance its security and performance. Unlike pre installation site surveys, post installation surveys focus more on the entire site environment.

Verify RF footprint of all installed APs. Use Ekahau Survey or AirMagnet Survey PRO.

First use Passive Survey mode

<ul>
    <li>Conduct a separate passive survey per media type, IEEE 802.11a, 802.11b, 802.11g, 802.11n.</li>
    <li>Verify that all APs are working with the expected level of coverage.</li>
    <li>Verify co-channel interference and separation. Check for co-channel interference by standing near an access point on one channel and watch for other access points that are on the same channel. Check to see if the signal level on other access points heard on the same channel is at least 19 dBm weaker than the access point that you are next to.</li>
    <li>Check to ensure you have adequate signal levels as surveyed.</li>
    <li>Compare the coverage and data rates of the postinstallation survey with the survey that was performed prior to the installation.</li>
    <li>Make any required adjustments that were not accounted for in the preinstallation portion in order to make the network meet user and throughput requirements.</li>
    <li>Survey by SSID to ensure that roaming is taking place.</li>
    <li>For 802.11n active surveys, use Iperf to verify up and down link speeds.</li>
</ul>

<!--more-->

Next Run an active Survey

<ul>
    <li>Verify data rate and packet loss</li>
    <li>Confirm roaming works seemlessly. Use the path that a normal roaming user would use.</li>
</ul>

Fine tune Controller settings

<ul>
    <li>Enable or disable channels (12, 13)</li>
    <li>Some clients may not support UNII3 or UNII2 extended</li>
    <li>Configure the Controller Dynamic Channel Assignment (DCA) channel list to match the channels supported by all the wireless clients present</li>
</ul>

Finetune Radio Resource Management (RRM)

For RFID tags, send a predefined message at regular intervals on preset channels.

<ul>
    <li>These channels should match APs channels</li>
    <li>RFID message is forwarded to MSE. MSE feeds WCS with location information and displays position of tag on map.</li>
    <li>Map refresh interval on WCS should be &gt; than RFID message interval.</li>
</ul>

<h2>RRM Tuning</h2>

Many 5-GHz client adapters do not support all 23 channels available. Adjust designated channel assignment (DCA) for RRM on all controllers to support only channels supported by wireless clients. Many do not support the UNII-2 extended channels 100 through 140 (5.470 to 5.725 GHz).<a href="https://littlenerdsdiary.files.wordpress.com/2014/11/2014_11_30_22_56_46_nldcbpwlc01.png"><img class="alignnone size-full wp-image-3596" src="https://littlenerdsdiary.files.wordpress.com/2014/11/2014_11_30_22_56_46_nldcbpwlc01.png" alt="2014_11_30_22_56_46_NLDCBPWLC01" width="628" height="463" /></a>

<h2>Mesh Audit</h2>

Locate possible dead spots

Need to Test:

<ul>
    <li>Throughput - this is the download speed (userexpirience rate). Increasing the number of hops decreases backhaul throughput.
<ul>
    <li>Capacity is the system bandwidth</li>
</ul>
</li>
</ul>

<blockquote>Throughput = BR * (0.5 * 1/n) * PSR
<p style="padding-left:30px;">whereby</p>
<p style="padding-left:60px;">BR - Raw backhaul rate</p>
<p style="padding-left:60px;">n - Backhaul hop count</p>
<p style="padding-left:60px;">PSR - packet success rate (value between 0.0 - 1.0_</p>
</blockquote>

<ul>
    <li>SNR and RSSI</li>
    <li>Latency of the cell and backhaul from the farthest MAP
<ul>
    <li>Each hop adds 3ms latency usually. Latency per hop should be &lt;10ms</li>
    <li>Latency increases when number of APs at any hop level increases.</li>
</ul>
</li>
    <li>Jitter (&lt;3ms per hop)</li>
</ul>

Common issues faced:

<ul>
    <li>Hidden nodes - APs communicating at backhaul but do not hear each other. This leads to collisions when sending traffic to same destination.</li>
    <li>Exposed nodes - two stations send frames at the same time to different destinations. These frames collide because the stations are on the same channel. This can be prevented by setting RRM to auto.</li>
    <li>SomeAPs in the mesh network get disconnected.TheAPs thenneedtotryandfindanalternatepathusingtheAWPP algorithm
<ul>
    <li>AWPP discards the link as not viable if SNR is too low (&lt;10 dB) or if path has many hops to RAP.</li>
    <li>This is fixed by adding more APs or designing failover paths</li>
</ul>
</li>
</ul>

<h2>Application Testing</h2>

<ul>
    <li>Test each Application from Layer 1 to 7.</li>
    <li>Do load testing,</li>
    <li>Test roaming.</li>
    <li>Enable all apps to make sure that they can function together.</li>
    <li>Verify RFID tags are located properly and with expected accuracy.</li>
    <li>Test rate shifting area (where AP signal drops and clients use lower rates). Brutal rate shifting increases frame delay because of many retries.</li>
    <li>Modify AP power as needed</li>
    <li>Test redundancy.</li>
    <li>Verify packet error rate.Check for multipath and collision issues.</li>
</ul>

<h3>VoWLAN Verification Testing.</h3>

Check that the wireless IP phones can do the following:

<ul>
    <li>Associate with all access points in the WLAN</li>
    <li>Authenticate with all access points in the WLAN</li>
    <li>Register with Cisco Unified Communications Manager</li>
    <li>Make stationary phone calls with good quality audio</li>
    <li>Make roaming phone calls with good quality audio and no disconnections</li>
    <li>Place multiple calls, especially in areas designated for high-density
use</li>
</ul>

Measure wireless parameters from the client using tools like:

<ul>
    <li>Xirrus WiFi inspector can be used on Windows.</li>
    <li>INSSIDer (free for Windows and Linux)</li>
    <li>Test for throughput using IPerf</li>
    <li>Vendor tools
<ul>
    <li>AirMagnet WiFI Analyzer Pro</li>
    <li>IxChariot ( can simulate more than 150 apps)</li>
    <li>WaveDeploy/Wave Magnet (displays rate in heat map form)</li>
</ul>
</li>
</ul>

<h2><strong>References:</strong></h2>

<ol>
    <li>CCNP Wireless  (642-732 CUWSS) Quick Reference Guide by Jerome Henry</li>
    <li>IPexpert’s CCNP CUWSS Wireless Voice on Demand (642-731)</li>
    <li>CUWSS Student Guide v1.0</li>
</ol>
