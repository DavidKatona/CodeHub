---
title: "Event Base"
permalink: /eventaggregator/event-base/
layout: single
author_profile: false
toc: true
---

## Class description

UEventBase serves as the base class for events within the Event Aggregator plugin. 
Project-specific events should derive from this class, allowing each subclass to represent a distinct gameplay event.

Additionally, UEventBase can be used as a payload when broadcasting events through the “EventAggregatorSubsystem”. 
Employing UEventBase as a payload promotes type safety when casting payloads to specific types during event handling.