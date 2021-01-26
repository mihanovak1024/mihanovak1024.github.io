---
title: "Broccoli"
excerpt: "Scraper for Slovenian real estates with BROKEr Android app"
header:
  image: /assets/images/portfolio/real-estate-scraper/broker-screens.png
  teaser: assets/images/portfolio/real-estate-scraper/teaser.png
sidebar:
  - title: "Languages"
    text: "Java, Kotlin"
  - title: "Backend"
    text: "Wildfly/JBoss on DigitalOcean Droplet, JAX-RS, EclipseLink JPA, PostgreSQL, JSoup, tmux, Bash, Cron"
  - title: "Client"
    text: "Android native app - Kotlin, AndroidX, MVVM, OKHttp, Dagger2, ViewBinding, ConstraintLayout"
---

I was searching for an apartment, and I didn't really want to check for new real estates
every day since I'm kinda lazy and inconsistent, when it comes to this stuff.

I came up with a quite simple solution; 
<br>instead of checking for new ones 
I could get notified when something that suits my preferences comes to market.
<br><i><font size="2">For all the fellow programmers out there; you know, the good old Observer/Observable pattern.</font></i>

So I created my very own solution that did exactly that; a scraper called <b style="color:#00adb5">Broccoli</b> (wanted a random name, I think I didn't disappoint).

## Broccoli

<figure style="width: 80px; height:80px;margin-top:0px; margin-bottom:0px" class="align-left">
  <img src="/assets/images/portfolio/real-estate-scraper/broccoli-icon.png" alt="Broker Icon">
</figure> 

<b style="color:#00adb5">Broccoli</b> is a server-side brains of the project.
It contains logic for creating real estate filters, scraping data and retrieving data from the database.

#### API

Backend API receives filters based on my preferences; for example:
<figure class="align-center">
  <img src="/assets/images/portfolio/real-estate-scraper/broccoli-filter1.png" alt="Broccoli Field Filter">
  <figcaption>Real Estate Filter for Fields [type=2]</figcaption>
</figure> 

<figure class="align-center">
  <img src="/assets/images/portfolio/real-estate-scraper/broccoli-filter2.png" alt="Broccoli Flat Filter">
  <figcaption>Real Estate Filter for Flats [type=3]</figcaption>
</figure> 

The server was running on [DigitalOcean's Droplet](https://www.digitalocean.com/products/droplets/) and I would SSH to it to check if everything works fine 
and to optimise the code by transferring it from my local machine.

API returns the data and pushes the config to the servers; all in JSON format.

Through the API I can:
- get the data to my mobile app
- check the data via Postman
- check all my filters
- create new filters based on my preferences (as seen from the upper two screenshots)

and I also wanted to check how the COVID-19 affects the prices of real estates, so the API can also offer me to:  
- create filters for real estate prices statistics
- get data for real estate prices statistics

Unfortunately nothing has been done with this statistic data afterwards.

#### Architecture

<figure class="align-center">
  <img src="/assets/images/portfolio/real-estate-scraper/broccoli-architecture.png" alt="Broccoli Architecture">
  <figcaption>Broccoli Architecture</figcaption>
</figure> 

## BROKEr

<figure style="width: 80px; height:80px;margin-top:0px; margin-bottom:0px" class="align-left">
  <img src="/assets/images/portfolio/real-estate-scraper/broker-icon.png" alt="Broker Icon">
</figure> 

<b style="color:#00adb5">BROKEr</b> is an Android app that was created as a client for the <b style="color:#00adb5">Broccoli</b> server.
It polls the data from the server and keeps track of already seen real estates.

#### Home Screen
The Home screen was initially meant for several types of data, not just real estates; data like cars, clothes,... 
Which explains the pretty much empty main screen.

The screen contains info about the number of not yet defined real estates; liked or archived.

<figure class="align-center">
  <img src="/assets/images/portfolio/real-estate-scraper/broker-screen-home.png" alt="Home Screen">
  <figcaption>Home Screen</figcaption>
</figure>

#### Nepremičnine Screen

<figure class="align-center">
  <img src="/assets/images/portfolio/real-estate-scraper/broker-screen-nepremicnine.png" alt="Nepremicnine Screen">
  <figcaption>Nepremičnine Screen</figcaption>
</figure> 

This screen contains three tabs:
- first one (<b style="color:#00adb5">archive</b> icon) contains archived real estates, that I didn't really like
- middle one (<b style="color:#00adb5">plus</b> icon) contains the new or not yet defined real estates
- third one (<b style="color:#00adb5">heart</b> icon) contains the real estates that I liked

<figure style="width:400px" class="align-center">
  <img src="/assets/images/portfolio/real-estate-scraper/real-estate-sample.png" alt="Real Estate Sample">
  <figcaption>Real Estate Sample</figcaption>
</figure> 

Each real estate has the information about:
- price (<b style="color:#00adb5">€</b>)
- price per square meter (<b style="color:#00adb5">€/m<sup>2</sup></b>)
- size in square meters (<b style="color:#00adb5">m<sup>2</sup></b>)
- build year
- short description

Click on a specific real estate takes you to the site it was published on, 
so you can check all the other information the real estate ad offers.

## RIP
The whole thing was running for half a year.

I shut down the server because certain real estate sites blocked my IP since they probably detected my program was not an actual user.
I did only around 5 requests per day, so something else must have triggered the algorithms to block my IP. 
As I've heard quite some people had similar issues while scraping these data for personal use, so I was not that disappointed.

Though the scraping of real estate auctions on the other site still works as intended.

The Droplet was shut down, but the experience of my own backend server lives on. 