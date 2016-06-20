# Treatments 

Being able to show users different instructions, interfaces, or information is
an important part of conducting controlled experiments. 

TurkServer accomplishes this through **treatments**, containing structured data
that are made available to the front-end app under `TurkServer.treatment()` as a
[reactive variable][rv] in Meteor.

[rv]: http://guide.meteor.com/data-loading.html#stores 
 
Treatments contain arbitrary key-value pairs, and can be assigned to both users
and worlds. The client code for a user in a particular world will have access to
all of the treatment data for both the user and the world, creating a useful way
to programming control the display of different parts of the user interface
(such as instructions) and mechanisms of interaction. Since treatment data is
reactive, it is easy to use with [Blaze], Meteor's UI rendering system.
 
[blaze]: http://guide.meteor.com/blaze.html

Treatments can also be viewed in the [admin interface](admin-console.md).

Additional details and examples of treatments to be added.
