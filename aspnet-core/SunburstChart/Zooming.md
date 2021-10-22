---
layout: post
title: Sunburst Zooming in ASPNET Core SunburstChart Control | Syncfusion
description: Learn how to Zoom the ASPNET Core SunburstChart for better data visualization, its elements, features, and more.
platform: aspnet-core
control: SunburstChart
documentation: ug
---

# Zooming in ASPNET Core SunburstChart

Sunburst chart provides zooming (drill down) experience with animation for both mouse and touch enabled devices. It allows you to Virtualize large sets of data into minimum data view. The zooming is achieved by using the property of *e-sunburstchart-zoom-settings*

The following code shows how to initialize the zooming.

{% highlight cshtml %}

<ej-sunburstchart id="SunburstChart" >
   <e-sunburstchart-zoom-settings enable="true"></e-sunburstchart-zoom-settings>
  <ej-sunburstchart>

{% endhighlight %}

## Zooming toolbar
By default, zooming toolbar will be enabled while zooming the segment. It contains both back and reset option.
You can align the zooming toolbar position by using *toolbar-horizontal-alignment* and *toolbar-vertical-alignment* property.

{% highlight cshtml %}

<ej-sunburstchart id="SunburstChart" >
   <e-sunburstchart-zoom-settings enable="true"toolbar-horizontal-alignment="@SunburstHorizontalAlignment.Left">
   </e-sunburstchart-zoom-settings>
  <ej-sunburstchart>

{% endhighlight %}

![Sunburst chart Zooming2](Zooming_images/Zooming_img2.png)


