---
layout: default
title: Types of Attacks
nav: types
---

## Common Attacks

- **[Man in the Middle](./attacks/mitm.md)**:  
*When an attacker intercepts internet traffic between a user and end-destination and modifies the contents. Most instances prevented by the use of HTTPS.*
- **Fuzzing**:  
*Trying a large range of inputs on user generated inputs, often using special characters not used by normal users. This is done in an attepmt to find ways to break the program or web server*
- **SQL Injection**:  
*When user input is used as part of a database query an SQL injection is possible when there isn't a sanitization step that stops a user from inputting SQL commands. Often SQL Injection attacks result in the attacker being able to obtain a database dump.*
- **DDOS**:  
When a large amount of traffic or requests is sent to a website in order to overwhelm a server and make it go offline.*
- **[Credential Stuffing](./attacks/credential_stuffing.md)**:  
*When a user/password combination which has been obtained from a website or source is used en mass on another site to find accounts using the same password on both.*
- **Brute Force**:  
*When many possible combinations for a password are attempted in an attempt to find the correct one. This can be done sequentially or using a list of common passwords, or a dictionary of common words.*
- **SIM Swap**:  
*When an attacker contacts a phone company to fraudulenty claim a cellphone has been lost or stolen and have the number moved to another SIM card in pocession of the attacker. Often used as a way to gain access to websites or accounts which require 2FA*.
- **Session Hijacking**:  
*When an attacker resumes another users session with a website or app by gaining access to the means by which the website/application tracks the logged in user, this could be a cookie, token, or other means.*

## Other Attacks

- Shell Shock
- Email bombing
