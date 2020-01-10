---
layout: post
title: CCNP Wireless CUWSS 642-732 Summary Notes 16 - Layer 2 Active Site Survey  using AirMagnet  Survey Pro
date: 2014-11-28 12:05
author: tnotez
comments: true
categories: [642-732, CCNP Wireless, CCNP Wireless Summary Notes, CUWSS]
---
<h2>AirMagnet Survey</h2>

Layer 2 site survey can be performed with AirMagnet Survey PRO to determine the access point placement and coverage. AirMagnet Survey PRO has the capability of doing pre-site surveys (before the install) and post-site surveys (after the install), also known as an audit, to ensure adequate coverage.

In the configuration menu:

<ul>
    <li>Select the SSID</li>
    <li>Set the Tx power to match that of the AP</li>
    <li>Select Channel Width</li>
</ul>

<h3>Survey Modes:</h3>

<ul>
    <li>Active Survey - (Default)  the wireless network card actively associates itself with the selected access point or SSID, sending and receiving RF packets to and from the access point or SSID. If a specific AP is not selected, then the PC will connect to the AP that has the strongest signal.</li>
    <li>Active with Iperf for greenfield survey - Airmagnet syncs with an Iperf server to test throughput on the uplink and downlink.
<ul>
    <li> Watch for the following:
<ul>
    <li>Uplink data rate</li>
    <li>Downlink data rate</li>
    <li>Signal strength</li>
    <li>Noise</li>
    <li>Signal-to-noise ratio (SNR)</li>
    <li>Percentage of packets lost</li>
    <li>Percentage of packets retried</li>
</ul>
</li>
    <li>Turn power down to at least half of what the 802.11n client supports</li>
    <li>Configure the access point and client for 40-MHz wide channels to improve throughput up to 300 Mb/s. Channel bonding must be enabled on the client and
the access point for 40-MHz high throughput.</li>
</ul>
</li>
</ul>

<blockquote>iperf -p &lt;port&gt; -s &lt;server&gt;</blockquote>

<ul>
    <li>Passive - simply listens to the RF data moving through the site, detecting and recording all RF signals and noises in the environment.</li>
</ul>

When performing a site survey with AirMagnet Survey PRO, at least one active survey of each access point should be completed (two are recommended). When all active access point site surveys are completed, a passive site survey of the floor should be completed.

<h3>Pre- Installation Site Survey Procedure:</h3>

<ul>
    <li>Conduct one passive survey of the floor or facility with the SSID set to Any.</li>
    <li>After you have completed coverage of the floor or facility, merge the survey data.
<ul>
    <li>Merge the survey data by access point</li>
    <li>Then merge the merged access point data files</li>
    <li>Finally, merge the merged access point data file with the passive survey data file.</li>
</ul>
</li>
    <li>review the data for proper placement of additional access points to fill in any null areas.
<ul>
    <li>Check the AP Noise level</li>
    <li>AP SNR level</li>
    <li>AP Speed</li>
    <li>AP Retry Rate</li>
    <li>Packet loss rate</li>
</ul>
</li>
</ul>

<h3>Active Survey Procedure</h3>

<ul>
    <li>Choose the AP to associate to</li>
    <li>Specify the location of the AP to begin</li>
    <li>walk around the area</li>
    <li>save survey data</li>
</ul>

<h3>Passive Survey Procedure</h3>

<ul>
    <li>Choose passive survey and leave SSID as any</li>
    <li>walk around the area</li>
    <li>save survey data</li>
</ul>

<h2>Generate a Report</h2>

AirMagnet can generate 10 different reports:

<ol>
    <li>Overall Coverage Report by Channel: Contains data about the overall RF signal
coverage on the selected channel</li>
    <li>Overall Coverage Report by SSID: Contains data about the overall RF signal coverage of the selected SSID</li>
    <li>Overall Coverage Report by AP: Contains data about the overall RF signal coverage of the selected access point</li>
    <li>Per Channel Report: Contains signal data of the selected channel</li>
    <li>Per SSID Report: Contains signal data of the selected SSID</li>
    <li>Per AP Report: Contains signal data of the selected access point</li>
    <li>Channel Interference Report: Contains data about the channel interference</li>
    <li>AP Interference Report: Contains data about the interference between the access points</li>
    <li>AirWISE Report: Shows data relating to the AirWISE screen</li>
    <li>Spectrum Analyzer Report: Shows reports on Spectrum Analyzer data</li>
</ol>

<h2>Survey Modes using 802.11n APs.</h2>

When surveying for 802.11n, an Iperf server is used with AirMagnet Survey PRO to measure uplink and downlink data rates.

<ul>
    <li>Greenfield mode: This means no legacy 802.11 devices. All devices are 802.11n-capable.</li>
    <li>Mixed mode: Mixed mode supports both legacy devices 802.11a/b/g as well as 802.11n. This mode uses both a high-throughput preamble and a legacy preamble.</li>
    <li>Legacy mode: Support for 802.11a/b/g clients, no 802.11n clients.</li>
</ul>

<h2><strong>References:</strong></h2>

<ol>
    <li>CCNP Wireless  (642-732 CUWSS) Quick Reference Guide by Jerome Henry</li>
    <li>IPexpert’s CCNP CUWSS Wireless Voice on Demand (642-731)</li>
    <li>CUWSS Studnet Guide v1.0</li>
</ol>
