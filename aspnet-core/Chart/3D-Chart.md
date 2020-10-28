---
layout: post
title: 3D Chart | Chart | ASP.NET CORE | Syncfusion
description: 3d chart
platform: aspnet-core
control: Chart
documentation: ug
---

# 3D Chart

Essential 3D chart for ASP.NET Core allows you to view 8 chart types in 3D view such as bar, stacking bar, stacking bar 100, column, stacked column, 100% stacked column, pie, and doughnut.

## 3D column chart

For rendering a 3D column chart, specify the series type to **Column** in the chart series, and set **Enable3D** option to true in the chart.

{% highlight cshtml %}

<ej-chart id="container" enable3d="true">
    <e-chart-series>
        <e-series type="Column">
            <e-points>
             //..
            </e-points>
        </e-series>
    </e-chart-series>
</ej-chart>

{% endhighlight %}

![](3D-Chart_images/3D-Chart_img1.png)


## 3D bar chart

You can create a 3D bar chart by setting the series type to **Bar** in the chart series, and enabling **Enable3D** option in the chart.

{% highlight cshtml %}

<ej-chart id="container" enable3d="true">
     <e-chart-series>
        <e-series type="Bar">
            <e-points>
             //..
            </e-points>
        </e-series>
    </e-chart-series>
</ej-chart>

{% endhighlight %}

![](3D-Chart_images/3D-Chart_img2.png)


## 3D stacked column chart

You can create a 3D stacked column chart by setting the series type to **StackingColumn** in the chart series, and enabling **Enable3D** option in the chart.

{% highlight cshtml %}

<ej-chart id="container" enable3d="true">
    <e-chart-series>
        <e-series type="StackingColumn">
            <e-points>
             //..
            </e-points>
        </e-series>
        <e-series type="StackingColumn">
            <e-points>
             //..
            </e-points>
        </e-series>
    </e-chart-series>
</ej-chart>

{% endhighlight %}

![](3D-Chart_images/3D-Chart_img3.png)

## 3D 100% stacked column chart

100% stacking column 3D chart is rendered by specifying the series type to **StackingColumn100** in the chart series, and enabling **Enable3D** option in the chart.

{% highlight cshtml %}

<ej-chart id="container" enable3d="true">
    <e-chart-series>
        <e-series type="StackingColumn100">
            <e-points>
             //..
            </e-points>
        </e-series>
        <e-series type="StackingColumn100">
            <e-points>
             //..
            </e-points>
        </e-series>
    </e-chart-series>
</ej-chart>

{% endhighlight %}

![](3D-Chart_images/3D-Chart_img4.png)


## 3D stacked bar chart

To create stacking bar 3D chart, set the series type to **StackingBar** in the chart series, and enabling **Eenable3D** option in the chart.

{% highlight cshtml %}

<ej-chart id="container" enable3d="true">
    <e-chart-series>
        <e-series type="StackingBar">
            <e-points>
             //..
            </e-points>
        </e-series>
        <e-series type="StackingBar">
            <e-points>
             //..
            </e-points>
        </e-series>
    </e-chart-series>
</ej-chart>

{% endhighlight %}

![](3D-Chart_images/3D-Chart_img5.png)


## 3D 100% stacked bar chart

You can create 100% stacking bar 3D chart by setting the series type to **StackingBar100** in the chart series, and enabling **Eenable3D** option in chart.

{% highlight cshtml %}

<ej-chart id="container" enable3d="true">
    <e-chart-series>
        <e-series type="StackingBar100">
            <e-points>
             //..
            </e-points>
        </e-series>
        <e-series type="StackingBar100">
            <e-points>
             //..
            </e-points>
        </e-series>
    </e-chart-series>
</ej-chart>

{% endhighlight %}

![](3D-Chart_images/3D-Chart_img6.png)


## 3D pie chart

To render the pie chart in 3D view, enable the **Enbel3D** option in the chart, and set the series type to **Pie** in the chart series.

{% highlight cshtml %}

<ej-chart id="container" enable3d="true">
    <e-chart-series>
        <e-series type="Pie">
            <e-points>
             //..
            </e-points>
        </e-series>
    </e-chart-series>
</ej-chart>

{% endhighlight %}

![](3D-Chart_images/3D-Chart_img7.png)


## 3D doughnut chart

To render the doughnut chart in 3D view, enable the **Enbel3D** option in the chart, and set the series type to **Doughnut** in the chart series.

{% highlight cshtml %}

<ej-chart id="container" enable3d="true">
 <e-chart-series>
        <e-series type="Doughnut">
            <e-points>
             //..
            </e-points>
        </e-series>
    </e-chart-series>
</ej-chart>

{% endhighlight %}

![](3D-Chart_images/3D-Chart_img8.png)


## Configure 3D chart

### 3D view

To render the chart in 3D view, set the **Enable3D** option to true in the chart.

{% highlight cshtml %}

<ej-chart id="container" enable3d="true">

//..

</ej-chart>

{% endhighlight %}


![](3D-Chart_images/3D-Chart_img9.png)


### Placing bar/column kind of series side-by-side

The **SideBySideSeriesPlacement** property defines the appearance of the different sets of data in 3D chart. When this property is enabled, the data is displayed side by side, otherwise it is displayed along the depth of the axis.
 
{% highlight cshtml %}

<ej-chart id="container" enable3d="true" side-by-side-series-placement="true">

//..

</ej-chart>

{% endhighlight %}


![](3D-Chart_images/3D-Chart_img10.png)


### Setting axis wall size

In 3D chart, Cartesian axes lines are represented as walls, and they define the width of the 3D wall. 3D pie and doughnut chart does not support **WallSize** because they do not have axes.

{% highlight cshtml %}

<ej-chart id="container" enable3d="true" wall-size="10">

//..

</ej-chart>

{% endhighlight %}


![](3D-Chart_images/3D-Chart_img11.png)


### 3D depth

By using the **Depth** property, you can view the 3D chart from the front view of the series to the background wall.

{% highlight cshtml %}

<ej-chart id="container" enable3d="true" depth="120">

//..

</ej-chart>

{% endhighlight %}


![](3D-Chart_images/3D-Chart_img12.png)


### Rotating and tilting 3D chart

To spin the 3D chart by dragging the mouse, enable **EnableRotation** option in the chart. The **Tilt** property specifies the angle of the slope of the 3D chart. The positive and negative values are declared to the side where the slope is present. The **Rotation** option is used to rotate the 3D chart towards left or right side of the chart. The direction of the chart depends on the positive and negative values of the angle.

{% highlight cshtml %}

<ej-chart id="container" enable3d="true" tilt="10" rotation="40" enable-rotation="true">

//..

</ej-chart>

{% endhighlight %}


![](3D-Chart_images/3D-Chart_img13.png)


### PerspectiveAngle	

The **PerspectiveAngle** specifies the appearance of the height, width, depth, and wall of the 3D chart. When the PerspectiveAngle is decreased, the 3D object appears very close to the viewer. But when it is increased, the 3D object appears far away from the viewer. 

{% highlight cshtml %}

<ej-chart id="container" enable3d="true" perspective-angle="150">

//..

</ej-chart>

{% endhighlight %}

![](3D-Chart_images/3D-Chart_img14.png)