---
title: "Events in C++"
permalink: /eventaggregator/events-in-cpp/
layout: single
author_profile: false
toc: true
---

For each **gameplay** or **global** event you wish to broadcast, it is advisable to create a distinct subclass of `UEventBase`. 
This approach helps differentiate between various events and allows for the addition of specific parameters or payloads as needed.

For instance, in a shooter game, you may want to create a gameplay event that broadcasts whenever your character takes damage 
(e.g., from a bullet). This allows UI widgets to react, such as by updating the character's health display.

## Creating the C++ event via the Editor

To create an event in C++ via the **Editor**, do the following:

1. Find and click the `Tools` option at the top-left hand corner of the Editor.

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