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
*You will need to include `EventAggregator.h` in the file you wish to use the subsystem. Use the include below!*
**#include "System/EventAggregatorSubsystem.h"**
2. Declare a variable of type `FOnGlobalEventBroadcastedSignature`.