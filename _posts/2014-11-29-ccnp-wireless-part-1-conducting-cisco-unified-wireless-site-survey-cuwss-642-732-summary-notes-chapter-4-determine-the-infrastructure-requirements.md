---
layout: post
title: CCNP Wireless CUWSS 642-732 Summary Notes 19 - Infrastructure Requirements Part 1
date: 2014-11-29 22:05
author: tnotez
comments: true
categories: [642-732, CCNP Wireless, CCNP Wireless Summary Notes, CUWSS]
---
<h2><strong>AP Power </strong></h2>

Options for powering the AP

<ul>
    <li>AP model-specific Power module (DC Power)</li>
    <li>Power Injector - combine 48-VDC power with the data signal, sending both to the access point or bridge.
<ul>
    <li>The AIR-PWRINJ3 power injector for Cisco Aironet 1130AG, 1140AG, and 1240AG Series Access Points works with the power supply provided with the access point.</li>
    <li>The Cisco Aironet Power Injector Media Converter (AIR-PWRINJ-FIB) converts fiber media to Category 5 media and combines the resulting data signal with power for delivery to the access point or bridge.</li>
    <li>The AIR-PWRINJ-1000AF provides 802.13af inline PoE. It accepts 100–240 VAC and outputs 48 VDC.</li>
    <li>The AIR-PWRINJ1500 power injector converts AC power into DC power and sends it along with the Ethernet signal to the access point. It is designed to be used with the Cisco Aironet 1500 Series Outdoor Ethernet Cable (AIR-ETH1500-150) to power the Cisco Aironet 1500 Series Lightweight Outdoor Mesh Access Point.</li>
</ul>
</li>
    <li>PoE from the switch
<ul>
    <li>Cisco Pre-Standard PoE mode</li>
    <li>IEEE 802.3af standardizedPoE
<ul>
    <li>15.4 W of power per port for class 3</li>
</ul>
</li>
    <li>Cisco Enhanced Power for 56-VDC power or 802.3at protocol
<ul>
    <li>Up to 30W per port</li>
    <li>The difference is that the optimized maximum transmitter power drops from 20 dBm (100 mW) to 14 dBm (25 mW)</li>
</ul>
</li>
</ul>
</li>
</ul>

<a href="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_30_21_14_56_cuwss_v1-0_student_guide_vol1-pdf_adobe_reader.png"><img class="alignnone size-full wp-image-3386" src="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_30_21_14_56_cuwss_v1-0_student_guide_vol1-pdf_adobe_reader.png" alt="2014_10_30_21_14_56_CUWSS_v1.0_Student_Guide_Vol1.pdf_Adobe_Reader" width="468" height="160" /></a>

What happens when you connect an AP to less power than it is intended ( to 802.3at instead of 802.3af)? The AP will function but:

<ul>
    <li>AP drops to using a single stream for both bands and through a single transmitter</li>
    <li>Throughput is reduced to 72 Mbps over a 20-MHz channel for 2.4 band and 150 Mbps over a 40-MHz channel</li>
</ul>

Most APs can function with 12.95 W but if we use a long cable, then the power drawn can reach up to 15W 802.3af for Class 3 device.

No AP should be more than 100m away from the wiring closet. 802.11n APs should connect to GE ports

If your access point is connected to Ethernet inline power, do not connect the local power module to the access point. Using two power sources on the access point might cause the access point to shut down to protect internal components and might cause the switch to shut down the port to which the access point is connected.

<!--more-->

<h2>AP Deployment<em> Models: </em></h2>

<ul>
    <li>TheautonomousAPs model:
<ul>
    <li>Traffic is directly translated at the AP level between the wireless and the wired space.</li>
    <li>Used for simple and small deployments</li>
    <li>They have additional features like RADIUS, user database, or DHCP</li>
    <li>APs can be partly managed from WCS</li>
    <li>This deployment is cheaper than controller based usually</li>
    <li>no central device to manage all the APs and the radio frequency (RF) environment</li>
    <li>All parameters have to be configured AP per AP</li>
    <li>no dynamic inter-AP dialog for global RF management</li>
    <li>Does not scale well</li>
</ul>
</li>
    <li>The controller-based model:
<ul>
    <li>Some traffic (CAPWAP control) always flows between APs and their controller.Clientauthenticationanddatatrafficflowdependsonthesubmodel you choose
<ul>
    <li>central switching</li>
    <li>local switching</li>
    <li>central authentication</li>
    <li>local authentication</li>
</ul>
</li>
    <li>Parameters are centrally managed</li>
    <li>Better roaming</li>
    <li>Better control of client parameters like QoS, vlan mapping etc</li>
    <li>Scales easily</li>
    <li>More expensive</li>
    <li>its richness of features makes it more complex to configure and maintain</li>
    <li>The controller can become a single point of failure and a bottleneck for client traffic if not designed properly</li>
    <li>Increased latency if client traffic needs to pass by WLC</li>
</ul>
</li>
</ul>

To be able to design the network properly, we need to know the different data flows.

<h3><strong>Authentication Data Flow</strong></h3>

<ul>
    <li>pre-shared key (PSK)</li>
</ul>

<p style="padding-left:60px;">Client &gt; Autonomous AP</p>

<p style="padding-left:60px;">Client &gt; Controller (CAPWAP AP in local mode or Flexconnect / HREAP with central authentication)</p>

<p style="padding-left:60px;">Client &gt; CAPWAP AP (Flexconnect AP with local authentication)</p>

<ul>
    <li> 802.1x authentication. Each client authentication exchange represents up to 14 packets.</li>
</ul>

<blockquote>
<p style="padding-left:30px;">Client -&gt; Autonomous AP -&gt; Radius Server.</p>
<p style="padding-left:60px;">When roaming, new authentication needs to be done every time.</p>
<p style="padding-left:30px;">Client &gt; Auto AP &gt; AP set as Wireless Domain Service (WDS) &gt; Radius Server. WDS can cache the credentials eliminating Radius when client roams within the same subnet. WDS AP and AP should be in same subnet.</p>
<p style="padding-left:60px;">When roaming: Client &gt; new AP &gt; WDS AP.</p>
<p style="padding-left:60px;">If AP and WDS are in  different subnets, authentication must be done again.</p>
<p style="padding-left:30px;">Client &gt; (CAPWAP AP in local mode or Flexconnect / HREAP with central authentication) tagged DSCP CS4 &gt; WLC &gt; Radius tagged DSCP CS4 &gt; WLC &gt; CAPWAP AP &gt; Client. WLC informs all other controllers in mobility group about new client to help in roaming. If APs in same HREAP group,</p>
<p style="padding-left:60px;">When roaming (same mobility group): Client &gt; New AP &gt; New WLC &gt; Queries Old WLC and gets credentials &gt; new WLC. Radius is not involved.</p>
<p style="padding-left:60px;">If HREAPs not in the same HREAP group, new auth must occur.</p>
<p style="padding-left:30px;">Client &gt; CAPWAP AP (Flexconnect AP with local/RADIUS authentication) tagged DSCP CS4 &gt; Radius &gt; AP &gt; Client</p>
<p style="padding-left:60px;">When roaming:</p>
<p style="padding-left:90px;">If in same HREAP group, APs exchange credentials with each other</p>
<p style="padding-left:90px;">If not in same HREAP, new auth needs to be done</p>
</blockquote>

<h3><strong>Client Traffic Flow</strong></h3>

<ul>
    <li>AutonomousAPs
<ul>
    <li>Source and Destination in same WLAN and Same VLAN: Traffic goes through AP only</li>
    <li>All other cases: Client Traffic &gt; AP &gt;SW &gt; Router(if different subnet)&gt;etc etc</li>
</ul>
</li>
    <li>Controller Based Solution (APs in local mode or HREAP with central switching): Client Traffic &gt; AP&gt; WLC &gt; Same or different A P depending on destination &gt;</li>
    <li>Controller Based Solution (HREAP with local switching): Clients &gt;AP and switched directly.</li>
    <li>InterController roaming
<ul>
    <li>BothWLCmaptheWLANtosameVLAN (local to local roaming)
<ul>
    <li>Credentials are completely moved to the new Controller</li>
    <li>Old WLC forgets about the client</li>
    <li>Traffic starts flowing only through new WLC</li>
</ul>
</li>
    <li>BothWLC map the WLAN to different  VLANs  (local to foreign roaming)
<ul>
    <li>new controller cannot switch the client directly because associated VLANs are different so it pushes clients to a different VLAN &gt;Client IP address has to change and may lead to disconnection</li>
    <li>Instead Traffic from Client &gt;new AP &gt;new WLC via CAPWAP tunnel&gt; Initial controller via Ethernet over IP frame (EoIP) &gt; to destination</li>
    <li>traffic always seems to come from initial WLC and client keeps it's IP</li>
    <li>Return traffic is sent to client subnet &gt; initial WLC interscepts traffic &gt; sends to new WLC via EoIP &gt; new AP via CAPWAP &gt; client</li>
</ul>
</li>
    <li>When Anchor Controller is present
<ul>
    <li>Client &gt; AP &gt; WLC &gt; Anchor WLC via EoIP packet &gt;destination</li>
    <li>Return traffic: Anchor Intercepts &gt; sends to initial WLC via EoIP &gt; AP &gt; Client</li>
</ul>
</li>
</ul>
</li>
</ul>

<h3><strong>Control Traffic Flow</strong>  and Ports</h3>

CAPWAP traffic (between AP andWLC)

<ul>
    <li>to WLC (0.35 Kbps per AP) : sent from AP via UDP 5246 with DSCP tag CS6</li>
    <li>Initial AP configuration = 6000 bytes</li>
    <li>from WLC sent to APs via UDP 5247 with DSCP depending on WLC for that client WLAN</li>
    <li>CAPWAPdiscoveriesfromAPtoWLCs
<ul>
    <li>Sent every 30 s by default</li>
</ul>
</li>
</ul>

Mobility Messages ( betweenWLCs in same Mobility group)

<ul>
    <li>destination port UDP 16666
<ul>
    <li>Keepalive about new clients</li>
    <li>EoIP for passing client traffic between controllers</li>
    <li>Sent without QoS tags (best effort)</li>
</ul>
</li>
    <li>WLCs in same RF
<ul>
    <li>Exchange messages to optimize AP channels and power levels without QoS tags (best effort)
<ul>
    <li>For 2.4 band - Source port UDP 12124 and Destination UDP 12134</li>
    <li>For 5 GHz - - Source port UDP 12125 and Destination UDP 12135</li>
</ul>
</li>
</ul>
</li>
</ul>

<ul>
    <li>For Cisco Mobility Service Engine
<ul>
    <li>ProtoclusedtocommunicatewithWLCs is - Network Management Service Protocol (NMSP) - no QoS
<ul>
    <li>From WLC to MSE - destination port TCP 16113</li>
    <li>If Aeroscout engine is activated, other ports may be needed</li>
</ul>
</li>
    <li>ProtocolusedforcommunicationBetweenMSE and WCS - Simple Object Access Protocol/ Extensible Markup Language (SOAP/XML) - no QoS
<ul>
    <li>TCP 80/443 HTTP ports used</li>
</ul>
</li>
    <li>For3rdpartyinteractionwithMSE via API - no QoS
<ul>
    <li>TCP port 8001 by default</li>
</ul>
</li>
</ul>
</li>
    <li>For WCS
<ul>
    <li>CommunicationwithWLC
<ul>
    <li>SNMP UDP ports 161 and 162</li>
</ul>
</li>
</ul>
</li>
</ul>

<a href="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_02_08_54_33_9780133096491-pdf_secured_adobe_reader.png"><img class="alignnone size-full wp-image-2905" src="http://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_02_08_54_33_9780133096491-pdf_secured_adobe_reader.png" alt="2014_10_02_08_54_33_9780133096491.pdf_SECURED_Adobe_Reader" width="705" height="246" /></a>

Controller Interfaces:

<ul>
    <li>Management Interface - communication with the WCS, the MSE, Lightweight Directory Access Protocol (LDAP) servers, and RADIUS servers. We can force the dynamic interface associated with the WLAN to be used instead by checking</li>
</ul>

<a href="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_02_09_02_03_nldcbpwlc01.png"><img class="alignnone size-full wp-image-2907" src="http://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_02_09_02_03_nldcbpwlc01.png" alt="2014_10_02_09_02_03_NLDCBPWLC01" width="705" height="223" /></a>

<ul>
    <li>Dynamic interface - used to relay DHCP traffic to DHCP server</li>
    <li>AP manager interface - communication with CAPWAPs</li>
</ul>

<h2><strong>References:</strong></h2>

<ol>
<li><p>CCNP Wireless  (642-732 CUWSS) Quick Reference Guide by Jerome Henry</p></li>
<li><p>IPexpert’s CCNP CUWSS Wireless Voice on Demand (642-731)</p></li>
</ol>
