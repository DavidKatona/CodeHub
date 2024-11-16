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

To access the subsystem in C++, call its static `Get` function and provide a valid world context object of type `UObject`.

Here's an example of retrieving the subsystem by passing in `this`, as called from a `GameMode` class:

{% highlight c++ %}

// Getting the subsystem in C++.
UEventAggregatorSubsystem* EventAggregator = UEventAggregatorSubsystem::Get(this);

{% endhighlight %}

## Getting the Subsystem in Blueprints

To access and utilize the subsystem in Blueprints, use the editor-generated getter. 
Once retrieved, you can call any of the subsystem's functions directly within your Blueprint scripts.

{% include figure popup=true image_path="/assets/images/eventaggregator-get-subsystem-in-bp.png" %}