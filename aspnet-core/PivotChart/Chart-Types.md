---
layout: post
title: Chart Types | PivotChart | ASP.NET Core | Syncfusion
description: This document illustrates that how to define chart types and its customization in ASP.NET Core PivotChart control
platform: aspnet-core
control: PivotChart
documentation: ug
---

# Chart types

The Essential **PivotChart ASP.NET** supports 18 types of chart as follows:

* Column
* Stacking column
* Bar
* Stacking bar
* Pie
* Pyramid
* Funnel
* Line
* Step line
* Spline
* Area
* Step area
* Spline area
* Stacking area
* Doughnut
* Scatter
* Bubble
* WaterFall

## Column chart

The **column chart** is the most commonly used chart type. This uses vertical bars (called columns) to display different values of one or more items. Points from adjacent series are drawn as bars to compare frequency, count, total, or average of data in different categories. The column chart is ideal to show the variations in the value of an item over a period of time.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    <e-common-series-options type="Column"></e-common-series-options>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

The following screenshot displays **column chart**:

![ASP NET Core column chart control](Chart-Types_images/Chart-Types_img1.png)

Column chart
{:.caption}

## Stacking column chart

The **stacking column** chart is similar to column chart except for the Y-values. The Y-values stack on top of each other in a specified series order. This helps to visualize the relationship of parts to the whole chart across various categories.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    <e-common-series-options type="StackingColumn"></e-common-series-options>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

The following screenshot displays **stacking column chart**:


![ASP NET Core stacking column chart control](Chart-Types_images/Chart-Types_img2.png)

Stacking Column Chart
{:.caption}

## Bar chart

The **bar chart** displays horizontal bars for each point in the series and points from adjacent series. Bar charts are used to compare values across various categories for displaying the variations in the value of an item over a period of time or comparing the values of several items at a single point of time.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    <e-common-series-options type="Bar"></e-common-series-options>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

The following screenshot displays **bar chart**:

![ASP NET Core bar chart control](Chart-Types_images/Chart-Types_img3.png)

Bar Chart
{:.caption}

## Stacking bar chart

The **stacking bar chart** is a regular **bar** chart with X-values stacked on top of each other in the specified series order.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    <e-common-series-options type="StackingBar"></e-common-series-options>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

The following screenshot displays **stacking bar chart**:

![ASP NET Core stacking bar chart control](Chart-Types_images/Chart-Types_img4.png)

Stacking Bar Chart
{:.caption}

## Pie chart

The **pie chart** is used to summarize a set of categorical data or display different values of a given variable (e.g., percentage distribution). This type of chart is in a circular form that is divided into a series segments. Each segment represents a particular category.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    <e-common-series-options type="Pie"></e-common-series-options>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}


The following screenshot displays **pie chart**:

![ASP NET Core pie chart control](Chart-Types_images/Chart-Types_img5.png)

Pie Chart
{:.caption}

## Pyramid chart

The **pyramid chart** displays data in the form of a triangle. You can visualize data in a hierarchical structure without any axes.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    <e-common-series-options type="Pyramid"></e-common-series-options>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

The following screenshot displays **pyramid chart**:


![ASP NET Core pyramid chart control](Chart-Types_images/Chart-Types_img6.png)

Pyramid Chart
{:.caption}


## Funnel chart

The **funnel chart** displays data in the form of an inverted triangle. You can visualize data in a hierarchical structure without any axes.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    <e-common-series-options type="Funnel"></e-common-series-options>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

The following screenshot displays **funnel chart**:


![ASP NET Core funnel chart control](Chart-Types_images/Chart-Types_img14.png)

Funnel Chart
{:.caption}

## Line chart

The **line chart** joins the data points on a plot by using straight lines that show the trends in data at equal intervals.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    <e-common-series-options type="Line"></e-common-series-options>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}


The following screenshot displays **line chart**:

![ASP NET Core line chart control](Chart-Types_images/Chart-Types_img7.png)

Line Chart
{:.caption}

## Step line chart

The **step line chart** uses horizontal and vertical lines to connect data points resulting in a step like progression.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    <e-common-series-options type="StepLine"></e-common-series-options>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}


The following screenshot displays **step line chart**:

![ASP NET Core step line chart control](Chart-Types_images/Chart-Types_img8.png)

Step Line Chart
{:.caption}

## Spline chart

The **spline chart** is similar to the line chart except that it connects different data points with curve lines instead of straight lines.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    <e-common-series-options type="Spline"></e-common-series-options>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

The following screenshot displays **spline chart**:

![ASP NET Core spline chart control](Chart-Types_images/Chart-Types_img9.png)

Spline Chart
{:.caption}

## Area chart

The **area chart** emphasizes the degree of change of values over a period of time. Instead of rendering data as discrete bars or columns, the area chart renders the continuous ebb-and-flow pattern as defined against the Y-axis.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    <e-common-series-options type="Area"></e-common-series-options>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}


The following screenshot displays **area chart**:

![ASP NET Core area chart control](Chart-Types_images/Chart-Types_img10.png)

Area Chart
{:.caption}

## Step area chart

The **step area** chart is similar to the regular area chart except for a straight line tracing the shortest path between the data points. The values are connected by continuous vertical and horizontal lines to form a step like progression.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    <e-common-series-options type="StepArea"></e-common-series-options>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}


The following screenshot displays **step area chart**:

![ASP NET Core step area chart control](Chart-Types_images/Chart-Types_img11.png)

Step Area Chart
{:.caption}

## Spline area chart

The **spline area** chart is similar to the area chart, but differs by connecting data points in a series. This connects each series of points by a smooth **spline curve**.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    <e-common-series-options type="SplineArea"></e-common-series-options>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}


The following screenshot displays **spline area chart**:

![ASP NET Core spline area chart control](Chart-Types_images/Chart-Types_img12.png)

Spline Area Chart
{:.caption}

## Stacking area chart

The **stacking area** chart is similar to the regular area chart except for the Y-values. These Y-values stack on top of each other in the specified series order. This helps to visualize the relationship of parts to the whole chart across various categories.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    <e-common-series-options type="StackingArea"></e-common-series-options>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

The following screenshot displays **stacking area chart**:

![ASP NET Core stacking area chart control](Chart-Types_images/Chart-Types_img13.png)

Stacking Area Chart
{:.caption}

## Doughnut chart

The **doughnut chart** is a doughnut like structure used to summarize a set of categorical data that is divided into several segments. Each segment represents a particular category.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    <e-common-series-options type="Doughnut"></e-common-series-options>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

The following screenshot displays **doughnut chart**:

![ASP NET Core doughnut chart control](Chart-Types_images/DoughnutChart.png)

Doughnut Chart
{:.caption}

## Scatter chart

The **scatter chart** displays data as a collection of points corresponding to the associated values.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    <e-common-series-options type="Scatter"></e-common-series-options>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

The following screenshot displays **scatter chart**:

![ASP NET Core scatter chart control](Chart-Types_images/ScatterChart.png)

Scatter Chart
{:.caption}

## Bubble chart

The **bubble chart** displays data as a collection of bubbles.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    <e-common-series-options type="Bubble"></e-common-series-options>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

The following screenshot displays **bubble chart**:

![ASP NET Core bubble chart control](Chart-Types_images/BubbleChart.png)

Bubble Chart
{:.caption}

## WaterFall chart

The **waterfall chart** type is used to show how an initial value is increased and decreased by a series of intermediate values, leading to a final value.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    <e-common-series-options type="WaterFall"></e-common-series-options>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

The following screenshot displays the **waterfall chart:**

![ASP NET Core waterfall chart control](Chart-Types_images/WaterFall.png)

## Combination chart

The **combination chart** combines two or more series types in a single chart, but there are some limitations in the combination Chart. They are:

1. The combination chart cannot combine column and bar series.
2. The pie chart cannot be used with other series types.



{% highlight CSHTML %}

<ej-pivot-chart id="PivotChart1" series-rendering="onSeriesRenders">
    <e-common-series-options type="Column"></e-common-series-options>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

<script>
function onSeriesRenders(args) {
    this.model.series[5].type = ej.PivotChart.ChartTypes.Line;
    this.model.series[5].marker.visible = true;
}
</script>

{% endhighlight %}

The following screenshot displays **combination chart**:

![ASP NET Core combinations of charts](Chart-Types_images/combinationalchart.png)
