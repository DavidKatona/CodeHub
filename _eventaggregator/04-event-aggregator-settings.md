---
title: "Event Aggregator Settings"
permalink: /eventaggregator/event-aggregator-settings/
layout: single
author_profile: false
toc: false
---

**Event Aggregator Settings** defines a `UObject` settings object for the **Event Aggregator** plugin, allowing you
to customize various aspects of the plugin's behaviour. These settings include debug and general configurations you 
can modify to tailor the plugin to your specific needs.

{% highlight c++ %}

UCLASS(Config=EventAggregator, DefaultConfig, Meta = (DisplayName = "Event Aggregator"))
class EVENTAGGREGATOR_API UEventAggregatorSettings : public UObject

{% endhighlight %}

It also allows you to control which log categories are active and specify the actions to be logged, such as event binding, broadcasting, and more.

The **Event Instance Debugger** can also be configured here, enabling adjustments to its color scheme, row and column sizes, and other visual settings.