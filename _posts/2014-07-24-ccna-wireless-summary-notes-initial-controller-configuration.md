---
layout: post
title: CCNA Wireless Summary Notes- Initial Controller Configuration
date: 2014-07-24 17:15
author: tnotez
comments: true
categories: [640-722, CCNA Wireless, CCNA Wireless Summary Notes, Cisco Wireless]
---
For WLC ports and interfaces refer to different concepts. Controller ports are physical connections made to an external switched network, whereas interfaces are logical connections made internally within the controller.

Port types:
<ul>
	<li>Service port - OOBM, system recovery, initial boot. Connects using Access port only.</li>
	<li>Distribution system port - For AP and management traffic, Client data. Usually a 802.1Q trunk port. For resiliency, configure as LAG port (etherchannel)</li>
	<li>Console port - OOBM, system recovery, initial boot</li>
	<li>Redundancy port — connect to peer controller for redundancy.</li>
</ul>
Controller interfaces:
<ul>
	<li>Management interface - For management traffic</li>
	<li>AP-manager interface (Optional) - Used to terminate CAPWAP tunnels between the controller and its APs. Should be on same vlan as the management but it can be created separately if we want to seperate the management and CAPWAP traffic.</li>
	<li>Virtual interface - Used to relay client DHCP requests, client web authentication,
and to support client mobility (all WLCs in same mobility group should have the same IP)</li>
	<li>Service port interface - Connects to the SP port for OOBM</li>
	<li>Dynamic interface - connects WLAN to VLAN</li>
</ul>
Initial setup via WEB and CLI
<ul>
	<li>Configure system access.</li>
	<li>Configure SNMP access. v3 is recommended</li>
	<li>Configure the service port.</li>
	<li>Enable or disable LAG</li>
	<li>Configure the management interface.</li>
	<li>Configure the RF mobility domain and country code. Default is US.</li>
	<li>Configure the virtual interface. Should add this to the DNS because it is used for client web authentication</li>
	<li>Configure a WLAN. The WLAN ID is an internal index used when configuration templates are applied to a controller from an Cisco Prime Network Control System (NCS) or Cisco Prime Infrastructure (PI) management station.</li>
	<li>Configure a RADIUS server for client authentication</li>
	<li>Configure 802.11 support.</li>
	<li>Configure the system clock.</li>
	<li>Save and Reboot.</li>
</ul>
&nbsp;

&nbsp;
