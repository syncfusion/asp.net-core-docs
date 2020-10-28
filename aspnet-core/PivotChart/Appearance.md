---
layout: post
title: Appearance | PivotChart | ASP.NET Core | Syncfusion
description: appearance
platform: aspnet-core
control: PivotChart
documentation: ug
---

# Appearance

## Built-in themes

Following are the built-in themes available in the pivot chart:

* Flat light
* Gradient light
* Gradient dark
* Azure
* Azure dark
* lime
* Lime dark
* Saffron
* Saffron dark
* Gradient light
* Gradient dark
* High contrast 01
* High contrast 02
* Material
* Office365
* Boot strap

By using the `theme` property, you can set the desired theme in the pivot chart. By default, the **"Flat Light"** theme is applied to the pivot chart.

{% highlight cshtml %}

//Using gradient theme
<ej-pivot-chart id="PivotChart1" theme="LimeDark"></ej-pivot-chart>

{% endhighlight %}

![ASP NET Core pivot chart control rendered with built-in theme](Appearance_images/themes.png)

## Pivot chart - area customization

### Border customization

To customize the pivot chart border, use `border` property in the pivot chart.

{% highlight cshtml %}

//Customize the chart border and opacity
<ej-pivot-chart id="PivotChart1" border-width="2" border-color="#FF0000"></ej-pivot-chart>

{% endhighlight %}

![Border customization for ASP NET Core pivot chart control](Appearance_images/bordercustomize.png)

### Animation

You can enable the animation by using the `enable-animation` property under `e-common-series-options` of the pivot chart control. This animates the chart series on two occasions - when the chart is loaded for the first time and when the series type is changed by using the `type` property.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    <e-common-series-options enable-animation="true"></e-common-series-options>
    //Enabling animation in series
    <e-size width="100%" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}
