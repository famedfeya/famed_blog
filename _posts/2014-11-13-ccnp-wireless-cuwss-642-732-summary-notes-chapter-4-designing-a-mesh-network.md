---
layout: post
title: CCNP Wireless CUWSS 642-732 Summary Notes 10 : Designing a mesh network
date: 2014-11-13 12:54
author: tnotez
comments: true
categories: [642-732, CCNP Wireless, CCNP Wireless Summary Notes, CUWSS]
---
<h2>Design Considerations (especially outdoors)</h2>

Consider the data rate required at the edge of the cell

<ul>
    <li>Larger cells offer binary phase shift keying (BPSK) or quadrature phase shift keying (QPSK) data rates at the edge but require fewer hops to wired network.</li>
    <li>Smaller cells may offer quadrature amplitude modulation (QAM) (16QAM or even 64 QAM) at the edge hence increased performance BUT
<ul>
    <li>More APs are needed to cover the area</li>
    <li>More APs means more backhaul traffic leading to need for multiple backhauls to increase throughput and reduce hop count to wired closet.</li>
</ul>
</li>
    <li>Approximate AP radius per speed offered and area of the cell
<ul>
    <li>AP with QPSK at the edge can have 0.619 m radius (in open space)</li>
    <li>16-QAM rate AP offers  0.324-m radius per cell at the edge</li>
    <li>64-QAM rate AP offers  0.226-m radius per cell at the edge</li>
</ul>
</li>
    <li>Common distances
<ul>
    <li>MAP to MAP: 100 to 200 m</li>
    <li>Client to MAP: 80 to 150 m</li>
    <li>RAP to first MAP: 200 to 800 m ( If RAP is high, APs at the foot of the building are in the shadow area, and need to go through another MAP to reach the RAP)</li>
    <li>Maximum recommended number of hops to RAP is 4</li>
</ul>
</li>
    <li>AP cell area can be approximated as
<blockquote style="margin:0 0 0 40px;border:none;padding:0;">Area = Pi (3.14159) x Square of the radius</blockquote>
<ul>
    <li>For Mesh, neighbouring APs overlap forming a hexagon with aan AP on each side</li>
</ul>
</li>
</ul>

<!--more-->

<p style="padding-left:120px;">Area = 2.598 x Square of the radius</p>

<p style="padding-left:120px;">Number of APs per Km= 1 / (2.598 x Square of the radius)</p>

<p style="padding-left:30px;"><a href="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_03_10_49_40_9780133096491-pdf_secured_adobe_reader.png"><img class="alignnone size-full wp-image-2926" src="http://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_03_10_49_40_9780133096491-pdf_secured_adobe_reader.png" alt="2014_10_03_10_49_40_9780133096491.pdf_SECURED_Adobe_Reader" width="542" height="233" />
</a><span style="color:#000000;font-weight:bold;font-style:inherit;line-height:1.625;">Planning for Outdoor Surveys</span></p>

<ul>
    <li>MAPs are commonly located on light poles and RAPs on towers or rooftops</li>
    <li>Issues with mounting on the pole
<ul>
    <li>The mounting hardware might not fit the pole.</li>
    <li>The antenna might end up too close to the pole.</li>
    <li>Power might not be available all the time.</li>
    <li>The pole might not handle the AP weight and wind load.</li>
    <li>Aesthetics</li>
</ul>
</li>
    <li>All outdoor APs must be grounded</li>
    <li>Make sure that nothing is blocking the first Fresnel zone, even the mounting point itself.
<ul>
    <li>Poles placed near the antenna can also affect the antenna radiation pattern and create dead spots in the direction of the pole.</li>
    <li>The minimum distance between the antenna and the pole depends on:
<ul>
    <li>Pole thickness</li>
    <li>Antenna height</li>
    <li>the street angle, the lower pole antenna radiation may be too low to be in range with the next AP up the street.</li>
    <li>Frequency to be used (5 GHz APs need more clearance)</li>
</ul>
</li>
    <li>the antenna should be placed far enough so that the pole does not block more than 5 degrees in the antenna field of view.</li>
</ul>
</li>
    <li>Outdoor mesh APs should not be used to provide indoor coverage. Indoor APs should be used to relay signal from the mesh AP</li>
    <li>Surrounding environment will also affect the design
<ul>
    <li>Buildings in the path change the cell shape</li>
    <li>Light pole positions determine where MAPs can be placed</li>
</ul>
</li>
    <li>APs and antennas in the same physical space interfere with each other even if they are not using the same channel soAPs should be separated to limit interference.
<ul>
    <li>Vertical separation is more efficient than horizontal separation.</li>
</ul>
</li>
</ul>

<a href="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_03_12_30_28_9780133096491-pdf_secured_adobe_reader.png"><img class="alignnone size-full wp-image-2927" src="http://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_03_12_30_28_9780133096491-pdf_secured_adobe_reader.png" alt="2014_10_03_12_30_28_9780133096491.pdf_SECURED_Adobe_Reader" width="705" height="187" /></a>

&nbsp;

<a href="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_03_12_48_36_9780133096491-pdf_secured_adobe_reader.png"><img class="alignnone size-full wp-image-2928" src="http://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_03_12_48_36_9780133096491-pdf_secured_adobe_reader.png" alt="2014_10_03_12_48_36_9780133096491.pdf_SECURED_Adobe_Reader" width="705" height="174" /></a>

&nbsp;

<a href="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_03_12_51_42_9780133096491-pdf_secured_adobe_reader.png"><img class="alignnone size-full wp-image-2929" src="http://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_03_12_51_42_9780133096491-pdf_secured_adobe_reader.png" alt="2014_10_03_12_51_42_9780133096491.pdf_SECURED_Adobe_Reader" width="674" height="121" /></a>

&nbsp;

<h2><strong>References:</strong></h2>

<ol>
<li><p>CCNP Wireless  (642-732 CUWSS) Quick Reference Guide by Jerome Henry</p></li>
<li><p>IPexpert’s CCNP CUWSS Wireless Voice on Demand (642-731)</p></li>
</ol>
