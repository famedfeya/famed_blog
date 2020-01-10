---
layout: post
title: CCNP Wireless CUWSS 642-732 Summary Notes 5 - Regulatory Issues
date: 2014-11-04 18:02
author: tnotez
comments: true
categories: [642-732, CCNP Wireless, CCNP Wireless Summary Notes, CUWSS]
---
<h2>Regulatory Domains:</h2>

Several countries use the same regulatory rules, forming regulatory domains. They define such things as power of transmission, antenna gain and frequency used.

<ul>
    <li>A domain - US, Taiwan, Puerto Rico etc - Follow Federal Communication Commision rules</li>
    <li>E domain - Europe, Israel, Mexico, Singapore etc - follow Europe Telecommunication Standard Institute Rules</li>
    <li>Japan - follow Ministry of Communication Rules and  their applications are managed by Telec</li>
</ul>

<!--more-->

<h2>Unlicensed Frequency bands</h2>

<a href="https://littlenerdsdiary.files.wordpress.com/2014/09/2014_10_31_11_22_19_cuwss_v1-0_student_guide_vol1-pdf_adobe_reader.png"><img class="alignnone size-full wp-image-3391" src="https://littlenerdsdiary.files.wordpress.com/2014/09/2014_10_31_11_22_19_cuwss_v1-0_student_guide_vol1-pdf_adobe_reader.png" alt="2014_10_31_11_22_19_CUWSS_v1.0_Student_Guide_Vol1.pdf_Adobe_Reader" width="455" height="235" /></a><a href="https://littlenerdsdiary.files.wordpress.com/2014/09/2014_10_31_11_25_03_cuwss_v1-0_student_guide_vol1-pdf_adobe_reader.png"><img class="alignnone size-full wp-image-3392" src="https://littlenerdsdiary.files.wordpress.com/2014/09/2014_10_31_11_25_03_cuwss_v1-0_student_guide_vol1-pdf_adobe_reader.png" alt="2014_10_31_11_25_03_CUWSS_v1.0_Student_Guide_Vol1.pdf_Adobe_Reader" width="564" height="301" /></a>

<h2>2.4 Band Rules</h2>

Defined by ITC-R as an Industrial, Medical and Scientific band (IMS).

An IMS does not require a license to emit signal in this band so long as it complies with the regulations

Most countries limit upper band to 2.4835 GHz, 11 to 13 channels which are 5 MHz apart. Japan allows channel 14 too which is 12 MHZ apart from 13 but this channel is not supported for 802.11g mode.<a href="https://littlenerdsdiary.files.wordpress.com/2014/09/2014_10_31_11_27_10_cuwss_v1-0_student_guide_vol1-pdf_adobe_reader.png"><img class="alignnone size-full wp-image-3393" src="https://littlenerdsdiary.files.wordpress.com/2014/09/2014_10_31_11_27_10_cuwss_v1-0_student_guide_vol1-pdf_adobe_reader.png" alt="2014_10_31_11_27_10_CUWSS_v1.0_Student_Guide_Vol1.pdf_Adobe_Reader" width="435" height="275" /></a>

For Mexico, channels 1 through 8 are for indoor use only, while channels 9 through 11 can be used indoors and outdoors.

Spectrum Masks use dare DSSS and OFDM

<ul>
    <li>DSSS signals are 22MHz wide
<ul>
    <li>Initially supported datarates of 1 - 2 Mbps</li>
    <li>Added CCK to support 5.5 and 11 Mbps</li>
</ul>
</li>
    <li>OFDM signals are 20 MHz wide</li>
    <li>Both have 5 MHz channel overlap</li>
</ul>

Adjacent and non overlapping channels:

<ul>
    <li>IEEEdefination: 25 MHz apart or 30 dB attenuation between channels. From this we have 2 interpretations:
<ul>
    <li>FCC used the 25 MHz defination to determine only channel 1, 6 11 as non overlapping. To use channel 12 and 13, the signal must be 50 dB weaker than signal on channel 11</li>
    <li>ETSI used the 30 dB isolation to determine non overlapping as 1,5,9,13 when indoors. Channel separation is 20 Mhz like in OFDM network. Channels 1,6 and 11 have higher noise. For compatibility, ETSI also can use 1,6 11 channels.</li>
</ul>
</li>
</ul>

Adjacent channels are next non overlapping channel in number like 1 and 6. Overlapping channels are 1 and 2

Alternate adjacent channels are 40 MHz apart from the main channel (channel 1  and 9)

<ul>
    <li>FCC and Industry, Science and Technology Canada (ISTC) rules:
<ul>
    <li>Each vendor should use proprietary connectors. Cisco APs use the reverse-polarity threaded Neill-Concelman connector (RP-TNC) connectors.</li>
    <li>any removable antenna had to use a unique, nonstandard connector that is not available through general distribution channels</li>
    <li>You can use an amplifier only if allowed for intended equipment</li>
    <li>max EIRP effective Isotropic radiated power for point to multipoint links is 36 dBm with a 30 dBm max transmitter and 6 dBi antenna. Ratio between transmitter power and antenna gain/ cable loss is 1:1, if you increase/decrease the power you can decrease/increase the gain by same number.</li>
    <li>max EIRP effective Isotropic radiated power for point to point links is 36 dBm with a 30 dBm max transmitter and 6 dBi antenna. Ratio between transmitter power and antenna gain/ cable loss is 1:3, if you increase/decrease the power you can decrease/increase the gain by 3</li>
    <li>Highest gain antenna approved for Cisco is . 21dBi parabolic gain dish antenna.</li>
    <li>the FCC requires owners to register certain antenna structures (generally those more than 200 feet in height or located near an airport) with the FCC.</li>
</ul>
</li>
    <li>ETSI rules (France, Singapore, Israel, MexicoandotherETSI countries)
<ul>
    <li>Effective radiated power - This is the total power of the transmitter. max EIRP effective Isotropic radiated power is 20 dBm with a 17 dBm max transmitter and 3 dBi antenna for both point to point and point to multipoint. Ratio between transmitter power and antenna gain/ cable loss is 1:1 for both link types.<a href="https://littlenerdsdiary.files.wordpress.com/2014/09/2014-11-05-07_54_37-cuwss-v1-0-student-guide_vol1-pdf-adobe-reader.png"><img class="alignnone size-full wp-image-3396" src="https://littlenerdsdiary.files.wordpress.com/2014/09/2014-11-05-07_54_37-cuwss-v1-0-student-guide_vol1-pdf-adobe-reader.png" alt="2014-11-05 07_54_37-CUWSS v1.0 Student Guide_Vol1.pdf - Adobe Reader" width="502" height="186" /></a></li>
</ul>
</li>
</ul>

<h2>5 GHz band Rules</h2>

Rules in this band are more complex.<a href="https://littlenerdsdiary.files.wordpress.com/2014/09/2014-11-05-08_15_35-cuwss-v1-0-student-guide_vol1-pdf-adobe-reader.png"><img class="alignnone size-full wp-image-3397" src="https://littlenerdsdiary.files.wordpress.com/2014/09/2014-11-05-08_15_35-cuwss-v1-0-student-guide_vol1-pdf-adobe-reader.png" alt="2014-11-05 08_15_35-CUWSS v1.0 Student Guide_Vol1.pdf - Adobe Reader" width="628" height="381" /></a>

Band is dividedinto4subbands with a totalof23nonoverlapping channels:

<ul>
    <li>UNII-1 (band 1)</li>
    <li>UNII-2 (band 2) - intended for wireless bridging for both indoor and short-range outdoor applications. The EIRP allowed in the UNII-2 band is 1 watts (30 dBm)</li>
    <li>UNII-2 extended (band 3). The EIRP allowed in the UNII-2 band is 1 watts (30 dBm)</li>
    <li>UNII-3 (band 4) - with far greater transmission power and antenna gain
allowances, is preferable for long-range outdoor wireless bridging. The EIRP allowed in the UNII-3 band is 4 watts (36 dBm)</li>
</ul>

Depending on the country, some subbands are allowed whereas others are not.

<ul>
    <li>5-GHz EIRP Output Rules - For a multipoint transmitter, the EIRP is 36 dBm; for a point-to-point transmitter the EIRP is 53 dBm</li>
    <li>For 802.11a
<ul>
    <li>All channels are non overlapping (20 MHz apart). Uses only OFDM. Recommended not to use adjacent channels to avoid overlap.</li>
</ul>
</li>
    <li>From 5.725 to 5.875 GHz range, there are 5 non overlapping channels defined by the ISM but IEEE partly allows this band by allowing the first 4 channels but not the last</li>
    <li>FCC allows all channels indoors (23 non overlapping) but only band 2 - 4 outdoors.</li>
    <li>ETSI allows band 1 - 3 indoors (19 nonoverlapping) but only band 3 outdoors.</li>
    <li>FCC expreses power limitations in transmitter max power values with  a default antenna, but ETSI still expects and antenna.</li>
    <li>802.11h forband 2 and 3. Derives Dynamic Frequency Selection (DFS) and Transmit Power Control (TPC). band 2 and 3 should comply with the 802.11h amendment because clients get disconnected when the two algorithms are being calculated.
<ul>
    <li>DFS - when Radar is detected, they shutdown the radar then wait, if it continues, then they change the channel.</li>
    <li>TPC APs can dynamically control power for clients in a given range.</li>
</ul>
</li>
</ul>

<a href="https://littlenerdsdiary.files.wordpress.com/2014/09/2014_09_02_07_52_04_172-20-0-113_remote_desktop_connection1.png"><img class="alignnone size-full wp-image-2793" src="http://littlenerdsdiary.files.wordpress.com/2014/09/2014_09_02_07_52_04_172-20-0-113_remote_desktop_connection1.png" alt="2014_09_02_07_52_04_172.20.0.113_Remote_Desktop_Connection" width="660" height="168" /></a>

<ul>
    <li> The cells should be as small as possible for higher throughput.</li>
    <li>Disable speeds lower than 24 Mbps</li>
    <li>For Voice:
<ul>
    <li>voice needs lower throughput</li>
    <li>Video needs higher throughput</li>
    <li>Video can be sent both unicast and multicast</li>
</ul>
</li>
</ul>

The highest approved antenna for Cisco antennas in the 5-GHz band is 28 dBi.

<h2>802.11y -2008</h2>

<ul>
    <li>Licenced band was allowed from 3.65 GHz to 3.7 GHz</li>
    <li>wireless ISPs pay a fee to use the band and for ever high powered AP they put up. Clients connecting to the base station need not pay a fee but need to be authorized by power base stations (dependent Stations Enablement) to avoid oversubscriptions.</li>
</ul>

<h2>Other Rules</h2>

<ul>
    <li>FCC
<ul>
    <li>For indoors:
<ul>
    <li>FCC Title 47 Chapter 1 Part 17, if the radio tower is &gt;200 feet high, it needs to be registered by FCC</li>
    <li>If close  to the airport, need to register with Federal Aviation Administration (&lt;20000 feet or 3.05 km)</li>
</ul>
</li>
</ul>
</li>
    <li>When in doubt, design to the weakest link.</li>
</ul>

<h2>Effective Isotropic Radiated Power</h2>

<blockquote>EIRP = access point transmitter power (dBm) - Cable loss (dB) + antenna gain (dBi)</blockquote>

<h2>References:</h2>

<ol>
    <li>CCNP Wireless  (642-732 CUWSS) Quick Reference Guide by Jerome Henry</li>
    <li>CUWSS Student Guide v1.0</li>
</ol>
