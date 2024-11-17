---
title: "Event Aggregator Statics"
permalink: /eventaggregator/event-aggregator-statics/
layout: single
author_profile: false
toc: false
---

The **Event Aggregator Statics** class is a Blueprint Function Library that provides utility functions for working with the **Event Aggregator** plugin.

{% highlight c++ %}

UCLASS()
class EVENTAGGREGATOR_API UEventAggregatorStatics : public UBlueprintFunctionLibrary

{% endhighlight %}

Currently, it primarily includes logging functions but may be expanded in the future to incorporate additional utility features.

It includes functions such as `AreLogFlagsActive()` and `IsLogFlagActive()`, which allow the plugin to determine whether specific debug 
logs should be written to the **output log**.

These functions are invoked automatically by the system at appropriate points, so manual calls are generally unnecessary.

{% highlight c++ %}

/**
 * Checks whether the supplied log flags are toggled in 'Event Aggregator Settings'.
 *
 * @param InBitmask						Bitmask to compare.
 *
 * @returns True if the supplied log flags are toggled; false otherwise.
 */
UFUNCTION(BlueprintPure, Category = "Event Aggregator|Logging")
static bool AreLogFlagsActive(UPARAM(meta = (Bitmask, BitmaskEnum = "/Script/EventAggregator.EEventAggregatorLogFlags")) const int32 InBitmask);

/**
 * Checks whether the supplied log flag is toggled in 'Event Aggregator Settings'.
 *
 * @param InLogFlag						Specific flag to check for.
 *
 * @returns True if the supplied log flag is toggled; false otherwise.
 */
UFUNCTION(BlueprintPure, Category = "Event Aggregator|Logging")
static bool IsLogFlagActive(const EEventAggregatorLogFlags& InLogFlag);

{% endhighlight %}