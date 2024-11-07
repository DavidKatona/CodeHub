---
title: "Event Base"
permalink: /eventaggregator/event-base/
layout: single
author_profile: false
toc: true
---

**EventBase** serves as the base class for events within the **Event Aggregator** plugin. 
Project-specific events should derive from this class, allowing each subclass to represent a distinct gameplay event.

Additionally, **EventBase** can be used as a payload when broadcasting events through the **EventAggregatorSubsystem**. 
Employing **EventBase** as a payload promotes type safety when casting payloads to specific types during event handling.

{% highlight c++ %}

UCLASS(BlueprintType, Blueprintable)
class EVENTAGGREGATOR_API UEventBase : public UObject

{% endhighlight %}