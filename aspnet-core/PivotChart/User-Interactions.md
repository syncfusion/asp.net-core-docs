---
layout: post
title: User-Interactions | PivotChart | ASP.NET Core | Syncfusion
description: user interactions
platform: aspnet-core
control: PivotChart
documentation: ug
---

# User interactions

## Tooltip

### Enable tooltips for data points

Tooltips for the data points can be enabled by using the **"visible"** option of the `e-chart-tooltip` property under **"e-common-series-options"** in the pivot chart.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    //Enabling tooltip of data point
    <e-common-series-options>
        <e-chart-tooltip visible="true"></e-chart-tooltip>
    </e-common-series-options>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

![Tooltip in ASP NET Core pivot chart control](User-Interactions_images/tooltip.png)

### Tooltip template

HTML elements can be displayed in the tooltip by using the `tooltip-template` option. The template option takes the value of the "id" attribute from the HTML element. You can use the **#point.x#** and **#point.y#** as place holders in the HTML element to display the X and Y values of the corresponding data points.

{% highlight cshtml %}

<div id="Tooltip" style="display: none;">
    <div id="icon">
        <div id="ccicon"> </div>
    </div>
    <div id="value">
        <div>
            <label id="ccvalue">&nbsp;#point.y# </label>
            <label id="cc">Customer Count </label>
        </div>
    </div>
</div>
<ej-pivot-chart id="PivotChart1">
    <e-common-series-options>
        <e-chart-tooltip visible="false" tooltip-template="Tooltip"></e-chart-tooltip>
    </e-common-series-options>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

![Tooltip template in ASP NET Core pivot chart control](User-Interactions_images/tooltiptemplate.png)

### Tooltip customization

By using the `fill` and `border` properties of the tooltip, you can customize its background color, border color, and border width.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    <e-common-series-options>
        <e-chart-tooltip visible="false" tooltip-fill="#FF9933" tooltip-border-width="1" tooltip-border-color="#993300"></e-chart-tooltip>
    </e-common-series-options>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

![Tooltip customization in ASP NET Core pivot chart control](User-Interactions_images/tooltipcustomization.png)

### Tooltip with rounded corners

The tooltip properties `rx` and `ry` are used to customize its corner radius.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1">
    //Customize the corner radius of the tooltip rectangle.
    <e-common-series-options>
        <e-chart-tooltip visible="false" tooltip-rx="50" tooltip-ry="50"></e-chart-tooltip>
    </e-common-series-options>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

{% endhighlight %}

![Tooltip with rounded corners in ASP NET Core pivot chart control](User-Interactions_images/tooltiprouded.png)

## Marker and crosshair

### Marker shape customization

In the pivot chart, you can customize the marker `shape` with the following symbols:

* Rectangle
* Circle
* Cross
* Diamond
* Pentagon
* Hexagon
* Star
* Ellipse
* Triangle etc.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1" series-rendering="onSeriesRenders">
    <e-common-series-options type="Line"></e-common-series-options>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>
<script type="text/javascript">
    function onSeriesRenders(args) {
        for (var seriescount = 0; seriescount < this.model.series.length; seriescount++)
            this.model.series[seriescount].marker.shape = "Triangle";
    }
</script>

{% endhighlight %}

![Marker customization in ASP NET Core pivot chart control](User-Interactions_images/marker.png)

## Highlight

The pivot chart provides highlighting support for the series and data points by hovering the mouse. To enable highlighting, set the **“enable”** property to true in the `highlightSettings` of the series.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1" series-rendering="onSeriesRenders">
    <e-common-series-options type="Column"></e-common-series-options>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>
<script type="text/javascript">
    function onSeriesRenders(args) {
        for (var seriescount = 0; seriescount < this.model.series.length; seriescount++)
            this.model.series[seriescount].highlightSettings.enable = true
    }
</script>

{% endhighlight %}

### Highlight mode

You can set three different modes for highlighting data points and series by using the `mode` property of the `highlightSettings`.

* series
* points
* cluster

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1" series-rendering="onSeriesRenders">
    <e-common-series-options type="Column"></e-common-series-options>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>
<script type="text/javascript">
    function onSeriesRenders(args) {
        for (var seriescount = 0; seriescount < this.model.series.length; seriescount++) {
            this.model.series[seriescount].highlightSettings.enable = true
            this.model.series[seriescount].highlightSettings.mode = "series";
        }
    }
</script>

{% endhighlight %}

![Highlight mode in ASP NET Core pivot chart control](User-Interactions_images/highlightmode.png)

### Customize the highlight styles

To customize the highlighted series, use the `border.color`, `border.width`, and `opacity` options in the `highlightSettings` property.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1" series-rendering="onSeriesRenders">
    <e-common-series-options type="Column"></e-common-series-options>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>
<script type="text/javascript">
    function onSeriesRenders(args) {
        for (var seriescount = 0; seriescount < this.model.series.length; seriescount++) {
            this.model.series[seriescount].highlightSettings.enable = true
            this.model.series[seriescount].highlightSettings.opacity = "0.5";
            this.model.series[seriescount].highlightSettings.border.width = "1.5";
            this.model.series[seriescount].highlightSettings.border.color = "red";
        }
    }
</script>

{% endhighlight %}

![Highlight style in ASP NET Core pivot chart control](User-Interactions_images/customizehighlight.png)

### Patterns to highlight

The pivot chart provides pattern support for highlighting the data by setting an appropriate value to the `pattern` property of the `highlightSettings`. The different types of highlight patterns are as follows:

* chessboard
* crosshatch
* dots
* pacman
* grid
* turquoise
* star
* triangle
* circle
* tile
* horizontalDash
* verticalDash
* rectangle
* box
* verticalStripe
* horizontalStripe
* bubble
* diagonalBackward
* diagonalForward


{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1" series-rendering="onSeriesRenders">
    <e-common-series-options type="Column"></e-common-series-options>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>
<script type="text/javascript">
    function onSeriesRenders(args) {
        for (var seriescount = 0; seriescount < this.model.series.length; seriescount++) {
            this.model.series[seriescount].highlightSettings.enable = true
            this.model.series[seriescount].highlightSettings.pattern = "chessboard";
        }
    }
</script>

{% endhighlight %}

![Highlight settings in ASP NET Core pivot chart control](User-Interactions_images/patternhighlight.png)

## Selection

The pivot chart provides selection support for series and data points by clicking the mouse. To enable selection, set the **“enable”** property to true in the `selectionSettings` of the series.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1" series-rendering="onSeriesRenders">
    <e-common-series-options type="Column"></e-common-series-options>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>
<script type="text/javascript">
    function onSeriesRenders(args) {
        for (var seriescount = 0; seriescount < this.model.series.length; seriescount++) {
            this.model.series[seriescount].selectionSettings.enable = true;
        }
    }
</script>

{% endhighlight %}

### Selection mode

You can set three different selection modes for highlighting the data points and series by using the `mode` property of the `selectionSettings`.

* series
* points
* cluster

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1" series-rendering="onSeriesRenders">
    <e-common-series-options type="Column"></e-common-series-options>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>
<script type="text/javascript">
    function onSeriesRenders(args) {
        for (var seriescount = 0; seriescount < this.model.series.length; seriescount++) {
            this.model.series[seriescount].selectionSettings.enable = true;
            this.model.series[seriescount].selectionSettings.mode = "series";
        }
    }
</script>

{% endhighlight %}

![Selection mode in ASP NET Core pivot chart control](User-Interactions_images/selectionmode.png)

### Customize the selection styles

To customize the selection styles, use the `border.color`, `border.width`, and `opacity` options in the `selectionSettings`.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1" series-rendering="onSeriesRenders">
    <e-common-series-options type="Column"></e-common-series-options>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>
<script type="text/javascript">
    function onSeriesRenders(args) {
        for (var seriescount = 0; seriescount < this.model.series.length; seriescount++) {
            this.model.series[seriescount].selectionSettings.enable = true;
            this.model.series[seriescount].selectionSettings.border.width = "1.5";
            this.model.series[seriescount].selectionSettings.border.color = "red";
        }
    }
</script>

{% endhighlight %}

![Selection style in ASP NET Core pivot chart control](User-Interactions_images/customizeselection.png)

### Patterns for selection

The pivot chart provides pattern support for selecting data by setting an appropriate value to the `pattern` property of the `selectionSettings`. The different types of selection patterns are as follows:

* chessboard
* crosshatch
* dots
* pacman
* grid
* turquoise
* star
* triangle
* circle
* tile
* horizontalDash
* verticalDash
* rectangle
* box
* verticalStripe
* horizontalStripe
* bubble
* diagonalBackward
* diagonalForward

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1" series-rendering="onSeriesRenders">
    <e-common-series-options type="Column"></e-common-series-options>
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>
<script type="text/javascript">
    function onSeriesRenders(args) {
        for (var seriescount = 0; seriescount < this.model.series.length; seriescount++) {
            this.model.series[seriescount].selectionSettings.enable = true
            this.model.series[seriescount].selectionSettings.pattern = "chessboard";
        }
    }
</script>

{% endhighlight %}

![Selection settings in ASP NET Core pivot chart control](User-Interactions_images/patternselecion.png)
