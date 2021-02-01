---
title: "On eBay's Imperial Roman Coin market and History"
date: 2018-04-12T15:37:48+02:00
draft: false
categories:
- Research
tags:
- History
- Rome
- Numismatics
- Data
---

![EID MAR - An Ancient Roman Coin Commemorates the Assassination of Caesar](https://www.coinworld.com/images/default-source/news/eidmarsilverdenarius_together.jpg?sfvrsn=e459b4b5_0)

eBay's Ancient Roman Coin market is likely the largest market place for ancient coins in today's world.
Hundreds of thousands of ancient items exchanged hands through eBay's marketplace in the last year.

In the last 7 months, more than a quarter of a million coins  been listed on eBay alone.

Given the inherit historical value in ancient coins and my personal interest in them, I have been collecting data on every Roman Imperial Coin listing on eBay for the past seven months.

While the data is raw, and the collection continues as I'm writing this article, I found some of the collected data might be of interest to fans of history, data scientists, and collectors alike.

I am yet to draw conclusive points from the study, but have found enough information to personally consider it worth while.
 
Data science and history don't meet as often as they should, and I hope that with this study I could provide more evidence for the value in the combination.

## Data set

The numbers shared here are based on a data-set of 255,568 eBay listings in the [Roman Imperial Coins category](https://www.ebay.com/sch/Roman-Imperial-27-BC-476-AD-/4734/i.html?_fsrp=1). Out of which 19.6% sold and the rest died out without a buyer (and most likely re-listed).

## The market size

In terms of listings, an average of 194 new listings appear every day, with large spikes on Sundays, as seen in the following chart:

<iframe width="100%" height="800" frameborder="0" scrolling="no" src="./charts/coins-per-day.html"></iframe>

<italic><a href="./charts/coins-per-day.html" target="_blank">Open in full size</a><italic>

And in terms of money exchanging hands (i.e, the total sum of the price on sold listings per day) the following chart gives a perspective on the real net market size:

<iframe width="100%" height="800" frameborder="0" scrolling="no" src="./charts/market-share-per-day.html"></iframe>

<italic><a href="./charts/market-share-per-day.html" target="_blank">Open in full size</a><italic>

Note the spike on January 24, caused by a [single sell](http://www.ebay.com/itm/GALBA-69AD-Authentic-Ancient-Roman-Gold-Aureus-Ex-Mazzini-Collection-VERY-RARE-/222800214994) of $75,000.
The coin has since been re-listed. 

## Coin's Location

Coins exchange hands and resell on international scale, meaning coins originating from Italy or Spain might find their way to other countries and resold there.

As far as exporters of Imperial Roman Coins goes, United States takes the lead by far with 110,313 coins (almost half of the entire market).

But more traditional locations are also sparkling with listings, places like Spain (36,689 coins), and Ukraine (11,477 coins) are more in line with the traditional Imperial borders, as can be seen on the map:

<iframe width="100%" height="800" frameborder="0" scrolling="no" src="./charts/all-coins-per-sale-country.html"></iframe>

<italic><a href="./charts/all-coins-per-sale-country.html" target="_blank">Open in full size</a><italic>

### Disregarding the new world

It is clear that Imperial Roman Coins didn't end up in North America by Roman expansionism and rather by modern trade, and as such offer little historical value. 

Disregarding locations that were unknown to the Romans gives us a map more similar to what one might expect:

<iframe width="100%" height="800" frameborder="0" scrolling="no" src="./charts/coins-per-sale-country-not-us.html"></iframe>

<italic><a href="./charts/coins-per-sale-country-not-us.html" target="_blank">Open in full size</a><italic>
### Trajan on the map

Global all inclusive data might hide some delicate and interesting details.

When mapping up all the listing that were listed as minted under Trajan, a complete different image is shown, one where modern day Ukraine is the main exporter by a large margin:

<iframe width="100%" height="800" frameborder="0" scrolling="no" src="./charts/trajan-coins-per-sale-country-not-us.html"></iframe>

<italic><a href="./charts/trajan-coins-per-sale-country-not-us.html" target="_blank">Open in full size</a><italic>  

This is interesting, as Trajan is known for conquering the area known as Dacia, which is around modern day Ukraine. The correlation might be coincidental, but the symmetry is definitely interesting.

![Trajan Rome Map](http://www.bible-history.com/maps/roman_empire_color.gif)

This in comparison to the mapped listings of Augustus minted coins:

<iframe width="100%" height="800" frameborder="0" scrolling="no" src="./charts/augustus-coins-per-sale-country-not-us.html"></iframe>

<italic><a href="./charts/augustus-coins-per-sale-country-not-us.html" target="_blank">Open in full size</a><italic>  

## Further work and collaboration

The charts and indicators above would be obviously interesting for the crowds to which this article is intended, but no strong significant historical conclusions were drawn out of it yet.

For the foreseeable future, I will continue to collect data and attempt to analyse it for more interesting data. 

As a full time employee, I can not dedicate enough hours to this project as I wish. If you wish to collaborate on this project, have good insights, or/and a strong background in statistics / Roman History, please email me at dzautner@gmail.com and we could discuss the project and it's future direction.
