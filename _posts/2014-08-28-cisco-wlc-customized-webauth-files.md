---
layout: post
title: Cisco Wireless - Cisco WLC Customized Webauth files
date: 2014-08-28 15:56
author: tnotez
comments: true
categories: [Cisco Hub]
---
Spent the better part of the day trying to get upload webauth files for several SSIDs to our Cisco 5500 Controller but ran into issues. I have since solved these issues, so this is basically a - how to - blogpost.

The error that I kept hitting was this:<!--more-->

<a href="https://littlenerdsdiary.files.wordpress.com/2014/08/2014_08_28_15_09_01_nmdcbpwlc100.png"><img class="alignnone size-full wp-image-2772" src="http://littlenerdsdiary.files.wordpress.com/2014/08/2014_08_28_15_09_01_nmdcbpwlc100.png" alt="2014_08_28_15_09_01_NMDCBPWLC100" width="660" height="257" /></a>

This error basically means that there is something wrong with the tar file that you are trying to  upload.

Points you need to keep in mind are as follows:

<ol>
    <li>The tar file should be less than 1 MB.</li>
    <li>The number of files in the tar is also limited. I however have not established what the limit is. So far I have managed to upload a file with 12 items for 5 different SSIDs.</li>
    <li>The file name for the tar file itself and all items in it should each be less than 30 characters.</li>
</ol>

This is an example of the items that I want in my tar file

<a href="https://littlenerdsdiary.files.wordpress.com/2014/08/2014_08_28_15_21_38_login38.png"><img class="alignnone size-full wp-image-2775" src="http://littlenerdsdiary.files.wordpress.com/2014/08/2014_08_28_15_21_38_login38.png" alt="2014_08_28_15_21_38_login38" width="622" height="281" /></a>

Now that I have all the files, editted with the required information and ready to be packed, the hardest thing is actually getting them tared correctly and ready to be used.

People advise that you can use the following programs.

<p style="padding-left:30px;">Picozip</p>

<p style="padding-left:30px;">7Zip</p>

<p style="padding-left:30px;">PowerArchiver 2010 for Windows (GUI)</p>

Truth be told, none of them worked for me. I think you should not waste your time on that, just get a virtual machine with Unix and you are set. That's what worked for me. Error one down, 2 to go.

Next issue that I ran into was that even though my files were created in Unix, I still got the same error. This is because I did not have root access to the Linux server. The Server admin had created a folder for me so the files that I created did not have the root UDI and GDI described in this Support thread. <a title="WebAuth Bundle tar error " href="https://supportforums.cisco.com/discussion/11038511/wlc-5508-webauth-bundle-tar-error-256">https://supportforums.cisco.com/discussion/11038511/wlc-5508-webauth-bundle-tar-error-256</a>. In short, the tar file that you create should be created from the root folder itself or you can simply change directories as I did below:

This is the original folder showing the files that I needed to tar

<blockquote>[UserXX@ServerXX ~]$ cd login38
[UserXX@ServerXX login38]$ ll
total 140
-rw-rw-r--. 1 UserXX UserXX 11004 May 12 2012 ButtonBackground.jpg
-rw-rw-r--. 1 UserXX UserXX 59601 May 11 2012 GuestPortal_Banner.jpg
-rw-rw-r--. 1 UserXX UserXX 3940 Aug 27 16:39 GuestWireless.Terms_DE.htm
-rw-rw-r--. 1 UserXX UserXX 5997 Nov 25 2013 GuestWireless.Terms.htm
-rw-rw-r--. 1 UserXX UserXX 3448 Aug 27 17:50 GuestWireless.Terms_LIT.htm
-rw-rw-r--. 1 UserXX UserXX 3810 Aug 27 17:10 GuestWireless.Terms_POL.htm
-rw-rw-r--. 1 UserXX UserXX 6000 Aug 27 16:57 GuestWireless.Terms_RU.htm
-rw-rw-r--. 1 UserXX UserXX 6292 Aug 27 18:10 login_DE.html
-rw-rw-r--. 1 UserXX UserXX 6665 Nov 25 2013 login.html
-rw-rw-r--. 1 UserXX UserXX 6254 Aug 27 17:52 login_LIT.html
-rw-rw-r--. 1 UserXX UserXX 6328 Aug 27 18:41 login_POL.html
-rw-rw-r--. 1 UserXX UserXX 6656 Aug 27 17:15 login_RU.html</blockquote>

Change the path to root

<blockquote>[UserXX@ServerXX login38]$ <strong>sudo chown root:root *</strong>
[UserXX@ServerXX login38]$ ll
total 140
-rw-rw-r--. 1 root root 11004 May 12 2012 ButtonBackground.jpg
-rw-rw-r--. 1 root root 59601 May 11 2012 GuestPortal_Banner.jpg
-rw-rw-r--. 1 root root 3940 Aug 27 16:39 GuestWireless.Terms_DE.htm
-rw-rw-r--. 1 root root 5997 Nov 25 2013 GuestWireless.Terms.htm
-rw-rw-r--. 1 root root 3448 Aug 27 17:50 GuestWireless.Terms_LIT.htm
-rw-rw-r--. 1 root root 3810 Aug 27 17:10 GuestWireless.Terms_POL.htm
-rw-rw-r--. 1 root root 6000 Aug 27 16:57 GuestWireless.Terms_RU.htm
-rw-rw-r--. 1 root root 6292 Aug 27 18:10 login_DE.html
-rw-rw-r--. 1 root root 6665 Nov 25 2013 login.html
-rw-rw-r--. 1 root root 6254 Aug 27 17:52 login_LIT.html
-rw-rw-r--. 1 root root 6328 Aug 27 18:41 login_POL.html
-rw-rw-r--. 1 root root 6656 Aug 27 17:15 login_RU.html
[UserXX@ServerXX login38]$ man chown</blockquote>

Tar the files

<blockquote>[UserXX@ServerXX login38]$ <strong>tar -cvf weblogin38.tar ./*</strong>
./ButtonBackground.jpg
./GuestPortal_Banner.jpg
./GuestWireless.Terms_DE.htm
./GuestWireless.Terms.htm
./GuestWireless.Terms_LIT.htm
./GuestWireless.Terms_POL.htm
./GuestWireless.Terms_RU.htm
./login_DE.html
./login.html
./login_LIT.html
./login_POL.html
./login_RU.html</blockquote>

Verify that the tared file is there

<blockquote>[UserXX@ServerXX login38]$ ls
ButtonBackground.jpg GuestWireless.Terms_POL.htm login_POL.html
GuestPortal_Banner.jpg GuestWireless.Terms_RU.htm login_RU.html
GuestWireless.Terms_DE.htm login_DE.html <strong>weblogin38.tar</strong>
GuestWireless.Terms.htm login.html
GuestWireless.Terms_LIT.htm login_LIT.html</blockquote>

Use a program like WinSCP to copy the file from the server to the required destination or desktop

<a href="https://littlenerdsdiary.files.wordpress.com/2014/08/2014_08_28_15_41_36_new_2_notepad_.png"><img class="alignnone size-full wp-image-2776" src="http://littlenerdsdiary.files.wordpress.com/2014/08/2014_08_28_15_41_36_new_2_notepad_.png" alt="2014_08_28_15_41_36_new_2_Notepad_" width="660" height="474" /></a>

Copy the tar file to the controller

<a href="https://littlenerdsdiary.files.wordpress.com/2014/08/2014_08_28_15_43_57_wldcbpinf02-mkcorp-com_remote_desktop_connection.png"><img class="alignnone size-full wp-image-2777" src="http://littlenerdsdiary.files.wordpress.com/2014/08/2014_08_28_15_43_57_wldcbpinf02-mkcorp-com_remote_desktop_connection.png" alt="2014_08_28_15_43_57_wldcbpinf02.mkcorp.com_Remote_Desktop_Connection" width="660" height="269" /></a>

That should be successful.

Ps. The last error that I ran into was that no file actually had a login.html name, all the  login files had login_RU or sth depending on the Country. Once I added one with the login.html name, everything worked well.

So now you know :)
