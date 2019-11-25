---
layout: default
title: Fuzzing
nav: fuzzing
---

## Fuzzing

Fuzzing is the practise of attempting a large variety of inputs to a server endpoints or client software in an attempt to find one that returns an unexpected result.

### Fuzzing URLs

When applied to web servers one of the main methods for fuzzing is to target a server by fuzzing at URL. That is taking a URL which has inputs using the url, for example URLs which end with `?variable=someValue`, and replacing the `someValue` with a large variety of different values and monitoring the response. The same can be applied to the `?variable` part of the URL. If the server responds in an unusual way or returns an error it is noted for further investigation.

### AFL - American Fuzzy Loop

AFL is a tool maintained by Google which applies the same fuzzing concept but targets binary applications instead of web ones. It comes with a modified version of the Clang and GCC compilers which can insert additional tools in the binary that make it possible to test various things. In addition to testing the different inputs to a binary, it can also test for which bits in an end program cause it to stop working.
