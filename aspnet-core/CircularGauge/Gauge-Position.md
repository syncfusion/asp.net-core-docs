---
layout: post
title: Gauge Position | CircularGauge | Syncfusion
description: gauge position
platform: aspnet-core
control: CircularGauge
documentation: ug
---

# Gauge Position

Semi-circular Gauge can be positioned within the canvas element which provides better appearance for the gauge in the canvas.

## Positioning

* Semi-circular Gauge can be positioned with the help of the attribute called `gauge-position`. It is an enumerable value. You can position the gauge away from the corner with the help of the distanceFromCorner attribute. 
* The possible enum values for the gaugePosition are as follows:
1. TopLeft
2. TopCenter
3. TopRight
4. MiddleLeft
5. Center
6. MiddleRight
7. BottomLeft
8. BottomCenter
9. BottomRight


{% highlight CSHTML %}

<ej-circular-gauge id="circulargauge" background-color="transparent" width="500" 
height="500" radius="100" value="60" gauge-position="@GaugePosition.TopLeft" distance-from-corner="25">
<e-frame frame-type="@Frame.HalfCircle" 
half-circle-frame-start-angle="270" half-circle-frame-end-angle="90"></e-frame>
<e-circular-scale-collections>
<e-circular-scales  radius="100" maximum="120" major-interval-value="20"
minor-interval-value="10" show-scale-bar="true" size="1" start-angle="270" sweep-angle="180">
<e-border width="0.5"></e-border>
</e-circular-scales>
</e-circular-scale-collections>
</ej-circular-gauge>

{% endhighlight %}

Execute the above code to render the following output.

![](Gauge-Position_images/Gauge-Position_img1.png)

Semi-circular Gauge with default top left position
{:.caption}

