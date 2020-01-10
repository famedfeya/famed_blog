---
layout: post
title: CCNA Wireless Summary Notes- Understanding the CUWN Architecture
date: 2014-07-25 20:23
author: tnotez
comments: true
categories: [640-722, CCNA Wireless, CCNA Wireless Summary Notes]
---
AP traffic is divided into the following:
<ul>
	<li>Data Plane traffic - end user traffic</li>
	<li>Control Plane traffic - control, configure, manage, and monitor the AP</li>
</ul>
Recall that autonomous APs bridge traffic between a wireless BSS and a wired VLAN. An Autonomous AP performs the following combined functions
<ul>
	<li>Lightweight AP functions (Real Time functions)
<ul>
	<li>RF Transmit/Receive</li>
	<li>MAC Management</li>
	<li>Encryption</li>
</ul>
</li>
	<li>WLC Functions (Management functions)
<ul>
	<li>RF Management</li>
	<li>Association &amp; Roaming Management</li>
	<li>Client Authentication</li>
	<li>Security Management</li>
	<li>QoS</li>
</ul>
</li>
</ul>
The Cisco Unified Wireless Network (CUWN) is a centralized, unified approach. In the CUWN, a lightweight access point (LAP) performs only the real-time 802.11
operation. Management is performed on the WLC. The LAP-WLC division of labor is known as a split-MAC architecture. The Control and Provisioning of Wireless Access Points (CAPWAP - RFCs 5415, 5416, 5417, and 5418) tunneling protocol enables the AP and the WLC to communicate despite their location. It encapsulates the data between the APs and the WLC. UDP port 5246 transports CAPWAP control data to the WLC. CAPWAP data uses UDP port 5247 and is not encrypted by default. Encrypted packets are protected by Datagram Transport Layer Security (DTLS).

Every LAP and WLC must also authenticate each other with X.509 digital certificates.

Activities performed by the WLC:
<ul>
	<li>Dynamic channel assignment</li>
	<li>Automatically sets the power for each LAP according to the coverage area needed</li>
	<li>Self-healing wireless coverage incase a LAP dies by increasing power for remaining LAPSю able to pinpoint and recover from external problems dynamically.</li>
	<li>L2 and L3 client roaming</li>
	<li>Dynamic client load balancing</li>
	<li>RF Monitoring</li>
	<li>Security management</li>
	<li>Wireless intrusion protection system</li>
</ul>
For Autonomous APs, traffic from client to client passes through the LAP then to the next client. For LAP, The client traffic  usually travels through the CAPWAP tunnel and passes through the WLC before making a return trip back through the tunnel to the other client. Clients may use DLS to communicate directly, without passing through the AP and controller; LAPs can also be configured in FlexConnect mode, so that traffic can be forwarded locally at the AP if needed.

Flexconnect: remote site LAPs are able to locally switch the traffic without traversing the CAPWAP tunnel. FlexConnect allows the LAP to keep switching traffic locally to maintain wireless connectivity available inside the remote site.

<strong>Cisco WLCs</strong>

<a href="https://littlenerdsdiary.files.wordpress.com/2014/07/2014_07_25_19_18_03_ccna_wireless_640_722_official_cert_guide_secured_adobe_reader.png"><img class="alignnone size-full wp-image-2748" src="http://littlenerdsdiary.files.wordpress.com/2014/07/2014_07_25_19_18_03_ccna_wireless_640_722_official_cert_guide_secured_adobe_reader.png" alt="2014_07_25_19_18_03_CCNA_Wireless_640_722_Official_Cert_Guide_SECURED_Adobe_Reader" width="580" height="644" /><img class="alignnone size-full wp-image-2747" src="http://littlenerdsdiary.files.wordpress.com/2014/07/2014_07_25_19_16_10_ccna_wireless_640_722_official_cert_guide_secured_adobe_reader.png" alt="2014_07_25_19_16_10_CCNA_Wireless_640_722_Official_Cert_Guide_SECURED_Adobe_Reader" width="617" height="234" /></a>

The vWLC cannot support any APs in local mode; all APs must be configured for FlexConnect instead.

<strong>Cisco APs. </strong>

<a href="https://littlenerdsdiary.files.wordpress.com/2014/07/2014_07_25_19_23_21_ccna_wireless_640_722_official_cert_guide_secured_adobe_reader.png"><img class="alignnone size-full wp-image-2749" src="http://littlenerdsdiary.files.wordpress.com/2014/07/2014_07_25_19_23_21_ccna_wireless_640_722_official_cert_guide_secured_adobe_reader.png" alt="2014_07_25_19_23_21_CCNA_Wireless_640_722_Official_Cert_Guide_SECURED_Adobe_Reader" width="581" height="500" /></a> <a href="https://littlenerdsdiary.files.wordpress.com/2014/07/2014_07_25_19_23_36_ccna_wireless_640_722_official_cert_guide_secured_adobe_reader.png"><img class="alignnone size-full wp-image-2750" src="http://littlenerdsdiary.files.wordpress.com/2014/07/2014_07_25_19_23_36_ccna_wireless_640_722_official_cert_guide_secured_adobe_reader.png" alt="2014_07_25_19_23_36_CCNA_Wireless_640_722_Official_Cert_Guide_SECURED_Adobe_Reader" width="581" height="346" /></a>

CleanAir - allows an AP to perform spectrum analysis on the wireless channels to detect non-802.11 interference.

As the number of radios and spatial streams increases, the AP is able to provide a greater throughput for its clients.

AP Operation Modes:
<ul>
	<li>Local (Default). During times that it is not transmitting, the LAP will scan  the other channels to measure the noise floor, measure interference, discover rogue
devices, and match against intrusion detection system (IDS) events.</li>
	<li>Monitor Mode. No transmission of traffic. but its receiver is enabled to act  as a dedicated sensor. The LAP checks for IDS events, detects rogue access points,
and determines the position of stations through location-based services (LBS).</li>
	<li>Flexconnect (HREAP). LAP can locally switch traffic between an SSID and a VLAN if its CAPWAP tunnel to the  WLC is down or configured to.</li>
	<li>Sniffer Mode. Acts as packet sniffer and passes traffic to software analyzers like wireshark</li>
	<li>Rogue detector.</li>
	<li>OfficeExtend AP (OEAP).  LAP connects to the local broadband service and builds  a CAPWAP tunnel to the central WLC. User data can be encrypted over the
CAPWAP data tunnel using DTLS.</li>
	<li>SE-Connect for spectrum analysis.</li>
</ul>
<strong>CUWN Management</strong>
<ul>
	<li>Wireless Control System (WCS)
<ul>
	<li>Dedicated appliance</li>
	<li>WLAN management or configuration tasks</li>
	<li>RF planning</li>
	<li>wireless user tracking, troubleshooting, and monitoring</li>
	<li>display predictive “heatmap” representations of coverage</li>
	<li>locate a wireless client  to within a few meters by triangulating the client’s signal as received by multiple LAPs.</li>
	<li>with Cisco Wireless Location Appliance it could track client location</li>
	<li>The WCS Navigator product provided a single portal to manage up to 20 instances  of WCS and up to 30,000 APs</li>
</ul>
</li>
	<li>Cisco Prime Network Control System (NCS)
<ul>
	<li>Either dedicated appliance or vMware</li>
	<li>wireless device management</li>
	<li>switch management</li>
	<li>dynamic RF coverage heatmaps</li>
	<li>with MSE it could provide client location tracking</li>
</ul>
</li>
	<li>Cisco Prime Infrastructure (PI)
<ul>
	<li>offers converged management  of both wireless and wired network devices</li>
	<li>integration with wireless intrusion  prevention services,</li>
	<li>spectrum analysis,</li>
	<li>tracking of users, interferers, and rogue devices.</li>
</ul>
</li>
</ul>
