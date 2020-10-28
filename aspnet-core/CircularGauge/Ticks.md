---
layout: post
title: Ticks | CircularGauge | Syncfusion
description: ticks
platform: aspnet-core
control: CircularGauge
documentation: ug
---

# Ticks

Ticks are used to mark some values on the scale. Based on the tick’s value you can set the labels on the required position.

## Adding Tick Collection 

Tick collection is directly added to the scale object. Refer the following code example to add tick collection in a Gauge control.

{% highlight CSHTML %}

<ej-circular-gauge id="circulargauge">
<e-circular-scale-collections>
<e-circular-scales>
<e-tick-collections>
<e-ticks color="red" type="@CircularTickTypes.Major"></e-ticks>
</e-tick-collections>
</e-circular-scales>
</e-circular-scale-collections>
</ej-circular-gauge>


{% endhighlight %}
Execute the above code to render the following output.

![](Ticks_images/Ticks_img1.png)

Circular Gauge with tick collection
{:.caption}


## Tick Customization

* Height and width of the ticks can be applied by using the properties height and width. You can customize ticks with the properties such as angle, color, etc. angle attribute is used to display the labels in the specified angles and color attribute is used to display the labels in specified color. Ticks are two types such as major and minor.
* Major type ticks are for major interval values and minor type ticks are for minor interval values.You can position ticks with the help of two properties such as distanceFromScale and placement. distanceFromScale property defines the distance between the scale and ticks.  Placement property is used to locate the ticks with respect to scale either inside the scale or outside the scale or along the scale. It is an enumerable data type.

{% highlight CSHTML %}

<ej-circular-gauge id="circulargauge">
<e-circular-scale-collections>
<e-circular-scales>
<e-tick-collections>
// for tick 1
<e-ticks color="red" type="@CircularTickTypes.Major"></e-ticks>
// for tick 2
<e-ticks color="yellow" type="@CircularTickTypes.Minor" height="8" 
placement="@TickPlacement.Near" distance-from-scale="5"></e-ticks>
</e-tick-collections>
</e-circular-scales>
</e-circular-scale-collections>
</ej-circular-gauge>

{% endhighlight  %}

Execute the above code to render the following output.

![](Ticks_images/Ticks_img2.png)

Circular Gauge with tick customization
{:.caption}




