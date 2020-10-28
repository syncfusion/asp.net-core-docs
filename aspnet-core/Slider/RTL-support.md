---
layout: post
title: RTL support | Slider | ASP.NET Core | Syncfusion
description: rtl support
platform: aspnet-core
control: Slider
documentation: ug
---

# RTL support

Slider includes the Right to Left alignment support. Operations in the Slider is performed from Right to Left.

## Enabling RTL

Use the EnableRTL property to enable the RTL support. By default this property is disabled. Data type of this property is “Boolean”.

The following steps explains you on how to enable RTL support in Slider.

1. In an view page, specify the Tag helper elements to render the Range Slider.

{% highlight CSHTML %}

    @*Add this code in your view page*@

    <ej-slider id="rangeSlider" slider-type="Range" values="25,75" width="500px" enable-rtl="true" />


{% endhighlight %}

Execute the above code example to render the following output.

![](RTL-support_images/RTL-support_img1.png)