---
title: "Events in Blueprints"
permalink: /eventaggregator/events-in-blueprints/
layout: single
author_profile: false
toc: true
---

If you prefer to define your events in blueprints you can do so simply via the `Content Browser`, 
the same way you would create any other asset (e.g. a `DataAsset`).

## Creating a Blueprint event via the Editor

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