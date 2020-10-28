---
layout: post
title: Public Methods and Events | BulletGraph	 |  Syncfusion
description: Public Methods and Events
platform: ejmvc
control: BulletGraph	
documentation: ug
---


## Methods



### destroy ()


To destroy the bullet graph



{% highlight html %}

<ej-bullet-graph id="BulletGraph">
</ej-bullet-graph>

var bullet = $("#BulletGraph").data("ejBulletGraph");
bullet.destroy();


{% endhighlight %}





### redraw()


To redraw the bullet graph



{% highlight html %}

<ej-bullet-graph id="BulletGraph">
</ej-bullet-graph>

var bullet = $("#BulletGraph").data("ejBulletGraph");
bullet.redraw();

{% endhighlight %}





### setComparativeMeasureSymbol()


To set the value for comparative measure in bullet graph.


{% highlight ts %}

<ej-bullet-graph id="BulletGraph">
</ej-bullet-graph>

var bullet = $("#BulletGraph").data("ejBulletGraph");
bullet.setComparativeMeasureSymbol();

{% endhighlight %}






### setFeatureMeasureBarValue()


To set the value for feature measure bar.


{% highlight ts %}

<ej-bullet-graph id="BulletGraph">
</ej-bullet-graph>

var bullet = $("#BulletGraph").data("ejBulletGraph");
bullet.setFeatureMeasureBarValue();

{% endhighlight %}





## Events



### drawCaption


Fires on rendering the caption of bullet graph.


{% highlight html %}

<ej-bullet-graph id="Bullets" draw-caption="DrawCaption">
</ej-bullet-graph>

<script type="text/javascript">
    function DrawCaption(args) {
        // Do Something
    }
</script>

{% endhighlight %}





### drawCategory


Fires on rendering the category.


{% highlight html %}

<ej-bullet-graph id="Bullets" draw-category="DrawCategory">
</ej-bullet-graph>

<script type="text/javascript">
    function DrawCategory(args) {
        // Do Something
    }
</script>

{% endhighlight %}









### drawComparativeMeasureSymbol

Fires on rendering the comparative measure symbol.


{% highlight html %}

<ej-bullet-graph id="Bullets" draw-comparative-measure-symbol="DrawComparativeMeasureSymbol">
</ej-bullet-graph>

<script type="text/javascript">
    function DrawComparativeMeasureSymbol(args) {
        // Do Something
    }
</script>

{% endhighlight %}






### drawFeatureMeasureBar

Fires on rendering the feature measure bar.

{% highlight html %}

<ej-bullet-graph id="Bullets" draw-feature-measure-bar="DrawFeatureMeasureBar">
</ej-bullet-graph>

<script type="text/javascript">
    function DrawFeatureMeasureBar(args) {
        // Do Something
    }
</script>

{% endhighlight %}







### drawIndicator


Fires on rendering the indicator of bullet graph.



{% highlight html %}

<ej-bullet-graph id="Bullets" draw-indicator="DrawIndicator">
</ej-bullet-graph>

<script type="text/javascript">
    function DrawIndicator(args) {
        // Do Something
    }
</script>

{% endhighlight %}







### drawLabels

Fires on rendering the labels.



{% highlight html %}

<ej-bullet-graph id="Bullets" draw-labels="DrawLabels">
</ej-bullet-graph>

<script type="text/javascript">
    function DrawLabels(args) {
        // Do Something
    }
</script>

{% endhighlight %}







### drawQualitativeRanges


Fires on rendering the qualitative ranges.



{% highlight html %}

<ej-bullet-graph id="Bullets" draw-quality-ranges="DrawQualityRanges">
</ej-bullet-graph>

<script type="text/javascript">
    function DrawQualityRanges(args) {
        // Do Something
    }
</script>

{% endhighlight %}







### load


Fires on loading bullet graph.




{% highlight html %}

<ej-bullet-graph id="Bullets" load="Load">
</ej-bullet-graph>

<script type="text/javascript">
    function Load(args) {
        // Do Something
    }
</script>

{% endhighlight %}









