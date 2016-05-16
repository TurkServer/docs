---
layout: default
author: kgao
date: '2015-05-05'
title: Managing an Active Experiment
slug: active-management
permalink: active-management
published: true
icon:
category: launching
order: 5
---

# Managing an Active Experiment

### While you're live:

**Server status:**

* On your local machine, in your Meteor project folder use mup logs -f to pull recent server logs and check for errors 
* Turk Server status
    * Have a window open (or check occasionally) displaying experimentURL/turkserver so you can see what's going on in realtime

**Keep tabs on a few places:**  

+ Connections:
    + shows who's connected and in what state of Turkserver they're in
    + use this to see if something weird is happening (e.g. matching is breaking, people keep disconnecting, etc) 
+ Assignments Completed:
    + shows submitted HITs
    + use this to look at feedback people are providing, and a quick glimpse at experiment outcomes if people's behaviors are linked to their bonus payoffs
+ Experiments:
    + shows current and completed experiment instances
    + use this to see who's doing your task, who's connected, who needed to be rematched, how long experiments are taking, number of completed experiments
+ Workers:
    + search for a worker by their worker ID
    + If someone emails you with an issue you can see if they submitted a HIT, or returned it, or even if they're actively connected by searching their worker ID here 
+ Amazon HIT availability
    + You don't usually need to actively keep tabs on this but in case no one is signing up make sure your HIT is visible through Amazon or that there are Assignments remaining so new Turkers can sign up, see paying turkers below for how

**Multi-Turk matching monitoring**

- Often for multi-agent experiments (i.e. 2 or more people) some kind of matching mechanism exists in your meteor application
- Even if it works flawlessly there's no guarantee that Turkers will be connected *quickly* to other Turkers
- Less some kind of timeout feature within your app, another strategy is to increase their bonus payment through the TurkServer interface and send them a message apologizing for the extended time
    - Assignments Completed > Click bonus under the worker and type in the amount and message to send them

### After you finish a batch

**Approve assignments and Pay Bonuses (if any)**

- Sometimes approving all assignments or paying all bonuses returns an error in the Turkserver admin interface. Nothing to worry about either way a few minutes and try again or first go to a specific user, refresh their status and then try again. If the error persists see this [solution](https://github.com/VirtualLab/turkserver-meteor/issues/56)
- Try to be as prompt as possible as this helps the lab reptuation, speaking of which...

**Check feedback on [Turkopticon](https://turkopticon.ucsd.edu/)**

- This the principle feedback forum where the lab gets reviewed by Turkers

- It's **critical** to maintain a good reputation, key to which is providing prompt service 


**Paying Turkers (alternative)**

- If everything is going according to plan you should be able to pay folks directly through the Turkserver admin interface (including bonuses)
- Alternatively you can pay folks through Amazon's mTurk interface (e.g. in case you wiped your Turkserver database prematurely and don't know who completed your experiment!)
    - Login to [requester.mturk.com](http://requester.mturk.com/)
    - Click Manage > Manage HITs individually (on the right) > Assignments Pending Review/Download Results
    - Scroll down to see who needs to be approved, who was approved, who wasn't
    - Click any WorkerID to accept their HIT and/or pay them a bonus  

**Communicating with Turkers**

- If a Turker has completed a HIT for you previously and they are in your Turkserver database you should be able to contact their through the Turkserver admin interface:
    - Assignments (Active or Completed) > hover over Worker ID > click mail glyphicon
    - You should be able see see sent messages under Panel
        - WARNING: Messages might appear here as if they were successfully sent, but this may not be true! Turkserver currently (as of 9/22/15) requires Turkers to have completed as least 1 HIT with you previously, i.e. Turkserver needs to "know" who this worker is *before* they complete a HIT
- Otherwise you can email workers directly through Amazon's interface:
    - Follow directions above for paying folks through Amazon's interface
    - Clicking any WorkerID will also give you the option to email them  

**Checking available Assignment(s) information**

- Depending on how your Meteor experiment is setup you can get a sense of how many Assignments are left simply based on a combination of the following:
    - HITs > Assignments - Assignments Completed - Assignments Active
- This may not always be reliable if you have special rules setup for rematching Turkers, HIT comprehension, disconnection etc
- In this case navigate to Amazon's request mTurk interface by following the directions above 
    - Under Manage HITs individually you should see the "Remaining Assignments" value along with other info about your HIT
    - This is the "gold standard" regardless of what Turkserver says because it's what Turkers will be able to see as well 

### Troubleshooting

- If something is going wrong you should immediately freak out! (ask Eshin he know's all about this)
- Actually don't that. Just figure out what's up by checking the following:

**Is the hosting server online?**  

+ PANIC LEVEL: Low 
    + Not the worst thing in the world because if the server is restarted quickly enough, Turkserver will automagically reconnect users in the middle of experiment to the exact point they were at!
    + If not, you risk losing active assignments, getting a few angry emails, but no potentially new users will be affected 
+ HOW TO CHECK:
    + Try to ssh to the webserver where your meteor project is hosted
    + If you can't or if experimentURL/turkserver (the Turkserver admin interface) is unreachable your experiment is no longer being served to Turkers
+ WHAT THIS MEANS:
    + Users currently doing your experiment will be stuck 
    + New users trying to view your HIT they won't see anything in the mTurk window or they'll see a message saying the website doesn't exist/isn't reachable; they should not be able to click Accept HIT at this point but this is unclear (plus it would be kind of stupid for them to do so anyway)
+ SOLUTION:
    + Try and restart your web server as quick as possible 

**Is Turkserver working properly? (i.e. is your Assigner behaving?)**

+ PANIC LEVEL: High
    + This can be pretty bad depending on how your experiment is setup
    + You risk losing active assignments, and new assignments can get stuck in the lobby
+ HOW TO CHECK:
    + Pull server logs (mup logs -f) from your local Meteor project folder to see if there are application errors
    + You should be able to see them if you're currently ssh'd into the hosting server as well
+ WHAT THIS MEANS:
    + Users currently doing your experiment *could* be ok, but might have problems submitting their HITs
    + New users will likely get stuck in the lobby and never be pushed to the experiment
    + You can have a huge list of stuck Turkers very quickly! 
+ SOLUTION:
    + Stop all experiments (your call):
        + If you don't think that current users will be affected by this problem don't do this
        + Otherwise: Turkserver admin interface > Experiments > Stop All Experiments
    + Immediately force expire your HIT:
        + Turkserver admin interface > HITs > Click on your HIT > Force Expire
        + This way no new users will be affected
        + Current users may not be able to submit their HITs after this 
    + Try and contact Turkers and pay them for accepting the HIT through Amazon's mTurk interface, or through Turkserver
    + Debug your code at your leisure
 
**Is your Meteor app not working?**

+ PANIC LEVEL: ?
    + This is the most ambiguous type of issue because depending on how your experiment is setup, here are a few possible situations ordered from low to high panic level:
        + New users may still be able to accept the HIT, current users may still be able to submit the HIT, but your experiment may be rendering improperly or data may not be saving properly or saving at all = Turker thinks everything is ok
        + New users can't see the HIT and current users are stuck = Turker will be confused and email you if they're in the experiment 
        + New users can still accept the HIT but current users can never submit = Turker will email you angrily
            + THIS IS BAD because you run the same type of risk as Turkserver crashing
+ HOW TO CHECK:
    + Pull server logs (mup logs -f) from your local Meteor project folder to see if there are application errors
    + You should be able to see them if you're currently ssh'd into the hosting server as well
    + Check your database:
        + ssh to your web server and navigate to /opt/appName
        + mongo appName
        + `db.yourdatabase.find().pretty()`
    + Make liberal use of console.logs() when things work as expected or don't during your meteor app
+ WHAT THIS MEANS:
    + Again this is pretty ambiguous depending on your code see above for a few possible scenarios 
    + Users currently doing your experiment *could* be ok, but might have problems submitting their HITs
    + New users will likely get stuck in the lobby and never be pushed to the experiment
    + You can have a huge list of stuck Turkers very quickly! 
+ SOLUTION:
    + You probably want to stop all current experiments and force expire your HIT before debugging your code, see above for how 
