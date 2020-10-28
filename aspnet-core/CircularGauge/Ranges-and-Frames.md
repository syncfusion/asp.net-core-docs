---
layout: post
title: Ranges and Frames | CircularGauge |  Syncfusion
description:  ranges and frames
platform: aspnet-core
control: CircularGauge
documentation: ug
---

#  Ranges and Frames

Ranges are used to specify or group the scale values. By using ranges, you can describe the values in the pointers. 

## Add Range Collection

Range collection is directly added to the scale object. Refer the following code example to add range collection in a Gauge control. 

{% highlight CSHTML %}

<ej-circular-gauge id="circulargauge">
 <e-circular-scale-collections>
<e-circular-scales   show-ranges="true">
<e-circular-range-collections>
<e-circular-ranges background-color="green" start-value="20" end-value="80">
</e-circular-ranges>
</e-circular-range-collections>             
</e-circular-scales>
</e-circular-scale-collections>
</ej-circular-gauge>

{% endhighlight %}

### Range Customization

#### Appearance

* The API size is used to specify the width of the ranges.  The major attributes for ranges are startValue and endValue. startValue defines the start position of the ranges and endValue defines the end position of the ranges.
* StartWidth and endWidth are used to specify the range width at the starting and ending position of the ranges. You can add the gradient effects to the ranges by using gradient object.

{% highlight CSHTML %}


<ej-circular-gauge id="circulargauge">
 <e-circular-scale-collections>
<e-circular-scales   show-ranges="true" show-scale-bar="true" radius="150" size="5">
<e-circular-range-collections>
<e-circular-ranges background-color="green" start-value="20" end-value="80" placement="@RangePlacement.Far">
</e-circular-ranges>
</e-circular-range-collections>             
</e-circular-scales>
</e-circular-scale-collections>
</ej-circular-gauge>

{% endhighlight  %}

Execute the above code to render the following output.

![](Ranges-and-Frames_images/Ranges-and-Frames_img1.png)

Circular Gauge with customized ranges with startValues and endValues
{:.caption}

### Colors and Border

* By customizing the ranges, the appearance of the Gauge can be improved. The range border is modified with the object called border. It has two border property such as color and width. These are used to customize the border color of the ranges and border width of the ranges. 
* You can set the background color to improve the look and feel of the Circular Gauge. For customizing the background color of the ranges, backgroundColor is used.

{% highlight CSHTML %}

<ej-circular-gauge id="circulargauge">
 <e-circular-scale-collections>
<e-circular-scales   show-ranges="true" show-scale-bar="true" radius="150" size="5">
<e-circular-range-collections>
<e-circular-ranges background-color="Yellow" start-value="20" end-value="80" 
placement="@RangePlacement.Far">
<e-border color="Green" width="2"></e-border>
</e-circular-ranges>
</e-circular-range-collections>             
</e-circular-scales>
</e-circular-scale-collections>
</ej-circular-gauge>

{% endhighlight  %}

Execute the above code to render the following output.

![](Ranges-and-Frames_images/Ranges-and-Frames_img2.png)

Circular Gauge with customized range colors and borders
{:.caption}


### Position the ranges

* You can position ranges using two properties such as `distance-from-scale` and `placement`. 
* distanceFromScale property defines the distance between the scale and range. 
* Placement property is used to locate the pointer with respect to scale either inside the scale or outside the scale or along the scale. It is an enumerable data type.

{% highlight CSHTML %}

<ej-circular-gauge id="circulargauge">
 <e-circular-scale-collections>
<e-circular-scales   show-ranges="true" show-scale-bar="true" radius="150" size="5">
<e-circular-range-collections>
<e-circular-ranges background-color="Green" start-value="0" end-value="100" distance-from-scale="-30"
placement="@RangePlacement.Far">
<e-border color="Black" width="2"></e-border>
</e-circular-ranges>
</e-circular-range-collections>             
</e-circular-scales>
</e-circular-scale-collections>
</ej-circular-gauge>


{% endhighlight  %}

Execute the above code to render the following output.



![](Ranges-and-Frames_images/Ranges-and-Frames_img3.png)

Circular Gauge with customized ranges
{:.caption}

## Multiple Ranges

You can set multiple ranges by adding an array of ranges objects. Refer the following code example for multiple ranges functionality.


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
</e-circular-scales>
</e-circular-scale-collections>
</ej-circular-gauge>

{% endhighlight %}

Execute the above code to render the following output.

![](Ranges-and-Frames_images/Ranges-and-Frames_img4.png)

Circular Gauge with multiple ranges
{:.caption}


## Frames

* Frame is the element that decides the appearance of the Circular Gauge. You can customize it using the object called frame.  It has the properties such as `frame-type`, `backGround-Url`, `half-Circle-Frame-Start-Angle` and `half-Circle-Frame-End-Angle`.
* frameType is used to specify whether frame is a half circle frame or full circle frame. halfCircleFrameStartAngle and halfCircleFrameEndAngle are used to specify the angle for Gauge with frame type as half circle. backgroundUrl is used to set the background image for the frame.

{% highlight CSHTML %}

<ej-circular-gauge id="circulargauge">
<e-frame frame-type="@Frame.HalfCircle" 
half-circle-frame-start-angle="205" half-circle-frame-end-angle="335"></e-frame>
<e-circular-scale-collections>
<e-circular-scales  start-angle="180" sweep-angle="180">
<e-pointer-cap radius="8"></e-pointer-cap>
<e-border color="blue" width="2"></e-border>
<e-pointer-collections>
 <e-pointers value="40" width="1" length="120" type="@PointerType.Needle" 
 needle-type="@NeedleType.Rectangle">
</e-pointers>
</e-pointer-collections>       
</e-circular-scales>
</e-circular-scale-collections>
</ej-circular-gauge>

{% endhighlight  %}

Execute the above code to render the following output.

![](Ranges-and-Frames_images/Ranges-and-Frames_img5.png)

Circular Gauge with multiple ranges
{:.caption}
