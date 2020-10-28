---
layout: post
title: Ticks | lineargauge | Syncfusion
description: ticks
platform: aspnet-core
control: lineargauge
documentation: ug
---

# Ticks

Ticks are used to mark some values on the scale. Based on the tick’s value you can set the labels on the required position.

Adding tick collection 

Tick collection can be directly added to the scale object. Refer the following code example to add tick collection in a Linear Gauge control.



{% highlight js %}

<ej-linear-gauge id="LinearGauge" enable-animation="false" value="78" >
 <e-frame  inner-width="8" outer-width="10" 
 background-image-url="../images/gauge/Gauge_linear_light.png" ></e-frame>
<e-linear-scale-collections>
<e-linear-scales width="0" show-bar-pointers="true" background-color="transparent"
type="@ScaleType.RoundedRectangle" >
<e-border color="transparent" width="0"></e-border>
<e-bar-pointer-collections>
<e-bar-pointers width="6" bar-pointer-background-color="#95C7E0" bar-pointer-distance-from-scale="-15"
bar-pointer-value="30">
</e-bar-pointers>
</e-bar-pointer-collections>
 <e-linear-label-collections>
<e-linear-labels >
<e-distance-from-scale x="-25" y="0" ></e-distance-from-scale>
</e-linear-labels>
</e-linear-label-collections>
<e-linear-tick-collections>
<e-linear-ticks type="@TickType.MajorInterval"  width="2" color="#8c8c8c" >
<e-distance-from-scale x="-10" y="0"></e-distance-from-scale>
</e-linear-ticks>
<e-linear-ticks type="@TickType.MinorInterval" height="6"  width="1" color="#8c8c8c" >
<e-distance-from-scale x="-10" y="0"></e-distance-from-scale>
</e-linear-ticks>
</e-linear-tick-collections>
</e-linear-scales>
</e-linear-scale-collections>
</ej-linear-gauge> 

{% endhighlight %}

Execute the above code to render the following output.

![](Ticks_images/Ticks_img1.png)



## Tick Customization

### Appearance

* Height and width of the ticks can be applied by using the properties height and width. You can customize ticks with the properties like angle, color, etc. angle attribute is used to display the labels in the specified angles and color attribute is used to display the labels in specified color. 
* Ticks are two types such as major and minor. The opacity of the labels can be adjusted with the property opacity. The opacity values lies between 0 and 1.



{% highlight js %}

<ej-linear-gauge id="LinearGauge" enable-animation="false" value="78" >
<e-frame  inner-width="8" outer-width="10" 
 background-image-url="../images/gauge/Gauge_linear_light.png" ></e-frame>
<e-linear-scale-collections>
<e-linear-scales width="0" show-bar-pointers="true" background-color="transparent"
type="@ScaleType.RoundedRectangle" >
<e-border color="transparent" width="0"></e-border>
<e-bar-pointer-collections>
<e-bar-pointers width="6" bar-pointer-background-color="#95C7E0" bar-pointer-distance-from-scale="-15"
bar-pointer-value="30">
</e-bar-pointers>
</e-bar-pointer-collections>
 <e-linear-label-collections>
<e-linear-labels >
<e-distance-from-scale x="-25" y="0" ></e-distance-from-scale>
</e-linear-labels>
</e-linear-label-collections>
<e-linear-tick-collections>
<e-linear-ticks type="@TickType.MajorInterval"  width="2" height="14" angle="10" color="black" placement="@TickPlacement.Near">
<e-distance-from-scale x="-10" y="0"></e-distance-from-scale>
</e-linear-ticks>
<e-linear-ticks type="@TickType.MinorInterval" height="6"  width="1" opacity="0.5" color="black"
placement="@TickPlacement.Near" >
<e-distance-from-scale x="-10" y="0"></e-distance-from-scale>
</e-linear-ticks>
</e-linear-tick-collections>
</e-linear-scales>
</e-linear-scale-collections>
</ej-linear-gauge> 

{% endhighlight %}

Execute the above code to render the following output.

![](Ticks_images/Ticks_img2.png)



### Types

Ticks are two types such as majorInterval and minorInterval. Major type ticks are for major interval values and minor type ticks are for minor interval values.



{% highlight js %}

<ej-linear-gauge id="LinearGauge" enable-animation="false" value="78" >
<e-frame  inner-width="8" outer-width="10" 
 background-image-url="../images/gauge/Gauge_linear_light.png" ></e-frame>
<e-linear-scale-collections>
<e-linear-scales width="5"  background-color="transparent" show-bar-pointers="true" background-color="transparent"
type="@ScaleType.RoundedRectangle" >
<e-border color="Grey" width="1"></e-border>
<e-bar-pointer-collections>
<e-bar-pointers width="5" bar-pointer-background-color="#95C7E0" >
</e-bar-pointers>
</e-bar-pointer-collections>
 <e-linear-label-collections>
<e-linear-labels >
<e-distance-from-scale x="-25" y="0" ></e-distance-from-scale>
</e-linear-labels>
</e-linear-label-collections>
<e-linear-tick-collections>
<e-linear-ticks type="@TickType.MajorInterval"  width="2" height="14" color="black" >
</e-linear-ticks>
<e-linear-ticks type="@TickType.MinorInterval" ></e-linear-ticks>
</e-linear-tick-collections>
</e-linear-scales>
</e-linear-scale-collections>
</ej-linear-gauge> 

{% endhighlight %}

Execute the above code to render the following output.



![](Ticks_images/Ticks_img3.png)



### Positioning the ticks

* You can position ticks with the help of two properties such as distanceFromScale and placement. The property distanceFromScale defines the distance between the scale and ticks. 
* Placement property is used to locate the ticks with respect to scale either inside the scale or outside the scale or along the scale. It is an enumerable data type.



{% highlight js %}

<ej-linear-gauge id="LinearGauge" enable-animation="false" value="78" >
<e-frame  inner-width="8" outer-width="10" 
 background-image-url="../images/gauge/Gauge_linear_light.png" ></e-frame>
<e-linear-scale-collections>
<e-linear-scales width="5"  background-color="transparent" show-bar-pointers="true" background-color="transparent"
type="@ScaleType.RoundedRectangle" >
<e-border color="Grey" width="1"></e-border>
<e-bar-pointer-collections>
<e-bar-pointers width="5" bar-pointer-background-color="#95C7E0" >
</e-bar-pointers>
</e-bar-pointer-collections>
 <e-linear-label-collections>
<e-linear-labels >
<e-distance-from-scale x="-25" y="0" ></e-distance-from-scale>
</e-linear-labels>
</e-linear-label-collections>
<e-linear-tick-collections>
<e-linear-ticks type="@TickType.MajorInterval"  width="2" height="14"  color="red" 
placement="@TickPlacement.Near">
<e-distance-from-scale x="-10" y="0"></e-distance-from-scale>
</e-linear-ticks>
<e-linear-ticks type="@TickType.MinorInterval" opacity="0.5" color="grey"
placement="@TickPlacement.Near" >
<e-distance-from-scale x="-10" y="0"></e-distance-from-scale>
</e-linear-ticks>
</e-linear-scales>
</e-linear-scale-collections>
</ej-linear-gauge> 

{% endhighlight %}

Execute the above code to render the following output.



![](Ticks_images/Ticks_img4.png)



