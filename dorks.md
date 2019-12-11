---
layout: default
title: Google Dorks
nav: dorks
---

## Google Dorks or Dorks

### What are Google Dorks

A Google Dork is a search term which can be used to find unsecured website or some other resource on the internet. Often this includes specifying a certain file type or a string of words or symbols which commonly appear in an admin page.

It should be noted that these same techniques can be used on other search engines such as DuckDuckGo, which may even be a better source as Google sometimes censors the results of dorks in order to prevent malicious use.

### Internet Connected Devices

In this section we'll look at some search queries which return internet connected devices.

#### Weather station WS-2
- intitle:"Weather Wing WS-2"

#### Live Cameras
- inurl:top.htm inurl:currenttime
- intitle:"webcamXP 5"
- inurl:"lvappl.htm"
- inurl:"ViewerFrame?Mode="

#### Find Music

As search engines crack down on sharing of copy-righted music dorks which find MP3 files from your favourite muscians can also come in handy.

- ?intitle:index.of? mp3 artist-name

#### FTP 

In many cases FTP is not inteded to be accessed via web browser but it can be left open to do so. The query below will return ftp servers, you can modify the `after:2019` to get older results, or remove it all together to get results from anytime.

- intitle:"index of" inurl:ftp after:2019
- intitle:index of ws_ftp.ini
- filetype:conf inurl:proftpd.conf –sample

#### Passwords, Admin Panels, and Config Files

Note: notice the use of `ext:` in this section, logs, and others. It specifies the specific file-type. Don't limit yourself to what you see here, try searching other filetypes that you think could result in interesting content, you may end up creating your own dork.

- ext:inc "pwd=" "UID="
- ext:asa \| ext:bak intext:uid intext:pwd -"uid..pwd" database \| server \| dsn
- ext:txt inurl:unattend.txt
- ext:asp inurl:pathto.asp
- ext:cgi inurl:editcgi.cgi inurl:file=
- "AutoCreate=TRUE password=*"
- filetype:rdp rdp
- allinurl: admin mdb
- auth_user_file.txt
- config.php

#### Logs

- inurl:_vti_pvt “service.pwd”
- intitle:index.of .bash_history
- intitle:index.of .sh_history
- “index of ” lck
- filetype:reg reg HKEY_CURRENT_USER username
- ext:yml database inurl:config

#### User Lists

- inurl:admin inurl:userlist
- inurl:admin filetype:asp inurl:userlist
