# Live Experimenter View

TurkServer has a built-in administration interface at `/turkserver`, providing a
real-time view of everything that is happening with your users and in your
experiments. You can use this to manage batches, manage treatments, view the
progress of experiments, and post HITs to recruit subjects.

![admin console](/img/turkserver.png)

A brief overview of the different sections:

- **Overview**: provides a summary of traffic and load on the server.
- **MTurk**: manage HIT types and qualifications for Mechanical Turk.
- **HITs**: create, expire, and renew HITs, which will send participants to the server.
- **Workers**: look up information about particular workers who have participated in the past.
- **Panel**: summary of information about all workers known to the system.
- **Connections**: shows all currently connected users and their state.
- **Assignments**: shows currently active and completed assignments, and associated metadata.
- **Lobby**: shows all participants who are currently waiting for experiment instances (see below).
- **Experiments**: shows experiment instances, their participants, and timing information.
- **Manage**: controls batch and treatment data which are used to configure experiments.

We aim to provide more information about the interface as its design is
finalized. For now, the admin interface is mostly self-explanatory.

<!--
Batches and treatments can be viewed and edited from the
administration interface.
-->
