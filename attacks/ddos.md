---
layout: default
title: DDOS
nav: ddos
---

## DDOS (Distributed Denial of Service Attack)

A distributed denial of service attack in an attack which involves making a swarm of requests to a server all coming from different IP addresses.

In the early days of the internet DDOS attacks could be performed simply by having a large amount of people visit a site, and refresh it over and over. Given the limited server capacity at that time the website would often become unavailible for any potential visitor.


### Preventing DDOS Attacks

As the internet has grown in popularity the average capacity of most servers has grown, furthermore it is common for companies to make use of components or services which make DDOS more difficult, these include:

#### Web Caching

Web caching has several benefits, one of which is increasing the capacity of server by lightening the load that each user request to a page causes.

Consider for example a website that when given a city will get weather data from several sources and display a compilation of the data, the function of getting the data and copiling it is some what resource intensive. A user who goes to URL:

    example.com/weather?city=London

Will cause the function to compile the data and serve it. In a caching system we may create an intermediate between the actual server and the user so the architecture looks like:

      +-------------------+
      |        	     	  | A user makes a request to some specific URL.
      |       User     	  |
      |              	  |
      +--------+-^--------+
	       | |
	       | |
      +--------v----------+
      |                   | The request checks the cache server.
      |     Cache         | If a version of the page has been saved in 
      |                   | the last X minutes, it is servered to the user.
      +----------^--------+
	       | |
	       | |
      +--------v----------+
      |                   | If there is no recent saved version in cache
      |     Server        | the user request reaches the server, where
      |                   | the server-side code is executed.
      +-------------------+


#### Anti-DDOS Protection

An anti-DDOS service protects against DDOS by analyzing traffic in real-time and denying access to users which look like bots.

This can be deduced from several factors including:

- Request Source
- Packet Analysis
- Request Frequency

Request source is simply the IP address of the request, or IP range. This may be variable used among many which is accounted for. For example a high-risk IP address may be allowed to access a website when traffic is low, but during an active attack it may be blocked to maintain server capacity.

Advanced anti-DDOS systems make use of machine learning to combine the factors listed and others to decide which traffic should be let through and which should be blocked.

