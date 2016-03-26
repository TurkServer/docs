---
layout: default
title: Design Considerations
---

# Design Considerations

When doing multi-Turker (i.e. 2 or more users) experiments using Meteor there are a number of important considerations that need to be factor into experimental design and when HITs are launched live.

### Connection Issues:

- Your project code should keep tabs on the connection state of each user and should have some kind of connection timer that prevents one user from getting "stuck" if their partner(s) disconnect
- Likewise if rematching users is important, make sure to build that into your project code and critically set it up in a way that your Assigner knows what to do, for example:
- An Assigner that uses number of instances and a boolean flag to properly route users:
    - When a user hits the TS Lobby the assigner checks if they have been in any experiment instances
    - If they have, it looks for a rematch boolean flag and if it sees it, leaves them in the lobby to get matched again
    - If it doesn't see that flag it assumes they have completed their experiment instance and pushes them to the TS Exit survey 
    - If it doesn't see any experiment instances it assumes this is their first time in the lobby and leaves them there to get matched 

### Matching Issues:

- It's important to make sure Turkers aren't waiting an inordinate amount of time for another user to arrive before the experiment starts
- While this doesn't happen too often, it **will** happen at least 10% of the time **especially** if your HIT has been live for a while 
- One solution is to monitor the amount of the time a user has spent in the lobby and if it exceeds some threshold, push them to the TS Exit survey and pay them for their time (e.g. half the HIT amount)
    - This sucks because we have to pay for 0 data, but we can write it off as the cost of saving lab reputation 
* Another solution for users that do wait an exceedingly long time and eventually complete your experiment is to pay them a bonus for being patient

### Idling Issues:

- Your project should probably deal with users that take exceedingly long to respond
- One solution is to setup the Assignment duration so that that a user must complete it within a certain time otherwise risk being unable to submit
    - This can be problematic if one user *causes* another user to lose out on the opportunity to submit the HIT because they themselves took too long
- Another solution is to track the idle state of a user through Turkserver and start a forced disconnect if a user has been idling too long
    - This is tricky to setup, but more ideal because users can be handled independently of each other, e.g.
        - If user A idles and is force disconnected, user B can simply be rematched or pushed to the end of the of experiment 

### Social Issues:

* It's obviously important that Turkers understand your experiment and don't simple "click-through" to get their payment
* Instituting comprehension questions that prevent a user from advancing or moving past a certain point in your meteor app is a good way to filter out this kind of behavior

### Going Live

- When you finally launch your meteor experiment rejoice for you have earned a long-rest and a vacation on the beach
- Actually don't because things aren't as "automatic" as they may seem
- You still need to [manage your active experiment](/experimentManagement.html) to deal with users in real time
- As of this writing (9/24/15) it seems far more advantageous to launch many "small" HITs instead of several large ones
- Why? Turkers will **not** sit around your lobby waiting to getting matched for very long
- You will likely get angry emails and because they have to return your HIT in order to leave (or simply disconnect) it will be non-trivial/impossible to compensate them for their time (see Matching issues above for some strategies to avoid this) 
- Though speculative, this is probably because as other Requesters launch their HITs, your's will fall to the bottom of the list getting lost and missed by Turkers
- To combat this, use the HITs menu on Turkserver to launch new HITs (with the same parameters you set using the MTurk menu) one after another
    - 10-20 seem's fairly reliable and finishes up within 15 minutes
    - 40+ really depends on the time of day and can take anywhere from 30 minutes to never finishing  
- *[NEEDS TESTING]*  It might be possible to simply add more assignments to an expired HIT and relaunch it, but it's unclear whether this "pushes" your HIT to the top of the page for Turkers to see [UPDATE 9/25/15] it looks like this works! 

