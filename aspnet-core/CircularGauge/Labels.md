---
layout: post
title: Labels | CircularGauge | ASP.NET Core| Syncfusion
description:  labels
platform: aspnet-core
control: CircularGauge
documentation: ug
---

#  Labels

Labels are units that are used to display the values in the scales. You can customize Labels with the properties like angle, color, font, opacity, etc.

## Adding Label Collection 

Label collection is directly added to the scale object. Refer the following code example to add label collection in a Gauge.


{% highlight CSHTML %}

<ej-circular-gauge id="circulargauge">
<e-circular-scale-collections>
<e-circular-scales show-labels="true">
<e-label-collections>
<e-circular-labels angle="30" ></e-circular-labels>
</e-label-collections>
</e-circular-scales>
</e-circular-scale-collections>
</ej-circular-gauge>

{% endhighlight  %}

Execute the above code to render the following output.

![](Labels_images/Labels_img1.png)

Circular Gauge with  label collection
{:.caption}

## Label Customization

### Appearance

* The attribute angle is used to display the labels in the specified angles and color attribute is used to display the labels in specified color. You can adjust the opacity of the label with the property opacity and the values of it lies between 0 and 1.
* You can adjust the labels based on the tick’s direction by setting autoAngle as true. includeFirstValue is an special property especially used in some special scenarios such as in clock, where the value 0 needs to be replaced with that of 12. By enabling this property the first value of the label is not rendered.
* Font option is also available on the labels. The basic three properties of fonts such as size, family and style can be achieved by size, fontStyle and fontFamily. Labels are two types such as major and minor.Major types labels are for major interval values and minor types labels are for minor interval values.

{% highlight CSHTML %}

<ej-circular-gauge id="circulargauge" >
<e-circular-scale-collections>
<e-circular-scales radius="110" size="10" show-labels="true" 
show-scale-bar="true" background-color="#FAF4B5" >
<e-border color="Yellow" width="2"></e-border>
<e-pointer-collections>
<e-pointers background-color="#FAF4B5" value="40" length="80" width="16" opacity="0.6" >
<e-border width="2" color="yellow"></e-border>
</e-pointers>
</e-pointer-collections>
<e-label-collections>
<e-circular-labels angle="30" opacity="0.8" include-first-value="true" color="yellow" >
<e-font font-family="Arial" size="15px" font-style="bold"></e-font>
</e-circular-labels>
</e-label-collections>
</e-circular-scales>
</e-circular-scale-collections>
</ej-circular-gauge>

{% endhighlight %}

Execute the above code to render the following output.

![](Labels_images/Labels_img2.png)

Circular Gauge with customized label
{:.caption}

### Unit text and Position

* unitText is used to add some text along with the labels. For example, in speedometer, you need to mention the units in kph. You can also add the unit text in front of the labels. You can achieve this by using an enumerable property unitTextPosition. With this you can position the unit text in front or back.
* Labels can be positioned with the help of two properties such as distanceFromScale and placement. distanceFromScale property defines the distance between the scale and labels.  Placement property is used to locate the labels with respect to scale either inside the scale or outside the scale or along the scale. It is an enumerable data type.


{% highlight CSHTML %}


<ej-circular-gauge id="circulargauge">
<e-circular-scale-collections>
<e-circular-scales   show-ranges="true" show-scale-bar="true" radius="150" size="5">
<e-circular-range-collections>
<e-circular-ranges background-color="Green" start-value="0" end-value="50" distance-from-scale="-30"
placement="@RangePlacement.Far">
</e-circular-ranges>
<e-circular-ranges background-color="Yellow" start-value="50" end-value="80" distance-from-scale="-30"
placement="@RangePlacement.Far">
</e-circular-ranges>
<e-circular-ranges background-color="Red" start-value="80" end-value="100" distance-from-scale="-30"
placement="@RangePlacement.Far">
</e-circular-ranges>
</e-circular-range-collections> 
<e-pointer-collections>
<e-pointers value="40" length="100" width="16" show-back-needle="true" >
</e-pointers>
<e-label-collections>
<e-circular-labels unit-text="kmph" unit-text-position="@UnitTextPlacement.Back" >
</e-circular-labels>
</e-label-collections>
</e-pointer-collections>            
</e-circular-scales>
</e-circular-scale-collections>
</ej-circular-gauge>


{% endhighlight %}

Execute the above code to render the following output.

![](Labels_images/Labels_img3.png)

Circular Gauge with unit text
{:.caption}

## Multiple Labels

You can achieve multiple labels such as minor and major in a Gauge sample scale. Refer the following code example for multiple labels variation.

{% highlight CSHTML %}

<ej-circular-gauge id="circulargauge" >
<e-circular-scale-collections>
<e-circular-scales radius="150" size="5" show-labels="true" show-ranges="true" 
show-scale-bar="true" background-color="Yellow" minor-interval-value="5">
<e-border color="Red" width="1.5"></e-border>
<e-pointer-cap background-color="yellow" border-color="red" border-width="0.5" radius="10">
</e-pointer-cap>
<e-pointer-collections>
<e-pointers background-color="#FAF4B5" value="40" length="80" width="16" opacity="0.6" >
<e-border width="2" color="yellow"></e-border>
</e-pointers>
</e-pointer-collections>
<e-label-collections>
<e-circular-labels type="@GaugeTypes.Minor" color="Yellow" >                       
</e-circular-labels>
<e-circular-labels type="@GaugeTypes.Major" color="Red">
</e-circular-labels>
</e-label-collections>
</e-circular-scales>
</e-circular-scale-collections>
</ej-circular-gauge>

{% endhighlight  %}

Execute the above code to render the following output.

![](Labels_images/Labels_img4.png)

Circular Gauge with multiple labels
{:.caption}


