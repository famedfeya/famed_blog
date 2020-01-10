---
layout: post
title: CCNP Wireless CUWSS 642-732 Summary Notes 7 -  Survey Models
date: 2014-11-10 08:17
author: tnotez
comments: true
categories: [642-732, APs, CCNP Wireless, CCNP Wireless Summary Notes, Cisco, CUWSS, omnidirectional antennas, RSSI]
---
<h2>Data Only Coverage</h2>

<ul>
    <li>Does not require a large amount of overlap due to rate shifting; generally 5 to 10 percent, with 10 - 15  % overlap between the cells</li>
    <li>Separation of access points is typically 120 to 130 feet ( 37 to 40 m)</li>
    <li>2.4 band 802.11b/g propagates through floors. The 5-GHz waveform of 802.11a has approximately half the tendency for a given power to transmit suitable amounts of energy through walls because of its higher frequency. avoid overlapping cells on adjacent floors too.</li>
    <li>All the client devices using 5 GHz must have the hardware support for all 23 channels before RRM should be allowed to configure all 23 channels. (this feature can be disabled for the 5GHz band)</li>
    <li>If no legacy clients then 1-Mbps and 2-Mbps data rates should be turned off</li>
</ul>

<!--more-->

<ul>
    <li>If no 802.11b clients are expected, turn the 802.11b rates off</li>
    <li>If there is a need to support 802.11b, then enable only 11 Mb/s</li>
    <li>For an 802.11g/a high-density design, it is recommended that you set 12 Mb/s as the minimum data rate. The lowest configured required rate is the rate that beacons will
be sent. Clients will tend to gravitate over time to this rate as well. The slower the data rate, the higher the channel usage will be. Slower rates require more time in the channel to transmit.</li>
    <li>Use channels 1.6.11 (1,5,13 for ETSI domain)</li>
    <li>Prefer use of 802.11a especially in high density deployment areas because it has more non overlapping channels.</li>
    <li>When deciding the thresholds for the cell edge, consider not only the RSSI but also the signal-to-noise ratio (SNR), because the noise  floor may impact the throughput</li>
    <li>For RSSI, check the min and max then determine the average. Use average value</li>
    <li>During Survey
<ul>
    <li>Reduce power level of AP to half the expected client maximum power value</li>
    <li>Test the cells with static power level (Do not enable DTPC - Dynamic Transmit Power Control which allows the AP to dynamically adjust the client power level</li>
    <li>Test using antenna that will be used in the final deployment</li>
    <li>For omnidirectional antennas, set AP mode to Diversity - both 2.4 and 5 GHz band</li>
    <li>Monitor packet loss rate</li>
    <li>Cisco recommends that you take a 10-dB margin during the survey when testing in the RSSI range for expected speeds.</li>
</ul>
</li>
</ul>

<ul>
    <li>Enable  DTPC - Dynamic Transmit Power Control. This ensures that excessive power is not used which would add unnecessary interference to the radiating area. Client devices using DTPC receive the information and adjust their settings automatically. This setting prevents one-way audio when RF traffic is heard in
only one direction. Both the 2.4- and 5-GHz radios of the access point advertise a transmit power value in the 802.11 beacon and probe responses. Generally, the advertised transmit power is the current transmit power of the access point radio.</li>
    <li>Reduce the power during the survey to a maximum of 20 mW to ensure that RRM
works properly once it is deployed. In an environment where there are a high number of client devices in a small coverage area, high transmit powers work against channel efficiencies. Higher power increases the collision domain of channels. Increasing the collision domain increases co-channel interference and decreases channel efficiency.</li>
</ul>

<h2>Voice over WLAN (VoWLAN) Coverage</h2>

<ul>
    <li>Some voice devices required the wired and wireless network to support multicast</li>
    <li>Plan for cell edges set to –65-dBm (Vocera Communications Badges)  to –67-dBm RSSI and 25-dB SNR. -67 provides for a packet error of 1 percent, which requires an SNR value of 25 dB (92-dBm noise level) with a –67 dBm signal being maintained. The cell edge for the Cisco Unified Wireless IP Phone 7921G at the 11-Mb/s data rate is –67 dBm.</li>
    <li>Separation between adjacent AP channels should be –86 dBm if you are using a Cisco Unified Wireless IP Phone 7921G</li>
    <li>Design WLAN for 24 Mb/s; 36 to 54 Mb/s can optionally be enabled</li>
    <li>Plan for 20% cell overlap which minimizes the amount of data rate shifting, retransmissions, and scanning needs at a cell boundary. The area of overlap between two circles of radius equaling 1 is given by</li>
</ul>

<blockquote>X=d2 / 2d
<p style="padding-left:30px;">where: X is the distance between the centers of each circle</p>
<p style="padding-left:30px;">For 20 % ( X = 1.374 for a standard radius of 1)</p>
<p style="padding-left:30px;">For 10% (X = 1.611)</p>
<p style="padding-left:30px;">For 15 percent (X = 1.486)</p>
<p style="padding-left:30px;">For 25 percent (X = 1.269)</p>
<p style="padding-left:30px;">For 30 percent (X = 1.198).</p>
</blockquote>

<ul>
    <li>Use 40 mW (16dBm) maximum power or 25 mW or less recommended. the planning needs to consider that if an access point is going to increase its power level to adjust for a hole, clients also need to increase their power to adjust for a hole. Auto-RF on Cisco Wireless networks helps AP detect if WLAN clients are experiencing poor signal-to-noise ratio (SNR) values and increase the power of the access point as needed to rectify SNR issues.</li>
    <li>Using a standard antenna gain of 2 dB and an access point output power of 16 dBm (40 mW), the RF environment would give an access point a client radius of 43 feet (13 m) as well as a co-channel interference radius of 150 feet (46 meters)</li>
    <li>Final packet error rate should be &lt;%</li>
    <li>Cells on same channel should be 19dBm apart at an 11-Mb/s data rate. Keeping the separation at 19 dBm between same-channel cells produces a cell with minimal throughput degradation because of media contention.</li>
    <li>The 802.11b/g protocol also defines that channel separation should be 30 dB. Use channels 1, 6, and 11 (even in the ETSI domain) for the 2.4 band. In Japan Channel 14 can be used additionally as non overlapping.</li>
    <li>Prefer 5 GHz band because it suffers from less interference and has a higher channel capacity (23)</li>
    <li>UNII-2 and UNII-2 extended require 802.11h support and should be avoided in areas where airport radar blasts may be an issue. In such areas, use only UNII-1 and UNII-3 band (radar blasts never occur here) because they do not have DFS and TPC requirements (channels 36,40,44,48,149,153,157,161 and 165). Take note that some clients may not support some channels.</li>
    <li>Max power on AP for UNII-1 should be 14 dBm and for UNII 3 - 20 dBm. The recommended power setting for access points when you design voice networks is 25 mW (14 dBm). If you are using UNII-1 channels, 12 mW (11 dBm) would be more appropriate to ensure that RRM still has the ability to boost power, if it becomes necessary.</li>
    <li>Prefer using fewer channels to avoid risking sudden AP channel changes.</li>
    <li>You should set the minimum data rate to 11 or 12 Mb/s for the 2.4-GHz band (dependent upon 802.11b client support policy) and 12 Mb/s for the 5-GHz band, which should also be the only rate configured as a basic rate.</li>
    <li>EnableDTPC. IftheaccesspointdoesnotsupportDTPC, then manually set the transmit power on the phone to match the highest transmit power of an access point in the WLAN. Clients like VoceraandPloycomSpectraLinkdonotsupportDTPC.
<ul>
    <li>If using autonomous APs, set the client power to 20 mW or 25 mW and the AP Tx power to the power nearest to 20 mW or 25 mW. Do not default settings to max on AP or DTPC will not function. In the beacons and probe responses, the autonomous APs advertise the Tx power set in the client Tx power field.</li>
    <li>If using lightweight APs, set the AP Tx power to the power nearest to 20 mW or 25 mW. In the beacons and probe responses, the lightweight APs advertise the current Tx power of the AP.</li>
    <li>Cisco recommends that the 5-GHz power level set on the access point matches the highest power level of the phone client.</li>
</ul>
</li>
    <li>The 5-GHz Cisco phone has a receive sensitivity of 18 Mb/s that is equal to the receive sensitivity of the Cisco Unified Wireless IP Phone 792x at 11 Mb/s.</li>
    <li>For 802.11g or 802.11a
<ul>
    <li>in 2.4 band, disable all rates below 12 Mbps. Set 12 Mbps as the only Mandatory rate and all the above as supported. <a href="https://littlenerdsdiary.files.wordpress.com/2014/11/2014_11_27_22_31_23_nmdcbpwlc100.png"><img class="alignnone size-full wp-image-3525" src="https://littlenerdsdiary.files.wordpress.com/2014/11/2014_11_27_22_31_23_nmdcbpwlc100.png" alt="2014_11_27_22_31_23_NMDCBPWLC100" width="628" height="332" /></a><a href="https://littlenerdsdiary.files.wordpress.com/2014/11/2014_11_27_22_33_59_nmdcbpwlc100.png"><img class="alignnone size-full wp-image-3526" src="https://littlenerdsdiary.files.wordpress.com/2014/11/2014_11_27_22_33_59_nmdcbpwlc100.png" alt="2014_11_27_22_33_59_NMDCBPWLC100" width="590" height="315" /></a></li>
    <li>Plan for 20 concurrent calls in 802.11a and 15 in 802.11g (7 - 8 calls in 802.11b). In ideal situations, Cisco AP can support up to 27 bidirectional Real-Time Transport Protocol (RTP) streams at 24 Mbps (13 streams at 6 Mbps).</li>
</ul>
</li>
    <li>For 802.11b
<ul>
    <li>If 802.11b clients exist, disable data rates of 1, 2, 5.5, 6, and 9 Mb/s. Basic (required ) data rate is 11 Mb/s<a href="https://littlenerdsdiary.files.wordpress.com/2014/11/2014_11_27_22_43_48_cuwss_v1-0_student_guide_vol2-pdf_adobe_reader.png"><img class="alignnone size-full wp-image-3527" src="https://littlenerdsdiary.files.wordpress.com/2014/11/2014_11_27_22_43_48_cuwss_v1-0_student_guide_vol2-pdf_adobe_reader.png" alt="2014_11_27_22_43_48_CUWSS_v1.0_Student_Guide_Vol2.pdf_Adobe_Reader" width="596" height="141" /></a></li>
</ul>
</li>
    <li>Set only the lowest data rate as the single basic rate for multicast traffic</li>
    <li>Call Capacity:
<ul>
    <li>802.11a and 802.11g can support up to 27 bidirectional RTP
streams at 24 Mb/s. To achieve this capacity, you must use unscheduled automatic power-save delivery (U-APSD) and have
minimal WLAN background traffic and RF utilization.</li>
    <li>13 bidirectional RTP streams can be supported at 6 Mb/s. Using U-APSD instead of power save poll (PS-Poll) provides higher call capacity because UAPSD is more efficient and has limited management overhead.</li>
</ul>
</li>
    <li>It is recommended that you set the minimum data rate to 11 Mb/s for 2.4 GHz and 6 Mb/s for 5 GHz, which should also be the only rate configured as a basic rate.</li>
    <li>During Survey
<ul>
    <li>plan to use two or three access points to measure cell coverage and cell overlap.</li>
    <li>Set Call Admission Control (CAC) on AP to limit percentage of the AP bandwidth allowed for voice/video . When enabled for voice, the default reserved bandwidth is 75 percent of the AP available bandwidth (6% for incoming roaming users, leaving 69% for voice users - rather high). No default value is set for Video. Need to decide the value based on the application that will be used. Voice + video bandwidth reservation should never exceed 85 percent</li>
    <li>Test using antenna that will be used in the final deployment</li>
    <li>For omnidirectional antennas, set AP mode to Diversity - both 2.4 and 5 GHz band</li>
    <li>Reduce power level of AP to half the expected VoWLAN client maximum power value of the corresponding band</li>
</ul>
</li>
</ul>

<h2>Video Tablet Coverage (BYOD Coverage)</h2>

<ul>
    <li>iPad -  supports 802.11n with one spatial stream (single antenna) and operates in 2.4-GHz and 5-GHz spectrums using 20-MHz channels.</li>
    <li>Cisco Cius - supports 802.11n with one spatial stream (single antenna) and operates in the 2.4-GHz spectrum using 20-MHz channels and the 5-GHz spectrum using 20-MHz or 40-MHz channels.</li>
    <li>iPhone 4 supports 802.11n with one spatial stream and operates in only the 2.4-GHz spectrum using 20-MHz channels.</li>
</ul>

<h2>location Services Coverage</h2>

<ul>
    <li>APs should be positioned not only in the interior but also at the edge of the area that needs monitoring. Access points should be placed in such a way that they surround the devices that they are tracking.Convex hull provides for 10 meters at 90 percent accuracy within hull.<a href="https://littlenerdsdiary.files.wordpress.com/2014/09/2014-11-11-06_57_25-cuwss-v1-0-student-guide_vol1-pdf-adobe-reader.png"><img class="alignnone  wp-image-3430" src="https://littlenerdsdiary.files.wordpress.com/2014/09/2014-11-11-06_57_25-cuwss-v1-0-student-guide_vol1-pdf-adobe-reader.png" alt="2014-11-11 06_57_25-CUWSS v1.0 Student Guide_Vol1.pdf - Adobe Reader" width="235" height="225" /></a><a href="https://littlenerdsdiary.files.wordpress.com/2014/11/2014_11_29_13_07_50_cuwss_v1-0_student_guide_vol2-pdf_adobe_reader.png"><img class="alignnone size-full wp-image-3544" src="https://littlenerdsdiary.files.wordpress.com/2014/11/2014_11_29_13_07_50_cuwss_v1-0_student_guide_vol2-pdf_adobe_reader.png" alt="2014_11_29_13_07_50_CUWSS_v1.0_Student_Guide_Vol2.pdf_Adobe_Reader" width="196" height="226" /></a></li>
    <li>Each point should be surrounded by at least 3APs hearing that point signal at –75 dBm RSSI or better (during survey,target 72 dBm - if it is supporting location-based services only (no data or voice)).</li>
    <li>In an open space, this requirement implies an AP separation of 40 feet to 70 feet (12 m to 21 m). APs should not be too close from one another (28 feet / 9 m or less) - the client signal level is approximately thesameontwoormoreAPs and location loses its accuracy.
<ul>
    <li>Indoors:Usually mounting height is 10 to 15 feet (3 to 4M) but preferred height is 20 feet (6 meters).</li>
    <li>should be placed between 40 to 70 feet (12 to 21 meters apart)</li>
    <li>Access points must have a neighbor access point within 70 feet in three directions to be considered location-ready.</li>
</ul>
</li>
    <li>Antennas should not be too high (20 feet = 6m or higher ), otherwise, the client signal is seen as weak even below the antenna, and there is no clear difference in the client signal when close or far from the AP</li>
    <li>Use only Cisco antennas as Third-party antennas coverage pattern is not known to WCS and not supported for location services</li>
    <li>To optimize the monitoring and location calculation of radio frequency identification (RFID) tags, you can enable location optimized monitor mode (LOMM) on up to four channels within the 2.4-GHz band of an 802.11b/g access point radio. This feature allows you to scan only the
channels on which tags are usually programmed to operate, such as channels 1, 6, and 11. ToconfigureLOMM:
<ul>
    <li>Change AP Mode to Monitor</li>
    <li>disable the access point 802.11b/g/n radio</li>
    <li>enable LOMM on the radio</li>
    <li>choose the channels on which you want to monitor RFID tags.</li>
    <li>Apply changes</li>
    <li>Enable the admin status.</li>
</ul>
</li>
    <li>During Survey
<ul>
    <li>Test using antenna that will be used in the final deployment</li>
    <li>For omnidirectional antennas, set AP mode to Diversity - both 2.4 and 5 GHz band</li>
    <li>View detected RSSI for the client or asset tag using</li>
</ul>
</li>
</ul>

<blockquote>show client detail &lt;mac address&gt;

show rfid detail controller

&nbsp;</blockquote>

<h2>Data, Voice, and Location Coverage</h2>

<ul>
    <li>Best to survey for Voice as it requires more APs for coverage</li>
    <li>use the 5-GHz bands for voice and the 2.4-GHz band for data, legacy voice and location</li>
    <li>Include voice/video-enabled tablets performance requirements in your cell edge RSSI/SNR design</li>
    <li>Use dual-radio APs</li>
    <li>Set the cell edge at –67 dBm for VoWLAN coverage</li>
    <li>reduce the power level on the 2.4-GHz radio to cover that same physical area as with the 5-GHz radio</li>
    <li>Add  additional APs at the edge of the floor, in monitor mode, to cover the location deployment requirements</li>
    <li>Cell overlap should be 20 percent for 802.11b/g/n cells and 15 to 20 percent for 802.11a/n cells.</li>
    <li>To ensure that Radio Resource Management (RRM) works correctly, the access point transmit power should be 25 mW or less.</li>
    <li>When the voice survey is complete, additional monitoring access points can be added to fill in corners and perimeter areas of the floor to ensure that the floor is location-ready.</li>
</ul>

<h2><strong>References:</strong></h2>

<ol>
    <li>CCNP Wireless  (642-732 CUWSS) Quick Reference Guide by Jerome Henry</li>
    <li>IPexpert’s CCNP CUWSS Wireless Voice on Demand (642-731)</li>
    <li>CUWSS Studnet Guide v1.0</li>
</ol>
