---
layout: post
title: RangeBand
description: Learn how to add Rangeband to Sparkline .
platform: aspnet-core
control: Sparkline
documentation: ug
---

## Range Band  

The range band feature is used to highlight a particular range along the y-axis using start and end range property. You can also customize the color and opacity of the range band. 

{% highlight cshtml %}

 <ej-spark-line id="sparkline" >                   
 <e-range-band-settings start-range="4" end-range="30" color="#ff14ae" opacity="0.4">
 </e-range-band-settings>
 </ej-spark-line>

{% endhighlight %}

![](Range-Band_images/Range-Band_img1.png)

