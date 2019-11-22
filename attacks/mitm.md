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

### SSL Hijacking



### SSL Stripping
