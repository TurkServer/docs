---
layout: default
author: 
title: System Overview
slug: overview
permalink: overview
published: true
icon: fa fa-cog fa-spin
category: navigation
order: 3
---

# Architecture Overview

TurkServer is a full-stack Javascript framework based on [Meteor][meteor]. 
This means you do all your programming in Javascript, on both the client-side
(user's browser) as well as server-side.

[meteor]: https://www.meteor.com/

<img src="img/arch/stack.png" width="40%">

Why is TurkServer designed this way, and what are the core concepts?

- Read [why we chose Meteor](why-meteor) and Javascript as the 
underlying framework, and why this facilitates social experiments research.
- Understand the [multiple worlds abstraction](worlds-assignment), its relation 
to Meteor's real-time data framework, and how this makes it easier to design 
apps for group interaction.
- Check out the [live experimenter view](admin-console) in TurkServer, which 
allows you to see the status of all connected users and ongoing experiments.
- Take a look at how [treatments](treatments) can be assigned to users or 
worlds in TurkServer.
- Look at [research methods](research-methods) that guided the development of
 TurkServer.
- See references to [alternative platforms](alternatives) and concepts for 
doing software-based, crowdsourcing-driven experiments.
