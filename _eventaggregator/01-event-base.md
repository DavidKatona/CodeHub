---
title: "Event Base"
permalink: /eventaggregator/event-base/
layout: single
author_profile: false
toc: true
---

**Event Base** (UEventBase in C++) derives from **UObject** and serves as the foundational class for defining
events in the **Event Aggregator** plugin. It is intended for extension by project-specific event classes, each subclass
uniquely representing an event or gameplay interaction within the system.

This class is also meant to be utilized as a payload when broadcasting events via the **Event Aggregator Subsystem**.
By using **UEventBase** as a base class for event payloads, developers can take advantage of type-safe casting when handling
and processing specific event types.


## UEventBase in C++

The base class in C++:

{% highlight c++ %}

UCLASS(BlueprintType, Blueprintable)
class EVENTAGGREGATOR_API UEventBase : public UObject

{% endhighlight %}

Developers are recommended to inherit from this base class with each subclass representing a distinct gameplay event.

## UEventBase in Blueprints

Blueprint developers can also utilize **UEventBase** as a foundation for creating their own **'Event Class Blueprints'**.