---
layout: post
title: Layout Customization in ASP.NET Core PivotClient Control | Syncfusion
description: Learn here about layout customization in Syncfusion Essential ASP.NET Core PivotClient Control, and more.
platform: aspnet-core
control: PivotClient
documentation: ug
---

# Layout customization in ASP.NET Core PivotClient Control

## Size

Allows you to render the pivot client in different sizes. You can set the height and width under the `e-size` property.

### Set size in pixels

{% highlight CSHTML %}

<ej-pivot-client id="PivotClient1" >
    //..
    <e-size width="1000px" height="685px"></e-size>
</ej-pivot-client>

{% endhighlight %}

Pivot client with decreased size from default size.

![ASP NET Core pivot client control with reduced size](Layout-Customization_images/small-size.png)

### Set size in percentage

You can set the pivot client size in percentage also.

N> Size of the parent container should be set in pixels.

{% highlight CSHTML %}

<ej-pivot-client id="PivotClient1" >
    //..
    <e-size width="50%" height="80%"></e-size>
</ej-pivot-client>

{% endhighlight %}

## Control placement

### Tab view

In tab view representation, both the grid and chart will be displayed in separate tabs. This can be set by using the `control-placement` property under the `e-display-settings`. By default, the **Tab** value is set.

{% highlight CSHTML %}

<ej-pivot-client id="PivotClient1" >
    //..
    <e-display-settings control-placement="Tab"></e-display-settings>
</ej-pivot-client>

{% endhighlight %}

![ASP NET Core pivot client control with tab view](Layout-Customization_images/tabview.png)

### Tile view

In tile view representation, both the grid and chart will be displayed one above the other in the same layout. The tile view can be set by using the `control-placement` property under the `e-display-settings` option.

{% highlight CSHTML %}

<ej-pivot-client id="PivotClient1" >
    //..
    <e-display-settings control-placement="Tile"></e-display-settings>
</ej-pivot-client>

{% endhighlight %}

![ASP NET Core pivot client control with tile view](Layout-Customization_images/tileview.png)

## Default view

### Grid view

To display grid control by default, set the `default-view` property under `e-display-settings` option to **Grid**, which is the default value of the property.

{% highlight CSHTML %}

<ej-pivot-client id="PivotClient1" >
    //..
    <e-display-settings default-view="Grid"></e-display-settings>
</ej-pivot-client>

{% endhighlight %}

![ASP NET Core pivot client control with grid view as default](Layout-Customization_images/gridview.png)

### Chart view

To display chart control by default, set the `default-view` property to **Chart**.

{% highlight CSHTML %}

<ej-pivot-client id="PivotClient1" >
    //..
    <e-display-settings default-view="Chart"></e-display-settings>
</ej-pivot-client>

{% endhighlight %}

![ASP NET Core pivot client control with chart view as default](Layout-Customization_images/chartview.png)

## Display mode

### Grid only

By setting the `mode` property under the `e-display-settings` option to **GridOnly**, the pivot grid component alone will get rendered and the pivot chart will not be rendered.

{% highlight CSHTML %}

<ej-pivot-client id="PivotClient1" >
    //..
    <e-display-settings mode="GridOnly"></e-display-settings>
</ej-pivot-client>

{% endhighlight %}

![ASP NET Core pivot client control with grid only view](Layout-Customization_images/gridonlyview.png)

### Chart only

By setting the `mode` property under the `e-display-settings` option to **ChartOnly**, the pivot chart component alone will get rendered and pivot grid will not be rendered.

{% highlight CSHTML %}

<ej-pivot-client id="PivotClient1" >
    //..
    <e-display-settings mode="ChartOnly"></e-display-settings>
</ej-pivot-client>


{% endhighlight %}

![ASP NET Core pivot client control with chart only view](Layout-Customization_images/chartonlyview.png)

### Both chart and grid

By setting the `mode` property under the `e-display-settings` option to **ChartAndGrid**, the data is displayed in both grid and chart. This is the default value of the property.

{% highlight CSHTML %}

<ej-pivot-client id="PivotClient1" >
    //..
    <e-display-settings mode="ChartAndGrid"></e-display-settings>
</ej-pivot-client>

{% endhighlight %}

![ASP NET Core pivot client control with grid and chart view](Layout-Customization_images/tileview.png)

## Toggle panel

Toggle panel option allows you to toggle the visibility of axis element builder and cube dimension browser panels in the pivot client by using a button. The button can be added to the control by enabling the `enable-toggle-panel` property under `e-display-settings` option.  This property is disabled by default.

{% highlight CSHTML %}

<ej-pivot-client id="PivotClient1" >
    //..
    <e-display-settings enable-toggle-panel="true"></e-display-settings>
</ej-pivot-client>

{% endhighlight %}

![ASP NET Core pivot client control with toggle panel](Layout-Customization_images/toggleview.png)

## Collapse toggle panel by default

Allows you to hide “Cube Browser” and “Axis Element Builder” panels while initiating the widget. You can enable this option in the pivot client by setting the `collapse-cube-browser-by-default` property to true.

{% highlight CSHTML %}

<ej-pivot-client id="PivotClient1" collapse-cube-browser-by-default="true">
    //..
</ej-pivot-client>

{% endhighlight %}

![ASP NET Core pivot client control with toggle panel by default](Layout-Customization_images/collapse-cube-browser-by-default.png)

## Maximized/full screen view

Full screen view helps to visualize the pivot grid and pivot chart controls in the pivot client precisely according to the browser window size. By selecting the full screen icon in the toolbar, the control which is in the view gets maximized. The drilldown action can be performed in both pivot grid and pivot chart in the maximized view. This option is enabled by setting the `enable-full-screen` property under `e-display-settings` option to true.  The value is false by default.

{% highlight CSHTML %}

<ej-pivot-client id="PivotClient1">
    //..
    <e-display-settings enable-full-screen="true"></e-display-settings>
</ej-pivot-client>

{% endhighlight %}

![Full screen icon in ASP NET Core pivot client control](Layout-Customization_images/maximizeicon.png)

The following screenshot shows the maximized view of the pivot grid:

![Full screen view of ASP NET Core pivot client control](Layout-Customization_images/maximizedview.png)


## Chart types

While loading the pivot client initially, the pivot chart widget can be rendered in any one of the available chart types by using the `chart-type` property.

{% highlight CSHTML %}

<ej-pivot-client id="PivotClient1" chart-type="Column">
    //..
</ej-pivot-client>

{% endhighlight %}

The `chart-type` property takes column chart by default. The types available are column, stacking column, bar, stacking bar, line, spline, step line, area, spline area, step area, stacking area, pie, funnel, and pyramid.

The chart type can be changed dynamically through the toolbar icon.

![Chart types icon in ASP NET Core pivot client control](Layout-Customization_images/charttypes.png)

![ASP NET Core pivot client control with line chart type](Layout-Customization_images/linechart.png)

### Pivot tree map

I> This feature is applicable only for OLAP data source bound from the server-side.

You can include the pivot tree map component as one of the chart types by setting `enable-pivot-tree-map` property to true.

{% highlight CSHTML %}

<ej-pivot-client id="PivotClient1" enable-pivot-tree-map="true">
    //..
</ej-pivot-client>

{% endhighlight %}

![Treemap icon in chart types panel of ASP NET Core pivot client control](Layout-Customization_images/TreeMap1.png)

![Treemap in ASP NET Core pivot client control](Layout-Customization_images/TreeMap2.png)


## Report toolbar

You can customize the display of toolbar by enabling/disabling the visibility of each of the icons. This can be achieved by setting the properties under `e-toolbar-icon-settings` option to false. The values are true by default.​​​

{% highlight CSHTML %}

<ej-pivot-client id="PivotClient1">
    //..
    <e-toolbar-icon-settings enable-add-report="false" enable-new-report="false" enable-remove-report="false"></e-toolbar-icon-settings>
</ej-pivot-client>

{% endhighlight %}

![Report toolbar in ASP NET Core pivot client control](Layout-Customization_images/toolbarIconSettings1.png)

The following screenshot shows after disabling the toolbar icons:

![Hiding report icons from toolbar of ASP NET Core pivot client control](Layout-Customization_images/toolbarIconSettings2.png)
