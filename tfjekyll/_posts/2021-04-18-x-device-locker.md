---
layout: post
title:  "X Device Locker"
date:   2021-04-18 08:00:00 -0600
subtitle: "Cross platform password storage"
thumbnail: "/img/ionic-small.png"
categories: ionic 
---
X Device Locker is an app storing ( Key, Value ) pairs where the Value is encrypted using the user's main password. The original intention was for a user to have a completely local, secure password storage for their online services.

Technologies: 
<div style="display: flex; align-items: center; flex-direction: row; flex-wrap: wrap;">
<img src="/img/vue-small.png" alt="vue logo"/>
<img src="/img/ionic-small.png" alt="ionic logo"/>
<img src="/img/capacitor-small.png" alt="capacitor logo"/>
<img src="/img/typescript-small.png" alt="typescript logo"/>
<img src="/img/android-studio-logo.png" alt="android studio logo"/>
</div>

## First Step
First, a user sets a main password that is used to protect all the passwords to the services they input.

<img src="/img/tcloud-register.png" alt="x device locker register" class="screenshot"/>

## Login
What the user sees each time they reopen the app. User has the ability to change their main password and on doing so, each of their passowrds is re-encrypted with the new main password.

<img src="/img/tcloud-login.png" alt="x device locker login" class="screenshot"/>

## Services
An example list of services and passwords.

<img src="/img/tcloud-main.png" alt="x device locker main" class="screenshot"/>


### Thanks
I appreciate you visiting my X Device Locker project!

Best.

<style>
.screenshot {
    height: 40%;
    width: 40%;
}
</style>
