---
layout: post
title:  "Processing a Stream of Endless Data"
subtitle: "Building a stream processor"
thumbnail: "/img/data-stream.gif"
date:   2021-03-26 08:00:00 -0600
categories: java 
tags: Showcase Java
technologies: java
---
<link rel="stylesheet" href="/css/styles.css">
Inspired by my work in Information Security with <img src="/img/splunk.png" id="splunk-icon"/>, I built a Stream Processor for my capstone project.

My Stream Processor can handle a continuous stream of events, parse, then alert on a desired event in the stream.

Extensible code was one of my main focuses developing this project. The main extensible part of the finished project is the workflow processing code. With this, one can create a workflow of operators that fit their unique stream of data.

Programming language: Java <img src="/img/java.png" class="inline-icon" style="width: 64px; height: 64px;"/>

## Stream Processors
What are Stream Processors? They are meant for data that essentially could never end.

Think of the following\*: 

<img src="/img/sp-use.png" alt="sp use" style="width: 43%; height: 43%;"/>


## Design
The following visualization\* best fits my Stream Processor design. A stream of data sent to parallel nodes sending output to operators.

<img src="/img/sp-design.png" alt="sp design" style="width: 50%; height: 50%;"/>

## Capabilities
My Stream Processor has the following capabilities\*:

<img src="/img/sp-summary.png" alt="sp summary"/>

### Ingest Data from Anywhere
Data can be retrieved from anywhere data is generated. The only requirement is it needs to be ingested into the Stream Processor from the [Stream Emitter](/java/2021/03/04/stream-emitter.html). Structured or unstructured, what matters is getting the data to the Stream Processor. From there, it is up to the processing engine to process it.

### Arbitrary Processing Code
A developer can write their own workflow using this Stream Processor.

What does arbitrary processing code mean, *exactly*?

<img src="/img/thermometer.png" class="inline-icon" style="width: 32px; height: 32px;"/> Imagine *I* want to process and alert on significant conditions in temperature sensors scattered about my farm.

<img src="/img/fish.png" class="inline-icon" style="width: 32px; height: 32px;"/> *You* may want to process how many fish swim by your laser sensor in the lake on two different sides on average per hour. 

Our needs are not the same, but we can *both* extend and use my Stream Processor to handle our scenarios. The code we write to process our data will not be the same.

### Parallel Tasks
My Stream Processor has the ability to have concurrent threads working on the same task. Each one would be assigned data that came into the Stream Processor. Working with out of order data was out of the scope of this project, although, it would be a concern for a real scenario.

### Operators
Operators are the nodes working on processing the data and can be chained in a series to extend the processing chain. The processing chain is modeled as the workflow of data processing.

<img src="/img/fish.png" class="inline-icon" style="width: 32px; height: 32px;"/> You may want to keep track of how many fish in total you've seen. At some point in your workflow, you'd write an operator keeping track of simply that.

### Search For Significant Conditions
Operators are capable of being written to alert (e.g. send notifications or take action themselves) on a significant event/set of events occuring in a stream. 

<img src="/img/thermometer.png" class="inline-icon" style="width: 32px; height: 32px;"/> I may want to know if the temperature falls below a threshold. I could write an Operator to watch for this.

<img src="/img/fish.png" class="inline-icon" style="width: 32px; height: 32px;"/> In the lake, you might want to know if you see more than 30 fish per hour swimming by your sensor. An operator could be written to listen for such an event in the stream.

## Thanks
Thanks for reading about my Stream Processing experience. This is one of my biggest accomplishments so far.

Best.

##### Links
\**(taken from my presentation at [Buena Vista University](https://www.bvu.edu/))*
<div style="font-size: 10px;">
<br/>
<a target="_blank" href="https://icons8.com/icon/49188/splunk">Splunk</a> icon by <a target="_blank" href="https://icons8.com">Icons8</a>
<br/>
<a target="_blank" href="https://icons8.com/icon/13679/java">Java</a> icon by <a target="_blank" href="https://icons8.com">Icons8</a>
<br/>
<a target="_blank" href="https://icons8.com/icon/poFZHQZ-CjsC/thermometer">Thermometer</a> icon by <a target="_blank" href="https://icons8.com">Icons8</a>
<br/>
<a target="_blank" href="https://icons8.com/icon/16040/fish">Fish</a> icon by <a target="_blank" href="https://icons8.com">Icons8</a>
</div>

<style>
#splunk-icon {
    display: inline-block; 
    vertical-align: middle; 
    width: 101px; height: 40px;
}
</style>
