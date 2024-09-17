---
layout: page
title: Slingshot Simulator
permalink: /slingshot-simulator/
has_children: true
nav_order: 2
---
# Slingshot Simulator

Slingshot itself consists of two parts, namely the **Framework** and the plugins. The framework serves as the base software onto which plugins can be made.
The Slingshot framework is based on event-driven architecture, so mostly everything is handled in an event-driven way. In other words, plugins can add behavior to the overall system by listening to events and reacting to them.

The framework itself therefore only consists of parts that can handle and forward events, and further contribute to the Eclipse's UI. There is only one extension point, and everything can be done on that extension point more or less.

The following sections introduce technical details for developing the Slingshot Simulator. 
If you are only interested in using the simulator, go to the <a href="../tutorial-usage">⇢ Usage Tutorial</a>.
If you are actually interested in developing the simulator, maybe go to the <a href="../tutorial-dev">⇢ Developer Tutorial</a> first, to learn how to set up the Slingshot Simulator in an development Environment. 

## Modules
The framework consists of three layers and four modules:
* The Event-Driver
* The System- and Simulation-Driver
* The Extension-Registry

<img src="../images/framework_modules.svg" alt="Slingshot's Framework Modules">

Furthermore, the framework provides abilities to create UI components for the simulation, especially launch configuration, and also a Workflow to start the simulation.

