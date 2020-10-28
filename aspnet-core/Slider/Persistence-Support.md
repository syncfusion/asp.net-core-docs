---
layout: post
title: Persistence Support | Slider | ASP.NET Core | Syncfusion
description: persistence support
platform: aspnet-core
control: Slider
documentation: ug
---

# Persistence Support

This feature supports you to save current model value to browser cookies for state maintenance. When you refresh the web page, the Slider control retains the model value apply from browser cookies. The data type of EnablePersistence is Boolean type. 

The following steps explains you on how to enable the EnablePersistence property.

1. In an view page, add a Tag helper element to render it as a Slider widget.

{% highlight CSHTML %}

    @*Add this code in your view page*@

    <ej-slider id="basicSlider" height="20px" width="500px" enable-persistence="true" />

{% endhighlight %}

After execute the code, Increase the value and reload the page. The state is maintained in the Slider control.

![](Persistence-Support_images/Persistence-Support_img1.png)