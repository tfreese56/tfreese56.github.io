---
layout: post
title:  "Stream Emitter"
date:   2021-03-04 08:00:00 -0600
categories: java 
---
<link rel="stylesheet" href="/css/styles.css">
Stream Emitter emits events logged from a desired source to the [Stream Processor](/java/2021/03/26/stream-processor.html).

I recommend reading about the [Stream Processor](/java/2021/03/26/stream-processor.html) first.

Programming language: Java <img src="/img/java.png" class="inline-icon" style="width: 64px; height: 64px;"/>

## Emitting Events
At the source of a data stream, the terminology I used to describe data being sent to the Stream Processor is called Events. Events are something that has happened in time. Data that has been generated in some way that ought to be processed.

The Stream Emitter also needs implemented by the developer. Here, the developer constructs the Event to be emitted to the Stream Processor. The Event data consists of data from the source like a timestamp, strings, numbers, or anything the source creates. 

Once an Event is created, the Stream Emitter will handle buffering and communicating with the Stream Processor. These two may be on the same machine or different machines. There can be several Stream Emitters emitting to one Stream Processor, or multiple. The two have a many to many relationship.

### Thanks
There's no much to this one, however, it warranted its own explanation!

Best.

##### Links
<div style="font-size: 10px;">
<a target="_blank" href="https://icons8.com/icon/13679/java">Java</a> icon by <a target="_blank" href="https://icons8.com">Icons8</a>
</div>
