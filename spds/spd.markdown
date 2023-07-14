---
layout: page
title: SPD Language
permalink: /spd/
has_children: true
nav_order: 2
---
# Overview

Below is a conceptual overview of the meta-model and the key elements behind the SPD language. The language aims at lowering
the effort for the self-adaptive system architect to model policies that effectively control the elasticity of the system.

Architects may define multiple policies triggered differently that adjust the modelled system in different ways. A typical use case 
is to for example analyse the performance of two services that use different elasticity control mechanisms. Of course, the SPD language 
is a modelling language, thus it abstracts from the actual implementation of the elasticity control mechanisms. 

If you are interested in the core concepts of the SPD language and how they are interrelated, head to the [[⇢ Core Concepts]](../overview/) page.
To understand what are triggers and how they are defined, head to the [[⇢ Triggers]](../triggers/) page. To know what type of adjustments are currently supported and how they are defined, head to the [[⇢ Adjustments]](../adjustments/) page. 
To know what type of constraints are currently supported and how they are defined, head to the [[⇢ Constraints]](../constraints/) page. 
To know what type of target groups are currently supported and how they are defined, head to the [[⇢ Target Groups]](../targets/) page.

The SPD language is based on the [Eclipse Modeling Framework](https://www.eclipse.org/modeling/emf/) and is defined as an Ecore model. 
The documentation of the meta-model is available [here](../docu/).

![SPD Language Overview](../images/spd-overview.png)

![service-group.png](..%2Fimages%2Fservice-group.png)