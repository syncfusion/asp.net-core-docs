---
layout: post
title: Image-Customization | RadialSlider | ASP.NET Core | Syncfusion
description: Image-Customization
platform: aspnet-core
control: RadialSlider
documentation: ug
keywords: image
---
# Image customization

## Customizing inner circle 

### Using Class

The **RadialSlider** property **inner-circle-image-class** allow to set image for the inner circle of the  **RadialSlider**.  By default, the **Radial Slider** inner-circle-image-class is set as "null". Refer to the following code example.

{% tabs %}
{% highlight CSHTML %}

  <ej-radial-slider id="slider" inner-circle-image-class="customcircle" />

{% endhighlight %}
{% highlight css %}
    <style>
        .customcircle {
            background-image: url("../images/radialslider/diagram.png");
        }
    </style>

{% endhighlight %}
{% endtabs %}

The following screenshot illustrates the output of above code.

![](image-customization_images\image-customization_img1.png)


### Using image URL 

The **RadialSlider** property **inner-circle-image-url** allow to set URL image to the inner circle of the **RadialSlider**.  By default, the **Radial Slider** inner-circle-image-url  is set as "null". Refer to the following code example.

{% highlight CSHTML %}

   <ej-radial-slider id="slider" inner-circle-image-url="@Url.Content("~/images/radialslider/chevron-right.png")" />g")

{% endhighlight %}

The following screenshot illustrates the output of above code.

![](image-customization_images\image-customization_img2.png)




