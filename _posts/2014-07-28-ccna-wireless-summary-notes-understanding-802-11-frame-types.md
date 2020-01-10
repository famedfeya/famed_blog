---
layout: post
title: CCNA Wireless Summary Notes- Understanding 802.11 Frame Types
date: 2014-07-28 19:26
author: tnotez
comments: true
categories: [640-722, CCNA Wireless, CCNA Wireless Summary Notes]
---
Switches do not actively participate in the exchange of frames. The APs however are active participants. a client must join or associate  with a specific wireless network by first getting permission from the AP. Then the client
must send and receive every frame through the AP or coordinate with the AP for direct  client-to-client communication to use 802.11z - Direct Link Setup (DLS). The 802.11 frame has a maximum length of 2346 bytes.<!--more-->

<a href="https://littlenerdsdiary.files.wordpress.com/2014/07/2014_07_28_11_46_52_ccna_wireless_640_722_official_cert_guide_secured_adobe_reader.png"><img class="alignnone size-full wp-image-2766" src="http://littlenerdsdiary.files.wordpress.com/2014/07/2014_07_28_11_46_52_ccna_wireless_640_722_official_cert_guide_secured_adobe_reader.png" alt="2014_07_28_11_46_52_CCNA_Wireless_640_722_Official_Cert_Guide_SECURED_Adobe_Reader" width="584" height="156" /></a>

&nbsp;

To DS and From DS bits can be 1 or 0. Both are set to 0 if:

<ul>
    <li>An AP sends a management or control frame, which is broadcast to all wireless clients in the BSS. The AP, and not the DS, is the source of the frame.</li>
    <li>A client sends a management frame to an AP, such that the AP itself is the destination.</li>
    <li>One client sends a frame directly to another client via DLS. The frame is not destined  for the AP or the DS.</li>
</ul>

Both are set to 1 if:

<ul>
    <li>frames are relayed from  AP to AP over wireless backhaul links. A backhaul link is neither in the BSS nor in the  DS</li>
</ul>

802.11 frame header can contain up to four different  address fields (1 to 4). Each frame header must contain a transmitter address  (TA) and a receiver address (RA). The Address1 field always contains the RA, though its
exact contents may vary depending on where the frame is headed. Likewise, Address2  always contains the TA. Address3 contains the final destination address when the RA is not the final recipient. Likewise, Address3 can contain the  original source address when the TA is not the originator. Address4 does not come into play unless a frame is being transported from one AP to  another AP across a wireless link.

<a href="https://littlenerdsdiary.files.wordpress.com/2014/07/2014_07_28_12_36_30_ccna_wireless_640_722_official_cert_guide_secured_adobe_reader.png"><img class="alignnone size-full wp-image-2767" src="http://littlenerdsdiary.files.wordpress.com/2014/07/2014_07_28_12_36_30_ccna_wireless_640_722_official_cert_guide_secured_adobe_reader.png" alt="2014_07_28_12_36_30_CCNA_Wireless_640_722_Official_Cert_Guide_SECURED_Adobe_Reader" width="577" height="214" /></a>
