---
layout: post
title: Segment Settings in ASP.NET Core DigitalGauge widget | Syncfusion
description: Learn about segment settings support in Syncfusion ASP.NET Core DigitalGauge control and more details.
platform: aspnet-core
control: DigitalGauge
documentation: ug
---

# Segment Settings in ASP.NET Core DigitalGauge

## Appearance

* Digital Gauge consists of several digital segments. Segment is customized with some properties. Color of the segment is set by using color property. Color is either given as string or hexadecimal value. 
* You can add gradient effects to the segments with the help of `e-gradient` attribute. The opacity of the segment is also adjustable. The space between two  segments are adjusted with spacing property.


{% highlight CSHTML %}

<ej-digital-gauge id="Digitalgauge" width="800" value="GO AHEAD">
<e-items>
<e-digital-gauge-items >
<e-segment-settings opacity="0.1" spacing="4" color="Green"></e-segment-settings>
</e-digital-gauge-items>
</e-items>
</ej-digital-gauge>

{% endhighlight %}


Execute the above code examples to render the DigitalGauge as follows.

![Appearance using DigitalGauge in ASP.NET Core](Segment-Settings_images/Segment-Settings_img1.png)

Digital Gauge control with segment settings
{:.caption}

## Dimension Modification

* Digital Gauge consists of several digital segments. Segment is customized with some properties. Color of the segment is set by using color property. Color is either given as string or hexadecimal value. 
* You can add gradient effects to the segments with the help of gradient attribute. The opacity of the segment is also adjustable. The space between two  segments are adjusted with spacing property.


{% highlight CSHTML %}

<ej-digital-gauge id="Digitalgauge" width="800" value="WELCOME">
<e-items>
<e-digital-gauge-items >
<e-segment-settings length="3" width="4"></e-segment-settings>
</e-digital-gauge-items>
</e-items>
</ej-digital-gauge>


{% endhighlight %}


Execute the above code examples to render the DigitalGauge as follows.


![Dimension Modification using DigitalGauge in ASP.NET Core](Segment-Settings_images/Segment-Settings_img2.png)

Digital Gauge control with segment dimension
{:.caption}

