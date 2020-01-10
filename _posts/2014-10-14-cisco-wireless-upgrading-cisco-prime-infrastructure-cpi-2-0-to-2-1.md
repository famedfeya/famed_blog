---
layout: post
title: Cisco Wireless - Upgrading Cisco Prime Infrastructure (CPI) 2.0 to 2.1
date: 2014-10-14 19:24
author: tnotez
comments: true
categories: [Cisco Hub, Cisco Prime, Cisco Prime Infrastructure, CPI, CPI v2.0, CPI v2.1]
---
<h2>Situation</h2>

I hate it when Cisco comes up with a feature or new release of the WLC or the APs, and we have to wait forever to get support for MSE, CPI etc!! How are they supposed to function in the meantime??

The issue is that I have the new 3700 APs and now that am running CPI 2.0, I cannot manage or even see them without having to upgrade the CPI.

Anyway, at least I get to play with my toys :)

<h2>Verify version</h2>

We can perform an inline upgrade of CPI from 2.0 to 2.1 without having to do a system migration. System migration is best and recommended because you perform a completely new installation then copy database. I however chose to take advantage of the inline upgrade because it's easier :) and I do not have to copy / re-host licences.

<!--more-->

My current CPI version is 2.0.0.0.294

<a href="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_14_17_20_23_pi_umdcbpcpi01_172-20-74-187_not_connected_securecrt.png"><img class="alignnone size-full wp-image-3125" src="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_14_17_20_23_pi_umdcbpcpi01_172-20-74-187_not_connected_securecrt.png" alt="2014_10_14_17_20_23_PI_UMDCBPCPI01_172.20.74.187_not_connected_SecureCRT" width="525" height="221" /></a>

For this version, I do not need to install any patches and can go straight ahead with upgrading the system.

<h2>Download the upgrade file</h2>

The upgrade file is referred to as <b class="cBold">PI-upgrade-bundle-2.1.0.0.87.tar.gz </b>and can be downloaded from Cisco website

<a href="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_14_17_24_58_cisco_systems.png"><img class="alignnone size-full wp-image-3126" src="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_14_17_24_58_cisco_systems.png" alt="2014_10_14_17_24_58_Cisco_Systems" width="660" height="349" /></a>

Download the file and copy it to the ftp server or tftp (whatever you prefer)

Make sure that you read the <a href="http://www.cisco.com/c/en/us/td/docs/net_mgmt/prime/infrastructure/2-1/release/notes/cpi_rn.html" target="_blank">Release guide for 2.1</a> before going ahead with the upgrade.

<h2 class="title-page">Release Notes Highlights</h2>

Verify that all your wireless equipment is supported in the <a href="http://www.cisco.com/c/en/us/support/cloud-systems-management/prime-infrastructure/products-device-support-tables-list.html" target="_blank">compatibility information</a>

<ol>
    <li>Prime Infrastructure 2.1 enables you to manage Cisco WLC Releases 7.5.102.0 and 7.6.100.0 with the features of Cisco WLC 7.4.121.0 and earlier releases. Prime Infrastructure 2.1 does not support any features that are introduced in Cisco WLC Releases 7.5.102.0 and 7.6.100.0 except the new access point platforms and the new mobility feature.</li>
    <li>The administrator should perform a “Refresh Config from Controller” or “Sync” operation for each of the network devices in Prime Infrastructure after the devices are upgraded (or the version is changed). Similarly, the administrator should perform a “Refresh Config from Controller” or “Sync” operation for each network device in Prime Infrastructure after the Prime Infrastructure server is upgraded from one release to another. These operations should be performed so that Prime Infrastructure can discover all the new features.</li>
    <li>If your browser prompts you to save your password, make sure click no and do not allow the browser to save any passwords. If necessary, disable the password save option in your browser.</li>
</ol>

<h2>Upgrade process</h2>

<ol>
    <li>Make sure that HA is not running. Mine  was not configured.</li>
    <li>Copy the upgrade file to the default repository.<a href="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_14_17_59_49_10-44-6-200_securecrt.png"><img class="alignnone size-full wp-image-3127" src="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_14_17_59_49_10-44-6-200_securecrt.png" alt="2014_10_14_17_59_49_10.44.6.200_SecureCRT" width="660" height="44" /></a></li>
    <li>Stop the Prime Infrastructure server<a href="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_14_18_05_12_10-44-6-200_securecrt.png"><img class="alignnone size-full wp-image-3128" src="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_14_18_05_12_10-44-6-200_securecrt.png" alt="2014_10_14_18_05_12_10.44.6.200_SecureCRT" width="530" height="207" /></a></li>
    <li>Start upgrade. This took about 20 - 30 minutes. <a href="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_14_18_09_10_10-44-6-200_securecrt.png"><img class="alignnone size-full wp-image-3129" src="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_14_18_09_10_10-44-6-200_securecrt.png" alt="2014_10_14_18_09_10_10.44.6.200_SecureCRT" width="660" height="138" /></a><a href="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_14_18_10_55_10-44-6-200_securecrt.png"><img class="alignnone size-full wp-image-3130" src="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_14_18_10_55_10-44-6-200_securecrt.png" alt="2014_10_14_18_10_55_10.44.6.200_SecureCRT" width="660" height="169" /></a><a href="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_14_18_32_21_10-44-6-200_securecrt.png"><img class="alignnone size-full wp-image-3131" src="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_14_18_32_21_10-44-6-200_securecrt.png" alt="2014_10_14_18_32_21_10.44.6.200_SecureCRT" width="660" height="325" /></a></li>
    <li>At this point, the CPI is expected to reboot. <img class="alignnone size-full wp-image-3132" src="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_14_18_35_47_10-44-6-200_securecrt.png" alt="2014_10_14_18_35_47_10.44.6.200_SecureCRT" width="660" height="113" /></li>
    <li>Verify that application is running . Start-up takes a few minutes so be patient. I actually had to manually start ncs.<a href="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_14_19_09_18_10-44-6-200_securecrt.png"><img class="alignnone size-full wp-image-3135" src="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_14_19_09_18_10-44-6-200_securecrt.png" alt="2014_10_14_19_09_18_10.44.6.200_SecureCRT" width="545" height="304" /></a></li>
    <li>Verify the version has been upgraded <a href="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_15_12_21_23_10-44-6-200_securecrt.png"><img class="alignnone size-full wp-image-3168" src="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_15_12_21_23_10-44-6-200_securecrt.png" alt="2014_10_15_12_21_23_10.44.6.200_SecureCRT" width="498" height="225" /></a></li>
    <li>clear the browser cache on all client machines that accessed an older version of Prime Infrastructure before accessing new server</li>
    <li>The  CPI has finally been upgraded.  <a href="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_14_19_10_51_cisco_prime_infrastructure_login_10-44-6-200.png"><img class="alignnone size-full wp-image-3137" src="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_14_19_10_51_cisco_prime_infrastructure_login_10-44-6-200.png" alt="2014_10_14_19_10_51_Cisco_Prime_Infrastructure_Login_10.44.6.200" width="590" height="422" /></a></li>
    <li>
<p class="p_H_Head2">Re-synchronize WLC Configurations<a href="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_14_19_18_11_cisco_prime_infrastructure_configure_controllers_10-44-6-200.png"><img class="alignnone size-full wp-image-3138" src="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_14_19_18_11_cisco_prime_infrastructure_configure_controllers_10-44-6-200.png" alt="2014_10_14_19_18_11_Cisco_Prime_Infrastructure_Configure_Controllers_10.44.6.200" width="660" height="123" /></a>  <a href="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_14_19_16_34_cisco_prime_infrastructure_configure_controllers_10-44-6-200.png"><img class="alignnone size-full wp-image-3140" src="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_14_19_16_34_cisco_prime_infrastructure_configure_controllers_10-44-6-200.png" alt="2014_10_14_19_16_34_Cisco_Prime_Infrastructure_Configure_Controllers_10.44.6.200" width="660" height="293" /><img class="alignnone size-full wp-image-3141" src="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_14_19_16_47_cisco_prime_infrastructure_configure_controllers_10-44-6-200.png" alt="2014_10_14_19_16_47_Cisco_Prime_Infrastructure_Configure_Controllers_10.44.6.200" width="660" height="251" /></a> <img class="alignnone size-full wp-image-3139" src="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_14_19_17_41_cisco_prime_infrastructure_configure_controllers_10-44-6-200.png" alt="2014_10_14_19_17_41_Cisco_Prime_Infrastructure_Configure_Controllers_10.44.6.200" width="486" height="221" /></p>
</li>
    <li>Verify that the APs are now visible <a href="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_14_19_23_26_cisco_prime_infrastructure_device_workcenter_10-44-6-200.png"><img class="alignnone size-full wp-image-3142" src="https://littlenerdsdiary.files.wordpress.com/2014/10/2014_10_14_19_23_26_cisco_prime_infrastructure_device_workcenter_10-44-6-200.png" alt="2014_10_14_19_23_26_CISCO_Prime_Infrastructure_Device_Workcenter_10.44.6.200" width="660" height="11" /></a></li>
</ol>

I hope you find this post helpful. Cheers!

<h2>Reference:</h2>

<ol>
    <li>
<p class="title-page">Cisco Prime Infrastructure 2.1 Quick Start Guide</p>
</li>
    <li><a href="http://www.cisco.com/c/dam/en/us/td/docs/net_mgmt/prime/infrastructure/2-1/supported/devices/pi21-supported-devices-list.xlsx" target="_blank">Cisco Prime Infrastructure 2.1 Supported Devices</a></li>
    <li>
<p class="title-page">Cisco Prime Infrastructure 2.1 Release Notes</p>
</li>
</ol>
