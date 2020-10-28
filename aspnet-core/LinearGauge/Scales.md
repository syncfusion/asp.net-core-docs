---
layout: post
title: Scales | lineargauge |  Syncfusion
description: scales
platform: aspnet-core
control: lineargauge
documentation: ug
---

# Scales

Scales are the basic functional block of the Linear Gauge. You can improve the appearance of scales by customizing it. The functional blocks of Linear Gauge are 

* Marker Pointers
* Bar Pointer
* Labels
* Custom Labels
* Indicators
* Ticks
* Ranges



## Adding scale collection

Scale is the basic element of Linear Gauge. Scale collection is directly added to the gauge object. Refer the following code example to add scale collection in Gauge control. 



{% highlight cshtml %}

<ej-linear-gauge id="LinearGauge" enable-animation="false" >
 <e-frame background-image-url="../images/gauge/Gauge_linear_light.png" ></e-frame>
<e-linear-scale-collections>
<e-linear-scales width="8" background-color="Grey" show-bar-pointers="false" show-marker-pointers="true" >
<e-linear-position x="20" y="50"></e-linear-position>
<e-border color="Grey" width="0"></e-border>
<e-linear-label-collections>
<e-linear-labels >
<e-distance-from-scale x="50" y="0"></e-distance-from-scale>
</e-linear-labels>
</e-linear-label-collections>
<e-marker-pointer-collections>
<e-marker-pointers length="10" markerdistance-from-scale="20" width="20" type="@MarkerType.Pentagon" marker-background-color="#FE8282" placement="@PointerPlacement.Near">           
</e-marker-pointers>
</e-marker-pointer-collections>
<e-linear-tick-collections>
<e-linear-ticks type="MajorInterval"  width="2" color="#8c8c8c">
<e-distance-from-scale x="30" y="0"></e-distance-from-scale>
</e-linear-ticks>
<e-linear-ticks type="MinorInterval" height="6"  width="1" color="#8c8c8c">
<e-distance-from-scale x="30" y="0"></e-distance-from-scale>
</e-linear-ticks>
</e-linear-tick-collections>
</e-linear-scales>
</e-linear-scale-collections>
</ej-linear-gauge>   

{% endhighlight %}

Execute the above code to render the following output.

![](Scales_images/Scales_img1.png)



## Scale Customization

### Colors and Border

* The Scale border is modified with border object. It has two border property, color and width  are used to customize the border color of the scale and border width of the scale. Setting the background color improves the look and feel of the Linear Gauge. You can customize the background color of the scale using backgroundColor. 
* Scales are used to enable or disable various properties such as showRanges, showIndicators, showCustomLabels, showLabels, showTicks, showBarPointers and showMarkerPointers. Enable/disable is done by setting the property into two states either “true” or “false”. You can adjust the Opacity of the scale with opacity property.



{% highlight cshtml %}

<ej-linear-gauge id="LinearGauge" enable-animation="false" >
 <e-frame background-image-url="../images/gauge/Gauge_linear_light.png" ></e-frame>
<e-linear-scale-collections>
<e-linear-scales width="8" background-color="#FE8282" show-bar-pointers="false" show-marker-pointers="true" shadow-offset="10" scale-opacity="0.5" type="@ScaleType.RoundedRectangle" >
<e-linear-position x="20" y="50"></e-linear-position>
<e-border color="Red" width="1"></e-border>
<e-linear-label-collections>
<e-linear-labels >
<e-distance-from-scale x="50" y="0"></e-distance-from-scale>
</e-linear-labels>
</e-linear-label-collections>
<e-marker-pointer-collections>
<e-marker-pointers length="10" markerdistance-from-scale="20" width="20" type="@MarkerType.Pentagon" marker-background-color="#C9E1E5" placement="@PointerPlacement.Near">           
</e-marker-pointers>
</e-marker-pointer-collections>
<e-linear-tick-collections>
<e-linear-ticks type="MajorInterval"  width="2" color="#8c8c8c">
<e-distance-from-scale x="30" y="0"></e-distance-from-scale>
</e-linear-ticks>
<e-linear-ticks type="MinorInterval" height="6"  width="1" color="#8c8c8c">
<e-distance-from-scale x="30" y="0"></e-distance-from-scale>
</e-linear-ticks>
</e-linear-tick-collections>
</e-linear-scales>
</e-linear-scale-collections>
</ej-linear-gauge>   

{% endhighlight %}

Execute the above code to render the following output.

![](Scales_images/Scales_img2.png)



### Appearance 

* You can improve the appearance of Linear Gauge using various properties. You can set the interval values for the scale with major interval value and minor interval value properties and maximum and minimum value by minimum and maximum property. The width property is used to set the scale bar width. 
* You can also adjust the Opacity of the scale with opacity property. The value for opacity lies between 0 and 1.Linear Gauge contains two scale directions, clockwise and counter clockwise. It can be set with direction property.



{% highlight cshtml %}

<ej-linear-gauge id="LinearGauge" enable-animation="false" >
 <e-frame background-image-url="../images/gauge/Gauge_linear_light.png" ></e-frame>
<e-linear-scale-collections>
<e-linear-scales width="18" minimum="10" maximum="20" minor-interval-value="25" major-interval-value="50"
direction="@Directions.CounterClockwise" background-color="Grey" 
show-bar-pointers="false" show-marker-pointers="true">
<e-linear-position x="20" y="50"></e-linear-position>
<e-border color="Red" width="1"></e-border>
<e-linear-label-collections>
<e-linear-labels >
<e-distance-from-scale x="50" y="0"></e-distance-from-scale>
</e-linear-labels>
</e-linear-label-collections>
<e-marker-pointer-collections>
<e-marker-pointers length="10" markerdistance-from-scale="20" width="20" type="@MarkerType.Pentagon" marker-background-color="#FE8282" placement="@PointerPlacement.Near">           
</e-marker-pointers>
</e-marker-pointer-collections>
<e-linear-tick-collections>
<e-linear-ticks type="MajorInterval"  width="2" color="#8c8c8c">
<e-distance-from-scale x="30" y="0"></e-distance-from-scale>
</e-linear-ticks>
<e-linear-ticks type="MinorInterval" height="6"  width="1" color="#8c8c8c">
<e-distance-from-scale x="30" y="0"></e-distance-from-scale>
</e-linear-ticks>
</e-linear-tick-collections>
</e-linear-scales>
</e-linear-scale-collections>
</ej-linear-gauge>  


{% endhighlight %}

Execute the above code to render the following output.

![](Scales_images/Scales_img3.png)



## Scale Types

Scale Type is an element which decides the appearance of the gauge. Linear Gauge contains three scale types such as,

* Rectangle
* Rounded Rectangle
* Thermometer



### Rectangle

For rectangular scale type, the scale renders with rectangular structure. Refer the following code example.



{% highlight cshtml %}

<ej-linear-gauge id="LinearGauge" enable-animation="false" >
 <e-frame background-image-url="../images/gauge/Gauge_linear_light.png" ></e-frame>
<e-linear-scale-collections>
<e-linear-scales width="18" length="300" background-color="#C0B082"  show-marker-pointers="false" type="@ScaleType.Rectangle" >
<e-linear-position x="54" y="50"></e-linear-position>
<e-border color="#C0B082" width="1"></e-border>
<e-linear-tick-collections>
<e-linear-ticks type="MajorInterval"  width="2" color="#206BA4" placement="@TickPlacement.Far">
<e-distance-from-scale x="-27" y="0"></e-distance-from-scale>
</e-linear-ticks>
<e-linear-ticks type="MinorInterval" height="6"  width="1" color="#206BA4" placement="@TickPlacement.Far">
<e-distance-from-scale x="-27" y="0"></e-distance-from-scale>
</e-linear-ticks>
</e-linear-tick-collections>
</e-linear-scales>
</e-linear-scale-collections>
</ej-linear-gauge>   

{% endhighlight %}



Execute the above code to render the following output.

![](Scales_images/Scales_img4.png)

Rounded Rectangle

{:.caption}

For rounded rectangular scale type, the scale renders as rectangular structure but with constant radius rounded corner. Refer the following code example.



{% highlight cshtml %}

<ej-linear-gauge id="LinearGauge" enable-animation="false" >
 <e-frame background-image-url="../images/gauge/Gauge_linear_light.png" ></e-frame>
<e-linear-scale-collections>
<e-linear-scales width="8" background-color="#206BA4" direction="@Directions.Clockwise"
type="@ScaleType.RoundedRectangle" >
<e-linear-position x="60" y="50"></e-linear-position>
<e-border color="#206BA4" width="1"></e-border>
<e-linear-label-collections>
<e-linear-labels >
<e-distance-from-scale x="-20" y="0"></e-distance-from-scale>
</e-linear-labels>
</e-linear-label-collections>
<e-linear-tick-collections>
<e-linear-ticks type="MajorInterval"  width="2" color="#206BA4" placement="@TickPlacement.Far">
<e-distance-from-scale x="-27" y="0"></e-distance-from-scale>
</e-linear-ticks>
<e-linear-ticks type="MinorInterval" height="6"  width="1" color="#206BA4" placement="@TickPlacement.Far">
<e-distance-from-scale x="-27" y="0"></e-distance-from-scale>
</e-linear-ticks>
</e-linear-tick-collections>
</e-linear-scales>
</e-linear-scale-collections>
</ej-linear-gauge>   


{% endhighlight %}

Execute the above code to render the following output.

![](Scales_images/Scales_img5.png)



## Thermometer

For thermometer scale type, the scale renders as thermometer structure with rounded bottom. Refer the following code example.



{% highlight cshtml %}

<ej-linear-gauge id="LinearGauge" enable-animation="false" >
 <e-frame background-image-url="../images/gauge/Gauge_linear_light.png" ></e-frame>
<e-linear-scale-collections>
<e-linear-scales width="18" length="300" background-color="#C0B082"  show-marker-pointers="false" type="@ScaleType.Thermometer"show-bar-pointers="false">
<e-linear-position x="54" y="50"></e-linear-position>
<e-border color="#C0B082" width="1"></e-border>
<e-linear-tick-collections>
<e-linear-ticks type="MajorInterval"  width="2" color="#206BA4" placement="@TickPlacement.Far">
<e-distance-from-scale x="-27" y="0"></e-distance-from-scale>
</e-linear-ticks>
<e-linear-ticks type="MinorInterval" height="6"  width="1" color="#206BA4" placement="@TickPlacement.Far">
<e-distance-from-scale x="-27" y="0"></e-distance-from-scale>
</e-linear-ticks>
</e-linear-tick-collections>
</e-linear-scales>
</e-linear-scale-collections>
</ej-linear-gauge> 

{% endhighlight %}

Execute the above code to render the following output.

![](Scales_images/Scales_img6.png)



Adding multiple scales

You can set multiple scales for a single Linear Gauge control by using an array of scale objects. Each scale object is independent of each other. Refer the following code example to add multiple scale collection. 

{% highlight cshtml %}

<ej-linear-gauge id="LinearGauge" enable-animation="false" >
 <e-frame background-image-url="../images/gauge/Gauge_linear_light.png" ></e-frame>
<e-linear-scale-collections>
<e-linear-scales width="8" length="300" background-color="Grey"  show-marker-pointers="true"  show-bar-pointers="false" >
<e-linear-position x="15" y="50"></e-linear-position>
<e-border color="Grey" width="1"></e-border>
<e-linear-label-collections>
<e-linear-labels >
<e-distance-from-scale x="50" y="0"></e-distance-from-scale>
</e-linear-labels>
</e-linear-label-collections>
<e-marker-pointer-collections>
<e-marker-pointers length="10" markerdistance-from-scale="20" width="20" type="@MarkerType.Pentagon" marker-background-color="#FE8282" placement="@PointerPlacement.Near">           
</e-marker-pointers>
</e-marker-pointer-collections>
<e-linear-tick-collections>
<e-linear-ticks type="MajorInterval"  width="2" color="#8c8c8c" >
<e-distance-from-scale x="30" y="0"></e-distance-from-scale>
</e-linear-ticks>
<e-linear-ticks type="MinorInterval" height="6"  width="1" color="#8c8c8c">
<e-distance-from-scale x="30" y="0"></e-distance-from-scale>
</e-linear-ticks>
</e-linear-tick-collections>
</e-linear-scales>
// adding scale 2 
<e-linear-scales width="8" background-color="#206BA4" direction="@Directions.Clockwise"  show-marker-pointers="false"  show-bar-pointers="false" show-labels="false" type="@ScaleType.RoundedRectangle" >
<e-linear-position x="90" y="50"></e-linear-position>
<e-border color="#206BA4" width="1"></e-border>
<e-linear-tick-collections>
<e-linear-ticks type="MajorInterval"  width="2" color="#206BA4" placement="@TickPlacement.Far">
<e-distance-from-scale x="-27" y="0"></e-distance-from-scale>
</e-linear-ticks>
<e-linear-ticks type="MinorInterval" height="6"  width="1" color="#206BA4" placement="@TickPlacement.Far">
<e-distance-from-scale x="-27" y="0"></e-distance-from-scale>
</e-linear-ticks>
</e-linear-tick-collections>
</e-linear-scales>
//adding scale 3
<e-linear-scales width="18" length="300" background-color="#C0B082"  type="@ScaleType.Thermometer" show-marker-pointers="false"  show-bar-pointers="false" show-labels="false" show-ticks="false" >
<e-linear-position x="54" y="50"></e-linear-position>
<e-border color="#C0B082" width="1"></e-border>
<e-linear-tick-collections>
<e-linear-ticks type="MajorInterval"  width="2" color="#206BA4" placement="@TickPlacement.Far">
<e-distance-from-scale x="-27" y="0"></e-distance-from-scale>
</e-linear-ticks>
<e-linear-ticks type="MinorInterval" height="6"  width="1" color="#206BA4" placement="@TickPlacement.Far">
<e-distance-from-scale x="-27" y="0"></e-distance-from-scale>
</e-linear-ticks>
</e-linear-tick-collections>
</e-linear-scales>
</e-linear-scale-collections>
</ej-linear-gauge> 


{% endhighlight %}

Execute the above code to render the following output.

![](Scales_images/Scales_img7.png)



