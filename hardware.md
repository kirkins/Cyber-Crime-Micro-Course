---
layout: default
title: IoT Devices and Botnets
nav: hardware
---

## Common Attacks

*Originally written for weekly discussion in COMP 601*

The rapid development of hardware has strongly influenced the state of cybersecurity and crime. While we normally think of desktop computers when thinking of hardware this is a very limited definition. For the purpose of this discussion we should consider all computing devices with access to a network of any kind, that includes computers, phones, laptops, appliances, IP cameras, and smaller IoT devices.

Many of these devices have been the target of security breaches or used as part of botnets. Most IoT devices run on some variation of linux. Linux provides a license free operating system with a large amount of capabilities. This also means that exploits that can be used to target web servers often can also be used against IoT devices and appliances.

IoT often provide an easier target for comporiming than traditional web servers. This is due to the fact that IoT devices may be less consistent in getting software security updates. For example a device shipped from a manufacturer to a consumer might not receive any security updates, even in the case that some exploit is exposed on the device, it may be impossible even for the original manufacturer to remotely connect and update the device.

Alternatively a device may receive security updates managed by the manufacturer for a short period of time and then have them later discontinued. If the device doesn’t have a monthly paid subscription attached their is little incentive for the manufacturer to provide timely updates. Furthermore in the fast moving technology industry it is possible that a manufacturer goes out of business or discontinues the product altogether.

Even when a manufacturer provides timely security updates there will be edge case scenarios. For example a smart-connected device is in an area of the home where internet is temporarily unavailable. Even with a security update being made available it may not be able to update, then when the device comes back online there will be a temporary period of insecurity before it updates.

Another factor is the fact that generally cool new features are more effective as a selling tool than good security. People buying IoT devices decide based on which devices have the coolest features. Companies all competing against each other to gain a market advantage by making the development of features their core goal. Security becomes an afterthought, though still a valid concern as an embarrassing security breach can hurt a brand. Though for a startup that requires going viral just to survive, it would be better to sell lots based on a feature and have a security issue later, than to focus on security and end up not selling lots of devices.

We know IoT devices can be easy targets for attacks, but once they’re controlled and added to a botnet what are the common ways attackers make use of them? The three main uses that have been popular are use a residential proxy, compromising private data, and cryptocurrency mining. A fourth use that is less common is industrial or private sabotage, that is causing harm to the owner of the device or process the device is being used for.

Using an IoT device as a residential proxy means that an attacker is routing Internet traffic through the device so that the websites receiving the traffic believe the origin of a request is the IP address of the device owner. This is useful as the origin IP address of a request is a key component used by fraud detection software like Maxmind or ThreatMetrix which is used by companies including BestBuy, TD Bank, and Visa.

Fraud detection software like ThreatMetrix takes all the data points of a transaction and creates a likelihood of fraud score based on all the factors. Companies using this software can determine their own acceptable risk levels. A company with a high profit margin like Starbucks might have a higher threshold for risk than a company with a lower profit margin like BestBuy.

If for example a large purchase is being made using a credit card with a billing address in Alberta and the IP making the purchase is in Quebec this would add to the fraud score. By creating a large botnet of IoT devices in many locations the attacker can make use of (or rent out to others) residential proxies in specific cities. Often those with access to such a botnet will specialize in renting out residential proxies. Then those with access to a stolen credit card will rent access to a proxy which is in the same city as the credit card owner.

After a residential proxy is used in this manner a few times it will itself be flagged by the fraud detection software. Most who specialize in renting residential proxies will detect the red flag and then remove the proxy from their premium section and repurpose it for other uses. A side effect of a red flag being applied to the IP is that the owner of the IoT device, completely unaware of the situation, will start to have their own legitimate transactions denied when using their home internet connection.

The second major use compromising personal data includes any type of attack where information is stolen from the user. This could include monitoring internet traffic or other data and relaying the data back to a server controlled by the attacker. This type of attack is less useful on an IoT device than it would on a personal computer, laptop, or phone. For this reason the attacker may try to spread over the local network from the IoT device to computers on the same network. The end-goal for most data harvesting of this kind is to obtain “logs” which include a users account passwords and other personal data which can be exploited for personal gain. Another popular variation is ransomware attack, where instead of transmitting data back to a server, the attacker encrypts it denying the original owner access, unless they pay a fee.

A third use of compromised IoT devices or appliances is to have them use proof of work cryptocurrency mining to generate profit for the attacker. Originally this attack would have focused on bitcoin mining, but at this time bitcoin is too difficult to mine on most machines so other less known currencies are used. One of the most popular mined currencies is Monero, in addition to being easy to mine it provides a level of privacy which is greater than bitcoin, making it impossible to detect the wallet address or end balance of the attacker.

As computing in everyday devices continues to become more popular, botnets which make use of them will continue to grow and spread. Of course many will be mitigated and shutdown, but as a new security methods shut old botnets down, new ones will spring up to take their place.

## Links:

https://www.shodan.io/
