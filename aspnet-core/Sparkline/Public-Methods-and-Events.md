---
layout: post
title: Public Methods and Events
description: Public Methods and Events in Sparkline.
platform: aspnet-core
control: Sparkline
documentation: ug
---


## Methods


### redraw()


Redraws the entire sparkline. You can call this method whenever you update, add or remove points from the data source or whenever you want to refresh the UI.



{% highlight html %}

<ej-spark-line id="SparkLine">
</ej-spark-line>

var line = $("#SparkLine").data("ejSparkLine");
line.redraw();

{% endhighlight %}








## Events



### load


Fires before loading the sparkline.



{% highlight html %}

<ej-spark-line id="SparkLine" load="Load">
</ej-spark-line>

<script type="text/javascript">
    function Load(args) {
        // Do Something
    }
</script>

{% endhighlight %}




### loaded


Fires after loaded the sparkline.



{% highlight html %}

<ej-spark-line id="SparkLine" loaded="Loaded">
</ej-spark-line>

<script type="text/javascript">
    function Loaded(args) {
        // Do Something
    }
</script>

{% endhighlight %}




### tooltipInitialize


Fires before rendering trackball tooltip. You can use this event to customize the text displayed in trackball tooltip.



{% highlight html %}

<ej-spark-line id="SparkLine" tooltip-initialize="TooltipInitialize">
</ej-spark-line>

<script type="text/javascript">
    function TooltipInitialize(args) {
        // Do Something
    }
</script>

{% endhighlight %}





### seriesRendering





Fires before rendering a series. This event is fired for each series in Sparkline.



{% highlight html %}

<ej-spark-line id="SparkLine" series-rendering="SeriesRendering">
</ej-spark-line>

<script type="text/javascript">
    function SeriesRendering(args) {
        // Do Something
    }
</script>

{% endhighlight %}







### pointRegionMouseMove


Fires when mouse is moved over a point. 



{% highlight html %}

<ej-spark-line id="SparkLine" point-region-mouse-move="PointRegionMouseMove">
</ej-spark-line>

<script type="text/javascript">
    function PointRegionMouseMove(args) {
        // Do Something
    }
</script>

{% endhighlight %}




### pointRegionMouseClick


Fires on clicking a point in sparkline. You can use this event to handle clicks made on points.



{% highlight html %}

<ej-spark-line id="SparkLine" point-region-mouse-click="PointRegionMouseClick">
</ej-spark-line>

<script type="text/javascript">
    function PointRegionMouseClick(args) {
        // Do Something
    }
</script>

{% endhighlight %}






### sparklineMouseMove


Fires on moving mouse over the sparkline.



{% highlight html %}

<ej-spark-line id="SparkLine" spark-line-mouse-move="SparkLineMouseMove">
</ej-spark-line>

<script type="text/javascript">
    function SparkLineMouseMove(args) {
        // Do Something
    }
</script>

{% endhighlight %}






### sparklineMouseLeave


Fires on moving mouse outside the sparkline.



{% highlight html %}

<ej-spark-line id="SparkLine" spark-line-mouse-leave="SparkLineMouseLeave">
</ej-spark-line>

<script type="text/javascript">
    function SparkLineMouseLeave(args) {
        // Do Something
    }
</script>

{% endhighlight %}




