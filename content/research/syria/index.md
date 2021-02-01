---
title: "The Most Documented War in History: The TOW Program"
date: 2016-09-17T15:37:48+02:00
draft: false
categories:
- Research
tags:
- Geopolitics
- Syria
- Research
- Data
---

In mid 2012, The former head of Syria's chemical weapons, Major General Adnan Silu, declared that “All we need from NATO are two air attacks on the presidential palace to topple the regime and we will be able to control all the Syrian cities”.

But two years later, amid clashes between the rebel fractions and the now independent ISIS (a few months before they would declare their Caliphate) the rebels and their supporters were not as optimistic.

The Syrian Arab Army have scored some important moral victories. Completely liberating Homs, “The Cradle of the Revolution”, and controlling the majority of the Syrian population, the Syrian Army used its superior arms to gain important victories. And the idea of obliterating the rebels militarily was no longer a far fetched dream for Bashar Al-Assad.

It was during that time, that the rebels started to receive a constant delivery of Anti Tank Guided Missiles (ATGM), or more specifically: the **BGM-71 TOW** ("Tube-launched, Optically tracked, Wire-guided”). 

## Escalations 

![A Syrian soldier aims a 7.62mm PKM light machine gun from his position in a foxhole during a firepower demonstration.](https://upload.wikimedia.org/wikipedia/commons/thumb/3/31/Syrian_soldier_with_a_machine_gun.JPEG/800px-Syrian_soldier_with_a_machine_gun.JPEG)

The war in Syria can be marked by constant escalations of different fraction’s backers.

In favour of the regime, it is Iran and Russia. For the Jihadist groups, it’s mostly actors from the gulf area.   
  
For the moderate groups in the opposition, it was the USA, Turkey, and the Kingdom of Saudi Arabia.    
  
And circa 2014, the later group escalated the situation in the form of BGM-71 TOW missile shipments.  

The TOW program would be so effective against a regime that was gaining ground with its superior armor, that the shipments continue to this day. 

And so, like any escalation, it turned into today’s status quo: Using American made TOW missiles, The Rebel fractions can be extremely effective against the regime’s tank forces.

While the program is said to be orchestrated by the CIA, it is truly a multi-national operation with the missile designed and produced in the USA, paid for by Saudi Arabia, and shipped to the rebel fractions through South-Western Turkey.
  
## Keeping the opposition in check

![FSA rebels cleaning their AK47s in Aleppo, Syria.](https://upload.wikimedia.org/wikipedia/commons/thumb/3/3a/FSA_rebels_cleaning_their_AK47s.jpg/800px-FSA_rebels_cleaning_their_AK47s.jpg)
In an active war zone that involves dozens of different fractions, and with a price tag of $60,000 per unit, no actor in the scheme to supply the moderate rebels with TOW missiles can be too cautious.
  
The moderate opposition groups might pass the missiles to more radical groups, sell them in the black market, or even stockpile them to build an arsenal too large for the comfort of the US or neighbouring Turkey.

All of these examples have happened before, and with such incidents being publicised, and the US criticised, going down the same route again is simply not an option. Something must be done to ensure the weapons are only used for their intended purpose - destroying regime tanks when ever possible.

## The absurdity of war

The solution, while effective, can seem absurd in its simplicity. 

Like something from a Thomas Pynchon or Joseph Heller novel, the CIA requires the rebels to send them a video of every missile launch.

Now the CIA can easily get any information they want on the progress and effectiveness of their project. Do the rebels use the missiles? Which rebels use them? On what targets? In what locations? How many missiles did they use? 

All of these important questions can be now answered, and answered with guarantee and with ease.

If the rebels don’t post any launches, or begin targeting unacceptable targets, the CIA can just stop the program at any given time.


## The data is there

What ever reaches the web hardly ever leaves it. Archives are constantly made and are easily accessible to whoever is interested.

As a part of a larger research on the Syrian Civil War, I downloaded more than four million tweets from the beginning of the Syrian Civil War to this day containing names of cities and locations in Syria.     
  
Searching for any tweet in the collection that contain words related to TOW missiles and an active link to a Youtube video, I was able to collect more than 1000 unique videos of different TOW and other ATGM missile shootings from the beginning of the war. Analysing the data, the trend is obvious: The amount only increases. 


## No end in sight

Each column in the chart represents a month. Every box in the the column is a separated video. The chart is interactive and you can press any entry to display the video linked to it:

<i>
<a target="_blank" href="./towchart/">Click here to open the chart in full view</a>
</i>

<iframe id='chart' src="./towchart/" frameborder="0" style="overflow: hidden; width: 100%; " width="100%"></iframe>

<script>
 var eventMethod = window.addEventListener ? "addEventListener" : "attachEvent";
  var eventer = window[eventMethod];
  var messageEvent = eventMethod == "attachEvent" ? "onmessage" : "message";
  // Listen for a message from the iframe.
  eventer(messageEvent, function(e) {
    if (isNaN(e.data)) return;

    // replace #sizetracker with what ever what ever iframe id you need
    document.getElementById('chart').style.height = e.data + 55 + 'px';

  }, false);
  setInterval(function () {
 document.getElementById('chart').contentWindow.postMessage('','*')
  }, 500);

  </script>

*This is the first part in a series of articles attempting to analyse large streams of data from the Syrian civil war.* 
  





