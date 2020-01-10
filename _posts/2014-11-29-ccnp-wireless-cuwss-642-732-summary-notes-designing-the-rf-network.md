---
layout: post
title: CCNP Wireless CUWSS 642-732 Summary Notes 18 - Hardware for the RF Network
date: 2014-11-29 20:45
author: tnotez
comments: true
categories: [642-732, CCNP Wireless, CCNP Wireless Summary Notes, CUWSS]
---
<strong>Designing the RF network</strong>

Define the APs and WLC requirements

<h2>AP Density</h2>

This depends on:

<ul>
    <li>Application requirements
<ul>
    <li>Data Networks (web browsing)
<ul>
    <li>15 to 25 users per AP
<ul>
    <li>802.11b users reduce a 802.11g AP throughput dramatically. The 802.11b client still has a maximum data rate of 11 Mb/s per second and a maximum throughput of 7.1 Mb/s.</li>
</ul>
</li>
    <li>Data requires 15 to 20 % overlap</li>
    <li>For an application such as bar code reading, the number of users can increase considerably and this may require using IEEE 802.11g to increase data rates.</li>
</ul>
</li>
    <li>Location based services
<ul>
    <li>To avoid co channel interference due to dense deployment, the APs at the edge should be set to monitor mode (only used for location purposes)</li>
    <li>inter-access point separation of between 40 to 70 feet.</li>
</ul>
</li>
    <li>Legacy clients may impact the network and should be taken into account
<ul>
    <li>Take into consideration protection mechanisms</li>
    <li>Supported channels</li>
    <li>Supported encr yptions</li>
</ul>
</li>
</ul>
</li>
    <li>Number of users</li>
    <li>Data Rate Supported
<ul>
    <li>By increasing the access point count and lowering the power, you can improve throughput for users.</li>
</ul>
</li>
</ul>

<!--more-->

<h2>Hardware use case APs</h2>

<ul>
    <li>1130APs
<ul>
    <li>Used Indoors</li>
    <li>Has internal antennas</li>
    <li>Used in schools and healthcare facilities</li>
    <li>With dual 802.11a and 802.11g radios, the access point provides up to 108 Mb/s of capacity in a single device.</li>
</ul>
</li>
    <li>1140APs
<ul>
    <li>similar to 1130</li>
    <li>has 802.11n</li>
</ul>
</li>
    <li>1240APs
<ul>
    <li>Ruggedized APs</li>
    <li>Used in warehouses</li>
    <li>Support 802.11a/b/g</li>
    <li>External connectors</li>
    <li>With dual 802.11a and 802.11g radios, the access point provides up to 108 Mb/s of capacity in a single device.</li>
</ul>
</li>
    <li>1250APs
<ul>
    <li>Ruggedized APs</li>
    <li>Used in warehouses</li>
    <li>has 802.11n</li>
    <li>Supports 1000 Ethernet which was specifically engineered to support the power, throughput, and 802.11n.</li>
    <li>needs 18.5Ws<a href="https://littlenerdsdiary.files.wordpress.com/2014/10/2014-11-11-17_21_46-cuwss-v1-0-student-guide_vol1-pdf-adobe-reader.png"><img class="alignnone size-full wp-image-3434" src="https://littlenerdsdiary.files.wordpress.com/2014/10/2014-11-11-17_21_46-cuwss-v1-0-student-guide_vol1-pdf-adobe-reader.png" alt="2014-11-11 17_21_46-CUWSS v1.0 Student Guide_Vol1.pdf - Adobe Reader" width="593" height="264" /></a></li>
</ul>
</li>
</ul>

<h2>Controllers</h2>

<ul>
    <li>5500
<ul>
    <li>Supports 12 - 500 APs (12,25,50,100,250,500)</li>
    <li>Max throughput of 8 Gbps</li>
    <li>Supports up to 7000 clients</li>
    <li>Up to 3000 RFIDs</li>
    <li>Supports up to 100 Concurrent AP upgrades and joins</li>
    <li>Up to 8, 1 Gbps SFPs that are non PoE</li>
    <li>Supports up to 18000 APs in a mobility domain</li>
    <li>Only 1 WLC per physical device</li>
    <li>Consumes 125 W power</li>
    <li>Flexible AP count and feature upgrade via licencing</li>
    <li>Encrypted data link between AP and WLC</li>
</ul>
</li>
    <li>4400
<ul>
    <li>Falvours: 4402 and 4404</li>
    <li>4402: Supports 12,25,50, APs and has 2 GB connections</li>
    <li>4404: Supports up to 100 APs, 4 GB connections and used in Medium to large office deployments</li>
    <li>Max throughput of 4 Gbps</li>
    <li>Supports up to 5000 clients</li>
    <li>Supports up to 10 Concurrent AP upgrades and joins</li>
    <li>Up to 4, 1 Gbps SFPs</li>
    <li>Supports up to 7200 APs in a mobility domain</li>
    <li>Only 1 WLC per physical device</li>
    <li>Consumes 47 W power</li>
    <li>No Flexible AP count and feature upgrade via licencing</li>
    <li>No Encrypted data link between AP and WLC</li>
    <li>WiSm (Wireless Intergrated Services Module)</li>
    <li>Used in 6500 Catalyst and 7800 routers</li>
    <li>Supports 300 APs</li>
    <li>Max throughput of 8 Gbps</li>
    <li>Supports up to 10000 clients</li>
    <li>Supports up to 20 Concurrent AP upgrades and joins</li>
    <li>uses cat6K backplane</li>
    <li>Supports up to 10800 APs in a mobility domain</li>
    <li>2 WLC per physical device</li>
    <li>Consumes 164 W power</li>
    <li>Flexible AP count and feature upgrade via licencing</li>
    <li>Encrypted data link between AP and WLC</li>
    <li>can be clustered to support up to 3600 APs (12 WiSMs)</li>
</ul>
</li>
    <li>2100
<ul>
    <li>Flavours - 2106 (6 APs) , 2112 (12 APs) and 2125 (25 APs)(21XX indicates the supported APs)</li>
    <li>8 ports, 2 of which can provide power to Cisco access points</li>
    <li>To avoid co-channel interference in dense deployments, some of the APs can be set to monitor mode</li>
    <li>Locations that deploys 3 or more APs can utilize RRM ( Radio Resource Manager) that is RF manager for the network. It dynamically manages power and channels for APs.</li>
</ul>
</li>
    <li>Cisco 2500 Series WLAN Controller
<ul>
    <li>Ideal for Enterprise branches and Small and medium sized businesses</li>
    <li>Supports up to 50 APs</li>
    <li>Supports up to 500 clients</li>
    <li>Has 4 GB ports (2 are PoE and can be used to power APs)</li>
</ul>
</li>
    <li>Cisco Catalyst 6500 Wireless Service Module 2 (WiSM2)
<ul>
    <li>Supports up to 500 APs (100,300,500)</li>
    <li>Up to 10000 WLAN Clients</li>
    <li>Up to 5000 RFIDs</li>
    <li>Up 2 5 WiSM blades if switch supports other modules, 7 blades if chassis does not support other modules (also forthe Cisco 7600 Series router)</li>
    <li>Several chassis can be clustered together (up to 36000 APs in one mobility group)</li>
    <li>Requires a Supervisor 720 module to support WiSM2</li>
</ul>
</li>
    <li>Cisco Flex 7500 Series Controller
<ul>
    <li>Designed specifically for HREAPs</li>
    <li>Does not support APs in other modes</li>
    <li>Suppports up to 2000 HREAPs (250,500,1000,2000)</li>
    <li>Up to 20000 wireless clientsConnects to the wired network through 2 10 GB ports</li>
</ul>
</li>
</ul>

<h2>WCS</h2>

<ul>
    <li>OS requirements
<ul>
    <li>Windows 2003 SP2 or later or Linux Red Hat 5.0.32 bit or later</li>
</ul>
</li>
    <li>Highend Server
<ul>
    <li>Supports up to 3000 LWAP AP, 1250 Autonomous APs and 750 Controllers</li>
    <li>Requires at least Intel Xeon 3.16 Quad GHz CPU with 8 GB RAM and 200 GB Hard-drive (80 free)</li>
</ul>
</li>
    <li>Standard Server
<ul>
    <li>Supports up to 2000 LWAP AP, 1000 Autonomous APs and 450 Controllers</li>
    <li>Requires at least Intel Xeon 3.2 GHz CPU with 4 GB RAM and 80 GB Hard-drive (40 free)</li>
</ul>
</li>
    <li>Low end Server
<ul>
    <li>Supports up to 500 AP, 200 Autonomous APs and 125 Controllers</li>
    <li>Requires at least Intel 3.06 GHz CPU with 2 GB RAM and 40 GB Hard-drive (30 free)</li>
</ul>
</li>
    <li>Location Based Services
<ul>
    <li>WCS requires a licence to enable location based services depending on the number of tracked clients</li>
    <li>WCS can track but on demand and only one device at a time</li>
    <li>RequiresMSE (also needs a licence)
<ul>
    <li>MSE 3310
<ul>
    <li>tracks 2000 devices simulteneously</li>
    <li>Supports up to 2000 APs in WiPS ( Wireless Intrusion Prevention System)</li>
</ul>
</li>
    <li>MSE 3355
<ul>
    <li>tracks 18000 devices simulteneously</li>
    <li>Supports up to 2000 APs in WiPS ( Wireless Intrusion Prevention System)</li>
</ul>
</li>
</ul>
</li>
</ul>
</li>
    <li>WCS Licence
<ul>
    <li>BasedonthenumberofdeployedAPsnown to the WCS
<ul>
    <li>Single-server  licence (50,100,500 AP units) with a total of up to 3000 APs per server</li>
    <li>Multiple server licences (1000, 2500, 10000, 50000 with a total of 50000 APs per WCS)</li>
    <li>Licences can be:
<ul>
    <li>Base Licence
<ul>
    <li>Location based on client RSSI from the closest AP</li>
</ul>
</li>
    <li>Plus Licence
<ul>
    <li>Provides real location determined from RSSI read from several APs</li>
    <li>Provides MSE support</li>
    <li>Provides HA for WCS feature</li>
</ul>
</li>
    <li>CAS (Context Aware Services)licences ( 3000, 6000, 12000 devices) for location tracking)</li>
    <li>WiPS Licence (25,100,500, 2000 APs)</li>
</ul>
</li>
    <li>MSE  can support WiPS and CAS on sma eappliance</li>
</ul>
</li>
    <li>Specific cleanair licence is not required</li>
    <li>Each located interferer consumes a standard CAS slot</li>
    <li>If you plan on running Spectrum intelligence ( Cisco Spectrum Expert) then a Spectrum intelligence licence is required for collecting information on WCS from Spectrum Expert stations)</li>
</ul>
</li>
</ul>

<h2>Wired Connection requirements</h2>

<a href="https://littlenerdsdiary.files.wordpress.com/2014/10/1.png"><img class="alignnone size-full wp-image-2948" src="http://littlenerdsdiary.files.wordpress.com/2014/10/1.png" alt="1" width="705" height="121" /></a>

<h2>Post Deployment</h2>

A detailed hardware requirement list should have:

<p style="padding-left:60px;">Wireless equipment needed</p>

<p style="padding-left:60px;">Supporting infrastructure upgrades</p>

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

<h2><strong>References:</strong></h2>

<ol>
<li>CCNP Wireless  (642-732 CUWSS) Quick Reference Guide by Jerome Henry</li>
<li>IPexpert’s CCNP CUWSS Wireless Voice on Demand (642-731)</li>
</ol>

&nbsp;

&nbsp;
