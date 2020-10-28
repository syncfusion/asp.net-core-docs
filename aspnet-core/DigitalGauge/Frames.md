---
layout: post
title: Frames | DigitalGauge | Syncfusion
description: frames
platform: aspnet-core
control: DigitalGauge
documentation: ug
---

# Frames

## Inner and Outer Customization

Frames are space that enclose the Digital Gauge. The inner width of the Frame is the distance between the canvas element and the frame. The outer width is the distance from the frame. The code example to set frame’s innerWidth and outerWidth is as follow.

{% highlight CSHTML %}

<ej-digital-gauge id="Digitalgauge" height="200" width="500" value="WELCOME">
<e-frame inner-width="6" outer-width="10" >
</e-frame>
</ej-digital-gauge>

{% endhighlight %}



Execute the above code examples to render the DigitalGauge as follows.

![](Frames_images/Frames_img1.png)

Digital Gauge control with frame inner and outer width
{:.caption}

## Setting Background Image

For a better appearance, you can set the background image for the Digital Gauge using the property `background-image-url`. 

{% highlight CSHTML %}

<ej-digital-gauge id="Digitalgauge" height="200" width="500" value="WELCOME">
<e-frame background-image-url="../Content/images/gauge/board3.jpg" >
</e-frame>
<e-items>
<e-digital-gauge-items value="RADAR">
<e-segment-settings color="Black"></e-segment-settings>
<e-digital-position x="80" y="10"></e-digital-position>
</e-digital-gauge-items>
</e-items>
</ej-digital-gauge>

{% endhighlight %}


Execute the above code examples to render the DigitalGauge as follows.


![](Frames_images/Frames_img2.png)

Digital Gauge control with frame background image
{:.caption}