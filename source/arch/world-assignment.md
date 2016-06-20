# Worlds and Assignment 

TurkServer uses Meteor's [powerful publication-based data model][meteor-pubsub]
to create multiple *worlds* or *instances* within which data can be synchronized
among a group of users in real time. This makes it easy to build and study
mechanisms of real-time interaction. However, the real utility of this
abstraction is the ability to create new worlds and assign or re-assign users
among them, allowing for flexibility of many experiment designs while keeping
programming simple.     

[meteor-pubsub]: http://guide.meteor.com/data-loading.html

TurkServer uses the concept of **batches** to logically group instances of
experiments together. Each batch allows for some high-level parameters to be
set, such as a limit on repeat participation.

Each batch has a **lobby** or waiting area, a state that users are in when they
are not part of any world. An **[assigner](../design/assigning.md)** controls
the state of the waiting area and therefore can arrange arriving or returning
users to different worlds.

A world can return users to the lobby once a task is complete, allowing for
users to be assigned to different groups, matched with different partners, and
so on. The assigner can also send users to an **exit survey** to complete the
task and debrief.

## Examples

To be completed.

## Additional References

TurkServer's multiple worlds abstraction is implemented by the [partitioner]
package in Meteor, which was written specifically for TurkServer.

[partitioner]: https://github.com/mizzao/meteor-partitioner 
 
