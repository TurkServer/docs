# Assignment and Matching

Experiments with individual users are simple and each participant can proceed
independently. Use the [`SimpleAssigner`][sa] to create this common form of
experiment in TurkServer, but gain all the benefits of the live experimenter
view.
 
[sa]: http://turkserver.meteorapp.com/#Assigners-SimpleAssigner

When matching users together, however, the precise details of the matching
mechanism become an important part of the experiment design. This is because
users who are waiting an inordinate amount of time for partner(s) to arrive to
start an experiment can either get frustrated, or go on to another task and
become inactive. This can aggravate problems of [disconnection and dropout](disconnection.md)
 and result in worse quality data.

Depending on how you post your HITs and how attractive they are, this may happen
rarely. However, it's still possible, especially if your HIT has been posted
for a while and the supply of workers is beginning to dwindle. Here are a few
ways to work around this issue:
 
- Configure your [assigner](assigning.md) to to monitor the amount of the time
users are spending in the lobby. If it exceeds some threshold, allow them to
submit the task and pay them for their time (e.g. half the HIT amount). Although
this can be viewed as paying something for nothing, it's important to [preserve the reputation](../launching/forums-reputation.md)
 of your requester account in order to recruit workers.
     
- For users that do wait an exceedingly long time and eventually complete your
experiment, consider paying them a bonus for their patience.

- When running really large groups, pre-recruit participants with an
informational task and schedule a participation session in advance. TurkServer
provides functions to e-mail users for this purpose. Then, you can expect all
users to arrive at once and be ready to participate.

## Assigner Examples

To be added. For now, take a look at some [source code][src] for inspiration.

[src]: https://github.com/TurkServer/turkserver-meteor/tree/master/server
 
