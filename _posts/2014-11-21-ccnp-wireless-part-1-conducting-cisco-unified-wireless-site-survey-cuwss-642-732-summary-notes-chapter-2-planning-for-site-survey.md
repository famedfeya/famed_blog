---
layout: post
title: CCNP Wireless CUWSS 642-732 Summary Notes 12 :  Planning for Site Survey
date: 2014-11-21 09:22
author: tnotez
comments: true
categories: [642-732, CCNP Wireless, CCNP Wireless Summary Notes, CUWSS]
---
<h2>Kickoff Meeting</h2>

<ul>
    <li>Arrange to meet up with the all the people that will be involved in the project from the sponsors to the IT to the security team.</li>
    <li>This is when you review and finalize the Statement of Work SoW
<ul>
    <li>Reconsile contradicting answers. Verify scope of the mission.</li>
    <li>Explain the expectations</li>
    <li>Let them know what will not be covered.</li>
</ul>
</li>
    <li>Notify the team which type of survey is going to be conducted:
<ul>
    <li>Predictive site survey - using a software tool to estimate the number of APs. usually not very appropriate but is chap and usually used to asses the budget.</li>
    <li>Passive Site Survery - Captures the current state in the RF environment, all the channels etc</li>
    <li>Active site surveys - on one BSSID to determine coverage.</li>
</ul>
</li>
    <li>Notify whether it will be a thorough site survey or sample only.</li>
    <li>Complete the customer questionnaie and especially take contact details prior to site survey.</li>
    <li>Obtain Site and Floor maps for the area to be surveyed.</li>
</ul>

<!--more-->

<h2>Walkthrough</h2>

<ul>
    <li>This is a quick visit to the site to assess:
<ul>
    <li>Verify that the map is up to date, the obstacles on the way, the wall types, any absorbers, the number of clients, the roaming path and scale of the map.</li>
    <li>Verify the RF environment, check the interferennce sources</li>
    <li>Verify the cable distance to the switchbox, port density and availability of PoE switches. Check that port speed is adequate for deployment</li>
    <li>For outdoor deployments, check the line of sight and that the first fresnel zone is at least 60% free from obstacles.</li>
    <li>Check for difficult areas like high ceiling walls, mettalic environment, concrete walls that cannot be drilled, areas with high user density</li>
</ul>
</li>
    <li>Survey speed is usually 8 to 10 APs per day per surveyor.</li>
</ul>

<h2>Select Survey Tools</h2>

<ul>
    <li>Cisco Wireless Control System (WCS) planning mode</li>
    <li>Cisco Spectrum Expert solution is a wifi sensor for laptops that can be used to scan channels for interference sources and locate them. This tool does a layer 1 sweep</li>
    <li>802.11 survey or analysis tool
<ul>
    <li>Spectrum analyzer eg. AirMagnet WiFi Analyzer - you input the map of the place you need to survey, move around ad indicate your position then it comes up with a coverage map of the existing 802.11 network</li>
</ul>
</li>
</ul>

<h3><strong>Right Survey Tools:</strong></h3>

<ul>
    <li>Predictive Survey
<ul>
    <li>AirMagnet</li>
    <li>WCS</li>
</ul>
</li>
    <li>Active Survey
<ul>
    <li>AirMagnet Survey</li>
    <li>Layer 1 Analysis
<ul>
    <li>Cisco Spectrum Expert</li>
    <li>Airmagnet Spectrum Analyzer</li>
</ul>
</li>
</ul>
</li>
</ul>

<h3>Prepare Survey Kit</h3>

<ul>
    <li>Includes the site survey tools</li>
    <li>APs for survey</li>
    <li>Connectors, antennas (If using diversity antennas, carry two of every antenna unless the antenna is especially made to support diversity and contains two antennas)</li>
    <li>Equipment for temporary mounting of the AP
<ul>
    <li>Mounting bracket</li>
    <li>Velcro, Zip ties</li>
    <li>Beam clamps</li>
</ul>
</li>
    <li>Battery for APs and for the laptop</li>
    <li>Measuringdevices
<ul>
    <li>Measuring wheel (for horizontal distances)</li>
    <li>Rope marked in 10-foot or 3-meter increments (for vertical distances)</li>
</ul>
</li>
    <li>Location markers</li>
    <li>Camera to take pictures of the area</li>
    <li>Client devices
<ul>
    <li>laptop with an embedded radio</li>
    <li>device with a CardBus card</li>
</ul>
</li>
    <li>Travel Case</li>
</ul>

<h2>Choosing the hardware</h2>

<ul>
    <li>Noise
<ul>
    <li>Path taken by signal :
<ul>
    <li>Circuit generates signal &gt; Transmitter where the modulator generates electric signal, the amplifier inceases its output power and the filter applies the spectral mask to ensure that the frequency range is within the one described in 802.11 standard &gt; Signal sent to antenna for transmission &gt; received by antenna in the other end &gt; filter, amplifier and demodulator &gt; destination. These electronic components generate what is known as thermal noise that degrades the signal received.</li>
</ul>
</li>
    <li>Modulations used
<ul>
    <li>In order from simplicity to complexity. More complex means that it  takes a smaller amount of noise to make the signal undecipherable therefore re-transmission of bits is usually factored in for statistical redundancy,
<ul>
    <li>binary phase shift keying BPSK - uses 180 degree changes</li>
    <li>Quadrature phase shift keying (QPSK) - uses 90 dergree changes. Output is 00, 01,10 and 11</li>
    <li>Quadrature amplitude modulation (QAM) - where 90-degree wave  angle changes are associated with amplitude changes
<ul>
    <li>16 (16-QAM)</li>
    <li>64 (64-QAM)</li>
</ul>
</li>
    <li>Complementary code keying (CCK) - uses wave sequences (symbols) to represent 4 bits or 8 bits of data</li>
</ul>
</li>
</ul>
</li>
</ul>
</li>
</ul>

<blockquote><img class="alignnone size-full wp-image-2827" src="http://littlenerdsdiary.files.wordpress.com/2014/09/2014_09_03_11_18_42_9780133096491-pdf_secured_adobe_reader.png" alt="2014_09_03_11_18_42_9780133096491.pdf_SECURED_Adobe_Reader" width="700" height="244" /></blockquote>

<ul>
    <li>Tx Performances - Higher power can be used for simpler modulations but lower powers should be used for more complex modulations because higher powers generate more thermal noise. The cell size for higher data rates may therefore be smaller than for lower data rates and this should be taken into consideration. Check the possible power levels for both the APs and the clients to be used.</li>
    <li>Rx Performances - Depending on the distance ofthereceiverfromtheemmitter, the power level of both antennas, the cell conditions and the quality of the receiver, a signal may or may not reach the receiver.
<ul>
    <li>A receiver that is located within the coverage area will receive and read the 802.11 frame including the MAC fields. The whole frame is sent at the same data rate.</li>
    <li>If receiver is out of coverage but still closer, it will not be able to read the frame (MAC) and will not know the length of the frame but it can still read the Layer 1 PHY header that has the data rate that is being used and the frame duration in microseconds for DSSS or length of the frame in bytes in OFDM. The PHY is usually sent at the lowest possible data rate regardless of whether or not that data rate has been disabled on the emitter. The receiver can therefore calculate the probable duration of the frame and this helps avoid collision. The receiver however does not know details like the type of frame (unicast or multicast, the receipient etc etc.</li>
    <li>If the frame is farther on than the second position, then the receiver can neither readtheMACnorthePHY layer but it is still able to detect a signal (energy of the frame should be &gt;20dBm than the receivers minimum sensitivity level (amountofenergyneededtodemodulate a signal).
<ul>
    <li>Good sensitivity means client can read weak signals. The sensitivity level is calculated based on an emitter sending a  signal at 1 mW, or 0 dBm, in a quiet environment (noise floor at –107 dBm). bit error rate (BER, or packet error rate [PER]) should be less than 8 percent.</li>
</ul>
</li>
    <li>At the last positon, the receiver cannot even detect the energy of the signal and may go ahead and send frames causing collisions.</li>
</ul>
</li>
</ul>

<h2></h2>

<h2><strong>References:</strong></h2>

<ol>
    <li>CCNP Wireless  (642-732 CUWSS) Quick Reference Guide by Jerome Henry</li>
    <li>IPexpert’s CCNP CUWSS Wireless Voice on Demand (642-731)</li>
    <li>CUWSS Student Guide 1.0</li>
</ol>
