---
title: "Exchange Of Ads"
categories:
  - mobile-advertisement
header:
  image: /assets/images/post3-2021-03-20/ad-exchange-header.png
  teaser: /assets/images/post3-2021-03-20/ad-exchange-teaser.png
tags:
  - mobile
  - advertisement
  - adtech
---

Ad Exchanges are technology platforms that serve as an open digital marketplace.

They are a huge part of the advertisement process since, as the name suggests, they exchange ads between SSPs, DSPs and Ad Networks.


## How an AdExchange works

As stated before, an Ad Exchange is a technology platform that's used as an open digital marketplace.
What that means is essentially that this platform lets advertisers and publisher buy and sell
advertising space, mostly through real-time auctions, thus being labeled as <b style="color:#00adb5">RTB</b> - Real Time Bidding. 

Since the auctions happen in fractions of a second, the bidding is done programmatically.
The auction must happen as fast as possible, since the publisher needs to fill its mobile application's ad space 
in order to display it to the user of the application and be paid for the impression (showing the ad to the user).

### The auction

So what exactly happens during an ad impression (ad space) auction?

Well, it's much like an actual auction, with minor differences:
- it happens really really fast; fraction of a second
- no human being is part of it

So how does the auction happen if no human is part of it?

There are certain algorithms of potential auction participants that make a decision whether a certain impression is
worth bidding on. Not all impressions suit the advertiser that could bid on it.  

<figure class="align-center">
  <img src="/assets/images/post3-2021-03-20/ad-exchange-auction.png" alt="Ad Exchange Auction">
  <figcaption>Ad Exchange Auction</figcaption>
</figure>

#### Context

Let's say the ad impression that advertisers could bid on happens:
- in Fruit Ninja game
- on a rewarded video ad space
- on an Android device
- in Uzbekistan
- to a 14 year old
- at 5:30 in the morning

Why would an advertiser, that has a Michelin tire ad prepared for the end user, 
actually bid on such an ad if the end user doesn't even have a driver's license, not to mention an actual car.

The upper example doesn't even make sense for such an advertiser, 
that's why advertisers feed <b style="color:#00adb5">target bidding parameters</b> to the earlier mentioned bidding algorithms through DSP dashboards.
The DSP dashboards then forwards this information to the Ad Exchange for a specific bid.
With this the advertisers achieve a smaller targeted audience, raising the <b style="color:#00adb5">impact</b> of the client's (Michelin's) advertisement on the end user.

#### Price

Each auction participant sets a price they would pay for the ad space in question and the highest bid wins the whole auction.

Prices between auction participants can vary based on their perception of the auction ad space's relevance to their <b style="color:#00adb5">target audience</b>
and the impact the ad creative in this specific ad space can have on the end user.

There is also one parameter that can be set from the publisher's side, called <b style="color:#00adb5">floor price</b> 
which actually sets the lowest limit the <b style="color:#00adb5">publisher</b> is still willing to sell his ad space for.<br>
If no bid has a higher price than the floor price, so called <b style="color:#00adb5">no-fill</b> occurs, 
which means that no advertiser filled the ad space and consequentially there will be no ad impression.  

###### first-price vs second-price auction

Auction winning bid prices are determined based on either of two models; 
<b style="color:#00adb5">first-price</b> and <b style="color:#00adb5">second-price</b> auctions.

Up until now Ad Exchanges mostly used second-price auctions and lately the push towards first-price model
was driven by major players such as Google, Rubicon, AppNexus. The transition started to happen mid 2019.

The transition towards a first-price auction is an improvement to the programmatic advertising ecosystem, 
as it will increase transparency across the industry and simplify yield management for publishers.

The difference between the two is actually in the <b style="color:#00adb5">price paid</b>.
First-price auction means that the winner of the auctions pays the price he won the auction with,
but with the second-price model the winner pays the price of the bid that came in second place.

<figure class="align-center">
  <img src="/assets/images/post3-2021-03-20/first-vs-second-price.png" alt="First-price vs second-price auction">
  <figcaption>First-price vs second-price auction</figcaption>
</figure>

Together with the publisher's floor price the difference between second- and first-price auctions can be seen from the following example:<br>
Let's say the highest bid is 4$, the bid price of the second bid is 2$ and the publisher has set the floor price of 3$.

<b style="color:#00adb5">First-price auction</b>: the advertiser with the highest bid gets to pay 4$ to the publisher

<b style="color:#00adb5">Second-price auction</b>: the advertiser with the highest bid gets to pay 3$ to the publisher, as the floor price is __higher__ than the second bid.

If the winning bid would remain 4$, the second bid would be 3$ and the floor price would be set to 2$. <br>
<b style="color:#00adb5">Second-price auction</b>: the advertiser with the highest bid gets to pay 3$ to the publisher, as the second bid is __higher__ than the floor price.

Well to be exact, within the second-price auction the winning bidder actually pays the <b style="color:#00adb5">second bid price + 0.01$</b>.

#### Aftermath

After the auction, all the participants are notified about the result. No one gets to know any details other than
whether they did or didn't win the bid.

The participants that lost, either they were outbid by the competition or they didn't pass the floor price limit, get a so called <b style="color:#00adb5">lose notice</b>.<br>
The one that bid the highest _usually_ gets displayed to the end user through the current ad space. 

## Unfair advantages

Like elsewhere, there are unfair advantages present in the digital advertising sphere. Mostly it's from Google's side as it
has a monopoly over this field and through it's ad exchange platform solution, <b style="color:#00adb5">Ad Manager</b>, achieves this unfair advantage.

Prior to switching to first-price auctions, Google's Ad Manager operated through the second-price auction model.<br> 
So what could Google be doing through Ad Manager since the auction should be an unified process without any special interruptions in between?

Well Google figured out that since it has such a huge demand under its belt and no one dares to overthrow it, it could do a tad shady thing.<br>
Instead of participating in the auction like all other participants, it <b style="color:#00adb5">waited</b> for all the participants to bid to have a look at all their prices, 
unlike other participants that had no idea about it. 


<figure class="align-center">
  <img src="/assets/images/post3-2021-03-20/ad-manager.png" alt="Ad Manager">
  <figcaption>Google's Ad Manager</figcaption>
</figure>

With <b style="color:#00adb5">last look</b>, Google could essentially out-bid advertisers of an impression by a very small margin.

## Ad Exchange vs Header Bidding

So let's briefly compare the hot topic, mobile Header Bidding, and the Ad Exchange.

Here's a wonderful image comparing these two:

<figure class="align-center">
  <img src="/assets/images/post3-2021-03-20/ad-exchange-vs-header-bidding.png" alt="Ad Exchange Bidding vs Header Bidding">
  <figcaption>Ad Exchange vs Header Bidding</figcaption>
</figure>

Header Bidding moves the actual bidding from Ad Exchange's server to <b style="color:#00adb5">publisher's</b> server side, enabling the publisher
to offer bidding to <b style="color:#00adb5">several</b> Ad Exchanges and SSPs.

A bit more on the Header Bidding approach, can be seen in one of the following posts that will focus solely on
the idea and technology behind it.

## Conclusion

Ad Exchange connects the supply, SSP, and demand, DSP, sides and enables them to participate in real time auctions
through <b style="color:#00adb5">programmatic</b> advertising.

With the rise of <b style="color:#00adb5">Header Bidding</b>, the bidding is being moved from the third party Ad Exchange side, to publisher's side,
minimising Google's tricks and enabling more transparency for ad providers.

---

<center style="color:#00adb5"><b><i>Thanks for reading!</i></b></center> 
