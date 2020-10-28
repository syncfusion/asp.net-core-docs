---
layout: post
title: Chart Annotations |Chart  | ASP.NET Core | Syncfusion
description: How to add annotations in Essential ASP.NET CORE Chart and the different options available to customize its position. 
platform: aspnet-core
control: Chart
documentation: ug
---

# Annotations

Annotations are used to mark the specific area of interest in the chart with texts, shapes, or images. 

You can add annotations to the chart by using the **Annotations** option. By using the **Content** option of annotation, you can specify the ID of the element that needs to be displayed in the chart area.

{% highlight cshtml %}

<div id= "watermark" style="font-size:100px; display:none">2014</div>
<div>
<ej-chart id="chartContainer">
    // ...
    <e-annotations>
        <e-annotation visible="true" content="watermark" opacity="0.2" region="Series"></e-annotation>
    </e-annotations>
    // ...
</ej-chart>
</div>

{% endhighlight %}

![](Annotations_images/Annotations_img1.png)

N> Annotations are not supported in 3D chart types.

## Rotate the annotation template

To rotate the annotation template, use the **Angle** property of the annotations. 

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
    <e-annotations>
        <e-annotation visible="true" angle="270"></e-annotation>
    </e-annotations>
    // ...
</ej-chart>

{% endhighlight %}

![](Annotations_images/Annotations_img2.png)


## Positioning annotation

You can position the annotations by using either the coordinates (**X** and **Y**) or the alignment options (**HorizontalAlignment** and **VerticalAlignment**).

By using the **CoordinateUnit** option, you can specify whether the value provided in the X and Y options are relative to the chart or axis.

* If the **CoordinateUnit** is set to None, the annotations are placed relative to the chart/plot area by using the **HorizontalAlignment** and **VerticalAlignment** options.

* If the **coordinateUnit** is set to points, the x and y values of the annotation are the coordinates relative to the axis, and annotation is positioned relative to the axis. By default, the x and y values are associated with the **PrimaryXAxis** and **PrimaryYAxis**. In case, when the chart contains multiple axis and you want to associate the annotation with a particular axis, specify the **XAxisName** and **YAxisName** options of the annotation object.

* If the **coordinateUnit** is set to pixels, the X and Y values are coordinates relative to the top-left corner of the chart/plot area.

N> By using the **Region** option, you can specify whether the annotation is placed relative to the entire chart or plot area.

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
    <e-annotations>
        <e-annotation visible="true" coordinate-unit="Pixels" x="170" y="350"></e-annotation>
    </e-annotations>
    // ...
</ej-chart>

{% endhighlight %}

![](Annotations_images/Annotations_img3.png)

## Annotation alignments

When the **coordinateUnit** is set to pixels or points, you can align the annotation relative to the coordinates by using the **HorizontalAlignment** and **VerticalAlignment** options. 

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
    <e-annotations>
        <e-annotation visible="true" vertical-alignment="Middle" horizontal-alignment="Left">
        </e-annotation>
    </e-annotations>
    // ...
</ej-chart>

{% endhighlight %}

![](Annotations_images/Annotations_img4.png)