---
layout: default
title: Credential Stuffing
nav: credential_stuffing
---

## Credential Stuffing

![OpenBullet Process](../imgs/openbullet.png)

Credential stuffing is the use of leaked password sites to gain a list of valid username/password combinations for a target site.

Often leaked passwords come from large website breaches like the famous LinkedIn breach, but they can also come from smaller less known sites. For example a small forum site with 100,000 users when attacked *(for instance by an SQL injection attack)* may leak a list of unprotected passwords.

While the small forum might not have much of value for the attacker the account/password list provides the raw resources which can be used for a credential stuffing attack on several other sites.

To get a more in depth description of the process of doing a credential stuffing attack, see [my paper on the topic](https://kirkins.github.io/Cyber-Crime-Micro-Course/papers/paper1.pdf).

Another attack that can be used in conjunction with credential stuffing is SSL certificate unpinning. This is where a certificate which has been compiled into a mobile app is extracted. Once the certificate has been extracted it can be used to make requests as a mobile device instead of through the normal web API. Often companies that have captcha on their website will not have captcha on the mobile app, thus by pretending to be a mobile app an attack can become much more efficient.

### SSL Pinning and Credential Stuffing

Another technique that can be used in conjunction with credential stuffing is SSL certificate unpinning. This is where a certificate which has been compiled into an app to prevent MiTM and packet sniffing is disabled. Once the certificate has been disabled the network traffic can be analyzed and that data used to create a configuration file. Often a configuration file based on a mobile app traffic is more efficient than one using website traffic. This is because often companies that require completing a captcha on their website don't have the same requirment on their mobile app.

### Bad Captchas

Some servers only require changing a user-agent value to disable captcha completely where others are more complicated and secure.

One cracker I talked to reported that he had even encountered fake captcha systems, which appeared to be Captcha but would actually accept any submitted value. On the front-end the captcha widget would simply generate a random number using the code snippet below:

    <input value="0.4464311458655813" name="captcharand" id="captcharand" style="display:inline-block" type="hidden">
    <div style="display:inline-block;">
    <span id="captcha"><img onclick="reloadimg(); return false;" src="captcha/generate.php" style="cursor:pointer;"></span>
    <script language="javascript" type="text/javascript">
    document.getElementById("login").focus();

    function reloadimg() {
      var a = Math.random();
      document.getElementById("captcharand").value=a;
      document.getElementById("captcha").innerHTML = '<img onclick="reloadimg();
                                                        return false;"
                                                        src="captcha/generate.php?rand='+a+' "
                                                        style="cursor:pointer;" />';
    };
    reloadimg();
    </script><br>Captcha:<br>

### **Note: Password Hashing**

A successful SQL attack can yield a list of hashed or unhashed passwords. Hashed passwords are ones which are transformed using a one-way function which transforms them into a standard sized string of scrambled charachters. The same password input run through the same hashing algorithm will always produce the same hased result.

Website developers should ensure to always encrypto passwords as it could potentially protect users from having their passwords exposed. A leaked list of account/password combinations which are hashed can require a significant amount of effort to make use. A database which saves passwords in plaintext on the other hand is very easily and quickly exploited.

What makes hasing so effective is that the algorithm is only one way. Plain-text can be put into the algorithm to produce a hash but there is no way to reverse the hash back into the password using the algorithm, even the website owners can't access these passwords.

Yet password hashing does not provide complete protection. A popular program [John the Ripper](https://github.com/magnumripper/JohnTheRipper) can be used to break password hashes given enough time. It has several modes for cracking one of the most popular being a dictionary attack. A dictionary attack involves comparing hashes in a database to a list of popular passwords in their hash formats. Of course having the same hash requires both the exact same input password and the exact same hashing algorithm. There may be many possible dictionaries to test against, but given the attacker has already obtained the database they have an essentially unlimited amount of time to make attempts at cracking.

Salting adds uniqueness to a hashed password meaning that a standard rainbow table won't be effective. A salt is essentially a random string of text which is prepended or appended to the users passwords before it goes into the hashing algorithm. 
