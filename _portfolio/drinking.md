---
title: "DrinKing"
excerpt: "A self-service beer machine with mobile app payment system"
header:
  image: /assets/images/portfolio/drinking/header.png
  teaser: assets/images/portfolio/drinking/teaser.png
sidebar:
  - title: "Languages"
    text: "Java, Kotlin, Python, HTML/CSS/JS"
  - title: "Backend"
    text: "Wildfly/JBoss on DigitalOcean Droplet, JAX-RS, EclipseLink JPA, PostgreSQL"
  - title: "Client mobile"
    text: "Android native app - Kotlin, AndroidX, MVVM, OKHttp, Dagger2, ViewBinding, ConstraintLayout"
  - title: "Client machine"
    text: "Python Flask server, <br>Javascript/HTML/CSS Frontend, <br>Python RBPi --- Arduino communication"
  - title: "Hours ~200"
---

Two of my friends, <b style="color:#00adb5">Tine</b> and <b style="color:#00adb5">Žiga</b>, and me started to work on a project for self-service drinks.
We came up with the idea of DrinKing --- a self-service beer machine that lets you pour beer and pay instantly.
The project is mostly in Slovenian language, since it was meant for the domestic marketplace.

Although the project didn't come to a finish, I'm pretty proud from my side as I did my part.

<figure class="align-center">
  <img src="/assets/images/portfolio/drinking/drinking-demo.gif" alt="DrinKing Demo">
  <figcaption>DrinKing Demo</figcaption>
</figure> 

## Flow

The initial draft of the flow was designed in a pub where brainstormed the ideas.

This was one of the initial mock flows and we altered it a bit during the whole implementation process: 
<figure class="align-center">
  <img src="/assets/images/portfolio/drinking/flow.png" alt="DrinKing Flow">
  <figcaption>DrinKing Flow Mock (Slovenian)</figcaption>
</figure>

The whole flow is designed to make be as simple as possible for the end user.

The main idea is that the user would pour his own drink and pay with the application (NFC/QR/button) or an RFID/NFC card/key.

## Building

The project's building process consisted of each member doing his own role at home:
- <b style="color:#00adb5">I</b> was responsible for the Backend, RBPi logic and Frontend
- <b style="color:#00adb5">Tine</b> was responsible for providing the beer machine, sensors and valves
- <b style="color:#00adb5">Žiga</b> was responsible for electronics; Arduino connection with sensors and valves

One day we gathered in <b style="color:#00adb5">Tine's</b> garage to test the initial flow.
The building of the demo prototype looked liked we'd be one of those garage companies that went viral such as Amazon, Apple, ...

The prototype consisted of:
- Beer machine
- Arduino
- RaspberryPi
- Computer for Arduino
- Computer for server
- a few cans of beer for motivation 

<figure class="align-center">
  <img src="/assets/images/portfolio/drinking/garage1.jpg" alt="DrinKing Garage 1">
  <figcaption>DrinKing Testing in a Garage</figcaption>
</figure>

<figure class="align-center">
  <img src="/assets/images/portfolio/drinking/garage2.jpg" alt="DrinKing Garage 1">
  <figcaption>DrinKing Testing in a Garage</figcaption>
</figure>

So the test went something like this:
1. Arduino read the RFID key
2. It sent the test data (millilitres poured) to RaspberryPi (RBPi)
3. RBPi displayed everything on the monitor via a simple webapp
4. After the 300 millilitres were "poured" the RBPi would make a payment to the server
5. The server received the payment and verified it

but to be a tad more visual, here's a gif of the test:

<figure style="width:300px" class="align-center">
  <img src="/assets/images/portfolio/drinking/test-demo.gif" alt="DrinKing Test Demo">
  <figcaption>DrinKing Testing Demo</figcaption>
</figure>

## Technical

The <b style="color:#00adb5">backend API</b> could:
- add new users
- add currency to an existing user
- add new bartenders/responsible staff
- get data for existing users
- get drinking statistics for existing users
<br>and more

<b style="color:#00adb5">Frontend</b> was quite nicely done, since I'm not such a designery-type of guy:
 
<figure class="align-center">
  <img src="/assets/images/portfolio/drinking/frontend-display.png" alt="DrinKing Frontend Sample">
  <figcaption>DrinKing Frontend Sample</figcaption>
</figure>

It presents to the user stuff like:
- quantity of poured beer in litres
- how much he'll need to pay for the beer
- how much currency he still has on his account

## RIP

Unfortunately the motivation fell, and we didn't even do a prototype,
but the server and frontend were mostly finished, so in that sense I'm not really disappointed. 
The project was really fun to build, and I poured (pun intended) in around 200 hours.

Even though we didn't pull it through to an end, I learned quite a lot of stuff.