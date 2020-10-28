---
layout: post
title: Labels | lineargauge | Syncfusion
description: labels
platform: aspnet-core
control: lineargauge
documentation: ug
---

# Labels

Labels are units that are used to display the values in the scales. You can customize Labels with the properties like angle, color, font, opacity, etc.

## Adding label collection 

Label collection can be directly added to the scale object. Refer the following code example to add label collection in a gauge.

{% highlight cshtml %}

<ej-linear-gauge id="LinearGauge" enable-animation="false" value="40" >
<e-frame  inner-width="8" outer-width="10" 
background-image-url="../images/gauge/Gauge_linear_dark1.png" ></e-frame>
<e-linear-scale-collections>
<e-linear-scales width="0" show-bar-pointers="true" show-marker-pointers="false"
show-custom-labels="true">
<e-border color="transparent" width="0"></e-border>
<e-bar-pointer-collections>
<e-bar-pointers width="10" bar-pointerdistance-from-scale="13" >
</e-bar-pointers>
</e-bar-pointer-collections>
<e-linear-label-collections>
<e-linear-labels text-color="white">
</e-linear-labels>
</e-linear-label-collections>
<e-linear-tick-collections>
<e-linear-ticks type="@TickType.MajorInterval"  width="2" color="#8c8c8c" >
<e-distance-from-scale x="7" y="0"></e-distance-from-scale>
</e-linear-ticks>
<e-linear-ticks type="@TickType.MinorInterval" height="6"  width="1" color="#8c8c8c" >
<e-distance-from-scale x="7" y="0"></e-distance-from-scale>
</e-linear-ticks>
</e-linear-tick-collections>
<e-custom-label-collections>
<e-custom-labels value="Download In Progress">
<e-linear-position x="53" y="20"></e-linear-position>
</e-custom-labels>
</e-linear-scales>
</e-linear-scale-collections>
</ej-linear-gauge> 

{% endhighlight %}

Execute the above code to render the following output.

![](Labels_images/Labels_img1.png)



## Label Customization

### Appearance

* The attribute angle is used to display the labels in the specified angles and color attribute is used to display the labels in specified color. You can adjust the opacity of the label with the property opacity and the values of it lies between 0 and 1.The includeFirstValue is a special property by enabling this property, the first value of the label is not rendered.
* Font option is also available on the labels. The basic three properties of fonts such as size, family and style can be achieved by size, fontStyle and fontFamily. Labels are two types such as major and minor.Major type labels are for major interval values and minor type labels are for minor interval values.



{% highlight cshtml %}

<ej-linear-gauge id="LinearGauge" enable-animation="false" value="40" >
<e-frame  inner-width="8" outer-width="10" 
background-image-url="../images/gauge/Gauge_linear_light1.png" ></e-frame>
<e-linear-scale-collections>
<e-linear-scales width="0" show-bar-pointers="true" show-marker-pointers="false"
show-custom-labels="true">
<e-border color="transparent" width="0"></e-border>
<e-bar-pointer-collections>
<e-bar-pointers width="10" bar-pointerdistance-from-scale="13" >
</e-bar-pointers>
</e-bar-pointer-collections>
<e-linear-label-collections>
<e-linear-labels text-color="red" angle="10" opacity="0.5" include-first-value="false">
<e-font size="12px" font-style="bold" font-family="Arial"></e-font>
</e-linear-labels>
</e-linear-label-collections>
<e-linear-tick-collections>
<e-linear-ticks type="@TickType.MajorInterval"  width="2" color="#8c8c8c" >
<e-distance-from-scale x="7" y="0"></e-distance-from-scale>
</e-linear-ticks>
<e-linear-ticks type="@TickType.MinorInterval" height="6"  width="1" color="#8c8c8c" >
<e-distance-from-scale x="7" y="0"></e-distance-from-scale>
</e-linear-ticks>
</e-linear-tick-collections>
</e-linear-scales>
</e-linear-scale-collections>
</ej-linear-gauge> 

{% endhighlight %}

Execute the above code to render the following output.


![](Labels_images/Labels_img2.png)



## Unit text and Positioning

* The unitText property is used to add some text along with the labels. For example, in speedometer, you need to mention the units in kph. You can also add the unit text in front of the labels. To achieve this use the enumerable property unitTextPosition. 
* Labels can be positioned with the help of two properties such as distanceFromScale and placement. distanceFromScale property defines the distance between the scale and labels. Placement property is used to locate the labels with respect to scale either inside the scale or outside the scale or along the scale. It is an enumerable data type.



{% highlight cshtml %}

<ej-linear-gauge id="LinearGauge" enable-animation="false" value="31" width="600" Height="250" themes="@Themes.FlatLight"
orientation="@Orientation.Horizontal">
<e-frame  inner-width="8" outer-width="10" 
background-image-url="../images/gauge/Gauge_linear_light1.png" ></e-frame>
<e-linear-scale-collections>
<e-linear-scales width="0" background-color="white" major-interval-value="25"
minor-interval-value="5" type="@ScaleType.RoundedRectangle"  direction="@Directions.Clockwise" 
show-bar-pointers="true" show-marker-pointers="false"
show-custom-labels="true">
<e-border color="#AEC75F" width="2"></e-border>
<e-bar-pointer-collections>
<e-bar-pointers width="4" bar-pointer-background-color="Red" >
</e-bar-pointers>
</e-bar-pointer-collections>
<e-linear-label-collections>
<e-linear-labels text-color="red" angle="90" unit-text="%">
<e-distance-from-scale x="0" y="60" ></e-distance-from-scale>
</e-linear-labels>
</e-linear-label-collections>
<e-linear-tick-collections>
<e-linear-ticks type="@TickType.MajorInterval"  width="2" color="#8c8c8c" >
<e-distance-from-scale x="25" y="0"></e-distance-from-scale>
</e-linear-ticks>
<e-linear-ticks type="@tickType.MinorInterval" height="6"  width="1" color="#8c8c8c" >
<e-distance-from-scale x="25" y="0"></e-distance-from-scale>
</e-linear-ticks>
</e-linear-tick-collections>
</e-linear-scales>
</e-linear-scale-collections>
</ej-linear-gauge> 

{% endhighlight %}

Execute the above code to render the following output.


![](Labels_images/Labels_img3.png)



