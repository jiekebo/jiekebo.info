---
layout: project
title: "Byens Puls"
modified:
excerpt: "Remake of DSB's Byens Puls for Mobile platforms"
date: 2013-03-06
tags: [projects]
image:
  feature: byenspuls.png
---
<div markdown="0">
  <a href="https://github.com/jiekebo/ByensPuls" class="btn">Go to GitHub project ></a>
  <a href="http://jiekebo.info/ByensPuls" class="btn">Go to Live Demo ></a>
</div>

At a point in my life I was commuting, and for quite a long stretch. I lived in Sweden but worked in Denmark, taking the Öresundsbridge every day. 

Growing tired of always missing a connecting train, i decided to make an app to help me solve the problem. The app should have a clear overview of where all the trains are located in the capital area of Sealand, and should be adjusted for the speed and screen-size of mobile devices. 

Early on I decided that this should be a purely client based application since data already was available from DSB, Denmark's national train service. The data came in a legacy format as you can see below.

{% highlight bash %}
STATUS
FOR 28265    126
TTP 31163 STP C3 KL
FOR 31165     27
FOR 72164     11
POS 12265  7576  1755  900
TTP 71163 STP F1 HL
TTP 31165 STP C3 KL
TTP 72264 STP F2 NEL
TTP 36264 STP C3 FS
FOR 28264     35
POS 12263  4276  8644    0
{% endhighlight %}

Creating a parser seemed like the way to solve the problem. Creating a parser from scratch however is not trivial. <a href="http://zaach.github.io/jison/">Jison</a> to the rescue! Creating a parser with Jison is a breeze, just define the structure of the data in <a href="http://en.wikipedia.org/wiki/Backus%E2%80%93Naur_Form">BNF</a>, and let Jison create the parsing logic for you. Here is an excerpt of the BNF used for parsing the data.

{% highlight javascript %}
status
    : instrlist
    ;

instrlist
    : inst EOL instrlist { }
    | inst EOF { return yy; }
    | EOF { return yy; }
    ;

inst
    : STATUS
        {$$ = console.log("Status");}
    | TID NUMBER
        {$$ = yy.setTid($2);}
    | MED MESSAGE
        {$$ = console.log("Meddelelse: " + $2);}
{% endhighlight %}

Train locations follow a certain path, which results in a track overview way to large for a mobile screen. I needed to translate the locations into something useful. I did that by tracing the train tracks directly on the map used by DSB. Using vector calculations and projecting positions onto the traced tracks, I got a ratio for the train position in relation to the track length.

Using Raphaël as framework for drawing on the canvas I was able to combine the ratio with the train tracks and their stations also projected onto the track. Raphaël was also used to create buttons for switching between the tracks.

All these vector calculations prooved to be too much for a single thread on a mobile, giving sluggish performance whenever a train update rolled in. Extracting the vector projection into a separate webworker thread worked wonders for the general feeling of responsiveness.

During the development of the app I needed reliable test-data, so creating a mock-server was needed. The server was written using Node. Also a recorder for guzzling up a lot of DSB-data was written using node. The live demo uses this mock-server.

The javascript code was wrapped in a Phonegap/Cordova app and shipped to AppStore where it, to my surprise, even sold a few copies! The app was taken offline when DSB decided to cut the data-stream, and an offer to reimburse were given to the people who had bought the app.

I guess that's a lesson for me not to think that a data-source will be ubiquitous...

#### Technologies used
* Javascript, Node
* Jison, WebWorkers, Raphaël
* Phonegap
* Python for scripts
