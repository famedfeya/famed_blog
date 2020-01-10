---
layout: post
title: Cisco Wireless - Troubleshooting Lightweight AP Connectivity Issues 
date: 2014-09-18 11:10
author: tnotez
comments: true
categories: [CAPWAP, Cisco Hub, WLC]
---
I have been having an issue with a Cisco AP 2600 rebooting every time (sometimes after 30 minutes, other times after 1 - 2 hours ). Troubleshooting the error using debugs did not provide any good leads. Opened a Case with Cisco TAC, and they also could not see what the issue was. The only thing that we noticed was the traceback below but TAC informed me that he could not see any bugs for that.<!--more-->

<blockquote>Apr 23 10:24:46.707: %EVT-3-ERR_TRACE: Power Table corruption: Domain
-Traceback= 1450B40z 1815760z 17C0500z 17C07D4z 1B6C934z 1B6CBA0z 1B74714z 1B99BE0z 1AEC348z 1AA4298z 1AB9450z 1AD5824z 132B15Apr 23 10:24:46.907: %EVT-5-CFG: Slot1: tx power level 1</blockquote>

Another person with a similar issue regarding the Cisco 1600 AP and 5700 series controller (mine was the 5500 series) had opened a TAC case too but they could not find the issue. A simple reboot resolved the issue.

I had rebooted the Controller several times since the issue occurred so I was rather reluctant in doing it again know that it would not help. But, I said, lets just try that again.

So I reboot the WLC again and guess what, the AP has been up for the last 15 hours!!!

<a href="https://littlenerdsdiary.files.wordpress.com/2014/09/2014_09_18_10_53_43_nldcbpwlc01.png"><img class="alignnone size-full wp-image-2863" src="http://littlenerdsdiary.files.wordpress.com/2014/09/2014_09_18_10_53_43_nldcbpwlc01.png" alt="2014_09_18_10_53_43_NLDCBPWLC01" width="660" height="19" /></a>

I know its too early to be happy, but thats record time. Will monitor it and update you :)

Ps.

Useful debug commands on the controller - these were rather clean in my case

<blockquote>#debug mac &lt;AP - mac:address&gt;
#debug capwap events enable
#debug capwap error enable
#debug capwap detail enable
#debug capwap info enable
#debug dtls all enable</blockquote>

This AP command is the one that helped us catch the traceback

<blockquote>#show evtlog</blockquote>
