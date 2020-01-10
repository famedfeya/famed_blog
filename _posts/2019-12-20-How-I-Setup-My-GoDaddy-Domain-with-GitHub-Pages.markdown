---
layout: post
title:  "How I Set up my new GoDaddy Domain with GitHub Pages"
date:   2019-12-20 01:11:33 +0100
categories: howtos
---

1. Add A Records with your DNS provider for apex domain (without www.):
![Asset 1](/assets/images/2020_01_05_01_16_28_Domain_Manager.png)
2. Add one CNAME record for www subdomain.
![Asset 2](/assets/images/2020_01_05_01_20_26_Domain_Manager.png)
3. Update the GitHub Pages > Settings > Custom Domain field to www.YOURDOMAIN.com (this will add a CNAME file to the root directory in the GitHub Pages branch)
![Asset 3](/assets/images/2020_01_05_01_23_01_Options.png)
I need to wait inorder to enforce HTTPS. Will do that once the certificate is issued. 
4. Go to your editor and in the repository of your website create a new file named “CNAME” in the root of your directory. In the “CNAME” file add your domain name purchased from GoDaddy.
![Asset 4](/assets/images/2020_01_05_01_28_50_CNAME_famed_blog_Sublime_Tex.png)
5. Add, commit, and push your changes to Github.
6. Verify Domain is set up correctly using nslookup
7. Once the option to enforce HTTPS is available, do not foregt to enable it in GitHub pages. 