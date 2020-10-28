---
layout: post
title: Public Methods and Events
description: Public Methods and Events in Sunburst Chart.
platform: aspnet-core
control: SunburstChart
documentation: ug
---

## Methods


### redraw()

Redraws the entire sunburst. You can call this method whenever you update, add or remove points from the data source or whenever you want to refresh the UI.



{% highlight html %}

<ej-sunburstchart id="SunBurstChart">
</ej-sunburstchart>

var sunburst = $("#SunBurstChart").data("ejSunBurstChart");
sunburst.redraw();

{% endhighlight %}




### _destroy ()


destroy the sunburst



{% highlight html %}

<ej-sunburstchart id="SunBurstChart">
</ej-sunburstchart>

var sunburst = $("#SunBurstChart").data("ejSunBurstChart");
sunburst._destroy();

{% endhighlight %}




## Events

### load

Fires before loading.



{% highlight html %}

<ej-circular-gauge id="CircularGauge" draw-custom-label="DrawCustomLabel">
</ej-circular-gauge>

<script type="text/javascript">
    function DrawCustomLabel(args) {
        // Do Something
    }
</script>

{% endhighlight %}





### preRender


Fires before rendering sunburst. 


{% highlight html %}

<ej-circular-gauge id="CircularGauge" draw-custom-label="DrawCustomLabel">
</ej-circular-gauge>

<script type="text/javascript">
    function DrawCustomLabel(args) {
        // Do Something
    }
</script>

{% endhighlight %}



### loaded

Fires after rendering sunburst. 


{% highlight html %}

<ej-circular-gauge id="CircularGauge" draw-custom-label="DrawCustomLabel">
</ej-circular-gauge>

<script type="text/javascript">
    function DrawCustomLabel(args) {
        // Do Something
    }
</script>

{% endhighlight %}



### dataLabelRendering

Fires before rendering the data label 


{% highlight html %}

<ej-circular-gauge id="CircularGauge" draw-custom-label="DrawCustomLabel">
</ej-circular-gauge>

<script type="text/javascript">
    function DrawCustomLabel(args) {
        // Do Something
    }
</script>

{% endhighlight %}



### segmentRendering


Fires before rendering each segment


{% highlight html %}

<ej-circular-gauge id="CircularGauge" draw-custom-label="DrawCustomLabel">
</ej-circular-gauge>

<script type="text/javascript">
    function DrawCustomLabel(args) {
        // Do Something
    }
</script>

{% endhighlight %}



### titleRendering


Fires before rendering sunburst title. 


{% highlight html %}

<ej-circular-gauge id="CircularGauge" draw-custom-label="DrawCustomLabel">
</ej-circular-gauge>

<script type="text/javascript">
    function DrawCustomLabel(args) {
        // Do Something
    }
</script>

{% endhighlight %}



### tooltipInitialize


Fires during initialization of tooltip. 


{% highlight html %}

<ej-circular-gauge id="CircularGauge" tooltip-initialize="TooltipInitialize">
</ej-circular-gauge>

<script type="text/javascript">
    function TooltipInitialize(args) {
        // Do Something
    }
</script>

{% endhighlight %}



### pointRegionClick


Fires after clicking the point in sunburst



{% highlight html %}

<ej-circular-gauge id="CircularGauge" point-region-click="PointRegionClick">
</ej-circular-gauge>

<script type="text/javascript">
    function PointRegionClick(args) {
        // Do Something
    }
</script>

{% endhighlight %}



### pointRegionMouseMove

Fires while moving the mouse over sunburst points


{% highlight html %}

<ej-circular-gauge id="CircularGauge" point-region-mouse-move="PointRegionMouseMove">
</ej-circular-gauge>

<script type="text/javascript">
    function PointRegionMouseMove(args) {
        // Do Something
    }
</script>

{% endhighlight %}



### drillDownClick

Fires when clicking the point to perform drilldown. 


{% highlight html %}

<ej-circular-gauge id="CircularGauge" drill-down-click="DrillDownClick">
</ej-circular-gauge>

<script type="text/javascript">
    function DrillDownClick(args) {
        // Do Something
    }
</script>

{% endhighlight %}



### drillDownBack


Fires when resetting drilldown points. 


{% highlight html %}

<ej-circular-gauge id="CircularGauge" drill-down-back="DrillDownBack">
</ej-circular-gauge>

<script type="text/javascript">
    function DrillDownBack(args) {
        // Do Something
    }
</script>

{% endhighlight %}



### drillDownReset


Fires after resetting the sunburst points 


{% highlight html %}

<ej-circular-gauge id="CircularGauge" drill-down-reset="DrillDownReset">
</ej-circular-gauge>

<script type="text/javascript">
    function DrillDownReset(args) {
        // Do Something
    }
</script>

{% endhighlight %}


