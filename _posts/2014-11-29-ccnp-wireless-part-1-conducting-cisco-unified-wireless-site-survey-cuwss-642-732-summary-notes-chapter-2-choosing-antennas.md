---
layout: post
title: CCNP Wireless CUWSS 642-732 Summary Notes 20 - Choosing Antennas
date: 2014-11-29 23:12
author: tnotez
comments: true
categories: [642-732, CCNP Wireless, CCNP Wireless Summary Notes, CUWSS]
---
<h2>Antennas</h2>

Antenna - “an intentional radiator of electromagnetic radiation.

Electromagnetic field - a sine wave that has an electric component and a magnetic field component.

Indoor antennas are always vertically polarized but this is not critical. Polarization plays a role in Outdoor links where a polarization mismatch can reduce the received signal by 20 dBm. Polarization may be an advantage or may be an issue. Advantageous when an outdoor link performance is experiencing interference, shifting the antenna by 90 degrees by rotating or changing polarization type may be enough to mitigate the interference issue.<!--more-->

All antennas should use the same type of polarization.

Frequency (Hertz) - The number of times an entire wave, from an up point to the next up point is repeated in 1 second.

<blockquote>
<p style="padding-left:30px;">Frequency = Speed of light (c) / wavelength (λ).</p>
</blockquote>

Antennas are defined by:

<ul>
    <li>Gain (dBi).
<ul>
    <li>This value is usually obtained by comparing to a theorical antenna (isotropic antenna) that is one point in size and radiates energy in all directions</li>
    <li> This is the amount of energy an antenna radiates in its direction of maximum strength compared to what an isotropic antenna would radiate in the same direction.</li>
    <li>If the value is obtained by using an esisting reference antenna (dipole antenna) then this value will be in (dBd)</li>
</ul>
</li>
</ul>

<blockquote>
<p style="padding-left:30px;">dBi = dBd + 2.14</p>
<p style="padding-left:30px;">dBd = dBi –2.14</p>
</blockquote>

<ul>
    <li>Beamwidth
<ul>
    <li>This is the area where the antenna provides useful beam (zone of maximum useful signal strength.</li>
    <li>This is The angle between the point of maximum strength and the points where the signal strength decrease by 3 dB</li>
</ul>
</li>
    <li>Type
<ul>
    <li>omnidirectional
<ul>
    <li>2 wire system  that connects the transmitter to the shield (dielectric). The wire is 1/4λ long, and radiates at 360 degrees</li>
    <li>Antenna gain is increased by increasing length of wire (by proportions of 1/4λ) which reduces the radiation in the elevation plane but increases it in the horizontal plane, increasing the horizontal gain</li>
    <li>Best when AP will be ceiling mounted.</li>
    <li>When mounted too high, the antennas have a blind spot  just below the antenna and other coverage holes at certain points that are caused by secondary lobes so they need to be tested at low power to detect the holes.</li>
</ul>
</li>
    <li>directional
<ul>
    <li>Uses plates rather than wires. (but Yagi uses rods rather than plates)</li>
    <li>Energy is concentrated in one direction. Depending on the size and number of the plates, and the nature of the dielectric (thickness and other
characteristics), the resulting gain in the main lobe is higher or lower.</li>
    <li>For Yagi Each rod is separated from the previous one by about 1/2λ, which makes that each rod amplifies the signal coming
from the previous one. Yagi's have 6 dBi to 13 dBi .</li>
    <li>Directional Patch antennas
<ul>
    <li>These are usually mounted to the walls</li>
    <li>They have a 5-dBi to 12-dBi gain</li>
    <li>Have wide beamwidths so usually can cover large areas.</li>
</ul>
</li>
    <li>Directional Sector antennas
<ul>
    <li>have a 50 to 120 beamwidth</li>
    <li>Have 8-dBi to 20-dBi gain</li>
    <li>The larger the beamwidth, the lower the gain</li>
    <li>Cover long and narrow areas from high points</li>
</ul>
</li>
    <li>Highly directional antennas
<ul>
    <li>Usually parabolic antennas used for outdoor long-range links</li>
    <li>(1- to 10-degree beamwidth</li>
    <li>up to 28 dBi</li>
</ul>
</li>
</ul>
</li>
</ul>
</li>
</ul>

Radiation pattern - is an illustration of how the energy is radiated from the antenna in the E-Plane of the H-Plane (vertical cut seen from the side and horizontal cut seen from the top).  The direction of maximum field strength (point of reference) -  The point where the radiation pattern line touches  the outer circle. The pattern shows how the energy decreases when turning around the antenna from the same distance from it. The distance ratio between the energy received at the point of maximum strength and the other point is the same.

Antenna bandwidth - range of frequencies for which the antenna is efficient (antenna absorbs the energy at those frequencies and transmits it to the circuit, instead of reflecting the energy) and measured in dB. -20dB is very efficient, 0 dB is not efficient.

<blockquote>
<p style="padding-left:30px;">3 dB = twice the power</p>
</blockquote>

Signal &gt; Cable &gt; Antenna

<blockquote>
<p style="padding-left:30px;">effective isotropic radiated power (EIRP) = Transmitter output power (dBm) – Cable loss (dB) + Antenna gain (dBi).</p>
</blockquote>

Return loss - if connector is not properly attached to the cable, the signal can be transmitted from the cable to the connector and reflected back to the cable.

Orthogonal frequency-division multiplexing (OFDM), used by IEEE 802.11g and 802.11a, helps to mitigate problems with reflections, nulls, and multipath; however, good antenna placement and the use of appropriate antenna types provide a superior solution.

<h3>2.4-GHz Antennas</h3>

<ul>
    <li>2.0-dBi Ceiling Mount Diversity Antenna (AIR-ANT5959)</li>
    <li>2.2-dBi Rubber Dipole Antenna (AIR-ANT4941)</li>
    <li>2.2-dBi Diversity Omnidirectional Ceiling-Mounted Antenna (AIR-ANT3351)</li>
    <li>5.2-dBi Mast-Mounted Antenna (AIR-ANT2506)</li>
    <li>5.2-dBi Omnidirectional Ceiling-Mounted Antenna (AIR-ANT1728)</li>
    <li>5.2-dBi Diversity Omnidirectional Pillar-Mounted Antenna (AIR-ANT3213)</li>
    <li>6.0-dBi Wall Mount Indoor/Outdoor Directional Patch Antenna (AIR-ANT1729)</li>
    <li>6.0-dBi Diversity Patch Wall-Mounted Antenna (AIR-ANT2012)</li>
    <li>8.5-dBi Hemispherical Patch Antenna (AIR-ANT3549)</li>
    <li>10.0-dBi Yagi Mast-Mounted Antenna (AIR-ANT2410Y-R)</li>
    <li>13.5-dBi Yagi Mast-Mounted Antenna (AIR-ANT1949)</li>
</ul>

<h3>5-GHz Antennas</h3>

<ul>
    <li>5-dBi/9-dBi Integrated RM21A Antenna Omnidirectional/Patch</li>
    <li>3.5-dBi Omnidirectional Antenna (AIR-ANT5135D-R)</li>
    <li>4.5-dBi Indoor Only Omnidirectional Mast or Ceiling Mountable (AIR-ANT5145V-R)</li>
    <li>6.0-dBi Indoor/Outdoor Use Omnidirectional Mast or Ceiling Mountable (AIRANT5160V-R)</li>
    <li>7.0-dBi Diversity Patch Indoor/Outdoor Wall Mountable (AIR-ANT5170P-R)</li>
    <li>9.5-dBi Patch Indoor/Outdoor Wall or Articulating Mount Mountable (AIR-ANT5195P-R)</li>
</ul>

<h2>Access Point Antenna Selection</h2>

<ul>
    <li>Cisco recommends a diversity ceiling-mount antenna for voice applications.</li>
    <li>Cisco recommends that all antennas be placed one to two wavelengths from highly reflective surfaces such as metal. The 2.4-GHz wave is 4.92 inches (12.5 cm) and the 5-GHz wave is 2.36 inches (6 cm). The separation of one or more wavelengths between the antenna and reflective surfaces allows the access point radio a better opportunity to receive a transmission, and reduces the creation of nulls when the radiobtransmits.</li>
</ul>

<h2>Connectors</h2>

<ul>
    <li>Has a male and female part which have an outer shell and a central connector. The male's connector is called a jack, whereas the female's - a plug.</li>
    <li>RP - putting a jack in a female shell and a plug in a male shell.</li>
    <li>Most regulatory domains impose the use of nonstandard connectors for antennas and APs, to avoid exceeding the  maximum allowed EIRP eg via Reverse Polarity (RP).</li>
    <li>Each vendor uses a specific connector, with a specific size and polarity
<ul>
    <li>Cisco normally uses the RP-TNC connector ( 8 mm wide for the female end (central jack pin, female outer shell), and 14 mm wide for the male end (central female plug, male outer
shell).</li>
    <li>For outdoor APs, Cisco uses N connectors (It is standard, not RP, and about 2 cm wide for the male part, and 1.2 cm  wide for the female part.)</li>
    <li>For SOHO APs, they mostly use subminiature version A connector variants ( SMAs ). The male end is  approximately 1 cm wide, and the female end is about 6 mm wide</li>
    <li>ForPCNICs we have smaller connector types (a few millimeter  wide) eg
<ul>
    <li>MMCX connectors</li>
    <li>subminiature version B ( SMB )</li>
</ul>
</li>
</ul>
</li>
</ul>

Amplifier - can be added between the AP and antenna to increase signal strength. It's an AC or DC powered device. It also has its own gain that needs to be taken into account when calculating the EIRP. This is used when the signal is too weak

Attenuator - used if the signal is too strong. This is a passive device that absorbs energy and is placed between the antenna and the AP.

Splitter - used mainly outdoors when you need to send the signal from one transmitter to two directional antennas. It basically acts as an attenuator and absorbs energy.

lightning arrestor - Also used outdoors to absorb surrounding static electricity. It is placed between the antenna and the cable. This does not prevent against direct lightning strike to the AP. Non metallic barriers between the AP and the internal network (like 1 meter segment of fiber optic cable with a copper to fiber optic transceiver) can prevent damage to the entire network should lightening strike the AP.

<h2><strong>References:</strong></h2>

<ol>
<li>CCNP Wireless  (642-732 CUWSS) Quick Reference Guide by Jerome Henry</li>
<li>IPexpert’s CCNP CUWSS Wireless Voice on Demand (642-731)</li>
</ol>

&nbsp;
