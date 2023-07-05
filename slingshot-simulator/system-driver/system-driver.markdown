---
layout: page
parent: Slingshot Framework
title: The System-Driver Module
permalink: /slingshot-simulator/system-driver/
nav_order: 2
has_children: true
---
# System-Driver Module
The Slingshot Framework is split up into two different modules further process the events to add behavior: *Simulation-Driver* and *System-Driver*.

The system-driver handles events that configure the whole system in some way. For example, it is possible to add UI components, workflow jobs and conclude the simulation afterwards.

In order for the system driver to consider the events as system events, the event type must be a sub-type of `SystemEvent`. Unlike simulation events, **system events do not contain time information**, since these events happen outside of the simulation. Furthermore, these events will not be counted in the event graph.