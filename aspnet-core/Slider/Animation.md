---
layout: post
title: Animation | Slider | ASP.NET Core | Syncfusion
description: animation
platform: aspnet-core
control: Slider
documentation: ug
---

# Animation

This feature includes the animation effect for the Slider when moving the Slider handle.

### Enabling Animation

By default, animation is enabled in the Slider. Using the EnableAnimation property you can enable/disable the animation effects. Data type of this property is “Boolean”.

The following steps explains you on how to disable the animation effect in Slider.

1. In an view page, specify the Tag helper elements to render the “Default Slider”.

{% highlight CSHTML %}

    @*Add this code in your view page*@

    <ej-slider id="defaultSlider" value="60" width="500px" enable-animation="false" />

{% endhighlight %}

![](Animation_images/Animation_img1.png)

### Customizing Animation speed

Animation speed of the Slider indicates the speed at which the slider handle can be moved. Higher the value specified for this property decreases the rate of speed at which the Slider handle can be moved. You can customize the animation speed of the Slider using the AnimationSpeed property. Default value of this property is “500”. 

The following steps explains you on how to customize the animation speed.

1. In an view page, specify the Tag helper elements to render the “Default Slider”.

{% highlight CSHTML %}

    @*Add this code in your view page*@

    <ej-slider id="defaultSlider" value="60" width="500px" animation-speed="600" />

{% endhighlight %}