---
layout: post
title: Animation
description: Learn how to animate the SunburstChart .
platform: aspnet-core
control: SunburstChart
documentation: ug
---

# Animation

Sunburst chart allows you to animate the chart segments. You can enable animation using **enable-animation** property. 

{% highlight cshtml %}

<ej-sunburstchart id="SunburstChart" enable-animation="true">
</ej-sunburstchart>


{% endhighlight %}


## Animation Types 
Sunburst chart provide options to animate the chart segments in different ways using **animation-type** property.
FadeIn – It gradually changes opacity of the chart segment.
Rotation – During an animation, control rotate from 0 to 360 angle.

### Fade In

The Fade In animation is enabled as follows 

{% highlight cshtml %}

<ej-sunburstchart id="SunburstChart" enable-animation="true" animation-type="@SunburstAnimationType.FadeIn" >
</ej-sunburstchart>

{% endhighlight %}

![](Animation_images/Animation_img1.gif)




### Rotation

The following example shows how to enable rotation animation in ejSunburstChart

{% highlight cshtml %}

<ej-sunburstchart id="SunburstChart" enable-animation="true"  animation-type="@SunburstAnimationType.Rotation" >
</ej-sunburstchart

{% endhighlight %}

![](Animation_images/Animation_img2.gif)


