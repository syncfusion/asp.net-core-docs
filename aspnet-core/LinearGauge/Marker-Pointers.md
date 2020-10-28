---
layout: post
title: Marker Pointers | lineargauge |  Syncfusion
description: marker pointers
platform: aspnet-core
control: lineargauge
documentation: ug
---

# Marker Pointers

Marker Pointer value points out the actual value set in the Linear Gauge. You can set values for various pointer attributes such as value, type, length, width, border and color in pointer collection. You can also customize the pointers to improve the appearance of gauge.

## Adding marker pointer collection

You can add Marker Pointer collection directly to the scale object. To add pointer collection in a gauge control refer the following code example.  


{% highlight cshtml  %}

<ej-linear-gauge id="LinearGauge" value="78"  >
<e-linear-scale-collections>
<e-linear-scales width="0" show-bar-pointers="true" >
<e-border color="transparent" width="0"></e-border>
<e-marker-pointer-collections>
<e-marker-pointers length="10" markerdistance-from-scale="17" width="5" marker-background-color="Grey">           
</e-marker-pointers>
</e-marker-pointer-collections>
<e-bar-pointer-collections>
<e-bar-pointers width="5" bar-pointerdistance-from-scale="15" bar-pointer-background-color="Grey">
</e-bar-pointers>
</e-bar-pointer-collections>
<e-linear-tick-collections>
<e-linear-ticks type="@TickType.MajorInterval"  width="2" color="#8c8c8c">
<e-distance-from-scale x="7" y="0"></e-distance-from-scale>
</e-linear-ticks>
<e-linear-ticks type="@TickType.MinorInterval" height="6"  width="1" color="#8c8c8c">
<e-distance-from-scale x="7" y="0"></e-distance-from-scale>
</e-linear-ticks>
</e-linear-tick-collections>
</e-linear-scales>
</e-linear-scale-collections>
</ej-linear-gauge>  


{% endhighlight %}

Execute the above code to render the following output.


![](Marker-Pointers_images/Marker-Pointers_img1.png)



## Add marker pointer value

The value property is the important element in the marker pointer collection which indicates the gauge value. Real purpose of the Linear Gauge is based on the pointer value. You can set the pointer value either directly during rendering the control or it can be achieved by public method.



{% highlight cshtml %}

<ej-linear-gauge id="LinearGauge" width="600" height="150" orientation="@Orientation.Horizontal"
label-color="Black" enable-animation="false" >
 <e-frame background-image-url="../images/gauge/Gauge_linear_light1.png" ></e-frame>
<e-linear-scale-collections>
<e-linear-scales width="30" background-color="#AEC75F" direction="@Directions.Clockwise"
type="@ScaleType.RoundedRectangle" show-bar-pointers="true" >
<e-border color="#AEC75F" width="0"></e-border>
<e-marker-pointer-collections>
<e-marker-pointers width="30" length="30" markerdistance-from-scale="20" 
 marker-background-color="#FE5C09" placement="@PointerPlacement.Near" value="67.5">           
</e-marker-pointers>
</e-marker-pointer-collections>
<e-linear-label-collections>
<e-linear-labels angle="90">
<e-distance-from-scale x="100" y="0" ></e-distance-from-scale>
</e-linear-labels>
</e-linear-label-collections>
<e-linear-tick-collections>
<e-linear-ticks type="@TickType.MajorInterval"  width="2" color="#8c8c8c">
<e-distance-from-scale x="45" y="0"></e-distance-from-scale>
</e-linear-ticks>
<e-linear-ticks type="@TickType.MinorInterval" height="6"  width="1" color="#8c8c8c">
<e-distance-from-scale x="45" y="0"></e-distance-from-scale>
</e-linear-ticks>
</e-linear-tick-collections>
</e-linear-scales>
</e-linear-scale-collections>
</ej-linear-gauge>  


{% endhighlight %}

Execute the above code to render the following output.


![](Marker-Pointers_images/Marker-Pointers_img2.png)



## Pointer Styles

### Appearance

* Based on the value, the pointer points out the label value. You can set the pointer length and width using length and width property respectively. You can also adjust the opacity of the pointer using the opacity property which holds the value between 0 and 1. You can add the gradient effects to the pointer using gradient object. 
* The marker pointer border is modified with the border object. It contains two border property namely color and width which are used to customize the border color of the scale and border width of the marker pointer. The background color can be customized with attribute backgroundColor.



{% highlight cshtml %}

<ej-linear-gauge id="LinearGauge" width="600" height="150" orientation="@Orientation.Horizontal"
label-color="Black" enable-animation="false" >
 <e-frame background-image-url="../images/gauge/Gauge_linear_light1.png" ></e-frame>
<e-linear-scale-collections>
<e-linear-scales width="30" background-color="#AEC75F" direction="@Directions.Clockwise"
type="@ScaleType.RoundedRectangle" show-bar-pointers="true" >
<e-border color="#AEC75F" width="0"></e-border>
<e-marker-pointer-collections>
<e-marker-pointers width="30" length="30" marker-opacity="0.4" marker-background-color="#FCDD34" markerdistance-from-scale="20" 
placement="@PointerPlacement.Near" value="67.5">           
</e-marker-pointers>
</e-marker-pointer-collections>
<e-linear-label-collections>
<e-linear-labels angle="90">
<e-distance-from-scale x="100" y="0" ></e-distance-from-scale>
</e-linear-labels>
</e-linear-label-collections>
<e-linear-tick-collections>
<e-linear-ticks type="@TickType.MajorInterval"  width="2" color="#8c8c8c">
<e-distance-from-scale x="-1" y="45"></e-distance-from-scale>
</e-linear-ticks>
<e-linear-ticks type="@TickType.MinorInterval" height="6"  width="1" color="#8c8c8c">
<e-distance-from-scale x="-1" y="45"></e-distance-from-scale>
</e-linear-ticks>
</e-linear-tick-collections>
</e-linear-scales>
</e-linear-scale-collections>
</ej-linear-gauge>  

{% endhighlight %}

Execute the above code to render the following output.

![](Marker-Pointers_images/Marker-Pointers_img3.png)



## Positioning the pointer

* You can position the Pointer with two properties, distanceFromScale and placement. The distanceFromScale property defines the distance between the scale and pointer. 
* The Placement property is used to locate the pointer with respect to scale either inside or outside the scale or along the scale. It is an enumerable data type.



{% highlight cshtml %}

<ej-linear-gauge id="LinearGauge" width="600" height="150" orientation="@Orientation.Horizontal"
label-color="Black" enable-animation="false" >
 <e-frame background-image-url="../images/gauge/Gauge_linear_light1.png" ></e-frame>
<e-linear-scale-collections>
<e-linear-scales width="30" background-color="#AEC75F" direction="@Directions.Clockwise"
type="@ScaleType.RoundedRectangle" show-bar-pointers="true" >
<e-border color="#AEC75F" width="0"></e-border>
<e-marker-pointer-collections>
<e-marker-pointers width="30" length="30" marker-opacity="0.4" marker-background-color="#01A357" markerdistance-from-scale="60" 
placement="@PointerPlacement.Near" value="55.5">           
</e-marker-pointers>
</e-marker-pointer-collections>
<e-linear-label-collections>
<e-linear-labels angle="90">
<e-distance-from-scale x="100" y="0" ></e-distance-from-scale>
</e-linear-labels>
</e-linear-label-collections>
<e-linear-tick-collections>
<e-linear-ticks type="@TickType.MajorInterval"  width="2" color="#8c8c8c">
<e-distance-from-scale x="-1" y="45"></e-distance-from-scale>
</e-linear-ticks>
<e-linear-ticks type="@TickType.MinorInterval" height="6"  width="1" color="#8c8c8c">
<e-distance-from-scale x="-1" y="45"></e-distance-from-scale>
</e-linear-ticks>
</e-linear-tick-collections>
</e-linear-scales>
</e-linear-scale-collections>
</ej-linear-gauge>  

{% endhighlight %}

Execute the above code to render the following output.

![](Marker-Pointers_images/Marker-Pointers_img4.png)



## Types

It is possible to change the dimension of the marker pointer. Dimensions available for marker pointer are,

* Rectangle
* Triangle
* Ellipse
* Diamond
* Pentagon
* Circle
* Slider
* Pointer
* Wedge
* Trapezoid
* Rounded Rectangle



### Multiple Marker Pointers

Linear Gauge can contain multiple pointers on it. You can use any combination and any number of pointers in a gauge. That is, a gauge can contain any number of marker pointer and any number of bar pointers. Refer the following code example containing multiple marker pointers.



{% highlight cshtml %}

<ej-linear-gauge id="LinearGauge" width="600" height="150" orientation="@Orientation.Horizontal"
label-color="Black" enable-animation="false" >
 <e-frame background-image-url="../images/gauge/Gauge_linear_light1.png" ></e-frame>
<e-linear-scale-collections>
<e-linear-scales width="30" background-color="#AEC75F" direction="@Directions.Clockwise"
type="@ScaleType.RoundedRectangle" show-custom-labels="true" >
<e-border color="#AEC75F" width="0"></e-border>
<e-marker-pointer-collections>
<e-marker-pointers width="30" length="30" marker-opacity="0.4" marker-background-color="#01A357" markerdistance-from-scale="60" 
placement="@PointerPlacement.Near" value="32.2">           
</e-marker-pointers>
// adding second marker 
<e-marker-pointers width="10" length="30"  marker-background-color="#90DAFB" markerdistance-from-scale="60" type="@MarkerType.Circle"
placement="@PointerPlacement.Near" value="23.7">           
</e-marker-pointers>
// adding third marker
<e-marker-pointers width="3" length="30" marker-background-color="#90DAFB" markerdistance-from-scale="60" type="@MarkerType.Star"
placement="@PointerPlacement.Near" value="23.7">           
</e-marker-pointers>
</e-marker-pointer-collections>
<e-linear-label-collections>
<e-linear-labels angle="90">
<e-distance-from-scale x="100" y="0" ></e-distance-from-scale>
</e-linear-labels>
</e-linear-label-collections>
<e-linear-tick-collections>
<e-linear-ticks type="@TickType.MajorInterval"  width="2" color="#8c8c8c">
<e-distance-from-scale x="-1" y="45"></e-distance-from-scale>
</e-linear-ticks>
<e-linear-ticks type="@TickType.MinorInterval" height="6"  width="1" color="#8c8c8c">
<e-distance-from-scale x="-1" y="45"></e-distance-from-scale>
</e-linear-ticks>
</e-linear-tick-collections>
</e-linear-scales>
</e-linear-scale-collections>
</ej-linear-gauge>  


{% endhighlight %}

Execute the above code to render the following output.



![](Marker-Pointers_images/Marker-Pointers_img5.png)



