---
layout: post
title:  "Chat Channels"
date:   2020-05-13 08:00:00 -0600
subtitle: "Chat platform using decentralized storage"
thumbnail: "/img/cc-many.png"
categories: python 
---
<link rel="stylesheet" href="/css/styles.css">
Chat Channels is a communications platform built on top of a [Distributed Hash Table](/python/2021/04/20/distributed-hash-table.html) written in Python <img src="/img/python.png" class="inline-icon"/>.

Goals of this platform:
* Easy, ephemeral chat rooms for work/projects/friends/people at an event
* Longer lasting chat boards for family members
* Minimal interface and user profiles
* Data stored on a decentralized structure

Additionally, I wanted a proof-of-concept use for the Distributed Hash Table (DHT) I had written from Networks & Distributed Systems class. I took this as the opportunity to do so.

### Chat Channels Home Page 
Home page of Chat Channels. Again the goal was minimal interface and user profiles.

<img src="/img/cc-main.png" alt="home page chat channels"/>

### User's Channels
A user's list of multiple channels that are sortable

<img src="/img/cc-many.png" alt="multiple page chat channels"/>

### Pros and Cons
After completion, came up with some good and bad things about the project.

<img src="/img/cc-proscons.png" alt="pros cons chat channels"/>

### Distributed Hash Table
A visualization of the [Distributed Hash Table](/python/2021/04/20/distributed-hash-table.html).
Keys for Chat Channels were the usernames; implying each new user had to have a unique username for lookup.

<img src="/img/DHT_VIS.png" alt="pros cons chat channels"/>

### That's All
Thanks for looking through Chat Channels!

Best.

##### Links
<div style="font-size: 10px;">
<a target="_blank" href="https://icons8.com/icon/13441/python">Python</a> icon by <a target="_blank" href="https://icons8.com">Icons8</a>
<br/>
DHT <a target="_blank" href="https://sujithjay.com/public/DHT-Dynamo.png">visualization</a>
</div>
