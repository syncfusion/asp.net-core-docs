---
layout: post
title: Axis Customize
description: Learn how to customize axis in Sparkline.
platform: aspnet-core
control: Sparkline
documentation: ug
---

## Axis Customize 

The Sparkline axis can be collapsed using visible property in `e-axis-line-settings` and this not applicable for win-loss. You can customize `color`, `width` and `dash-array` of axis line.

 {% highlight cshtml %}
 
 <ej-spark-line id="sparkline" >                   
 <e-axis-line-settings color="#ff14ae" visible="true"></e-axis-line-settings>
 </ej-spark-line>

{% endhighlight %}

![](Axis-Customize_images/Axis-Customize_img1.png)
