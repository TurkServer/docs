# Design Overview

## Typical Workflow using TurkServer

[cm]: https://github.com/TurkServer/CrowdMapper 
[pd]: https://github.com/TurkServer/long-run-cooperation

At a broad level, using TurkServer looks something like the following once 
you've done a literature review and settled on a research question.  

1. Prototype your experiment in a **standalone** Meteor app, designed around  
the smallest unit of people who will interact. This could even be a single 
user, but the point is to take advantage of Meteor's ease of development to 
investigate whether your experiment makes sense. Here are some examples:
 
    - In an [experiment on teamwork][cm], one unit was a team of people 
    working together.      
    - In a [prisoner's dilemma experiment][pd] with random rematching among a
     hundred people, one unit was two players in a repeated game.            

2. If the design is promising, add TurkServer to your app, and integrate with
its [assignment mechanism](worlds-assignment), which will allow you to make
different instances of your prototype world and control how participants 
enter and leave them.

3. Test, debug, and pilot your experiment extensively, making sure that your 
[code works as intended](debugging) and your [instructions are easy to 
understand](good-instructions). Start with your research team, then others in
your lab/department, and finally run a pilot with real crowdsourcing workers.
Experiments inevitably involve many redesigns and modifications, and it's 
better to do this in testing than to shoot from the hip.

4. [Run your experiment](launching)!

5. Share the source code of your app so others can look at your experiment 
protocol, and replicate or build on it.

## Designing Good Experiments

While TurkServer provides much of the software components necessary
for deploying web-based experiments, many elements of your 
experiment design are important to ensure that your study goes smoothly and 
workers leave happy.

In particular, when doing experiments that require coordinating 2 or more users
at once, there are a number of important considerations for experimental design
that affect how well you can collect data when your app is live. Consider the
following "state diagram" (credit: Eshin Jolly) that illustrates possible 
conditions a user passes through as they participate in a group task:   

![example flow](../_static/design/experiment-flow.png)
   
Among other things, the diagram illustrates:
   
- A [matching mechanism](assignment-matching) to group people together as 
they are waiting in the lobby.
- Providing [good instructions](good-instructions) and using a comprehension 
task to check that they are understood.
- Accounting for the possibility of [disconnection and dropout](disconnection)
in your design, both to minimize the amount of data that might be discarded 
and ensure a good experience for all remaining participants.

See also the following topics:
 
- Constructing a [one-way mirror](mirror) to qualitatively observe activity 
and diagnose potential issues.
- How to [debug and test your app](debugging) before running it live. 
- How to [minimize attrition](attrition) in experiments that run over a long 
period of time or over multiple days.
- Helpful [packages and software](software) that you may want to use in 
your app.
- Other [frequently asked questions](faq) about building experiments. 
        

