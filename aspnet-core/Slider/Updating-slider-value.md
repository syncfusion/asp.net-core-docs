---
layout: post
title: Updating slider value | Slider | ASP.NET Core | Syncfusion
description: updating slider value
platform: aspnet-core
control: Slider
documentation: ug
---

# Updating slider value

Slider widget includes an option to specify/update its value. And also you can specify the starting and ending value for the Slider using the MinValue and MaxValue properties.

### Value

This property is used to set the value in the “Default” and “Min-Range” Sliders. By default its value is null when no value is specified. Data type of this property is “Number”.
You can get/set the value in the slider handle by using [getValue](https://help.syncfusion.com/api/js/ejslider#methods:getvalue) and [setValue](https://help.syncfusion.com/api/js/ejslider#methods:setValue) methods.
Also [change](https://help.syncfusion.com/api/js/ejslider#events:change) event will be triggered whenever **Slider** value is changed.

### Values

This property is used to set the value in “Range Slider”. By default range values is from 0 to 100. This property is of “Array” data type.

The following steps explains you the configuration of “Value” and “Values” property.

1. In an view page, specify the Tag helper elements to render the “Range Slider” and “Default Slider”.

{% highlight CSHTML %}

    @*Add this code in your view page*@

    <ej-slider id="defaultSlider" slider-type="Default" value="60" width="500px" />

    <ej-slider id="rangeSlider" slider-type="Range" values="30,60" width="500px" />

{% endhighlight %}

Execute the above code example to render the following output.

![](Updating-slider-value_images/Updating-slider-value_img1.png)

### MinValue

To set the minimum/starting value of the Slider, you can use the MinValue property. By default its value is 0. Data type of this property is “number”.

### MaxValue

To set the maximum/ending value of the Slider, you can use the MaxValue property. By default its value is 100. Data type of this property is “Number”.

The following steps explains you on how to configure MinValue and MaxValue property.

1. In an view page, specify the helper elements to render the Default Slider and Range Slider.

{% highlight CSHTML %}

    @*Add this code in your view page*@

    <ej-slider id="defaultSlider" slider-type="Default" value="60" min-value="40" max-value="80" width="500px" />

    <ej-slider id="rangeSlider" slider-type="Range" values="30,60" min-value="10" max-value="90" width="500px" />

{% endhighlight %}

Execute the above code example to render the following output.

![](Updating-slider-value_images/Updating-slider-value_img2.png)


In the above example, for Default Slider the slider value starts from “40” (min value) and ends in “80” (max value), so the slider handle is placed at the center of the Slider while specifying the value as “60”.

For Range Slider, the value starts from “10” (min value) and ends in “90” (max value). The range shadow occupies the entire Slider, since the range (values) is specified as “[10, 90]”.

### Buttons

Slider includes the button support for increment or decrement the values of the slider.

#### Enabling Buttons

Use the show-buttons property to enable the button support. By default this property is disabled. Data type of this property is “Boolean”.

The following steps explains you on how to enable button support in Slider.

1. In an view page, specify the Tag helper elements to render the Range Slider.

{% highlight CSHTML %}

    @*Add this code in your view page*@

    <ej-slider id="rangeSlider" slider-type="Range" values="30,60" width="500px" show-buttons="true"/>


{% endhighlight %}

Execute the above code example to render the following output.

![](Button-Support_images/Button-Support_img1.png)