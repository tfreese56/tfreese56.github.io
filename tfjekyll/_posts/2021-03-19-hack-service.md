---
layout: post
title:  "Hack Service"
date:   2021-03-19 08:00:00 -0600
subtitle: "SQL injection bank hack"
thumbnail: "/img/incredi-safe-bank.png"
categories: python 
tags: Python
technologies: python sqldb
---
<link rel="stylesheet" href="/css/styles.css">
In Computer Security at BVU, we had the opportunity to write a hackable service. I built a proof-of-concept SQL injection site modeled after a bank website. The site uses flask as a Python <img src="/img/python.png" class="inline-icon"/> backend and sqlite3 as the database being hacked.


### The Hack
<img src="/img/incredi-safe-bank.png" alt="incredi-safe-bank home page" style="margin-bottom: 20px;"/>
On the banking website, there are banking tools such as a loan interest calculator, a real calculator, a stock ticker tape, and an info box about your connection. These interactive tools are just for looks. To use the website, a client can register, login, and search for users to send money to. 

The story is a developer accidently included the passwords with the usernames when a client runs a search. Therefore, being able to see passwords in plain text, you would want to find the admin password to get the flag in a CTF contest.

#### Steps to the hack
1. Register & login
1. Search for yourself in search bar and observe the results are USER \[ Account Number \] \| PASSWORD
* Shame on the dev for including "\| PASSWORD"...
1. Perform a SQL injection in the search bar of `ANYTHING' or '1' = '1`
1. Find the admin user & password on the page
1. Logout
1. Login as admin
1. Click FLAG ME
1. You've hacked the service

#### SQL Injection
The query hacked is:

`SELECT username, accountNum, password FROM customers WHERE username = ' + user_input + ';`

Certainly, the `user_input` being injected right into the query (no sanitization) is troublesome. This injection is not found in the registration or sign in functionality.

#### Extras
There are 100 randomly generated users with predetermined usernames and passwords. The passwords are simple, but random each time. The admin user is added as the 101st user also with a randomly generated password.

### Screenshot tutorial

#### New user registered and searched
<img src="/img/incredi-safe-bank_usersearch.png" alt="incredi-safe-bank user search" style="margin: 20px;"/>

#### Trying admin
<img src="/img/incredi-safe-bank_noadmin.png" alt="incredi-safe-bank no admin" style="margin: 20px;"/>

#### SQL Injection
<img src="/img/incredi-safe-bank_sql-injection.png" alt="incredi-safe-bank sql injection" style="margin: 20px;"/>

#### Hacked Admin
Finding the `admin` user and password, logging with credentials, and the `FLAG ME` button appears. Success.
<img src="/img/incredi-safe-bank_hacked.png" alt="incredi-safe-bank found admin" style="margin: 20px;"/>


### Ending
Thanks for reading about SQL Injections!

Best.

##### Links
<div style="font-size: 10px;">
<a target="_blank" href="https://icons8.com/icon/13441/python">Python</a> icon by <a target="_blank" href="https://icons8.com">Icons8</a>
</div>
