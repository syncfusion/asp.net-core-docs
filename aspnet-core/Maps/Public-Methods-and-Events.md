---
layout: post
title: Public Methods and Events
description: Public Methods and Events in Map control
platform: aspnet-core
control: Maps
documentation: ug
---


## Methods

### navigateTo(latitude, longitude, level)


Method for navigating to specific shape based on latitude, longitude and zoom level.



{% highlight html %}

<ej-map id="Map">
</ej-map>

var map = $("#Map").data("ejMap");
map.navigateTo();

{% endhighlight %}


### pan(direction)


Method to perform map panning


{% highlight html %}

<ej-map id="Map">
</ej-map>

var map = $("#Map").data("ejMap");
map.pan();


{% endhighlight %}


### refresh()


Method to reload the map.




{% highlight html %}

<ej-map id="Map">
</ej-map>

var map = $("#Map").data("ejMap");
map.refresh();


{% endhighlight %}


### refreshLayers()


Method to reload the shapeLayers with updated values



{% highlight html %}

<ej-map id="Map">
</ej-map>

var map = $("#Map").data("ejMap");
map.refreshLayers();


{% endhighlight %}


### refreshNavigationControl(navigation)


Method to reload the navigation control with updated values.



{% highlight html %}

export class AppComponent {

<ej-map id="Map">
</ej-map>

var map = $("#Map").data("ejMap");
map.refreshNavigationControl();


{% endhighlight %}


### zoom(level, isAnimate)


Method to perform map zooming.



{% highlight html %}

<ej-map id="Map">
</ej-map>

var map = $("#Map").data("ejMap");
map.zoom();


{% endhighlight %}



## Events

### markerSelected


Triggered on selecting the map markers.


{% highlight html %}

<ej-map id="CircularGauge" marker-selected="MarkerSelected">
</ej-map>

<script type="text/javascript">
    function MarkerSelected(args) {
        // Do Something
    }
</script>

{% endhighlight %}



### mouseLeave


Triggers while leaving the hovered map shape


{% highlight html %}

<ej-map id="CircularGauge" mouse-leave="MouseLeave">
</ej-map>

<script type="text/javascript">
    function MouseLeave(args) {
        // Do Something
    }
</script>

{% endhighlight %}



### mouseover


Triggers while hovering the map shape.


{% highlight html %}

<ej-map id="CircularGauge" mouse-over="MouseOver">
</ej-map>

<script type="text/javascript">
    function MouseOver(args) {
        // Do Something
    }
</script>

{% endhighlight %}



### onRenderComplete


Triggers once map render completed.


{% highlight html %}

<ej-map id="CircularGauge" on-render-complete="OnRenderComplete">
</ej-map>

<script type="text/javascript">
    function OnRenderComplete(args) {
        // Do Something
    }
</script>

{% endhighlight %}



### panned


Triggers when map panning ends.


{% highlight html %}

<ej-map id="CircularGauge" panned="Panned">
</ej-map>

<script type="text/javascript">
    function Panned(args) {
        // Do Something
    }
</script>

{% endhighlight %}



### shapeSelected


Triggered on selecting the map shapes.


{% highlight html %}

<ej-map id="CircularGauge" shape-selected="ShapeSelected">
</ej-map>

<script type="text/javascript">
    function ShapeSelected(args) {
        // Do Something
    }
</script>

{% endhighlight %}



### zoomedIn


Triggered when map is zoomed-in.


{% highlight html %}

<ej-map id="CircularGauge" zoomed-in="ZoomedIn">
</ej-map>

<script type="text/javascript">
    function ZoomedIn(args) {
        // Do Something
    }
</script>

{% endhighlight %}



### zoomedOut


Triggers when map is zoomed out.



{% highlight html %}

<ej-map id="CircularGauge" zoomed-out="ZoomedOut">
</ej-map>

<script type="text/javascript">
    function ZoomedOut(args) {
        // Do Something
    }
</script>

{% endhighlight %}

<a class="" href="http://www.syncfusion.com/copyright" target="_blank">Copyright &copy; 2001 - 2015 Syncfusion Inc. All Rights Reserved</a>

