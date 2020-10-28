---
layout: post
title: Interaction and Animation | lineargauge | Syncfusion
description: interaction and animation
platform: aspnet-core
control: lineargauge
documentation: ug
---

# Interaction and Animation

* Linear Gauge control contains Interaction feature. You can use this interaction feature to change the pointer values manually either by clicking or dragging the pointer over the Gauge. It dynamically changes the value of pointer when dragged. To Enable/Disable the user interaction you can use the `read-only` Boolean property. The user interaction option is enabled when you set readOnly property as false. By default it holds the true value.
* Linear Gauge contains another attractive concept called Animation. The animation option enables the movement of the pointer from the minimum value to the current value. You can use animation option to change the pointer value dynamically. You can enable/ disable it using `enable-animation` property. To enable animation set enableAnimation to ‘true’. 
* By default it holds the true value. You can control the speed of the pointer during animating using `animation-speed`. It is a numerical value that holds the time in milliseconds. That is when setting value is 1000, it is considered as 1 second.



{% highlight cshtml %}

 <ej-linear-gauge id="LinearGauge" width="300" height="500" minimum="10" 
 maximum="110" value="78" enable-animation="true" read-only="false" animation-speed="1000" >
<e-linear-scale-collections>
<e-linear-scales width="0" background-color="transparent" show-bar-pointers="true" >
<e-border color="transparent" width="0"></e-border>
<e-marker-pointer-collections>
<e-marker-pointers length="10" markerdistance-from-scale="20" width="10" marker-background-color="Grey">           
</e-marker-pointers>
</e-marker-pointer-collections>
<e-bar-pointer-collections>
<e-bar-pointers width="5" bar-pointerdistance-from-scale="15" bar-pointer-background-color="Grey">
</e-bar-pointers>
</e-bar-pointer-collections>
<e-linear-tick-collections>
<e-linear-ticks type="MajorInterval"  width="2" color="#8c8c8c">
<e-distance-from-scale x="7" y="0"></e-distance-from-scale>
</e-linear-ticks>
<e-linear-ticks type="MinorInterval" height="3"  width="1" color="#8c8c8c">
<e-distance-from-scale x="7" y="0"></e-distance-from-scale>
</e-linear-ticks>
</e-linear-tick-collections>
</e-linear-scales>
</e-linear-scale-collections>
</ej-linear-gauge>       


{% endhighlight %}

Execute the above code to render the following output.

![](Interaction-and-Animation_images/Interaction-and-Animation_img1.png)


### Enable Marker Pointer Animation

Specifies the animate state for marker pointer, you can set `enable-marker-pointer`property as **true**

{% highlight html %}

<ej-linear-gauge id="lineargauge" value=78 enable-marker-pointer="true">    
</ej-linear-gauge>

{% endhighlight %}




