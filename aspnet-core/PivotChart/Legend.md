---
layout: post
title: Legend | PivotChart | ASP.NET Core | Syncfusion
description: This document illustrates that how to define legend and its customization in ASP.NET Core PivotChart control
platform: aspnet-core
control: PivotChart
documentation: ug
---

# Legend

## Legend visibility

You can enable or disable the legend by using the `visible` property in the `e-legend` object.

N> By default, the legend is visible in the pivot chart.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    //Legend Visibility
    <e-legend visible="true"></e-legend>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

![Legend visibility in ASP NET Core pivot chart control](Legend_images/Legend_img1.png)

## Legend shape

You can customize the legend `shape` in the pivot chart control. The default value of legend shape is rectangle. Following are the supported legend shapes:

* rectangle
* circle
* cross
* diamond
* pentagon
* hexagon
* star
* ellipse
* triangle etc.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    //Applying legend shape
    <e-legend visible="true" row-count="3" shape="star"></e-legend>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

![Legend shape in ASP NET Core pivot chart control](Legend_images/Legend_img2.png)

## Legend position

By using the `position` property, you can place the legend at top, bottom, left, or right of the pivot chart.

N> The default value of legend position is bottom in the pivot chart.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    //Applying legend position
    <e-legend visible="true" row-count="3" position="top"></e-legend>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

![Legend position in ASP NET Core pivot chart control](Legend_images/Legend_img3.png)

## Legend title

To add the legend title, you should specify the title text in `e-title.text` property.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    //Place the legend at top of the Chart
    <e-legend visible="true">
        <e-title text="Countries"></e-title>
    </e-legend>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

![Legend title in ASP NET Core pivot chart control](Legend_images/Legend_img4.png)

## Legend alignment

You can align the legend to center, far, and near based on its position in the chart area by using the `alignment` option.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    //Place the legend alignment at near to the Chart
    <e-legend visible="true" row-count="3" alignment="near"></e-legend>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

![Legend alignment in ASP NET Core pivot chart control](Legend_images/Legend_img5.png)

## Legend items - size and border

By using the legend `item-style-width`, `item-style-height`, and `item-style-border` properties, you can change the size and border of legend items.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    //Changing legend items border, height and width
    <e-legend visible="true" item-style-width="12" item-style-height="12" item-style-border-color="Magenta" item-style-border-width="1.5"></e-legend>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

![Size and border of legend in ASP NET Core pivot chart control](Legend_images/Legend_img6.png)

## Legend border

By using the `border` option in legend, you can customize the color and width of the border.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    //Setting border color and width to legend
    <e-legend visible="true" border-width="2" border-color="#FFC342"></e-legend>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

![Legend border in ASP NET Core pivot chart control](Legend_images/Legend_img7.png)

## Legend text

By using the `e-font` option, you can customize the font family, font style, font weight, and size of the legend text.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    //Setting border color and width to legend
    <e-legend>
        //Customizing the legend text
        <e-font font-family="SegoeUI" font-size="13px" font-style="Italic" font-weight="Bold"></e-font>
    </e-legend>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

![Legend text in ASP NET Core pivot chart control](Legend_images/Legend_img8.png)