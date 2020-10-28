---
layout: post
title: Performance tips | ASP.NET Core | Syncfusion
description: How to improve the performance of Essential JavaScript Chart
platform: aspnet-core
control: Chart
documentation: ug
---

# Performance 

* When there are large number of points to load, you can enable canvas rendering mode in chart. Canvas rendering is faster than SVG, because it does not involve in manipulating DOM elements as much as SVG rendering.

{% highlight cshtml %}

<ej-chart id="chartContainer" enable-canvas-rendering="true">
</ej-chart>

{% endhighlight %}

* Instead of enabling data markers and labels when there are large number of data points, you can use **Trackball** and **Tooltip** to view point information.

## Lazy loading

Lazy loading feature provides an effective way for loading data on demand by scrolling and viewing a smaller range of data from a larger collection.

{% highlight cshtml %}

<ej-chart id="chartContainer" enable-canvas-rendering="true">
    <e-primary-x-axis><e-scrollbar-settings visible="true" can-resize="true"><e-scroll-range min="2009/1/1" max="2014/1/1"></e-scroll-range></e-scrollbar-settings></e-primary-x-axis>
</ej-chart>

{% endhighlight %}

![](Performance_images/Perform_img1.png)