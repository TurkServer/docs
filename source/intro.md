# Introduction

Since the 1950s, social scientists of all disciplines have been studying
people in "behavioral labs" at universities. These labs typically involve
cramming a group of people into a room for an hour or so and asking them to
do something:

![old labs](/img/intro/old-lab.png)

The lab is quite a useful tool in that it offers a great degree of control in
doing experiments, and hence the ability to draw correct, causal conclusions.
But there are clear limitations of using such an environment to study
practically *all* of human behavior:

- it's a pretty **artificial environment**
- the setup generally supports only **simple tasks**
- subjects are **[very homogeneous university undergraduates][1]**
- we can only take a **limited number of people** and keep them there for a
**short amount of time**
- lab experiments are **expensive**, **difficult to set up**, and **hard to
replicate**

[1]: http://www.ncbi.nlm.nih.gov/pubmed/20550733

# Why the Virtual Lab?

The "Virtual Lab" refers to using software-controlled experiments with
Internet participants to overcome many of the limitations of brick-and-mortar
 lab experiments. We can now study more complex tasks and set up interactions
 that happen over longer periods of time or among larger numbers of people.
 This allows us to design behavioral experiments that would have been very
 hard to do in the past.

![virtual lab design space](/img/intro/virtual-lab-design.png)

## What is TurkServer?

[TurkServer][ts] is a platform for building software-controlled, web-based
behavioral experiments using participants from the Internet. We can now study
more complex tasks and set up interactions that happen over longer periods of
time or among larger numbers of people. This allows us to design more expansive
and realistic behavioral experiments.

By taking advantage of the movement toward the web as an all-purpose 
application platform, and providing a common system on which to build 
software-based behavioral experiments, TurkServer allows for:

- **Easier real-time programming** using the [Meteor][2] web app framework
- Building synchronous experiments and studying [group interaction](design/assigning.md)
- A live web-based [experimenter console](arch/admin-console.md) showing all 
connected participants
- The ability to create [one-way mirrors](design/mirror.md) to view behavior
 in real time     
                
[2]: https://www.meteor.com/           
[ts]: https://github.com/TurkServer/turkserver-meteor 

This means we can go from very artificial environments to studying realistic,
 complex tasks such as teamwork and collective intelligence: 
 
[![CrowdMapper Replay](http://share.gifyoutube.com/mLnMWR.gif)][4]

[4]: http://journals.plos.org/plosone/article?id=10.1371/journal.pone.0153048 

## Sharing and Replication

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

## Next Steps

Ready to jump in? Check out the [quick start](quick-start.md), a basic 
(but fully functional) [tutorial app](examples/tutorial.md), or read up on how to 
think about [designing experiments with TurkServer](design/design.md).
