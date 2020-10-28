---
layout: post
title: EnableDisable the Slider | Slider | ASP.NET Core | Syncfusion
description: enable-disable the slider
platform: aspnet-core
control: Slider
documentation: ug
---

# Enable/Disable the Slider

Slider widget includes an option to enable/disable it. When you disable the Slider, it is displayed in a blur state and you cannot perform any operations in it.

### Enabled

Using this Enabled property you can enable/disable the Slider. Data type of this property is “Boolean”. Also you can enable/disable the **Slider** by using [enable](https://help.syncfusion.com/api/js/ejslider#methods:enable) and [disable](https://help.syncfusion.com/api/js/ejslider#methods:disable) methods.

The following steps explains you on how to disable the Slider.

1. In an view page, specify the Tag helper elements to render the Default Slider.

{% highlight CSHTML %}

    @*Add this code in your view page*@

    <ej-slider id="defaultSlider" value="60" width="500px" enabled="false" />

{% endhighlight %}

Execute the above code example to render the following output.

![](EnableDisable-the-Slider_images/EnableDisable-the-Slider_img1.png)