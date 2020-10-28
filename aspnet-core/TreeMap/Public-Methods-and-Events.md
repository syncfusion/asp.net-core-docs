---
layout: post
title: Public Methods and Events for ASP.NET Core
description: Public Methods and Events in treeMap control
platform: aspnet-core
control: TreeMap
documentation: ug
---

## Methods

### refresh()


Method to reload treemap with updated values.



{% highlight html %}

<ej-tree-map id="TreeMap">
</ej-tree-map>

var tree = $("#TreeMap").data("ejTreeMap");
tree.refresh();

 
{% endhighlight %}



## Events

### treeMapItemSelected


Triggers on treemap item selected.


{% highlight html %}
 
<ej-tree-map id="TreeMap" tree-map-item-selected="TreeMapItemSelected">
</ej-tree-map>

<script type="text/javascript">
    function TreeMapItemSelected(args) {
        // Do Something
    }
</script>

{% endhighlight %}

### drillStarted


Triggers when drilldown is started



{% highlight html %}
 
<ej-tree-map id="TreeMap" drill-started="DrillStarted">
</ej-tree-map>

<script type="text/javascript">
    function DrillStarted(args) {
        // Do Something
    }
</script>

{% endhighlight %}  

### drillDownItemSelected


Triggers on treemap  drilldown  item  selected.




{% highlight html %}
 
<ej-tree-map id="TreeMap" drill-down-item-selected="DrillDownItemSelected">
</ej-tree-map>

<script type="text/javascript">
    function DrillDownItemSelected(args) {
        // Do Something
    }
</script>

{% endhighlight %}

### headerTemplateRendering


Triggers before rendering the treemap drilldown header template



{% highlight html %}
 
<ej-tree-map id="TreeMap" header-template-rendering="HeaderTemplateRendering">
</ej-tree-map>

<script type="text/javascript">
    function HeaderTemplateRendering(args) {
        // Do Something
    }
</script>

{% endhighlight %}


### refreshed


Triggers after refreshing the treemap items.


 
{% highlight html %}
 
<ej-tree-map id="TreeMap" refreshed="Refreshed">
</ej-tree-map>

<script type="text/javascript">
    function Refreshed(args) {
        // Do Something
    }
</script>

{% endhighlight %}


### treeMapGroupSelected


Triggers when the group selection is performed on treemap items.


{% highlight html %}
 
<ej-tree-map id="TreeMap" tree-map-group-selected="TreeMapGroupSelected">
</ej-tree-map>

<script type="text/javascript">
    function TreeMapGroupSelected(args) {
        // Do Something
    }
</script>

{% endhighlight %}

