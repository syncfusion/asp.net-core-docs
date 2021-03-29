---
layout: post
title: 3D Visualization in ASP.NET Core PivotChart | Syncfusion
description: This document illustrates that how to define 3d visualization and its types in ASP.NET Core PivotChart control
platform: aspnet-core
control: PivotChart
documentation: ug
---

# 3D visualization for ASP.NET Core PivotChart Control

The pivot chart control allows you to view the data in a 3D view. Following are the chart types that are supported:

* Bar
* Column
* Stacking bar
* Stocking column
* Pie

## 3D column chart

The 3D column chart is rendered by specifying the chart type as **“Column”** in the **“e-common-series-options”** enumeration property and setting the `enable3d` property to **true.**

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1" enable3d="true" rotation="24">
    <e-common-series-options type="Column"></e-common-series-options>
    <e-size width="100%" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

![ASP NET Core column chart control rendered in 3D](3D-Visualization_images/column3d.png)

## 3D bar chart

The 3D bar chart is rendered by specifying the chart type as **Bar** in the **“e-common-series-options”** enumeration property and setting the `enable3d` property to **true.**

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1" enable3d="true" rotation="24">
    <e-common-series-options type="Bar"></e-common-series-options>
    <e-size width="100%" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

![ASP NET Core bar chart control rendered in 3D](3D-Visualization_images/bar3d.png)

## 3D stacking bar chart

The 3D stacking bar chart is rendered by specifying the chart type as **Stacking Bar** in the **“e-common-series-options”** enumeration property and setting the `enable3d` property to **true.**

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1" enable3d="true" rotation="24">
    <e-common-series-options type="StackingBar"></e-common-series-options>
    <e-size width="100%" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

![ASP NET Core stacking bar chart control rendered in 3D](3D-Visualization_images/stackingbar3d.png)

## 3D stacking column chart

The 3D stacking column chart is rendered by specifying the chart type as **Stacking Column** in the **“e-common-series-options”** enumeration property and setting the `enable3d` property to **true.**

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1" enable3d="true" rotation="24">
    <e-common-series-options type="StackingColumn"></e-common-series-options>
    <e-size width="100%" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

![ASP NET Core stacking column chart control rendered in 3D](3D-Visualization_images/stackingcolumn3d.png)

## 3D pie chart

The 3D pie chart is rendered by specifying the chart type as **"Pie"** in the **"e-common-series-options"** enumeration property and setting the `enable3d` property to **true.**

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1" enable3d="true" rotation="24">
    <e-common-series-options type="Pie"></e-common-series-options>
    <e-size width="100%" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

![ASP NET Core pie chart control rendered in 3D](3D-Visualization_images/pie3d.png)

## Rotating 3D chart

You can rotate the 3D chart towards left or right by setting an appropriate angle value to the `rotation` property. The direction of the chart display depends on the positive or negative angle value.

{% highlight cshtml %}

//Rotates the 3D Chart
<ej-pivot-chart id="PivotChart1" enable3d="true" rotation="40">
    <e-common-series-options type="Column"></e-common-series-options>
    <e-size width="100%" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

![ASP NET Core pivot chart control with 3D rotation](3D-Visualization_images/rotation3d.png)

