---
layout: post
title: Scale Settings | Slider | ASP.NET Core | Syncfusion
description: scale settings
platform: aspnet-core
control: Slider
documentation: ug
---

# Scale Settings

Slider widget includes option to display the scale on the Slider. Scale in Slider supports you to easily identify the current value/values of the Slider. Scale contains “small ticks” and “large ticks”. Values of the Slider is displayed above each large ticks.

## Show Scale

This property enables the scale in the Slider. By default, its value is “false”. Data type of this property is “Boolean”.

The following steps explains you the configuration of ShowScale property.

1. In an view page, specify the Tag helper elements to render the “Default Slider” and “Range Slider”.

{% highlight CSHTML %}

    @*Add this code in your view page*@

    <ej-slider id="defaultSlider" slider-type="Default" value="60" min-value="40" max-value="80" width="500px" show-scale="true" />

    <ej-slider id="rangeSlider" slider-type="Range" values="30,60" min-value="10" max-value="90" width="500px" show-scale="true" />

{% endhighlight %}
	
Execute the above code example to render the following output.

![](Scale-Settings_images/Scale-Settings_img1.png)

## Enable Small Ticks

Slider widget provides you an option to enable/disable the small ticks present in the scale. By default, when you enable “ShowScale” property, small ticks is displayed in the scale. Use the ShowSmallTicks property to disable the small ticks present in the scale. Data type of this property is “Boolean”. The [renderingTicks](https://help.syncfusion.com/api/js/ejslider#events:renderingticks) event will be triggered while creating each slider scale tick.

The following steps explains you on how to disable the small ticks in Slider.

1. In an view page, specify the Tag helper elements to render the “Default Slider” and “Range Slider”.

{% highlight CSHTML %}

    @*Add this code in your view page*@

    <ej-slider id="defaultSlider" slider-type="Default" value="60" min-value="40" max-value="80" width="500px" show-scale="true" show-small-ticks="false"/>

    <ej-slider id="rangeSlider" slider-type="Range" values="30,60" min-value="10" max-value="90" width="500px" show-scale="true" show-small-ticks="false"/>

{% endhighlight %}

Execute the above code example to render the following output.


![](Scale-Settings_images/Scale-Settings_img2.png)

### Small step

This property specifies the distance between the two small ticks present in the scale and the position of the small ticks in the Slider scale. Data type of this property is “Number”.

### Large step

This property specifies the distance between the two small ticks present in the scale and the position of the large ticks in the Slider scale. Data type of this property is “Number”.

The following steps explains you on how to configure the SmallStep and LargeStep property in Slider scale.

1. In an view page, specify the helper elements to render the “Default Slider” and “Range Slider”

{% highlight CSHTML %}

    @*Add this code in your view page*@

    <ej-slider id="defaultSlider" slider-type="Default" value="60" min-value="40" max-value="80" width="500px" show-scale="true" small-step="5" large-step="20"/>

    <ej-slider id="rangeSlider" slider-type="Range" values="30,60" min-value="10" max-value="90" width="500px" show-scale="true" small-step="5" large-step="20"/>

{% endhighlight %}
Execute the above code example to render the following output.


![](Scale-Settings_images/Scale-Settings_img3.png)

In the above example, for “Default Slider” the “SmallStep” value is specified as “5”, so for each 5 values from the starting value, small ticks is enabled. Also, “LargeStep” value is specified as “20”, so for each 20 values from the starting value, large ticks is enabled.

Similarly for “Range Slider”, “SmallStep” value is specifies as “5”, so for each 5 values from the starting value, small ticks is enabled. Also, “LargeStep” value is specified as “25” so, for each 25 values large ticks is enabled.