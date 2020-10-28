---
layout: post
title: Axes | PivotChart | ASP.NET Core | Syncfusion
description: This document illustrates that how to define chart axes and its customization in ASP.NET Core PivotChart control
platform: aspnet-core
control: PivotChart
documentation: ug
---

# Axes

## Label format

### Format numeric labels

By using the `label-format` property, you can format the numeric labels. Numeric values can be formatted with n (number with decimal points), c (currency), and p (percentage) commands.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    //Applying currency format to axis labels
    <e-primary-y-axis label-format="c" ></e-primary-y-axis>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

![Label formatting in ASP NET Core pivot chart control](Chart-Axes_images/Chart-Axes_img1.png)

Following table describes the result when applying some commonly used label formats on numeric values:

<table>
<tr>
<th>
Label Value</th><th>
Label Format Property Value</th><th>
Result</th><th>
Description</th>
</tr>
<tr><td>
1000</td><td>
n1</td><td>
1000.0</td><td>
The Number is rounded to 1 decimal place</td>
</tr>
<tr><td>
1000</td><td>
n2</td><td>
1000.00</td><td>
The Number is rounded to 2 decimal place</td>
</tr>
<tr><td>
1000</td><td>
n3</td><td>
1000.000</td><td>
The Number is rounded to 3 decimal place</td>
</tr>
<tr><td>
0.01</td><td>
p1</td><td>
1.0%</td><td>
The Number is converted to percentage with 1 decimal place</td>
</tr>
<tr><td>
0.01</td><td>
p2</td><td>
1.00%</td><td>
The Number is converted to percentage with 2 decimal place</td>
</tr>
<tr><td>
0.01</td><td>
p3</td><td>
1.000%</td><td>
The Number is converted to percentage with 3 decimal place</td>
</tr>
<tr><td>
1000</td><td>
c1</td><td>
$1,000.0</td><td>
The Currency symbol is appended to number and number is rounded to 1 decimal place</td>
</tr>
<tr><td>
1000</td><td>
c2</td><td>
$1,000.00</td><td>
The Currency symbol is appended to number and number is rounded to 2 decimal place</td>
</tr>
</table>

### Label format customization

By using the `label-format` property of `e-primary-y-axis`, you can add the category labels with a prefix and/or suffix.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    <e-primary-y-axis label-format="${value} K" ></e-primary-y-axis>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

![Label format customization in ASP NET Core pivot chart control](Chart-Axes_images/Chart-Axes_img2.png)

## Common axis features

### Axis visibility

The axis visibility can be set by using the `visible` property of the respective axis.

N> By default, the value of `visible` property is true in the pivot chart.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    //Disabling visibility of Y-axis
    <e-primary-y-axis visible="false"></e-primary-y-axis>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

![Axis visibility in ASP NET Core pivot chart control](Chart-Axes_images/Chart-Axes_img3.png)

### Label customization

By using the `font` property of the axis, you can customize the font family, color, opacity, size, and font-weight of labels.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    //Customizing label appearance
    <e-primary-x-axis font-color="Blue" font-font-size="14px" font-font-family="Segoe UI" font-font-weight="Bold"></e-primary-x-axis>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

![Label customization in ASP NET Core pivot chart control](Chart-Axes_images/Chart-Axes_img4.png)

### Label and tick positioning

Axis labels and ticks can be positioned inside or outside the chart area by using the `axis-label-position` and `tick-lines-position` properties. The labels and ticks are positioned outside the chart area, by default.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    //Customizing label and tick positions
    <e-primary-x-axis axis-label-position="Inside" tick-lines-position="Inside"></e-primary-x-axis>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

![Label and tick positioning in ASP NET Core pivot chart control](Chart-Axes_images/Chart-Axes_img5.png)

### Grid lines customization

By using the `major-grid-lines` and `minor-grid-lines` properties of the axis, you can customize the width, color, visibility, and opacity of the grid lines.

N> By default, the minor grid lines are not visible in the pivot chart.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    // Customizing grid lines
    <e-primary-x-axis major-grid-lines-width="5" major-grid-lines-visible="true" major-grid-lines-color="Blue" minor-ticks-per-interval="1" minor-grid-lines-width="25" minor-grid-lines-visible="true" minor-grid-lines-color="Red"></e-primary-x-axis>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

![Grid lines customization in ASP NET Core pivot chart control](Chart-Axes_images/Chart-Axes_img6.png)

### Tick line customization

By using the `major-tick-lines` and `minor-tick-lines` properties of the axis, you can customize the width, color, visibility, size, and opacity of the tick lines.

N> By default, the minor tick lines are not visible in the pivot chart.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    // Customizing tick lines
    <e-primary-x-axis major-tick-lines-width="10" major-tick-lines-visible="true" major-tick-lines-size="15" major-tick-lines-color="Blue" minor-ticks-per-interval="1" minor-tick-lines-width="15" minor-tick-lines-size="25" minor-tick-lines-visible="true" minor-tick-lines-color="Red"></e-primary-x-axis>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

![Tick lines customization in ASP NET Core pivot chart control](Chart-Axes_images/Chart-Axes_img7.png)

### Inversing axis

The axis can be inversed by using the `is-inversed` property of the axis.

N> By default, the `is-inversed` property is false in the pivot chart.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    //Inversing the X-axis
    <e-primary-x-axis is-inversed="true"></e-primary-x-axis>
    //Inversing the Y-axis
    <e-primary-y-axis is-inversed="true"></e-primary-y-axis>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

![Inversing axes in ASP NET Core pivot chart control](Chart-Axes_images/Chart-Axes_img8.png)

### Placing axes at opposite side

The `opposed-position` property of the chart axis can be used to place the axis at opposite direction from its default position.

N> By default, the `opposed-position` property is false in the pivot chart.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    //Placing axis at the opposite side of its normal position
    <e-primary-x-axis opposed-position="true"></e-primary-x-axis>
    //Placing axis at the opposite side of its normal position
    <e-primary-y-axis opposed-position="true"></e-primary-y-axis>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

![Position of axes in ASP NET Core pivot chart control](Chart-Axes_images/Chart-Axes_img9.png)

## Smart axis labels

When the axis labels overlap with each other based on the chart dimensions and label size, you can use the `label-intersect-action` property of the axis to avoid overlapping.

N> By default, the `label-intersect-action` property is none in the pivot chart.

The following options that are supported for `label-intersect-action` property are:

* Rotate45
* Rotate90
* Trim
* MultipleRows
* Wrap
* Hide.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    // Avoid overlapping of x-axis labels
    <e-primary-x-axis label-intersect-action="MultipleRows"></e-primary-x-axis>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

![Smart axis labels in ASP NET Core pivot chart control](Chart-Axes_images/Chart-Axes_img10.png)

