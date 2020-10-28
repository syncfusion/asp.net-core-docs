---
layout: post
title: Point Customization
description: Learn how to customize points in Sparkline.
platform: aspnet-core
control: Sparkline
documentation: ug
---

## Point Customization

You can customize points by initializing the point colors. The customization options allow you to differentiate the `First`, `Last`, `Highest`, `Lowest`, and `Negative` points. This customization only applicable for line, column and area type Sparkline.

{% highlight cshtml %}

<ej-spark-line id="sparkline" negative-point-color="red" 
high-point-color="blue"  low-point-color="orange" start-point-color="green"
end-point-color="green">                   
</ej-spark-line>

{% endhighlight %}

![](Point-Customization_images/Point-Customization_img1.png)
