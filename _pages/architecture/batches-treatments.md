---
layout: default
title: Batches and Treatments
slug: batches-treatments
permalink: batches-treatments
icon: fa fa-tag   
category: architecture
order: 5
---

# Batches and Treatments

TurkServer uses the concept of **batches** to logically group
instances of experiments together. Each batch limits repeat
participation.

Batch controls the assignment of incoming users to
**treatments**. Treatments can have structured data which are made
available to the front-end app under `TurkServer.treatment()`, making
them a useful way to control the display of different parts of the
user interface or app behavior. They can be defined for batches,
users, or worlds.

Batches and treatments can be viewed and edited from the
administration interface.
