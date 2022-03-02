---
title: "Compose My Inventory"
excerpt: "Building an inventory app Pogley with Jetpack Compose and newest Android development best practices."
categories:
  - learning
header:
  image: /assets/images/post7-2022-03-02/header.png
  teaser: /assets/images/post7-2022-03-02/teaser.png
tags:
  - learning
---

Recently Google's own declarative programming paradigm implementation for Android development, Jetpack Compose
recently (February 2022) came to a [stable 1.1 release](https://android-developers.googleblog.com/2022/02/jetpack-compose-11-now-stable.html) 
(first [1.0 stable release](https://android-developers.googleblog.com/2021/07/jetpack-compose-announcement.html) in July 2021), so I decided to give it a try and see what all the fuss is about.   

---

# Pogley

To test Compose on a "real" life project, I created an app called _Pogley_. 
The name is a derivation from a Slovenian word "poglej" which means "check it out" and it's intended to be used in
the following context; "_check out_ which and how many items we have in our warehouse".
It's an inventory/stock tracking app for small businesses (plumbers, carpenters) and personal workshops that tracks all items you own,
so you can easily asses what you need to buy when you're shopping for material (screws, iron bars, pipes, ...)
and so you can keep track which project/client consumed which items from your stock.

I've made it open source, so it's available on [my GitHub](https://github.com/mihanovak1024/pogley-android).

<figure class="align-center">
  <img src="/assets/images/post7-2022-03-02/pogley_mobile.jpg" alt="Pogley App">
</figure>   

# Project Intentions

I wanted to check out how Jetpack Compose works; how it changes the UI element creation, 
what some benefits are and what are the current drawbacks.

Apart from that, I also wished to check out some of the Google IO 2021 announcements (Android 12):
- Material You (Material3)
- Splash Screen Animations
- Unified Test Platform (UTP)

<figure class="align-center">
  <img src="/assets/images/post7-2022-03-02/googleio_material3.jpg" alt="Google IO 2021 Material You">
  <figcaption style="text-align:center">Google IO 2021 Material You</figcaption>
</figure>   

In 2021 LiveData was pushed a bit to the sidelines and Kotlin Flows took the spotlight. 
Why the shift? LiveData handled data exposure (to UI layer) and lifecycle awareness really well, 
but it is not part of the Kotlin programming language, rather part of the Android ecosystem. 
Kotlin Flows, on the other hand, fit perfectly into Compose reactive model.

LiveData is not yet deprecated, but Kotlin Flows are recommended to be used instead.

# Project Architecture

I decided to take the route of Clean Architecture approach from [Uncle Bob](https://en.wikipedia.org/wiki/Robert_C._Martin)
which is quite in line with Android best practices; which state that you should have UI, Domain and Data layers in your app.

Basically the bridges between the layers are:
- For communication between UI and Domain layer, you use Android's ViewModel
- For communication within the Domain layer, you use UseCases which communicate with Repository
- For communication between Domain and Data layer, you use Repository, where the interface resides in the Domain layer and the implementation in the Data layer
- For communication within the Data layer, you use DataSources which communicate directly with either RemoteDataSource (webservice) or LocalDataSource (database, file)

This makes the whole project easier to test, since the Separation of Concerns rule is perfectly used
and each bigger component mentioned above can be replaced with with a Fake test component.

<figure class="align-center">
  <a href="/assets/images/post7-2022-03-02/pogley_architecture.png"> <img src="/assets/images/post7-2022-03-02/pogley_architecture.png" alt="Pogley Architecture"> </a>
  <figcaption style="text-align:center">Pogley Architecture Diagram</figcaption>
</figure>         

# Jetpack Compose Thoughts

I kind of prefer the declarative approach introduced to Android development with Compose.
Designing the UI through XML was always a bit off for me.

### Benefits
You can write Composable components in a Component-like structure and can abstract it to a large extent
in a very OOP-kind of way. 
- Composable components can be provided through a parameter to other Composables, 
enabling you to write wrapper components with a specific look & feel
- You can provide lambda functions for click handlers, modifiers for style,... to child components
- You can have better state management through the State object introduced in Android
- You can build the Components in isolation and have an instant preview of them through @Preview annotation

### Drawbacks
However you need to be a bit more cautious when designing a screen. The whole structure can quite quickly become
unreadable and unmanageable. To tackle this problem, you should know when to cut a component and create it within its own file.

You need to get used to what features are included within the Composable's Modifiers and what the Composable provides itself.
For example some components take onClick listeners as an argument, others need to define a Modifier.clickable lambda.

The order of Modifier values is important and can change your Composable's look greatly, so you have to be careful how you stack them.

---

# Project TODOs

There are still several things left to be done, but I decided to start writing this blog post before I forget stuff. 

### Android       

I'll have to add some pretty beautiful designs, to see all aspects of Material3.
It sucks a bit since I'm a bad brainstormer for UI, so I'll probably combine the design of several other apps/websites.

I still need to figure out a cool logo for Pogley, to make a meaningful splash screen animation. 
An option that was also introduced during IO 2021.

I'll need to get my hands dirty with Unit, Integration and Instrumental tests, to see how easy it is to test Composable components.

### Pogley

A few things are on top of my mind:
- Project (hobby, for a client) definition and all the InventoryItems that were consumed by each
- Shopping list fragment
- Project list fragment
- Various history lists
- Client contact list

and some things that would need a backend:
- Account
- Multiple account syncing (small business with several employees)
- Webapp dashboard
- Client scheduling through business website

I highly doubt I'll do everything from above and I don't know how long I'll stick to the project
since I'm actively job hunting currently, but I'll try my best.

It also depends if anyone will even find this useful for their case and 
I'd need to come up with how I'm going to monetise this app.

# Conclusion
I've learned quite some things while making this little thing and I'll probably learn quite some more, 
if I'll stick to it long enough.

Like I already mentioned, I'm not entirely sure how much effort I could put into this, 
since I currently have other priorities.


--- 

<center style="color:#00adb5"><b><i>Enjoy your day and best of luck in your future endeavours!</i></b></center> 
<center><img width="450px" src="https://c.tenor.com/_NV1QH1Ct8IAAAAC/goodbye-harrypotter.gif"/></center>