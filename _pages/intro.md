---
layout: default
author: Andrew Mao
title: TurkServer
slug: intro
permalink: index
published: true
icon: fa fa-info-circle
category: Introduction
order: 0
---

[TurkServer][ts] is a platform for building software-controlled, web-based
behavioral experiments using participants from the Internet. We can now study
more complex tasks and set up interactions that happen over longer periods of
time or among larger numbers of people. This allows us to design more expansive
and realistic behavioral experiments.

By taking advantage of the movement toward the web as an all-purpose 
application platform, and providing a common system on which to build 
software-based behavioral experiments, TurkServer allows for:

- **Easier real-time programming** using the [Meteor][2] web app framework
- Building synchronous experiments and studying [**group interaction**]
(assigning-matching)
- A live web-based [**experimenter console**](admin-console) showing all 
connected participants
- The ability to create [**one-way mirrors**](mirror) to view behavior
 in real time     
                
[2]: https://www.meteor.com/           
[ts]: https://github.com/TurkServer/turkserver-meteor 

This means we can go from very artificial environments to studying realistic,
 complex tasks such as teamwork and collective intelligence: 
 
[![CrowdMapper Replay](http://share.gifyoutube.com/mLnMWR.gif)][4]

[4]: http://journals.plos.org/plosone/article?id=10.1371/journal.pone.0153048 

# Sharing and Replication

One significant annoyance of doing experiments is that they're **a lot of 
work**, yet **this work is often redundant**: it is either not shared or 
involves reinventing the wheel. So, other than just supporting more advanced 
experimental designs, another goal of TurkServer is to lower the barrier
 to both producing and sharing experimental research.
 
We can do this by making everything **open-source software**: not only is the
 core platform open-source, but experiments built on it are as well. This 
 means that researchers can now share not only data, but entire 
 **experimental protocols**. For example, check out [the code for the teamwork
  experiment above][5].
     
[5]: https://github.com/TurkServer/CrowdMapper      

In this way, building off someone else's experiment means you don't have to 
implement it from scratch: just grab their code and use it!

# Next Steps

Ready to jump in? Check out the [quick start](quickstart), a basic 
(but fully functional) [tutorial app](tutorial.html), or read up on how to 
think about [designing software-based online experiments](designConsiderations.html).
