---
layout: default
title: Man in the Middle
nav: mitm
---

## Man in the Middle

A man in the middle attack (MiTM) is one in which the attacker positions himself inbetween a legitimate website and a client side user. It is one of the oldest forms of attack used on the internet.

### ARP Spoofing

One of the early ways MiTM was performed was called ARP spoofing or ARP poisoning. This involved connecting a computer to a network such as a public wifi network, and then annoucing to the network that it is the router. This would result in other devices on the network sending their outgoing internet requests to the attackers computer. The attacker then sends the packets on to their intended destination so that everything appears to be working normally for the victims on the network. By having traffic routed through the attackers computer they can then analyze this traffic and extract sensitive information.

As a website owner one of the best ways to protect against a ARP Spoofing attack is to simply make use of an SSL certificate and enforce HTTPS. This can be done using a program like LetsEncrypt to create a free SSL certificate or buying one from a certificate authority (CA). When HTTPS is used all packets are encrypted with the final destinations public key. This means that even if an attacker is able to intercept the traffic they won't be able to read it.

### IP Spoofing

Attacker creates IP packets which have a false source IP address in order to impersonate another server. Can be used as part of a MiTM attack by sending false packets to both parties and forwarding on the responses. This gives the impression to both parties that they're talking to each other when in actuality they are talking to the attacker.

### DNS Spoofing (DNS Cache Poisoining)

An attack that involves corrupting a Domain Name Server so that website names can be associated with an incorrect IP address, thus allowing for MiTM attacks or phising.

### SSL Stripping

Involves intercepting the user when they are being transfered from an open HTTP connection to a secure HTTPS connection. The attacker makes a secure connection with the targets intended destination for example "https://website.com". From the end websites point of view the website is being delivered via HTTPS. The attacker then forwards the result as an HTTP unsecure version of "http://website.com".

SSL Stripping was first exposed as a method of attack in 2009, by security research Moxie Marlinspike at the annual BlackHat conference in Las Vegas.

### SSL Hijacking

SSL Hijacking is very similar to SSL Stripping, the main difference being that instead of forwarding an unencrypted version of the website to the target over HTTP, a fake certificate is used so the victim sees HTTPS.

The attacker provides a false SSL certificate to the end client making them interpret this SSL certificate as being that of the intended end website when it is in fact a certificate controlled by the attacker. The end-user encrypts their traffic using the fake SSL certificate, the data is decrypted by the attacker and then re-encrypted with the real private-key. The end website then responds, attacker recieves the response, decrypts it, encrypts the data with the fake certificate and then forwards the result on to the victims computer.

One of the ways SSL Hijacking is averted is through the use of Certificate Authorities (CA). Certificate Authorities sign the public keys which are used by websites. These trusted root certificate authorities are shipped with software like mobile phones and web browsers. Fake certificates created by attackers are not signed by the appropriate trusted root certificate authorities and thus are detected by browsers.

### Superfish and SSL Hijacking

One previously popular method of SSL Hijacking involved something called Superfish. Superfish involved a certified root certificate authority *(now bankrupt, due to the incident)*, which published a fraudulent certificate for Google. The result was that the owner of the fake certificate could perform a SSL Hijacking attack on anyone who visited Google and had the root certificate CA installed on their device. Since the problem was exposed their has been a major effort to remove the root CA certificate from software and devices. You can check if your device is vulnerable to Superfish or other bad trusted authorities by visiting [badSSL.com](https://badssl.com/dashboard/).

Originally the attack could only be performed by the holder of the private key. However the key was later leaked meaning anyone could perform the attack on a device which had the bad root CA installed.

Well Superfish has been removed on most devices it demonstrates the weakness of SSL. Your HTTPS connection is only as trusted as the root certificates on your device. When it comes to government organizations for example, there is not much gaurentee that they wouldn't be able to obtain fake keys *(or already have them)*.
