<img src="https://github.com/mitchellkrogza/apache-ultimate-bad-bot-blocker/blob/master/.assets/apache-ultimate-bad-bot-referrer-blocker-script.png" alt="Apache Ultimate Bad Bot, User-Agent and Spam Referrer Blocker - Apache Block Bad Bots, User-Agents, Vulnerability Scanners, Malware, Adware, Ransomware, Malicious Sites, Spam Referrers, Bad Referrers, Spam Blocker, Porn Blocker, Gambling Blocker,  Wordpress Theme Detector Blocking and Fail2Ban Jail for Repeat Offenders"/><img src="https://github.com/mitchellkrogza/apache-ultimate-bad-bot-blocker/blob/master/.assets/spacer.jpg"/>[![DUB](https://img.shields.io/dub/l/vibe-d.svg)](https://github.com/mitchellkrogza/apache-ultimate-bad-bot-blocker/blob/master/LICENSE.md)<img src="https://github.com/mitchellkrogza/apache-ultimate-bad-bot-blocker/blob/master/.assets/spacer.jpg"/>[![GitHub release](https://img.shields.io/github/release/mitchellkrogza/apache-ultimate-bad-bot-blocker.svg)](https://github.com/mitchellkrogza/apache-ultimate-bad-bot-blocker/releases/latest)<img src="https://github.com/mitchellkrogza/apache-ultimate-bad-bot-blocker/blob/master/.assets/spacer.jpg"/>[![Build Status](https://travis-ci.org/mitchellkrogza/apache-ultimate-bad-bot-blocker.svg?branch=master)](https://travis-ci.org/mitchellkrogza/apache-ultimate-bad-bot-blocker)<img src="https://github.com/mitchellkrogza/apache-ultimate-bad-bot-blocker/blob/master/.assets/spacer.jpg"/><a href='https://twitter.com/ubuntu101za'><img src='https://img.shields.io/twitter/follow/ubuntu101za.svg?style=social&label=Follow' alt='Follow @ubuntu101za'></a>

# CONFIGURATION INSTRUCTIONS FOR THE APACHE BAD BOT BLOCKER:
### PLEASE READ CONFIGURATION INSTRUCTIONS BELOW THOROUGHLY

##### Created by: https://github.com/mitchellkrogza
##### Copyright Mitchell Krog <mitchellkrog@gmail.com>

_______________
#### Version: V3.2018.03.803
#### Bad Referrer Count: 6193
#### Bad Bot Count: 510
____________________

## Update Notification System
Please subscribe your email address to the mailing list at **https://groups.google.com/forum/#!forum/apache-ultimate-bad-bot-blocker**
or simply send a blank email to **apache-ultimate-bad-bot-blocker+subscribe@googlegroups.com** to subscribe.
**Please make sure you are subscribed to notifications** to be notified when the blocker is updated and also to be notified when any important or mission critical changes take place.

## Also follow me on twitter @ubuntu101za for update notifications

<a href='https://twitter.com/ubuntu101za'><img src='https://img.shields.io/twitter/follow/ubuntu101za.svg?style=social&label=Follow' alt='Follow @ubuntu101za'></a>

## Step 1:

**COPY THE GLOBALBLACKLIST.CONF FILE FROM THE REPO**

Copy the contents of **globalblacklist.conf** into your /etc/apache2/custom.d folder. 
**You need to create this folder.**

`sudo mkdir /etc/apache2/custom.d`

`sudo wget https://raw.githubusercontent.com/mitchellkrogza/apache-ultimate-bad-bot-blocker/master/custom.d/globalblacklist.conf -O globalblacklist.conf`

## Step 2:

**WHITELIST ALL YOUR OWN DOMAIN NAMES AND IP ADDRESSES**

Whitelist all your own domain names and IP addresses. **Please note important changes**, this is now done using include files so that you do not have to keep reinserting your whitelisted domains and IP addresses every time you update.

`cd /etc/apache2/custom.d`

- copy the whitelist-ips.conf file into that folder

`sudo wget https://raw.githubusercontent.com/mitchellkrogza/apache-ultimate-bad-bot-blocker/master/custom.d/whitelist-ips.conf -O whitelist-ips.conf`


- copy the whitelist-domains.conf file into the same folder

`sudo wget https://raw.githubusercontent.com/mitchellkrogza/apache-ultimate-bad-bot-blocker/master/custom.d/whitelist-domains.conf -O whitelist-domains.conf`

Use nano, vim or any other text editor to edit both whitelist-ips.conf and whitelist-domains.conf to include all your own domain names and IP addresses that you want to specifically whitelist from the blocker script. 

When pulling any future updates now you can simply pull the latest globalblacklist.conf file and it will automatically include your whitelisted domains and IP addresses. No more remembering having to do this yourself.

## Step 3:

**DOWNLOAD CUSTOM BLACKLIST INCLUDE FILE FOR IP ADDRESS AND IP RANGE BLOCKING**

Blacklist any IP addresses or Ranges you wish to keep out of your servers. **Please note important changes**, this is now done using include files so that you have full control over what IP addresses and IP Ranges and blocked from your Apache Server.

`cd /etc/apache2/custom.d`

- copy the blacklist-ips.conf file into that folder

`sudo wget https://raw.githubusercontent.com/mitchellkrogza/apache-ultimate-bad-bot-blocker/master/custom.d/blacklist-ips.conf -O blacklist-ips.conf`


Use nano, vim or any other text editor to edit the blacklist-ips.conf file as you like. 

When pulling any future updates now your custom IP blacklist will not be overwritten.

## Step 4:

**DOWNLOAD CUSTOM BAD REFERRER WORDS INCLUDE FILE FOR CUSTOMIZED SCANNING OF BAD WORDS**

Scan for any bad referrer words you wish to keep out of your servers. **Please note important changes**, this is now done using include files so that you have full control over what IP addresses and IP Ranges and blocked from your Apache Server.

`cd /etc/apache2/custom.d`

- copy the bad-referrer-words.conf file into that folder

`sudo wget https://raw.githubusercontent.com/mitchellkrogza/apache-ultimate-bad-bot-blocker/master/custom.d/bad-referrer-words.conf -O bad-referrer-words.conf`


Use nano, vim or any other text editor to edit the bad-referrer-words.conf file as you like. 

When pulling any future updates now your custom bad referrer words list will not be overwritten.


## Step 5:

**DOWNLOAD CUSTOM BLACKLIST USER-AGENTS INCLUDE FILE FOR CUSTOMIZED BLOCKING OF USER AGENTS**

Allows you to add your own custom list of user agents with this new include file.

`cd /etc/apache2/custom.d`

- copy the blacklist-user-agents.conf file into that folder

`sudo wget https://raw.githubusercontent.com/mitchellkrogza/apache-ultimate-bad-bot-blocker/master/custom.d/blacklist-user-agents.conf -O blacklist-user-agents.conf`


Use nano, vim or any other text editor to edit the blacklist-user-agents.conf file as you like. 

When pulling any future updates now your custom bad referrer words list will not be overwritten.

**NOTE:** On the Apache Blocker if you want to over-ride any of the whitelisted bots you can add them to this include file and the previously whitelisted bots in the blocker will be over-ridden by this include file. So let's say for some "obscure" reason you really do not want any search engines like Googlebot or Bingbot to ever access or index your site, you add them to your blacklist-user-agents.conf and they will be over-ridden from the earlier whitelisting in the blocker. This now gives users total control over the blocker without every having to try and modify the globalblacklist.conf file. So now you can customize all your include files and you can still pull the daily updates of globalblacklist.conf and it will not touch any of your custom include files.

## Step 6:

**INCLUDE THE GLOBALBLACKLIST.CONF FILE INTO A VIRTUALHOST**

 Include the globalblacklist.conf file in the beginning of a directory block just after your opening Options statements and before the rest of your host config example below. **Remove the "<<<<<< This needs to be added" part**

```
 <VirtualHost *:443>
 .....
 .....
<Directory "/var/www/mywebsite/htdocs/">
Options +Includes
Options +FollowSymLinks -Indexes
Include /etc/apache2/custom.d/globalblacklist.conf <<<<<< This needs to be added
 ......
 ......
 BEGIN WordPress
<IfModule mod_rewrite.c>
```

## Step 7:

**TEST YOUR APACHE CONFIGURATION**

Do an Apache2 Config Test

`sudo apache2ctl configtest`

If you get no errors then you followed my instructions so now you can make the blocker go live with a simple.

`sudo service apache2 reload`

or

`sudo service httpd reload`

The blocker is now active and working so now you can run some simple tests from another linux machine to make sure it's working.

## Step 8:

*TESTING**

Run the following commands one by one from a terminal on another linux machine against your own domain name. 
**substitute yourdomain.com in the examples below with your REAL domain name**

`curl -A "googlebot" http://yourdomain.com`

Should respond with 200 OK

`curl -A "80legs" http://yourdomain.com`

`curl -A "masscan" http://yourdomain.com`

Should respond with 403 Forbidden

`curl -I http://yourdomain.com -e http://100dollars-seo.com`

`curl -I http://yourdomain.com -e http://zx6.ru`

Should respond with 403 Forbidden

The Apache Ultimate Bot Blocker is now WORKING and PROTECTING your web sites !!!

## Step 9:

**UPDATING THE APACHE BAD BOT BLOCKER** is now easy thanks to the automatic includes for whitelisting your own domain names.

Updating to the latest version is now as simple as:

`cd /etc/apache2/custom.d`

`sudo wget https://raw.githubusercontent.com/mitchellkrogza/apache-ultimate-bad-bot-blocker/master/custom.d/globalblacklist.conf -O globalblacklist.conf`

`sudo apache2ctl configtest`

`sudo service apache2 reload` 

And you will be up to date with all your whitelisted domains included automatically for you now. 

# AUTO UPDATING:

See my latest auto updater bash script at:

https://github.com/mitchellkrogza/apache-ultimate-bad-bot-blocker/raw/master/update-apacheblocker.sh

Relax now and sleep better at night knowing your site is telling all those baddies FORBIDDEN !!!

### Writing code like this makes me very thirsty [Why not buy me a beer](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=TNCNMH8QVM78J):beer:

## Update Notification System
Please subscribe your email address to the mailing list at **https://groups.google.com/forum/#!forum/apache-ultimate-bad-bot-blocker**
or simply send a blank email to **apache-ultimate-bad-bot-blocker+subscribe@googlegroups.com** to subscribe.
**Please make sure you are subscribed to notifications** to be notified when the blocker is updated and also to be notified when any important or mission critical changes take place.

## Also follow me on twitter @ubuntu101za for update notifications
