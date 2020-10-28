---
layout: post
title: Markers Customization
description: Learn how to add markers to Sparkline.
platform: ejmvc
control: Sparkline
documentation: ug
---

## Marker Customization

You can customize markers by initializing the `e-marker-settings` property. The customization options allow you to change the `fill`, `width`, `opacity`and `border` for marker. This customization only applicable for line, column and area type Sparkline.

{% highlight cshtml %}

 <ej-spark-line id="sparkline" >                   
 <e-marker-settings color="#ff14ae" visible="true">
 <e-border width="1" ></e-border>
 </e-marker-settings>
 </ej-spark-line>

{% endhighlight %}

![](Marker-Customization_images/Marker-Customization_img1.png)
