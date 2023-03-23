---
layout: post
title:  "Checkbook"
date:   2020-02-17 08:00:00 -0600
subtitle: "Managing finances with Java Swing"
thumbnail: "/img/mainframe.PNG"
categories: java
tags: Java
technologies: java
---
At the start of my coding experience (high school, 2016), I started a "business game" that I soon used to track my income and expenses. I used this program for ~3 years in college to manage my finances. Written in Java <img src="/img/java.png" style="width: 32px; height: 32px; display: inline-block;"/> and Java Swing for the UI.

<img src="/img/github.png" style="width: 32px; height: 32px; display: inline-block;"/> [Public GitHub repo](https://github.com/tfreese56/checkbook) for this project.

Below is the original goal I wrote for this program:

> This application is built for taking transactions off of a regular checkbook page to analyze, organize, and visualize them. My intended use of this program is to provide a tool to maintain your financial situation by creating an interactive checkbook. This application uses your transaction data to answer any inquiries you may have about your money at any point in time.

### Program
As you entered transactions, they would appear to the right in a queue ready to be saved.

<img src="/img/mainframe.PNG" alt="main frame"/>

The start of the inquiries I mentioned; the bargraph was printed out using a for loop. The Y axis was precalculated using the amounts queried.

<img src="/img/bargraph.png" alt="bargraph"/>

Finally, digging a little deeper, I put together "reports" like following.

<img src="/img/analysis.PNG" alt="analysis"/>

### Usage Summary
* View transactions in the IO tab as you add them
* Save transactions in a central database
* Load transactions from any period in time OR query ALL transactions stored for:
  * Displaying simple transaction data in the "Load Results" tab
  * View a bar graph of categorized amounts
  * View profit
  * Read a monthly analysis derived from transaction data
* Bring up transactions containing a key word
* Edit transactions you may have messed up on entry
* Delete unneeded transactions 

### Ending
I learned a ton back then developing this project. I taught myself Java in hs and this was the product over time of that experience. At first, the data storage was simply text file IO; then it upgraded to a remote (self hosted) MySQL database after Database Management Systems in college. 

When my future scope came to this:

> Thinking ahead, I would like to derive more information from transactions. Questions I want this program to answer are, "What period of time did I make the most money?" "When do I spend the most on fuel/food/entertainment/needs?" "Where did I spend most of my money the last three months?" Another future addition is a better graphing utility (possibly third party applications) that creates more visually appealing graphs of the data.

I eventually concluded it was time for a different environment. Could the program have answered these questions, yes, but I thought the UI could improve the most. Gratefully, I *still* have each transaction saved since I started this. They've all made it through each migration of code and I can still query them today.

Thanks for taking the time to read!

Best.

##### Links
<div style="font-size: 10px;">
<a target="_blank" href="https://icons8.com/icon/13679/java">Java</a> icon by <a target="_blank" href="https://icons8.com">Icons8</a>
<br/>
<a target="_blank" href="https://icons8.com/icon/AZOZNnY73haj/github">GitHub</a> icon by <a target="_blank" href="https://icons8.com">Icons8</a>
</div>
