---
layout: post
title: CCNP Wireless CUWSS 642-732 Summary Notes 23 : Assessing WLAN Readiness
date: 2014-12-01 13:55
author: tnotez
comments: true
categories: [642-732, CCNP Wireless, CCNP Wireless Summary Notes, CUWSS]
---
<h2>WLAN Readiness</h2>

WCS can be used to assess Wireless coverage readiness for both Location Services and VoWLAN. This however does not replace an onsite post-deployment site survey. The tools used are:

<ul>
    <li>Inspect VoWLAN Readiness</li>
    <li>Inspect location Readiness</li>
</ul>

Both tools are launched from the map that you are viewing on WCS. <!--more-->

<h3>Voice over WLAN Readiness</h3>

WCS Tool used: Inspect Voice Readiness (VoWLAN Readiness).

Tool checks to see which reas are within the acceptable RSSI for Voice (default is -67dBm).

Tool is predective and relies on the information provided to WCS.

How to Launch the tool: From the map, click

<blockquote>Inspect VoWLAN Readiness</blockquote>

It checks the map for the areas that are ready for VoWLAN

<ul>
    <li>Green Area - Ready for VoWLAN</li>
    <li>Yellow Area - Almost Ready</li>
    <li>Red Area - Not ready.</li>
</ul>

Troubleshooting VoWLAN pointers:

<ul>
    <li>To prevent one-way audio problems because of the lack of proper radio coverage, set the access point power levels to match the power levels of the VoWLAN client. The access point Tx power level cannot exceed the maximum Tx power of the client.</li>
</ul>

<h3>location READINESS</h3>

The Inspect Location readiness tool is also a predictive tool. It checks tha map for areas that are ready for Location services.

How to Launch the tool: From the map, click

<blockquote>Inspect Location Readiness</blockquote>

A spot is location ready if :

<ul>
    <li>There are at least 4 APs on the floor</li>
    <li>One AP is  in each quadrant of the point to check.</li>
    <li>3 of those APs need to be less than 70 feet (21m) from the point.</li>
</ul>

The tool basically shows the following regions

<ul>
    <li>Green Area - Ready for VoWLAN</li>
    <li>Red Area - Not ready.</li>
</ul>

<h2><strong>WCS Calibration</strong></h2>

Calibration is meant to increase location accuracy because the WCS collects real RSSI values from the floor APs. From the collected RSSI  values, probable location for clients can be deduced.

The WCS and MSE use a technique known as fingerprinting to evaluate the average signal loss when moving away from an AP so as to estimate the location of an object down to a few meters (within 10 m most times). This is known as calibration.

WCS provides several floor models to choose from when calibrating:

<ul>
    <li>Outdoor Open space</li>
    <li>Office building with dry wall only</li>
    <li>Office building with cubicles and drywall</li>
</ul>

To Calibrate from WCS navigate to:

<blockquote>Maps &gt; RF Calibration Models &gt; Go

Create new Model &gt; Go

Edit model parameters

Add data points</blockquote>

For data collection, a minimum of 5 clients should participate and the clients should be CCX2 capable or later.

How does data collection work:

<ol>
    <li>User clicks on the map</li>
    <li>WCS informs WLC</li>
    <li>WLC sends CCX message, s36 to clients via APs</li>
    <li>Probe messages are sent to the client</li>
    <li>AP collects the messages</li>
    <li>AP sends to the WLC</li>
    <li>WLC sends to the WCS</li>
    <li>If location data is received, user stops and moves to next location.</li>
</ol>

Location data collection can be done in two ways

<ul>
    <li>Linear calibration
<ul>
    <li>A series of linear paths are chosen and then calculated as
you traverse the path. This approach is generally faster than the data point collection. You can also employ data point collection to augment data collection for locations missed by the linear paths.</li>
    <li>Define a start and an end point and walk between the two points at a steady pace. Click done when you reach the endpoint.</li>
    <li>WCS gathers information about the client at given points and deduces the RSSI values along the path</li>
    <li>Easiest and most convinient</li>
    <li>Minimum code of 5.0 on Controller and WCS is required</li>
</ul>
</li>
    <li>Data Point Calibration
<ul>
    <li>Calibration points are chosen and their coverage area is
calculated one location at a time.</li>
    <li>Best for smaller enclosed environments</li>
    <li>Click on your position and move the laptop by turning your body. WCS collects RSSI values from the APs around.</li>
    <li>WCS takes snapshots of the network</li>
    <li>During the snapshots, the WCS takes readings from neighbouring APs</li>
</ul>
</li>
</ul>

WCS requires 150 different location points per band to validate calibration and must be collected over at least 50 different locations. Green indicates calibrated areas.

If some bands are not used, they should be deactivated in all WLCs that participate in the calibration process.

Once calibrated models have been created, they can be reused for similar floors

Validation of data points on a map are done using Location Quality Inspector. This tool is used to verify whether all points on the floor thathas been calibrated match the current location equation.Tool can be launched from the Calibration Detail Page. It shows the Location quality rating depending on the accuracy achieved. Incase accuracy is not good, more data points can be collected.

Changes that affected the RF signal loss will require new calibrations every time they are made.

<h2><strong>References:</strong></h2>

<ol>
    <li>CCNP Wireless  (642-732 CUWSS) Quick Reference Guide by Jerome Henry</li>
    <li>IPexpert’s CCNP CUWSS Wireless Voice on Demand (642-731)</li>
</ol>
