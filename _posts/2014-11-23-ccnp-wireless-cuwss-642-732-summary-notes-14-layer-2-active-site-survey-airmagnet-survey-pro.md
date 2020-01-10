---
layout: post
title: CCNP Wireless CUWSS 642-732 Summary Notes 15 : Attenuation and Data Rates
date: 2014-11-23 20:44
author: tnotez
comments: true
categories: [642-732, CCNP Wireless, CCNP Wireless Summary Notes, CUWSS]
---
<h2>RF Reflectors and Absorbers in the building</h2>

Signal Attenuation

<a href="https://littlenerdsdiary.files.wordpress.com/2014/09/2014_09_22_08_12_38_9780133096491-pdf_secured_adobe_reader.png"><img class="alignnone size-full wp-image-2866" src="http://littlenerdsdiary.files.wordpress.com/2014/09/2014_09_22_08_12_38_9780133096491-pdf_secured_adobe_reader.png" alt="2014_09_22_08_12_38_9780133096491.pdf_SECURED_Adobe_Reader" width="477" height="259" /></a>

<ul>
    <li>Each 3-dB attenuation reduces the signal strength by half</li>
    <li>Moving objects may also affect the signal</li>
    <li>Break rooms and test labs may produce 2.4-GHz iinterference and create multipath distortion and RF shadows.</li>
    <li>Elevator shafts block and reflect RF signals.</li>
    <li>Supply rooms with inventory absorb RF signals.</li>
    <li>Interior offices with hard walls absorb RF signals.</li>
    <li>Cubicles absorb and block signals.</li>
    <li>Conference rooms have high-utilization requirements</li>
</ul>

<!--more-->

Most affected areas are:

<ul>
    <li>Hospitals due to high multipath distortion, signal loss, and signal noise</li>
    <li>Office buildings and hospitality - high signal attenuation but a lesser degree of multipath distortion</li>
</ul>

802.11n MIMO technology makes use of multipath by combining information from all signals received, thereby increasing throughput. This is known as maximal ratio combining (MRC), where multiple received signals are combined to more accurately reconstruct the transmitted signal.

If auto-Radio Resource Management (RRM) is used for a data-only WLAN, you should survey at half power or less to ensure that the RRM can perform coverage hole mitigation.

802.11 clients respond to a lower signal from a nearby access point by stepping down their rate and taking a longer time to transmit.

Any energy in the WLAN spectrum that is not decodable as an 802.11 radio is considered noise. Electrical components have an internal noise, known as thermal noise, that will be present even in a quiet RF environment. The signal-to-noise ratio (SNR) is the ratio (actually the delta) of signal (802.11 radio) to noise (anything that is not an 802.11 radio signal). The SNR is expressed as a value in decibels (dB). The lower the SNR in an environment, the slower the resulting supportable data rate will be.

When performing the survey, you must set parameters and thresholds to identify where the cell edge should be placed.

<ul>
    <li>Minimum SNR</li>
    <li>Minimum signal strength</li>
    <li>Noise floor</li>
    <li>Packet counts, lost packets</li>
    <li>Use packet sizes similar to those for the applications that have the
largest packet size.</li>
    <li>Received Signal Strength Indicator (RSSI)
<ul>
    <li>Usable range typically from –60 to –80 dBm
<ul>
    <li>–55 dBm or greater is exceptional signal strength</li>
    <li>–85 dBm is poor signal strength and association is unlikely</li>
    <li>-–65 dBm for highest data rate supported (recommended)</li>
</ul>
</li>
</ul>
</li>
</ul>

For 2.4 Ghz Data Networks<a href="https://littlenerdsdiary.files.wordpress.com/2014/11/2014-11-23-19_31_33-cuwss-v1-0-student-guide_vol2-pdf-adobe-reader.png"><img class="alignnone size-full wp-image-3511" src="https://littlenerdsdiary.files.wordpress.com/2014/11/2014-11-23-19_31_33-cuwss-v1-0-student-guide_vol2-pdf-adobe-reader.png" alt="2014-11-23 19_31_33-CUWSS v1.0 Student Guide_Vol2.pdf - Adobe Reader" width="628" height="347" /></a>

For 2.4 GHz 802.11n Data networks with 20 MHz Channel Width

<a href="https://littlenerdsdiary.files.wordpress.com/2014/11/2014-11-23-19_37_42-cuwss-v1-0-student-guide_vol2-pdf-adobe-reader.png"><img class="alignnone size-full wp-image-3512" src="https://littlenerdsdiary.files.wordpress.com/2014/11/2014-11-23-19_37_42-cuwss-v1-0-student-guide_vol2-pdf-adobe-reader.png" alt="2014-11-23 19_37_42-CUWSS v1.0 Student Guide_Vol2.pdf - Adobe Reader" width="253" height="208" /></a>

For 5GHz Data Networks

<a href="https://littlenerdsdiary.files.wordpress.com/2014/11/2014-11-23-19_39_02-cuwss-v1-0-student-guide_vol2-pdf-adobe-reader.png"><img class="alignnone size-full wp-image-3513" src="https://littlenerdsdiary.files.wordpress.com/2014/11/2014-11-23-19_39_02-cuwss-v1-0-student-guide_vol2-pdf-adobe-reader.png" alt="2014-11-23 19_39_02-CUWSS v1.0 Student Guide_Vol2.pdf - Adobe Reader" width="409" height="214" /></a>

For 5GHz Data Networks with Channel width of 40 MHz

<a href="https://littlenerdsdiary.files.wordpress.com/2014/11/2014-11-23-19_40_56-cuwss-v1-0-student-guide_vol2-pdf-adobe-reader.png"><img class="alignnone size-full wp-image-3514" src="https://littlenerdsdiary.files.wordpress.com/2014/11/2014-11-23-19_40_56-cuwss-v1-0-student-guide_vol2-pdf-adobe-reader.png" alt="2014-11-23 19_40_56-CUWSS v1.0 Student Guide_Vol2.pdf - Adobe Reader" width="249" height="245" /></a>

For the above rates Minimum packet performance should be greater than 90 percent successful packet transfer (10 percent packet error rate [PER]).

The minimum receive (Rx) threshold indicates the absolute minimum that the receiver can hear and still properly decode the packet. A typical padding of 10 dB is sufficient.

The recommended minimum Rx threshold indicates the value that you should watch for to indicate the edge of reliable coverage.

The SNR rating indicates the minimum ratio between the noise floor and the desired signal level for proper reception of information.

The recommended SNR value provides a 10-dB padding to compensate for variations.

<h2><strong>References:</strong></h2>

<ol>
    <li>CCNP Wireless  (642-732 CUWSS) Quick Reference Guide by Jerome Henry</li>
    <li>IPexpert’s CCNP CUWSS Wireless Voice on Demand (642-731)</li>
    <li>CUWSS Studnet Guide v1.0</li>
</ol>
