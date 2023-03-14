---
layout: post
title:  "Distributed Hash Table"
date:   2021-04-20 08:00:00 -0600
categories: python 
---
<link rel="stylesheet" href="/css/styles.css">
In Networks & Distributed Systems class, we were assigned to write a Distributed Hash Table (DHT) in Python <img src="/img/python.png" class="inline-icon"/>. The DHT protocol was provided by [Dr. Nathan Backman](https://www.bvu.edu/academics/faculty/nathan-backman) of [Buena Vista University](https://www.bvu.edu/).

# DHT
<img src="/img/chord-route.png" alt="DHT chord route" style="width: 35%; height: 35%; margin-bottom: 20px;"/>
This is *easily* in my top three favorite projects/assignments at BVU. On the home page, I mention mind-bending ideas. Experiencing and implementing this concept (the DHT) is precisely the moment I'm referring to. Props to Professor Backman for this.

Post college, I spent time refining the code and creating a Python <img src="/img/python.png" class="inline-icon"/> interface to the main DHT code. The interface is basically an API to any DHT provided by an "IP:PORT" combo.\*

\* Given it uses Professor Backman's protocol.

### Best part
Implementing the ownership algorithm (how the nodes determine who owns a specific hash) was the most challenging but rewarding piece.

## So, what is it??
### TL;DR
Decentralized storage using ( Key, Value ) pairs.

### Usage
The entire ring is reachable from any entry point (a node [computer participating in the DHT]). Then the user can store ( Key, Value ) pairs within the system that can be retrieved again later.

As mentioned on the [Chat Channels](/python/2020/05/13/chat-channels.html) page, benefits of a DHT are:
* Data persists as long as the DHT does
  * being decentralized, data shifts owners as nodes enter and exit the DHT
* Decentralization means no single computer is in charge of the system
  * nodes communicate and adjust ownership accordingly
* K-Safety (not implemented here)
  * storing backups of data with predecessors in case sudden removal of a node

### Explanation
I think [Hazelcast's](https://hazelcast.com/glossary/distributed-hash-table/) definition explains it best:

<img src="/img/hazelcast-expl.png" alt="Hazelcast dht explanation"/>

### Visualization 
<img src="/img/DHT_VIS.png" alt="dht visualization"/>

## Data Types
Data types our DHT adhered to.
* Key/hash: SHA-1, 160-bit, 20-byte UTF-8
  * Key used to lookup values in the DHT
* valSize: 8-byte, big endian
  * valSize is the size of the data being stored
* peerAddress: \[4-byte ip\]\[2-byte port big endian\]
* peerHash/key: SHA-1 hash of “IP:Port”
  * Example: SHA1( "192.168.0.1:5000" )

## Operations
A few of our DHT operations:
```
Insert - Add/update/replace an item to/in the DHT
Remove - Removes an item from the DHT
Get - Retrieves an item from the DHT
Exists - Check to see if an item exists within the DHT
Owns - Asks a peer who they know to be the nearest owner to a key
...
```

### Thanks
Thanks for reading about my experience with the Distributed Hash Table. 

Best.

##### Links
<div style="font-size: 10px;">
<a target="_blank" href="https://icons8.com/icon/13441/python">Python</a> icon by <a target="_blank" href="https://icons8.com">Icons8</a>
<br/>
DHT chord <a target="_blank" href="https://tristanpenman.com/blog/images/implementing-a-dht-with-scala-and-akka/chord-route@2x.png">visualization</a>
<br/>
DHT node <a target="_blank" href="https://sujithjay.com/public/DHT-Dynamo.png">visualization</a>
</div>
