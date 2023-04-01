---
layout: post
title:  "Checkbook Online"
subtitle: "Django-Python website for managing finances"
thumbnail: "/img/tfcb-main.png"
date:   2022-05-30 08:00:00 -0600
categories: python 
tags: Python
technologies: python django
---
Checkbook Online is my previous project, [Checkbook](/java/2020/02/17/checkbook.html), but a website version. I wanted to manage my money from a desktop or mobile device from anywhere. Thus, I migrated my Checkbook project to a Django-Python web application.

Technical specifics: Two docker containers ran in the production environment, one for running Checkbook and one for a MySQL database.

I used self-signed certificates with Nginx to secure the communication with TLSv1.3.

## Technologies
<div style="display: flex; flex-direction: row; flex-wrap: wrap;">
<img src="/img/django.png" alt="django logo"/>
<img src="/img/python.png" alt="python logo"/>
<img src="/img/docker.png" alt="docker logo"/>
<img src="/img/mysql.png" alt="mysql logo"/>
</div>
<div style="display: flex; align-items: center; justify-content: center; flex-wrap: wrap;">
<div style="display: flex; align-items: center; justify-content: center;">
<img src="/img/uwsgi-small.png" alt="uwsgi logo" style="margin: 5px; width: 84px; height: 45px;"/>
<img src="/img/nginx.png" alt="nginx logo"/>
<img src="/img/encrypt.png" alt="encrypt logo"/>
</div>
</div>

## Web app

### Index page; (moving background on actual site)

<img src="/img/tfcb-main.png" alt="tfcb main"/>

### Home page; shows basic current information

<img src="/img/tfcb-home.png" alt="tfcb home"/>

### Search page; query transactions given criteria
*Amounts and descriptions redacted.*

<img src="/img/tfcb-search.png" alt="tfcb search"/>

### Search page results
*Amounts, descriptions, and dates redacted.*

The following statistics could be generated over a specified time period.
The number of transactions found is also reported.
```
Greatest income & Largest expense

Average gain/loss per transaction - divide profit out amongst all transactions

Min/Max Subarrays - calculate (using min/max algorithm) the time period where the greatest gain and largest loss occurred
```

<img src="/img/tfcb-search-results.png" alt="tfcb search results"/>


## Demise

Recently (2023), I started using [GnuCash](https://www.gnucash.org/). GnuCash replaced this web application for managing my finances. 

GnuCash can do it all, more than I ever wanted in my program. So, I chose not to reinvent the wheel and migrate to GnuCash.

I've successfully kept all of my transaction data since 2018 when I started managing my finances in college with [Checkbook](/java/2020/02/17/checkbook.html). I had over 1,000 transactions stored at the time of moving (Janurary 2023).


### Thanks
Thank you for taking the time to read about my Checkbook online experience!

Best.

##### Links
<div style="font-size: 10px;">
<a target="_blank" href="https://icons8.com/icon/XPdRFanRZtNK/django">Django</a> icon by <a target="_blank" href="https://icons8.com">Icons8</a>
<br/>
<a target="_blank" href="https://icons8.com/icon/13441/python">Python</a> icon by <a target="_blank" href="https://icons8.com">Icons8</a>
<br/>
<a target="_blank" href="https://icons8.com/icon/cdYUlRaag9G9/docker">Docker</a> icon by <a target="_blank" href="https://icons8.com">Icons8</a>
<br/>
<a target="_blank" href="https://icons8.com/icon/UFXRpPFebwa2/mysql-logo">MySQL Logo</a> icon by <a target="_blank" href="https://icons8.com">Icons8</a>
<br/>
<a target="_blank" href="https://www.nginx.com/wp-content/uploads/2018/08/NGINX-logo-rgb-large.png">Nginx</a>
<br/>
<a target="_blank" href="https://pythonist.ru/wp-content/uploads/2020/05/uwsgi.jpg">uWSGI</a>
</div>
