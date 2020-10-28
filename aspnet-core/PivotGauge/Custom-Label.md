---
layout: post
title: Custom labels | ASP.NET Core | PivotGauge | Syncfusion
description: This document illustrates that how to enable custom labels and its functionalities in ASP.NET Core PivotGauge control
platform: aspnet-core
control: PivotGauge
documentation: ug
---

# Custom labels

## Adding custom label collection

You can apply the custom label collection by using the `CustomLabelCollection` which can be directly added to the scales option within the pivot gauge control.

{% highlight cshtml %}

<ej-pivot-gauge id="PivotGauge1">
    <e-scales>
        <e-circular-scales>
            <e-custom-label-collections>
                <e-circular-custom-labels>
                    <e-custom-position x="180" y="290"></e-custom-position>
                </e-circular-custom-labels>
            </e-custom-label-collections>
        </e-circular-scales>
    </e-scales>
</ej-pivot-gauge>

{% endhighlight %}

## Appearance customization

The appearance of the custom labels can be changed through the following properties:

* **Position**: Sets the position of the labels.
* **Font**: Sets the font size, font style, and font family of the label text.
* **Color**: Sets the color of the label text.
* **TextAngle**: Rotates the label to a specified angle. By default, the value is 0.

{% highlight cshtml %}

<ej-pivot-gauge id="PivotGauge1">
    <e-scales>
        <e-circular-scales>
            <e-custom-label-collections>
                <e-circular-custom-labels color="blue" text-angle="20">
                    <e-custom-position x="180" y="320"></e-custom-position>
                    <e-custom-font size="12px" font-family="Segoe UI" font-style="Normal"></e-custom-font>
                </e-circular-custom-labels>
            </e-custom-label-collections>
        </e-circular-scales>
    </e-scales>
</ej-pivot-gauge>

{% endhighlight %}

![Custom label customization in ASP NET Core pivot gauge control](Custom-Label_images/AppearanceCustomization.png) 

## Multiple custom labels

Multiple ranges can be added to `CustomLabelCollection` to the scales option within the pivot gauge control.

{% highlight cshtml %}

<ej-pivot-gauge id="PivotGauge1">
    <e-scales>
        <e-circular-scales>
            <e-custom-label-collections>
                <e-circular-custom-labels color="red">
                    <e-custom-position x="180" y="150"></e-custom-position>
                    <e-custom-font size="12px" font-family="Segoe UI" font-style="Normal"></e-custom-font>
                </e-circular-custom-labels>
                <e-circular-custom-labels color="green">
                    <e-custom-position x="180" y="320"></e-custom-position>
                    <e-custom-font size="10px" font-family="Segoe UI" font-style="Normal"></e-custom-font>
                </e-circular-custom-labels>
                <e-circular-custom-labels color="blue">
                    <e-custom-position x="180" y="290"></e-custom-position>
                    <e-custom-font size="10px" font-family="Segoe UI" font-style="Normal"></e-custom-font>
                </e-circular-custom-labels>
            </e-custom-label-collections>
        </e-circular-scales>
    </e-scales>
</ej-pivot-gauge>

{% endhighlight %}

![Multiple custom labels in ASP NET Core pivot gauge control](Custom-Label_images/MultipleCustomLabels.png) 