---
layout: post
title: Animation
description: animation
platform: aspnet-core
control: PivotGauge
documentation: ug
---

# Animation

The animation option makes the pointer to rotate from minimum value to actual value with animation effects. The animation can be enabled/disabled by using the `enable-animation` property. The speed of the pointer can be controlled by using the `animation-speed` property. Time is represented in milliseconds.

{% highlight cshtml %}

<ej-pivot-gauge id="PivotGauge1" enable-animation="true" animation-speed="1000"></ej-pivot-gauge>

{% endhighlight %}

