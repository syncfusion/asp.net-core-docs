---
layout: post
title: Label Format | ASP.NET Core | PivotGauge | Syncfusion
description: This document illustrates that how to define label format feature and its functionalities in ASP.NET Core PivotGauge control
platform: aspnet-core
control: PivotGauge
documentation: ug
---

# Label format

You can customize the format of labels displayed in the pivot gauge control by using `e-label-format-settings` property.

Following are the formats that can be applied to labels in the pivot gauge:

* `number-format`  - Allows you to change the number format of the label values in the pivot gauge.
* `decimal-places` - Allows you to set the number of digits displayed after the decimal point.
* `prefix-text`  - Allows you to add a text at the beginning of the label.
* `suffix-text` - Allows you to add a text at the end of the label.

Number format for the label values can be set to any of the following types:

* Default	
* Currency
* Percentages
* Fraction
* Scientific
* Text
* Notation

{% highlight cshtml %}

<ej-pivot-gauge id="PivotGauge1">
    <e-label-format-settings number-format="Percentage" prefix-text="#*" suffix-text="*#" decimal-places="2"></e-label-format-settings>
</ej-pivot-gauge>

{% endhighlight %}

![Label formats in ASP NET Core pivot gauge control](Label-Format_images/labelformat.png) 
