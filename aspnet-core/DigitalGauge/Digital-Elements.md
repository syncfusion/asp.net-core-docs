---
layout: post
title: Digital Elements | DigitalGauge | Syncfusion
description: digital elements
platform: aspnet-core
control: DigitalGauge
documentation: ug
---

# Digital Elements

## Text Customization

* The attribute value refers the text displayed in the Digital Gauge. This text is applicable only for that item instead of all items. Text color is changed by using the property textColor.
* It is possible to align the text inside the Digital Gauge control by using the property `text-align`. Two possible values for text align are as follows
	1. left
	2. right

{% highlight CSHTML %}

<ej-digital-gauge id="Digitalgauge" height="200" width="500" value="WELCOME">
<e-items>
<e-digital-gauge-items value="STOP" text-align="@TextAlign.Right">
</e-digital-gauge-items>
</e-items>
</ej-digital-gauge>


{% endhighlight %}

Execute the above code examples to render the DigitalGauge as follows.

![](Digital-Elements_images/Digital-Elements_img1.png)

Digital Gauge control with text customization
{:.caption}

