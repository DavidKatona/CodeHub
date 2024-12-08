---
title: "Binding Events"
permalink: /eventaggregator/binding-events/
layout: single
author_profile: false
toc: true
---

Binding an event means associating a specific action or function with that event so that when the event occurs, the bound function is automatically triggered or executed.

For example, in your UI or HUD, you might bind an "OnCharacterDamaged" event, so that when the character takes damage, the UI reacts by updating your health bar to reflect the changes.

## Binding Events in C++

To bind an event in C++, you will have to retrieve the "Event Aggregator Subsystem", then use its functions to set up the event binding.

1. Retrieve the **Event Aggregator Subsystem** by using its static getter: `UEventAggregatorSubsystem::Get()`.
![image-center]({{ "/assets/images/event-aggregator/binding-events-in-cpp01.png" | relative_url }}){: .align-center}
2. Add the following include to the top of your file: **#include "System/EventAggregatorSubsystem.h"**
3. Declare a variable of type `FOnGlobalEventBroadcastedSignature`.
![image-center]({{ "/assets/images/event-aggregator/binding-events-in-cpp02.png" | relative_url }}){: .align-center}
4. Bind the function you want to execute to the `FOnGlobalEventBroadcastedSignature` variable you just declared.
![image-center]({{ "/assets/images/event-aggregator/binding-events-in-cpp03.png" | relative_url }}){: .align-center}
*`ThisClass` can be replaced with your class name instead, if you prefer grabbing function pointers by explicitly stating the class type.*
5. You can now pass the newly bound variable to the **Event Aggregator Subsystem**, by calling `UEventAggregatorSubsystem::BindGlobalEventByClass()`.
![image-center]({{ "/assets/images/event-aggregator/binding-events-in-cpp04.png" | relative_url }}){: .align-center}

When put together, you should have something like this:
![image-center]({{ "/assets/images/event-aggregator/binding-events-in-cpp05.png" | relative_url }}){: .align-center}

## Binding events in Blueprints

Binding events in blueprints is similar to how you would handle them in C++. Unreal, however, makes it a bit easier with the helpers it provides in blueprint event graphs.

To bind an event in blueprints, do the following:

1. Retrieve the *Event Aggregator Subsystem* (right click in the *Event Graph* and search for *Event Aggregator*).
![image-center]({{ "/assets/images/event-aggregator/binding-events-in-bp01.png" | relative_url }}){: .align-center}