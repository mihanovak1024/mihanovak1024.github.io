---
title: "Fejstbukov Parser"
excerpt: "Parser of Facebook posts for non-registered users"
header:
  image: /assets/images/portfolio/fejstbukov-parser/header.png
  teaser: assets/images/portfolio/fejstbukov-parser/teaser.png
sidebar:
  - title: "Languages"
    text: "HTML, Javascript"
---

As I was working on [Programmer's Guide Slovenia](/portfolio/programmers-guide-slovenia), which is
primarily an aggregated site of useful links from a Slovenian Developer Facebook group,
a number of requests slipped into my inbox asking if I could make the content visible for non-Facebook users.

<figure style="width:300px" class="align-center">
  <img src="/assets/images/portfolio/fejstbukov-parser/teaser.png" alt="Teaser Image">
</figure> 

After a brainstorming session I got quite interested in making a simple <b style="color:#00adb5">bookmarklet</b> that transformed
a Facebook post into a standalone HTML content preserving as much visual of an original post as possible.

Since it was a bit easier, I made the bookmarklet that transforms mobile (m.facebook.com) posts
into standalone HTML files that anyone can view.

It takes a mobile post:

<figure style="width:500px" class="align-center">
  <img src="/assets/images/portfolio/fejstbukov-parser/before.png" alt="Before Image">
</figure> 

and <b style="color:#00adb5">strips off</b>:
- javascript
- unnecessary HTML elements
- Facebook tracking URL wrappers
- current user data
<br>it also:
- <b style="color:#00adb5">replaces</b> relative with absolute Facebook URLs
- <b style="color:#00adb5">expands</b> all replies/comments

and spits everything out in a <b style="color:#00adb5">standalone HTML file</b> that looks like this:

<figure style="width:500px" class="align-center">
  <img src="/assets/images/portfolio/fejstbukov-parser/after.png" alt="After Image">
</figure> 

It's nothing fancy actually, since it operates on HTML DOM level.

The project is publicly available: <center style="color:#00adb5"><a href="https://github.com/mihanovak1024/fejstbukov-parser"><b>Fejstbukov Parser GitHub</b></a></center>

Since this <b style="color:#00adb5">violates</b> the Facebook Privacy Policies, the parser unfortunately was not used in any way.