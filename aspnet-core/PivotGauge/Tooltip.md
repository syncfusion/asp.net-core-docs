---
layout: post
title: Tooltip | ASP.NET Core | PivotGauge | Syncfusion
description: This document illustrates that how to enable tooltip and its customization in ASP.NET Core PivotGauge control
platform: aspnet-core
control: PivotGauge
documentation: ug
---

# Tooltip

The tooltip can be enabled by using the `enable-tooltip` property. 

N> By default, this property is set to false.

{% highlight cshtml %}

<ej-pivot-gauge id="PivotGauge1" enable-tooltip="true"></ej-pivot-gauge>

{% endhighlight  %}

The tooltip appearance can be customized by overriding its CSS class.

{% highlight css %}

    .e-pivotgauge-tooltip {
        background-color: #D2E9FE!important;
        border: 2px solid #01465C!important;
        color: #01232E!important;
        border-radius: 5px!important;
        margin-top: 20px;
        text-align: left;
        font: 12 px Segoe UI;
        line-height: 20px;
    }

{% endhighlight %}

![Tooltip in ASP NET Core pivot gauge control](Tooltip_images/Tooltip.png) 
