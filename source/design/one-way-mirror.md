---
layout: default
title: One-way Mirror
slug: mirror
permalink: mirror
published: true
icon: fa fa-photo
category: design
order: 8
---

![one-way mirror](http://www.todayifoundout.com/wp-content/uploads/2010/05/one-way-mirror.jpg)

A one-way mirror is used in some physical lab experiments to allow 
unobtrusive observation of participants. Using the real-time capabilities of 
Meteor, this is actually fairly easy to set up on an existing app.  

# Creating a digital one-way mirror

In the [worlds and assignment](world-assignment) section, we explained how
TurkServer is designed around multiple worlds that participants can be assigned
to. This example explains how to build a one way mirror or view into the
experiments you are running, so that you can observe what's happening in real
time. Although this may seem like a superfluous feature, in practice you're 
likely to find it incredibly useful for qualitatively understanding what's going 
on—even before getting to data analysis.

The following code is built around the [partitioner][partitioner] API that 
TurkServer users to divide a Meteor app into different 'worlds'. Consider the
 [example][chat-example] in the partitioner docs, describing how to use the 
 same `ChatMessages` collection to effectively create a collection of 
 separate chatrooms. To create a one-way mirror allowing you to see all 
 chatrooms simultaneously, you could do the following.   

[partitioner]: https://github.com/mizzao/meteor-partitioner
[chat-example]: https://github.com/mizzao/meteor-partitioner#examples

## Set up a new publication on the server

First, set up a new publication on the server, allowing direct access to the 
data from any particular world.  

```js
Meteor.publish("oneWayMirror", function (worldId) {
    return [
        ChatMessages.direct.find({ _groupId: worldId }),
        Meteor.users.direct.find({group: worldId}, { fields: { username: 1 } })
    ];
});
```

The above publication returns data about the chat messages and users, 
partitioned by a given world. 

> For those who are curious, `_groupId` is the world identifier in the
[partitioner][partitioner] package. The `.direct` syntax specifies to override
the automatic partitioning or or 'multiple worlds' logic to directly query any
particular world. The "magic" that happens with [different groups in
TurkServer](world-assignment) is that the `_groupId` field is inserted
automatically depending on a particular user's group membership.
 
> `Meteor.users` is the standard collection for [Meteor's accounts
system][meteor-accounts], which is already defined. This 
pre-existing collection is partitioned differently from other collections
that one creates (such as `ChatMessages`); the second argument is a [field 
specifier][field-specifier] so that the query returns just the username instead
 of other users fields such as the login token, which you would not want other
 users to see.

[meteor-accounts]: http://guide.meteor.com/accounts.html
[field-specifier]: http://docs.meteor.com/#/full/fieldspecifiers 
   
## Create a view for the experimenter on the client 

TurkServer uses [Iron Router][iron-router] to control the display of 
templates on the client. You can use the API to add a new route for the 
experimenter to use the one-way mirror:

[iron-router]: http://iron-meteor.github.io/iron-router/

```js
Router.map(function () {
    this.route('expAdmin', {
        path: 'exp/:groupId',
        waitOn: function () {
            return Meteor.subscribe("oneWayMirror", this.params.groupId);
        },
        data: function () {
            return { groupId: this.params.groupId }
        },
        template: 'experiment',
    });
});
```

For the details of the code above, take a look at the [Iron Router
documentation][iron-router]. It is a pretty well-documented client-side routing
package for Meteor, and currently the most commonly used. For example,
specifying a `path` of `exp/:groupId` means that browsing to `exp/foo` store
`foo` to the `groupId` parameter of the route params. The above function then
subscribes to the `oneWayMirror` publication with this `groupId` as well as
passing it as an argument to the template in the `data` function. Check out the
Iron Router guide to see more examples of how to specify routes.

The above code allows the experimenter to visit `https://<server>/exp/<id>` to
see what's happening with a particular group of people. The user interface that
will be seen is defined by the `experiment` template. Usually you can just use
the same interface that you have already built for participants, but for certain
instances it may be useful to design a particular experimenter view (see
examples below).  

## Hook up your mirror to the experimenter console

Since world identifiers are randomly generated by Meteor, it would be 
inconvenient to have to type them in yourself. Fortunately, you can specify 
the route for the one-way mirror in Meteor's `settings.json` to view worlds 
automatically:

```js
{
  "public": {
     "turkserver": { 
       "dataRoute": "expAdmin"
     }
  }
}
```

Under the **Experiments** view of the admin console, this will create a 
convenient button that you can click to watch ongoing or completed
experiments (worlds) in real time.

![data button](img/experiments4.png)

# Examples

Although the code for a one-way mirror is minimal, it may help to look at the
 following implementations for inspiration.
 
## Crisis Mapping

[![CrowdMapper Replay](http://share.gifyoutube.com/mLnMWR.gif)][cm-paper]

This code accomplishes a pretty complex one-way mirror that allows real-time 
observation over a number of different collections, producing the 
(fast-forwarded) video above. However, the code is still minimal. 

- [client code][cm-client]
- [server code][cm-server]

[cm-paper]: http://journals.plos.org/plosone/article?id=10.1371/journal.pone.0153048 
[cm-client]: https://github.com/TurkServer/CrowdMapper/blob/master/client/admin.coffee
[cm-server]: https://github.com/TurkServer/CrowdMapper/blob/master/server/server.coffee#L38

## Prisoner's Dilemma

![PD Mirror](img/design/pd-mirror.png)

This one-way mirror uses much simpler data, but also uses [D3][d3] to build 
a real-time visualization showing the experimenter much more than 
participants can see—including precise timing information. 

- [client code][pd-client]
- [server code][pd-server]

[d3]: https://d3js.org/ 
[pd-client]: https://github.com/TurkServer/long-run-cooperation/blob/master/client/admin/exp_admin.js
[pd-server]: https://github.com/TurkServer/long-run-cooperation/blob/master/server/admin.js