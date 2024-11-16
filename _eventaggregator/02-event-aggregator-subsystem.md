---
title: "Event Aggregator Subsystem"
permalink: /eventaggregator/event-aggregator-subsystem/
layout: single
author_profile: false
toc: true
---

The **Event Aggregator Subsystem** serves as the core component of the plugin. Derived from `UGameInstanceSubsystem`, 
it provides the foundation for managing and utilizing global events.

Key features include functions such as **Bind** and **Unbind**, which streamline the management of global event subscriptions. 
The subsystem facilitates the observation and dispatch of global events to various objects, actors, and game systems, 
ensuring *loose coupling* between broadcasters and receivers.

{% highlight c++ %}

UCLASS()
class EVENTAGGREGATOR_API UEventAggregatorSubsystem : public UGameInstanceSubsystem

{% endhighlight %}

## Getting the Subsystem in C++



{% highlight c++ %}

// Getting the subsystem in C++.
UEventAggregatorSubsystem* EventAggregator = UEventAggregatorSubsystem::Get(this);

{% endhighlight %}

## Getting the Subsystem in Blueprints

TBA