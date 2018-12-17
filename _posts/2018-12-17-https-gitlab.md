---
layout: post
title:  "HTTPS on Gitlab Pages using Let's Encrypt / Certbot"
date:   2018-12-17
excerpt: "These instructions are for Mac OS, uses Let's Encrypt's certbot, and does not require a challenge file, which makes things much easier."
---

I decided to move a personal project's webpage over from Github to Gitlab recently, chiefly because Gitlab allows private repositories for free. However, unlike Github, HTTPS encryption for custom domain names on Gitlab requires manual setup. I couldn't find any comprehensive guides, so here's the easiest method I've found so far that utilizes DNS verification with a TXT entry. These instructions are for Mac OS, uses Let's Encrypt's certbot, and does not require a challenge file, which makes things much easier.

Prerequisites for Mac OS
1. Homebrew installed
2. Access to domain DNS settings

### Install certbot
```
brew install certbot
```

### Run certbot to create verification keys
```
certbot -d yourdomain.com --manual --preferred-challenges dns certonly
```
Make sure to replace `yourdomain.com` with you actual domain. Do not add `http://` or `https://` to the beginning of your domain. Once the verification key is created, copy the key and move on to the next step without hitting "Enter" in the terminal window.

### Add TXT entry to DNS settings
Log into your domain's admin page and go into the DNS settings. In Google Domains, scroll all the way to the bottom of the "Configure DNS" tab to find "Custom resource recods".

Put `_acme-challenge.yourdomain.com` into the name field, change the Type to TXT, and place the resulting key into the Text field.

### Flush cache 
Flush Google DNS's cache for your domain's TXT entry [using Google's Public DNS tool](https://developers.google.com/speed/public-dns/cache). This makes your changes effective immediately so that certbot can verify you own the domain. 

### Continue on certbot
Go back into the terminal window and hit "Enter". You should get the following congrats message if everything was implemented correctly. Your certificate and SSL key will be created and placed in a folder.

```
IMPORTANT NOTES:
 - Congratulations! Your certificate and chain have been saved at
   /etc/letsencrypt/live/YOURDOMAIN.org/fullchain.pem. Your cert will
   expire on 2016-07-04. To obtain a new version of the certificate in
   the future, simply run Let's Encrypt again.
 - If you like Let's Encrypt, please consider supporting our work by:

   Donating to ISRG / Let's Encrypt:   https://letsencrypt.org/donate
   Donating to EFF:                    https://eff.org/donate-le
```
If you got an error message instead, try create another key and repeat the above steps, but wait a few minutes after flushing the cache before continuing on and hitting "Enter" on the terminal window.

### Copy the keys into Gitlab's repo settings
Navigate to the resulting folder using root access.
```
sudo su
cd /etc/letsencrypt/live/yourdomain.com/
```
Back on Gitlab, go to the Pages setting page and copy the contents of fullchain.pem using `nano fullchain.pem` into the "Certificate (PEM)" field on Gitlab. Similarly, use `nano privkey.pem` and copy the contents into the "Key (PEM)" field. Or use any editor of your choice, obviously.

### Enable SSL on Gitlab
Once saved, make sure to check the "Force domains with SSL certificates to use HTTPS" checkbox on the Pages settings page.

### Finished!
If everything was done correctly, HTTPS should now be working on your website. Changes may take an hour or two to appear, so give it some time. 