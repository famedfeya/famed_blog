---
layout: post
title: CCNA Wireless Summary Notes- Understanding Autonomous APs
date: 2014-07-26 07:05
author: tnotez
comments: true
categories: [640-722, CCNA Wireless, CCNA Wireless Summary Notes]
---
APs bridge wireless data from the air to normal wired network. Autonomous APs have both wired and wireless hardware so that wireless client associations can be locally terminated onto a wired connection. the AP is in charge of  mapping a service set identifier (SSID) to a VLAN, or in 802.11 terms, mapping a basic service set (BSS) to a distribution system (DS). Multiple SSIDs can be mapped to multiple VLANs using a trunk port.

By default, the AP will request an IP via DHCP. Otherwise, It will use the IP 10.0.0.1/26.

By default, any autonomous AP running IOS Release 12.3(4)JA or later has its radios disabled and does not have any SSIDs configured.

GUI initial credentials:
<ul>
	<li style="padding-left:30px;">username - blank</li>
	<li style="padding-left:30px;">password - Cisco</li>
</ul>
<strong>Radio Modes:</strong>
<ul>
	<li>Access Point Mode - AP maintains active BSS</li>
	<li>Repeater - AP associates with nearby AP to extend coverage. Ethernet port is disabled</li>
	<li>Root bridge - AP uses its Ethernet port to connect to bridge the wired network
to a remote wireless bridge over a point-to-point or point-to-multipoint link. No
wireless clients will be allowed to associate.</li>
	<li>Non-Root Bridge - The AP will act as a remote wireless bridge and will connect to a
root bridge AP over a wireless link.</li>
	<li>Workgroup Bridge - The AP will use one radio to associate with a nearby Cisco
access point, as if it is a wireless client. The other radio interface is disabled. The AP bridges between its radio and its Ethernet port. You can use an AP in workgroup
bridge (WGB) mode to provide wireless client capability to wired-only devices.</li>
	<li>Universal Workgroup Bridge —The AP will act as a workgroup bridge to associate
with Cisco and non-Cisco access points.</li>
	<li>Scanner —The AP will use its radio to scan channels and collect data</li>
</ul>
Aironet Extensions are Cisco proprietary information elements that Cisco APs can use to
interact with Cisco-compatible wireless clients. eg provide information  about its current client load so that potential clients can choose the least busy AP.  Aironet extensions are enabled by default.

Convert Autonomous AP to LAP
<ul>
	<li>Using Cisco PI</li>
	<li>Use the <a title="Autonomous to Lightweight Mode Upgrade tool" href="http://software.cisco.com/download/release.html?mdfid=279537740&amp;softwareid=280775089&amp;release=3.4">Autonomous to Lightweight Mode Upgrade tool</a>
<ul>
	<li>Only works for Cisco Aironet 1100, 1130, 1200, 1240, and 1310. Others need manual upgrade</li>
	<li>Download the Lightweight AP IOS Software. Its a recovery image file (small bootstrap  version of lightweight code) that allows the AP to boot up and find a wireless controller.</li>
	<li>Open the Upgrade tool as Administrator</li>
	<li>In the IP File field add fle that contains the list of AP IPs that need to be upgraded. This can be edited in notepad.</li>
	<li>Fill in Upgrade Options - are they using DHCP, WAN for upgrade etc</li>
	<li>LWAPP Recovery Image section - show path to TFTP or use internal.</li>
	<li>Add optional Controller Details</li>
	<li>Fill in Time Details</li>
	<li>If DNS is to be used enter DNS address and domain name</li>
	<li>Click start</li>
</ul>
</li>
	<li>Use AP’s CLI</li>
</ul>
<p style="padding-left:60px;">archive download-sw /overwrite /force-reload { tftp:|ftp:}//location/image-name</p>
If a filename contains k9w8,  as in Example 8-4 , it is a lightweight image. If it contains k9w7, it is an autonomous image.

<a href="https://littlenerdsdiary.files.wordpress.com/2014/07/2014_07_26_07_02_54_cisco_systems1.png"><img class="alignnone size-full wp-image-2754" src="http://littlenerdsdiary.files.wordpress.com/2014/07/2014_07_26_07_02_54_cisco_systems1.png" alt="2014_07_26_07_02_54_Cisco_Systems" width="660" height="180" /></a>

<a href="https://littlenerdsdiary.files.wordpress.com/2014/07/2014_07_26_07_03_17_cisco_systems2.png"><img class="alignnone size-full wp-image-2756" src="http://littlenerdsdiary.files.wordpress.com/2014/07/2014_07_26_07_03_17_cisco_systems2.png" alt="2014_07_26_07_03_17_Cisco_Systems" width="660" height="160" /></a>
