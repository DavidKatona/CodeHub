---
title: "Creating Events"
permalink: /eventaggregator/creating-events/
layout: single
author_profile: false
toc: true
---

For each **gameplay** or **global** event you wish to broadcast, it is advisable to create a distinct subclass of `UEventBase`. 
This approach helps differentiate between various events and allows for the addition of specific parameters or payloads as needed.

For instance, in a shooter game, you may want to create a gameplay event that broadcasts whenever your character takes damage 
(e.g., from a bullet). This allows UI widgets to react, such as by updating the character's health display.

## Creating a C++ event via the Editor

To create an event in C++ via the **Editor**, do the following:

1. Find and click the `Tools` option at the top-left hand corner of the Editor.
{% highlight c++ %}

	// Getting the subsystem in C++.
	UEventAggregatorSubsystem* EventAggregator = UEventAggregatorSubsystem::Get(this);

{% endhighlight %}
![image-center]({{ "/assets/images/native-events-create-step01.png" | relative_url }}){: .align-center}
2. From the dropdown, select and click `New C++ Class...`.
3. A window called `Add C++ Class` will open. Click on `All Classes`.
![image-center]({{ "/assets/images/native-events-create-step02.png" | relative_url }}){: .align-center}
4. Search for `EventBase` in the search field.
![image-center]({{ "/assets/images/native-events-create-step03.png" | relative_url }}){: .align-center}
5. Once you have `EventBase` selected, click `Next`.
6. Finally, assign a name to your new event class, choose the desired location for its creation, and click `Create Class`.
![image-center]({{ "/assets/images/native-events-create-step04.png" | relative_url }}){: .align-center}

With the new C++ event class created, you can now use that class as a means to broadcast events via the **Event Aggregator Subsystem**.


## Creating a Blueprint event via the Editor

If you prefer to define your events in blueprints you can do so simply via the `Content Browser`, 
the same way you would create any other asset (e.g. a `DataAsset`).

To create an event blueprint, do the following:

1. Navigate to a location where you wish your blueprint to be created in the `Content Browser`.
2. Right-click in the `Content Browser` to open the `Context Menu`.
3. Locate the `Event Aggregator` submenu in the `Context Menu`.
4. Navigate to the `Event Aggregator` submenu, and click `Event Class Blueprint`.
![image-center]({{ "/assets/images/blueprint-events-create-step01.png" | relative_url }}){: .align-center}
5. A new window will appear that will ask you to pick a parent class for your event.
6. Select a parent class for your new event. This will usually be the `EventBase` or your project-specific subclass of the base.
![image-center]({{ "/assets/images/blueprint-events-create-step02.png" | relative_url }}){: .align-center}
7. Once you have the parent class selected, hit `Select`.
8. After you have confirmed your selection, name your event in the `Content Browser`.

## Suggested Naming

It's recommended to name events based on the concept they represent. For instance, if creating an event to signify the 
death of a character, consider a name that clearly conveys this purpose, such as `OnCharacterDied` or `OnPlayerDied.`

It would also be beneficial to prefix your events with something that can be searched for easily in the content browser, 
for example `EBP_`. So for example, `EBP_OnCharacterDied`. *(EBP stands for Event Blueprint)*

Feel free to adjust naming conventions to your projects' needs!