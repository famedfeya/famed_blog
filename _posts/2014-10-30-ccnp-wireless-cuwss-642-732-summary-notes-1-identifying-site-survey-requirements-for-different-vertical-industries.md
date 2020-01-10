---
layout: post
title: CCNP Wireless CUWSS 642-732 Summary Notes 1 - Site Survey Requirements for Different Vertical Industries
date: 2014-10-30 09:28
author: tnotez
comments: true
categories: [CCNP Wireless, CUWSS, CWNA]
---
A site survey is a task-by-task process in which the surveyor studies the facility to understand the RF behavior, discovers RF coverage areas, checks for RF interference, and determines the appropriate placement of wireless devices.

<h2>Top considerations:</h2>

<ul>
    <li>Identify Customer Requirements  and his expectations. What type of environment?</li>
    <li>Consider the regulatory issues for that particular site</li>
    <li>Asses the network before deployment</li>
    <li>Consider logistics.</li>
    <li>Consider the models that we will use on the site<!--more--></li>
</ul>

Below are guidelines for different Verticals:

<h2>Manufacturing</h2>

Filled with machinery. High ceilings, moving objects and a lot of interference sources from the machinery. Chain-link fences block and grounds RF signals. 10 to 15 % overlap required to overcome RF Issues. Layer 1 analysis and validation is important. Multipath is a concern especially because of the metal. Also, verify the union regulations to know what can and cannot be done. Omni-directional antennas installed higher than 12.2 meters (40 feet) might cause data collection devices to lose signal.

<h2>Warehousing</h2>

Characterized by a lot of roaming. Nomadic client moves from one location to another and does not require a constant connection vs Roaming client requires a constant connection. Have large coverage areas leading to multipath. Does not require very high throughput. Cell size is more important than data rates. Cell coverage overlap needs to be from 10 to 15 percent. Need to take into account the user density which usually varies according to shipment. Best to use medium sized cells with dual antennas for diversity and best coverage. Medium-gain <span style="font-style:inherit;line-height:1.625;">antennas are generally the best solution. Different types of stock either reflect or absorb the radio frequency. Inventory that reflects an RF signal includes metal and lead-based paint. Inventory that absorbs an RF signal includes water, wood, plants, trees, paper, boxes, non-lead-based paint, pet food, and cat litter. Consider the elements that the AP will be exposed to, whether or not the Warehouse has freezers and hence heating may be necessary, whether it will be possible to mount an antenna and if the fork lifts might interfere with the antennas while they are moving around. If  a new warehouse is to be built, then WLAN needs to be in place before the inventory is received. The inventory storage racks and shelving should be installed before the survey. Survey should be conducted again after inventory has been added.</span>

<h2>Retail</h2>

This is characterized by uneven use of wireless during retail open and off hours. Currently, most data collection devices do not support 802.11a or 802.11n. Newer data collection devices have the ability to rate shift from 54 to 48 to 36 to 24 to 18 to 11 to 5.5 to 2 to 1 Mb/s for 802.11g.11 to 54 Mb/s connections might be sufficient to handle 20 to 30 data collection users. Barcode scanners and tablets are usually used but normally have low network bandwidth requirements. APs should be located away from sources of interference which include:

<ul>
    <li>Inventory items</li>
    <li>2.4-GHz and 5-GHz equipment</li>
    <li>Colocated stores using WLANs and Hotspots</li>
</ul>

<h2>Transportation</h2>

Yagi antennas usually provide good coverage when mounted on poles above the cars, to allow coverage between the cars and also inside the cars. Airport coverage is however more tricky.

<h2>Hospitality</h2>

Are usually multifloor with many rooms. Wireless connection is needed for basic data coverage, data collection. Need to tighten security, and also provide billing. SSID for staff and users should be different to prevent network exploration attempts. The equipment should not be seen. Physical security is important. Ensure data security and WLAN segmentation. In older hotels where the ceilings and walls are hard cap, Cisco Long Reach Ethernet (LRE) can be used by making use of the phone lines for high-speed Ethernet.

<h2>Hotspots</h2>

Usually for web browsing and needs to cater for different device types that use different bands.Effective range 300 to 500 feet (91.44 to 152.4 meters).

<h2>Healthcare</h2>

Need to cater for mobile devices used by staff, hotspots for patients and voice over WLAN. Require dense coverage. Because of the multifloor configuration of many sites, the survey must be thought of as a three-dimensional survey, covering not only the floor on which the access points are mounted but also the floors above and below. Use non overlapping channels as much as possible. X- ray rooms and trauma rooms may have lead lined walls. Elevator shafts may be detrimental to RF signals. Some applications used may require a lot of bandwidth. The hospital's biomedical department must certify that the equipment will not cause life-threatening problems.

<h2>Enterprise Office</h2>

Usually has a very high density of devices and is rich in applications and features. The Small office might not require a site survey. Channels should be selected either with low use or with a signal strength that is adequate but that does not send the signal far outside the required coverage area. Lowering the transmit (Tx) power to just what is needed to provide coverage inside the office area makes the network more secure against interference from outside the office.

<h2>Higher Education</h2>

APs should be hidden to avoid destruction. Device placement becomes critical. High number of users. Common practice is to have one dual-radio access point per classroom, which fits a class <span style="font-style:inherit;line-height:1.625;">size of 25 to 30 students.</span>

<h2>Government</h2>

Security is most important. Equipment lists and proper documentation are required when entering foreign countries or government facilities to conduct site survey. Governments might have requirements for APs etc.

<a href="https://littlenerdsdiary.files.wordpress.com/2014/09/2014_10_27_08_17_05_cuwss_v1-0_student_guide_vol1-pdf_adobe_reader.png"><img class="size-full wp-image-3341 aligncenter" src="https://littlenerdsdiary.files.wordpress.com/2014/09/2014_10_27_08_17_05_cuwss_v1-0_student_guide_vol1-pdf_adobe_reader.png" alt="2014_10_27_08_17_05_CUWSS_v1.0_Student_Guide_Vol1.pdf_Adobe_Reader" width="307" height="293" /></a>

<h2>References:</h2>

<ol>
    <li>CCNP Wireless  (642-732 CUWSS) Quick Reference Guide by Jerome Henry</li>
    <li>IPexpert's CCNP CUWSS Wireless Voice on Demand (642-731)</li>
    <li>CUWSS Student Guide v1.0</li>
</ol>
