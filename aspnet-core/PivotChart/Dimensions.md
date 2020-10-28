---
layout: post
title: Dimensions | PivotChart | ASP.NET Core | Syncfusion
description: dimensions
platform: aspnet-core
control: PivotChart
documentation: ug
---

# Dimensions

## Set size in percentage

You can customize the pivot chart dimension by setting the width and height of the control in percentage.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    //Set size to Chart container
    <e-size width="80%" height="80%"></e-size>
</ej-pivot-chart>
<style>
    #PivotChart1 {
        width:100%;
        height:450px;
    }
</style>

{% endhighlight %}

## Set size in pixels

You can customize the pivot chart dimension by setting the width and height of the control in pixels.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    //Set size to Chart container
    <e-size width="950px" height="540px"></e-size>
</ej-pivot-chart>
<style>
    #PivotChart1 {
        width:950px;
        height:450px;
    }
</style>

{% endhighlight %}

![ASP NET Core pivot chart control with specified size](Dimensions_images/Dimensions.png)

## Responsive

The pivot chart control supports responsive rendering based on the target device (desktop and tablet) resolution. It supports resolution upto 1024x600. You can enable responsiveness in the pivot chart by setting `is-responsive` property to true.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1" is-responsive="true">
    //Set size to Chart container
    <e-size width="950px" height="540px"></e-size>
</ej-pivot-chart>
<style>
    #PivotChart1 {
        min-width:525px;
        min-height:460px;
        height: 460px;
        width: 100%;
    }
</style>

{% endhighlight %}

![ASP NET Core pivot chart with normal layout](Dimensions_images/NormalView.png)

_Normal View_

![ASP NET Core pivot chart with responsive layout](Dimensions_images/ResponsiveView.png)

_ResponsiveView_

