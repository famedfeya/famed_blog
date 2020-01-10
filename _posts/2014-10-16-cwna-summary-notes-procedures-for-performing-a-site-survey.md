---
layout: post
title: CWNA Summary Notes - Procedures for Performing a Site Survey
date: 2014-10-16 14:50
author: tnotez
comments: true
categories: [CCNP Wireless, CUWSS, CWNA]
---
<h2>Gather background data for the site survey</h2>

<h3>Examine business requirements</h3>

<ul>
    <li>Why do they need a WLAN</li>
    <li>is mobility required</li>
    <li>What devices will be connecting</li>
    <li>What apps will be used</li>
    <li>What is the amount of bandwidth required by the user</li>
</ul>

<!--more-->

Conduct interviews with personnel

<ul>
    <li>One-on-one interviews</li>
    <li>Group interviews</li>
    <li>Facilitated sessions - a much larger group consisting of all primary and secondary stakeholders are gathered together with the goal of remaining together until all the requirements are gathered</li>
    <li>Questionnaires - should be used for gathering quick statistics to get a sense of the relative priority of issues</li>
    <li>shadowing - following the interviewee around while he performs his normal duties gives the interviewer opportunities to ask questions and receive answers as actual practices
occur.</li>
</ul>

<h3>Define physical and security requirements</h3>

Consider what type of data encryption and type of authentication that will be used. Consider the location, the wired infrastructure etc.

<h3>Gather site-specific documentation</h3>

Obtain blueprints, facility drawings, and other documents that show the building infrastructure components.

Inspect the site to see whether there are any changes that have been made to the building as the documentation obtained may be old.

<h3>Document existing network characteristics</h3>

This ensures that the new or expanded WLAN will dovetail into what is already in place. The documentation should answer the following questions

<ul>
    <li>How does the current network support the organization’s mission?</li>
    <li>What applications run on the network?</li>
    <li>How many users does it support?</li>
    <li>What are the strengths and weaknesses of the current network?</li>
    <li>What is the anticipated growth in network technology?</li>
</ul>

In the document, include the following information <a href="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_16_12_10_04_1133132170_wirele-pdf_adobe_reader.png"><img class="alignnone size-full wp-image-3176" src="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_16_12_10_04_1133132170_wirele-pdf_adobe_reader.png" alt="2014_10_16_12_10_04_1133132170_Wirele.pdf_Adobe_Reader" width="525" height="208" /></a>

<h3>Analyze technical requirements</h3>

<a href="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_16_12_18_52_1133132170_wirele-pdf_adobe_reader.png"><img class="alignnone size-full wp-image-3177" src="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_16_12_18_52_1133132170_wirele-pdf_adobe_reader.png" alt="2014_10_16_12_18_52_1133132170_Wirele.pdf_Adobe_Reader" width="656" height="191" /></a> <a href="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_16_12_17_42_1133132170_wirele-pdf_adobe_reader.png"><img class="alignnone size-full wp-image-3178" src="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_16_12_17_42_1133132170_wirele-pdf_adobe_reader.png" alt="2014_10_16_12_17_42_1133132170_Wirele.pdf_Adobe_Reader" width="659" height="216" /></a>

<h2>Performing the Survey</h2>

Involves:

<h3>AP configuration and location</h3>

Decide on

<ul>
    <li>type of AP to be used.</li>
    <li>type of antenna</li>
</ul>

Configure the AP for the optimum power output and channel assignments.

Place the APs in their temporary positions.

The surveyor should start at the closest point to the AP and slowly walk away in one direction recording his findings.

Test the actual applications that will be used in the network.

<h3>Identifying interference</h3>

Based on the amount of interference, it may be necessary to relocate the AP or reorient the antenna in order to reduce interference.

<a href="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_16_13_49_17_1133132170_wirele-pdf_adobe_reader.png"><img class="alignnone size-full wp-image-3183" src="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_16_13_49_17_1133132170_wirele-pdf_adobe_reader.png" alt="2014_10_16_13_49_17_1133132170_Wirele.pdf_Adobe_Reader" width="553" height="469" /></a>

If all of the APs were set to the same channel number then it would result in reduced throughput because each station must wait a longer period of time for their turn to transmit (cochannel interference). The APs should be placed in such a way that one channel does not interfere with an adjacent channel.Each cell is separated from other cells so that no two adjacent cells have the same channel number in order to reduce interference
(adjacent channel interference)

<h3>Outdoor Surveys</h3>

Depending on the season when the survey is taken, take note of what changes may impact RF. Consider climate conditions. Prior to any installation of an outdoor antenna the necessary permits must be secured from the local municipality.

A lightning arrestor, which limits the amplitude and disturbing interference voltages by channeling them to the ground, should always be used with outdoor antennas.

<h2>Creating the Site Survey Report</h2>

Parts of a site Survey Report:

narrative section

<ul>
    <li>State customer requirements</li>
    <li>Outline how survey was conducted</li>
    <li>measurements results</li>
    <li>capacity analysis</li>
    <li>coverage verification</li>
    <li>bill of materials (BOM)</li>
    <li>hardware, software, and networking recommendations regarding the WLAN</li>
</ul>

graphical section

<ul>
    <li>maps and diagrams of the coverage area
<ul>
    <li>Data Rate map</li>
    <li>Signal to Noise Ratio</li>
</ul>
</li>
</ul>

<h2>References:</h2>

<ol>
    <li>CWNA Guide to Wireless LANs – 3rd Edition (Chapter 8) by Mark Ciampa, Ph.D.</li>
</ol>
