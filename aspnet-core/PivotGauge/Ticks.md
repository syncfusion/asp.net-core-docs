---
layout: post
title: Ticks | ASP.NET Core | PivotGauge | Syncfusion
description: This document illustrates that how to enable ticks and its customization in ASP.NET Core PivotGauge control
platform: aspnet-core
control: PivotGauge
documentation: ug
---

# Ticks

## Adding tick collection

The tick collection can be directly added to the scales option within the pivot gauge control.

{% highlight cshtml %}

<ej-pivot-gauge id="PivotGauge1">
    <e-scales>
        <e-circular-scales>
            <e-tick-collections>
                <e-ticks type="Major"></e-ticks>
            </e-tick-collections>
        </e-circular-scales>
    </e-scales>
</ej-pivot-gauge>

{% endhighlight %}

## Tick customization

The appearance of the tick can be customized through the following properties:

* **type**: Indicates whether ticks are for major or minor intervals. By default, the type is "Major".
* **height**: Sets the height of the ticks.
* **width**: Sets the width of the ticks.
* **angle**: Rotates the ticks to a specified angle. By default, the angle value is 0.
* **color**: Displays the ticks in specified color.
* **distance-from-scale**: Sets the distance between scale and ticks. By default, the value is 0.
* **placement**: Positions the ticks with respect to the scale. By default, the value is set to "Far".

{% highlight cshtml %}

<ej-pivot-gauge id="PivotGauge1">
    <e-scales>
        <e-circular-scales>
            <e-tick-collections>
                <e-ticks type="Major" height="15" width="4" angle="0" placement="Near" distance-from-scale="2" color="green"></e-ticks>
            </e-tick-collections>
        </e-circular-scales>
    </e-scales>
</ej-pivot-gauge>

{% endhighlight %}

![Ticks in ASP NET Core pivot gauge control](Ticks_images/TickCustomization.png) 

