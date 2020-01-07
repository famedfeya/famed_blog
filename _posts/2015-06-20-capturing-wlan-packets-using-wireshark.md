---
layout: post
title: Capturing WLAN Packets using WireShark
date: 2015-06-20 13:41
author: tnotez
comments: true
categories: [CCIEv.3 Wireless, CCNP Wireless, Cisco Hub, CWSP]
---
If you are studying for CCNP Wireless or CWNP Certification, an essential part of the study process is actually getting to lab it all out so as to understand the concepts. I noticed that my Wireshark output lacked the 802.11 management or control packets while trying to capture Open System Authentication process. This blog will explain how to set up Wireshark for WLAN Capturing so that you do not miss the vital packet exchanges.
<!--more-->

So far, I have just installed and opened Wireshark. I have done nothing more. Select your WiFi interface that we will use to capture traffic.

<a href="https://littlenerdsdiary.files.wordpress.com/2015/06/2015_06_20_12_09_34_wi_fi_wireshark_1-12-5_v1-12-5_0_g5819e5b_from_master_1-12_.png"><img class="alignnone size-full wp-image-3856" src="https://littlenerdsdiary.files.wordpress.com/2015/06/2015_06_20_12_09_34_wi_fi_wireshark_1-12-5_v1-12-5_0_g5819e5b_from_master_1-12_.png" alt="2015_06_20_12_09_34_Wi_Fi_Wireshark_1.12.5_v1.12.5_0_g5819e5b_from_master_1.12_" width="660" height="254" /></a>

As you can see, the Capture starts from DHCP request process.<a href="https://littlenerdsdiary.files.wordpress.com/2015/06/2015_06_20_12_13_44_capturing_from_wi_fi_wireshark_1-12-5_v1-12-5_0_g5819e5b_from_master_1-12_.png"><img class="alignnone size-full wp-image-3857" src="https://littlenerdsdiary.files.wordpress.com/2015/06/2015_06_20_12_13_44_capturing_from_wi_fi_wireshark_1-12-5_v1-12-5_0_g5819e5b_from_master_1-12_.png" alt="2015_06_20_12_13_44_Capturing_from_Wi_Fi_Wireshark_1.12.5_v1.12.5_0_g5819e5b_from_master_1.12_" width="660" height="143" /></a>

Where are the 802.11 Auth frames? Well, when capturing with Wireshark (or other tools using libpcap/WinPcap) there are two ways in which 802.11 can be supplied by the system and stored in a capture file:

<ul>
    <li>"real" 802.11: the hardware/driver provides the actual protocol data that travels over the air, complete with 802.11 headers.</li>
    <li>"fake" Ethernet:  the hardware/driver translates the 802.11 headers into Ethernet headers so that the whole packet looks like a normal Ethernet packet.</li>
</ul>

We seem to be using Option 2. We see user data packets with fake Ethernet headers. We do not see 802.11-specific management and control frames as they are discarded because there's no equivalent to them in Ethernet

<a href="https://littlenerdsdiary.files.wordpress.com/2015/06/2015_06_20_12_25_59_capturing_from_wi_fi_wireshark_1-12-5_v1-12-5_0_g5819e5b_from_master_1-12_.png"><img class="alignnone size-full wp-image-3858" src="https://littlenerdsdiary.files.wordpress.com/2015/06/2015_06_20_12_25_59_capturing_from_wi_fi_wireshark_1-12-5_v1-12-5_0_g5819e5b_from_master_1-12_.png" alt="2015_06_20_12_25_59_Capturing_from_Wi_Fi_Wireshark_1.12.5_v1.12.5_0_g5819e5b_from_master_1.12_" width="660" height="160" /></a>

To capture the real 802.11 packets and radio layer information, then we have to capture in "monitor mode". We need to disable the translation/filtering and see what's "really" going on inside your WLAN. Then I read: <em><span style="color:#0000ff;">Note that Monitor mode is not supported by <a style="color:#0000ff;" href="https://wiki.wireshark.org/WinPcap">WinPcap</a>, and thus not by Wireshark or TShark, on Windows. It is supported, for at least some interfaces, on some versions of Linux, FreeBSD, NetBSD, OpenBSD, DragonFly</span> BSD, and Mac OS X. </em>Bummer!! Coffee Break. Will be back once I install Ubuntu :)

<h2>Getting Wireshark to work on Ubuntu</h2>

AM BACK with an Ubuntu desktop and ready to Install Wireshark. I must admit that Linux administration is not one of my strengths, but with google, nothing is impossible :).

To install wireshark, simply run the following command:

<blockquote>sudo apt-get install wireshark</blockquote>

<a href="https://littlenerdsdiary.files.wordpress.com/2015/06/screenshot-from-2015-06-20-234721.png"><img class=" size-full wp-image-3865 alignnone" src="https://littlenerdsdiary.files.wordpress.com/2015/06/screenshot-from-2015-06-20-234721.png" alt="Screenshot from 2015-06-20 23:47:21" width="705" height="438" /></a>

After Installation, I opened the application and noticed the error “No interface can be used for capturing in this system with the current configuration.”

<a href="https://littlenerdsdiary.files.wordpress.com/2015/06/screenshot-from-2015-06-20-234958.png"><img class="alignnone size-full wp-image-3866" src="https://littlenerdsdiary.files.wordpress.com/2015/06/screenshot-from-2015-06-20-234958.png" alt="Screenshot from 2015-06-20 23:49:58" width="599" height="272" /></a>

To fix this, simply run the following commands:

<ol>
    <li>Create the wireshark group.</li>
    <li>Add your username to the wireshark group</li>
    <li>Change the group  ownership of file dumpcap to wireshark</li>
    <li>Change the mode of the file dumpcap to allow execution by the group wireshark</li>
    <li>Grant capabilities with setcap</li>
</ol>

<a href="https://littlenerdsdiary.files.wordpress.com/2015/06/screenshot-from-2015-06-20-235241.png"><img class="alignnone wp-image-3867 size-full" src="https://littlenerdsdiary.files.wordpress.com/2015/06/screenshot-from-2015-06-20-235241.png" alt="Screenshot from 2015-06-20 23:52:41" width="705" height="192" /></a>

Verify the change

<a href="https://littlenerdsdiary.files.wordpress.com/2015/06/screenshot-from-2015-06-21-002202.png"><img class="alignnone size-full wp-image-3868" src="https://littlenerdsdiary.files.wordpress.com/2015/06/screenshot-from-2015-06-21-002202.png" alt="Screenshot from 2015-06-21 00:22:02" width="609" height="94" /></a>

<a href="https://littlenerdsdiary.files.wordpress.com/2015/06/screenshot-from-2015-06-21-0051451.png"><img class="alignnone size-full wp-image-3883" src="https://littlenerdsdiary.files.wordpress.com/2015/06/screenshot-from-2015-06-21-0051451.png" alt="Screenshot from 2015-06-21 00:51:45" width="705" height="409" /></a>

Now we are able to capture packets but I still see that Monitor Mode is disabled for WLAN Interface.

<a href="https://littlenerdsdiary.files.wordpress.com/2015/06/screenshot-from-2015-06-21-002910.png"><img class="alignnone size-full wp-image-3869" src="https://littlenerdsdiary.files.wordpress.com/2015/06/screenshot-from-2015-06-21-002910.png" alt="Screenshot from 2015-06-21 00:29:10" width="705" height="263" /></a>

Enable Monitor mode for the wlan interface by double-clicking on it and checking the capture packets in monitor mode box.

<a href="https://littlenerdsdiary.files.wordpress.com/2015/06/screenshot-from-2015-06-21-0037561.png"><img class="alignnone size-full wp-image-3880" src="https://littlenerdsdiary.files.wordpress.com/2015/06/screenshot-from-2015-06-21-0037561.png" alt="Screenshot from 2015-06-21 00:37:56" width="705" height="314" /></a>

Verify that Monitor Mode is now set to enabled.

<a href="https://littlenerdsdiary.files.wordpress.com/2015/06/screenshot-from-2015-06-21-010115.png"><img class="alignnone size-full wp-image-3884" src="https://littlenerdsdiary.files.wordpress.com/2015/06/screenshot-from-2015-06-21-010115.png" alt="Screenshot from 2015-06-21 01:01:15" width="705" height="142" /></a>

<span style="color:#000000;">When you start a capture file, you should be able to see 802.11 protocol packets.
</span>

<a href="https://littlenerdsdiary.files.wordpress.com/2015/06/screenshot-from-2015-06-21-0039051.png"><img class="alignnone size-full wp-image-3882" src="https://littlenerdsdiary.files.wordpress.com/2015/06/screenshot-from-2015-06-21-0039051.png" alt="Screenshot from 2015-06-21 00:39:05" width="705" height="202" /></a>

Now that everything is set, let's get started with the Wireless labs :).

Adios!

<h2>References:</h2>

<ol>
    <li><a href="https://wiki.wireshark.org/Wi-Fi">Wi-Fi (WLAN, IEEE 802.11)</a></li>
    <li><a href="https://wiki.wireshark.org/CaptureSetup/WLAN"><span id="pagelocation"><span class="pagepath">CaptureSetup</span><span class="sep">/</span>WLAN</span></a></li>
    <li><a href="https://ask.wireshark.org/questions/16343/install-wireshark-on-ubuntu">Wireshark on Ubuntu</a></li>
</ol>
