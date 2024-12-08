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
{% highlight c++ %}
// Getting the subsystem in C++.
UEventAggregatorSubsystem* EventAggregator = UEventAggregatorSubsystem::Get(this);
{% endhighlight %}
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

1. Retrieve the **Event Aggregator Subsystem** (right click in the `Event Graph` and search for `Event Aggregator`).
![image-center]({{ "/assets/images/event-aggregator/binding-events-in-bp01.png" | relative_url }}){: .align-center}
2. Select "Get EventAggregatorSubsystem" from the list of actions.
3. Drag a new node from the `Return Value` pin of the "Event Aggregator Subsystem Node" and type `Bind` in the search bar:
![image-center]({{ "/assets/images/event-aggregator/binding-events-in-bp02.png" | relative_url }}){: .align-center}
4. Select `Bind Global Event by Class`.
![image-center]({{ "/assets/images/event-aggregator/binding-events-in-bp03.png" | relative_url }}){: .align-center}
5. Make sure to select an `In Event Class` on the newly dragged out node in the graph.
![image-center]({{ "/assets/images/event-aggregator/binding-events-in-bp04.png" | relative_url }}){: .align-center}
6. Select the event you wish to bind to, then tick `Bind Unique` if you want to ensure that this is a unique binding.
*Unique binding means that if the same function from the same object has been bound already to the event, it won't bind it again.*
7. Drag another node from the `In Event` parameter of the function then type `Create Event` in the search bar.
![image-center]({{ "/assets/images/event-aggregator/binding-events-in-bp05.png" | relative_url }}){: .align-center}
8. Click `Create Event`.
9. Click the `Select Function...` dropdown on the node and select the function you wish to bind to the event. 
Usually this will be `Create a matching function...` or `Create a matching event...`, whichever you prefer, 
or in case you already have a function with a matching signature, you can select that one as well.
![image-center]({{ "/assets/images/event-aggregator/binding-events-in-bp06.png" | relative_url }}){: .align-center}
10. With everything set up, you will have something like this:
![image-center]({{ "/assets/images/event-aggregator/binding-events-in-bp07.png" | relative_url }}){: .align-center}