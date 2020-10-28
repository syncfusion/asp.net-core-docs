---
layout: post
title: Tooltip | CircularGauge | Syncfusion
description: tooltip
platform: aspnet-core
control: CircularGauge
documentation: ug
---

# Tooltip

* Tooltip feature has been added to the Circular Gauge. Circular Gauge has several elements such as pointers, label, customLabel, scales, etc.  
* There is a need for Tooltip feature in the Circular Gauge control because whenever the text hides or overrides with other gauge elements, it may not be fully visible. For resolving those problems Tooltip feature has been implemented in the Circular Gauge control.

## Default Tooltip

* Tooltip has three attributes in it. The first two attributes such as `show-label-tooltip` and `show-custom-label-tooltip` are for enabling the Tooltip for label as well as custom label in default appearance. 
* ShowLabelTooltip is to enable the Tooltip for labels and showCustomLabelTooltip is for enabling the Tooltip option for customLabels.

{% highlight CSHTML %}

<ej-circular-gauge id="circulargauge" >
<e-circular-tooltip show-label-tooltip="true" show-custom-label-tooltip="true"></e-circular-tooltip>
<e-circular-scale-collections>
<e-circular-scales show-labels="true" radius="130" >
<e-custom-label-collections>
<e-circular-custom-labels value="0 9 5 3 4 5">
<e-custom-position x="180" y="200">
</e-custom-position>
<e-custom-font font-style="bold" font-family="segoe UI" size="20px">
</e-custom-font>
</e-circular-custom-labels>
</e-custom-label-collections>
<e-pointer-collections>
<e-pointers value="60" length="90" ></e-pointers>
</e-pointer-collections>
</e-circular-scales>
</e-circular-scale-collections>
</ej-circular-gauge>

{% endhighlight %}

Execute the above code to render the following output.

![](Tooltip_images/Tooltip_img1.png)

Gauge with Default ToolTip
{:.caption}

## Tooltip Template

In Tooltip option, you can customize the Tooltip window by adding the tooltip template on that page with the help of API `template-id`. Refer to the following code example to know more about Tooltip template.


{% highlight CSHTML %}

<ej-circular-gauge id="circulargauge" >
<e-circular-tooltip show-label-tooltip="true" show-custom-label-tooltip="true"
template-id="Tooltip"></e-circular-tooltip>
<e-circular-scale-collections>
<e-circular-scales show-labels="true" radius="130" >
<e-custom-label-collections>
<e-circular-custom-labels value="0 9 5 3 4 5">
<e-custom-position x="180" y="200">
</e-custom-position>
<e-custom-font font-style="bold" font-family="segoe UI" size="20px">
</e-custom-font>
</e-circular-custom-labels>
</e-custom-label-collections>
<e-pointer-collections>
<e-pointers value="60" length="90" ></e-pointers>
</e-pointer-collections>
</e-circular-scales>
</e-circular-scale-collections>
</ej-circular-gauge>


{% endhighlight %}

Execute the above code to render the following output.



![](Tooltip_images/Tooltip_img2.png)

Circular gauge with tooltip template
{:.caption}


