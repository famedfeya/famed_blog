---
layout: post
title: CCNP Wireless CUWSS 642-732 Summary Notes 24 - Installation Report
date: 2014-12-01 15:31
author: tnotez
comments: true
categories: [642-732, CCNP Wireless, CCNP Wireless Summary Notes, CUWSS, CWNA]
---
<h2>Post Deployment</h2>

A detailed hardware requirement list should have:

Wireless equipment needed

Supporting infrastructure upgrades

<ul>
    <li>RF Validation for the installed wireless network
<ul>
    <li>Co channel interference and appropriate channel separation</li>
    <li>Power levels are consistent with site survey</li>
    <li>If designing for AP failover or designing to RRM</li>
    <li>RF Coverage (band by band)</li>
</ul>
</li>
    <li>Roaming audit
<ul>
    <li>Airmagnet can be used in active and also using IPERF</li>
</ul>
</li>
    <li>Wireless Infrastructure
<ul>
    <li>If designing especially globally, verify channel allocation is consistent</li>
    <li>For 5 GHz band, make sure that the clients support all those UNI bands.Verify that RRM is consistent with what was achieved during survey</li>
</ul>
</li>
    <li>Application testing
<ul>
    <li>Validate all layers 1 through 7</li>
</ul>
</li>
</ul>

<h2><strong>Installation Report / </strong><b>Deliverables</b></h2>

This report describes the deployment methodology and the tests that were performed to validate the installation.

The report should include the following:

<ul>
    <li>Spectrum analysis</li>
    <li>RF coverage analysis</li>
    <li>Hardware placement and configuration</li>
    <li>Application analysis - Includes results from application throughput testing</li>
</ul>

<!--more-->

<h3>Cables and Hardware</h3>

Include the following details.

<ul>
    <li>Cable maps for each floor and building.</li>
    <li>Cable testing reports
<ul>
    <li>Test of all pair combinations to 100 MHz for Category 5E</li>
    <li>Test of all pair combinations to 250 MHz for Category 6</li>
    <li>Measurement of near-end crosstalk</li>
    <li>Measurement of attenuation</li>
    <li>Test of return loss, resistance, and impedance</li>
    <li>Test of length of cable (If the cable exceeds 100 meters, the test fails)</li>
    <li>Test of capacitance and crosstalk</li>
    <li>Performance of a wire map test to ensure that no pairs are crossed and that all pairs are terminated correctly</li>
</ul>
</li>
    <li>Physical AP placement and physical placement to the switch</li>
    <li>Additional infrastructure that was added</li>
    <li>WCS, MSE and other hardware specific to the deployment should be added.</li>
</ul>

<h3>Software and Configuation</h3>

<ul>
    <li>Serial, software, model, IP and location should be included for all devices used</li>
    <li>Softcopies of configuration</li>
    <li>Licences used for the installation</li>
</ul>

<h3>Wireless Coverage</h3>

<ul>
    <li>Include maps of the facility displaying coverage levels</li>
    <li>Include both active and passive survey reports</li>
    <li>Survey findings, conclusions and recommendations</li>
    <li>Include best practise for AP deployments</li>
</ul>

<h2>Additional Reports:</h2>

Vendor Recommendations - It is recommended to stick to one vendor for both surveying and installation. This is because most vendors have different thresholds.

Implementation diagrams - a wireless topology map that illustrates where the access points will be installed and how the wireless network will be integrated into the existing wired infrastructure. AP placement, segmentation, and layer 3 boundaries will all be clearly defined.

Bill of materials - itemizes every hardware and software component necessary for the final installation of the wireless network.

Project schedule and costs - A detailed deployment schedule should be drafted that outlines all timelines, equipment costs, and labor costs

Security solution recommendations - Includes All aspects of authentication, authorization, accounting, encryption, and segmentation.

Wireless policy recommendations

Training recommendations for customer's network personnel and even end users.

<h2>References:</h2>

<ol>
    <li>CCNP Wireless  (642-732 CUWSS) Quick Reference Guide by Jerome Henry</li>
    <li>IPexpert’s CCNP CUWSS Wireless Voice on Demand (642-731)</li>
    <li>CWNA Certified Wireless Network Administrator Study Guide by David D. Coleman and David A. Wesrcott.</li>
    <li></li>
</ol>
