# Frequently Asked Questions

> *Where can I find more resources for how to do online experiments?*

[Andrew Mao] has given a tutorial at [IC2S2 2016], partially based on the 
content of this site, and focused on how to run social experiments involving 
group interaction.

- [Andrew Mao. **Experiments of collective social behavior in the online lab.**][ic2s2-tutorial]

[IC2S2 2016]: http://www.kellogg.northwestern.edu/news-events/conference/ic2s2/2016.aspx
[ic2s2-tutorial]: https://dl.dropboxusercontent.com/u/13229094/papers/IC2S216_experiments.pdf

At [WINE 2013], [Sid Suri] and [Andrew Mao] gave a tutorial on the opportunities
and practice of online behavioral experiments, targeted at a computer science
audience. Studying online behavior is a compelling opportunity for computer
scientists, and we believe that experimental work nicely complements existing
modeling and data mining approaches by providing a way to verify hypotheses in a
controlled setting and allowing for causal claims about interventions and
observations, which are important for all types of system and mechanism design.
Simply put, the best way to study online behavior experimentally is to do
experiments with online participants.

[WINE 2013]: http://wine13.seas.harvard.edu/
[Sid Suri]: http://www.sidsuri.com/
[Andrew Mao]: http://www.andrewmao.net/

- [Andrew Mao and Siddharth Suri. **How, When, and Why to Do Online Behavioral Experiments.**][wine13-tutorial]

[wine13-tutorial]: https://dl.dropboxusercontent.com/u/13229094/papers/WINE13_experiments.pdf

This tutorial consists of three sections: a review of how the experimental
approach fits in and complements other methods for studying behavior; an
overview of experimental design concepts from the abstract to the practical,
 including examples of pitfalls from our own experiments; and a survey of
methods and tools that have been used in different fields to conduct experiments
online.

> *I don't want to or can't write code. Can I hire a developer to build my web
 application (experiment) for me?* 

In theory, yes. **But there are many issues that can arise when this is 
process is poorly managed.** Here are some important ones. 

A primary issue is the process of taking a research question and
operationalizing it. In other words, when you build an experiment, you have a
particular question in mind (*or at least you should!*) and you are building an
app to collect data to answer that question. This process invariably requires
feedback, revision, and modification when you find that the original plan 
doesn't answer the question as well as you thought.
  
In contrast, software development often follows specifications that are a priori
much more concrete than research projects, and most developers will be much more
productive working from a spec rather than the more unstructured research
process in continually revising how the implementation of the user interface
answers the research question. This leads to potential errors in translation in
going from the question at hand to how it is implemnted, and the constant
revisions to the original plan could result in the project taking a long time.
But the real danger is in this frustration leading to giving up on doing things
correctly, which will result in a poorly designed experiment with questionable
data. **As a community, we should ensure that reducing barriers to doing
experiments doesn't result in many low-quality experiments.**

The other main aspect to consider is that running an experiment is not simply
about having the software, but also the protocol of the experimenter and
interaction with the participants. There is much less variation than in
traditional brick-and-mortar experiments, as much of this is encapsulated in the
software. However, there are still exceptions, a notable one being the
importance of [engaging with workers and maintaining your
reputation](../launching/forums-reputation.md). As a result, it's very difficult to run a
software-based experiment without understanding how the user interface and the
rest of the app was built. Either you'll need to be familiar with it anyway, or
your developer will also need to be a "lab manager" and run the experiment.

For all these reasons, I strongly suggest having a computer scientist or 
technically-inclined person as part of the research team—or at the very 
least, for such a person to work closely with a developer. Otherwise, make 
sure your developer understands the question you're trying to answer, what 
you're trying to do in the experiment, and what will be necessary to run the 
experiment successfully.  
