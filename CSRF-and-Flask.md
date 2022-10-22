---
title: "CSRF and Flask"
date: 2022-10-22T15:27:48-04:00
description: "How to prevent CSRF attack in Python Flask"
author: "Baichuan Li"
draft: true
---

## What is CSRF?

CSRF is short for Cross-Site Request Forgery. Here are the steps for CSRF:
- Victim logs into a good website such as https://www.bank.com. Then the server will add a cookie (login token, usually and random string) to the browser, and store the user-token pair in the server-side database.
- The victim user then goes to a website set up by the attacker.
- The attacker's server sends the user a HTML page containing a JavaScript program that sends a request to https://www.bank.com/transfermoney/. Note that this request will be sent with the cookies of bank.com attached.
- The bank.com server verifies that the login token set in the request cookies is indeed valid. So the bank server decides to transfer the money.
