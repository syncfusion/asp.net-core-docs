---
layout: post
title: Ruler is used to measure the distance of nodes and connectors from origin of the page.
description:  how to measure the distance of Nodes and Connectors?
platform: aspnet-core
control: Diagram
documentation: ug
---


# Rulers

The `Ruler` provides a Horizontal and Vertical guide for measuring in the Diagram control. The Ruler can be used to measure the Diagram objects, indicate positions, and align Diagram elements. This is especially useful in creating scale models. 

## Adding Rulers to the Diagram
Rulers can be enabled by setting the ruler Setting’s `ShowRulers` property for the diagram control.

Use the following code example to enable/disable the ruler to the Diagram.

{% highlight razor %}

     <ej-diagram id="diagram" width="1000px" height="600px" enable-context-menu="false">
         <e-ruler-settings show-rulers="true">
         </e-ruler-settings>
     </ej-diagram>

{% endhighlight %}

![](/aspnet-core/Diagram/Rulers_images/Rulers_image1.png)

## Customizing the Ruler

The rulerSetting's `Interval` property is used to define the number of tick's between two major stroke lines of the ruler. 

The ruler Setting’s `SegmentWidth` is used to defines the space between the two major tick strokes.

The `ArrangeTick` event will be triggered when each tick have been drawn.By using this event you can customize the length of the tick.

Use the following code example to customize the ruler's segment.

{% tabs %}
{% highlight razor %}

    <ej-diagram id="diagram" width="1000px" height="600px" enable-context-menu="false">
        <e-ruler-settings show-rulers="true">
            <e-horizontal-ruler interval="6" segment-width="100" arrange-tick="arrangeTick"></e-horizontal-ruler>
            <e-vertical-ruler interval="6" segment-width="100" arrange-tick="arrangeTick"></e-vertical-ruler>
        </e-ruler-settings>
    </ej-diagram>

{% endhighlight %}

{% highlight js %}

function arrangeTick(args) {
    
	// Customizing the Ruler ticks.
    if (args.tickInterval % 100 == 0) {
    }
    else if (args.tickInterval % 50 == 0) {
        args.tickLength = 12.5
    }
}

{% endhighlight %}



The width of the ruler can be set through `Thickness` property. If it’s an horizontal ruler, thickness will be taken as height of the ruler.

Tick alignment can be modified using `TickAlignment` as either `LeftOrTop` or `RightOrBottom`.

The `MarkerColor` property of the ruler is used to indicate the position of the mouse cursor.

Use the following code example to customize the ruler's tick.

{% highlight razor %}

     <ej-diagram id="diagram" width="1000px" height="600px" enable-context-menu="false">
         <e-ruler-settings show-rulers="true">
             <e-horizontal-ruler marker-color="blue" thickness="25" tick-alignment="LeftOrTop"></e-horizontal-ruler>
             <e-vertical-ruler marker-color="blue" thickness="25" tick-alignment="LeftOrTop"></e-vertical-ruler>
         </e-ruler-settings>
     </ej-diagram>

{% endhighlight %}

{% endtabs %}

![](/aspnet-core/Diagram/Rulers_images/Rulers_image2.png)

