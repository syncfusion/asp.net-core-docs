---
layout: post
title: Public Methods and Events
description: Public Methods and Events
platform: aspnet-core
control: RangeNavigator
documentation: ug
---

## Methods








### _destroy ()









destroy the range navigator widget



{% highlight html %}

<ej-range-navigator id="RangeNavigator">
</ej-range-navigator>

var gauge = $("#RangeNavigator").data("ejRangeNavigator");
gauge._destroy();

{% endhighlight %}








## Events








### load









Fires on load of range navigator.


{% highlight html %}

<ej-range-navigator id="RangeNavigator" load="Load">
</ej-range-navigator>

<script type="text/javascript">
    function Load(args) {
        // Do Something
    }
</script>

{% endhighlight %}








### loaded









Fires after range navigator is loaded.


{% highlight html %}

<ej-range-navigator id="RangeNavigator" loaded="Loaded">
</ej-range-navigator>

<script type="text/javascript">
    function Loaded(args) {
        // Do Something
    }
</script>

{% endhighlight %}








### rangeChanged









Fires on changing the range of range navigator.


{% highlight html %}

<ej-range-navigator id="RangeNavigator" range-changed="RangeChanged">
</ej-range-navigator>

<script type="text/javascript">
    function RangeChanged(args) {
        // Do Something
    }
</script>

{% endhighlight %}






### scrollChanged



Fires on changing the scrollbar position of range navigator.




{% highlight html %}

<ej-range-navigator id="RangeNavigator" scroll-changed="ScrollChanged">
</ej-range-navigator>

<script type="text/javascript">
    function ScrollChanged(args) {
        // Do Something
    }
</script>

{% endhighlight %}




### scrollStart



Fires on when starting to change the scrollbar position of range navigator.



{% highlight html %}

<ej-range-navigator id="RangeNavigator" scroll-start="ScrollStart">
</ej-range-navigator>

<script type="text/javascript">
    function ScrollStart(args) {
        // Do Something
    }
</script>

{% endhighlight %}


### selectedRangeStart




Fires on when starting to change the slider position of range navigator.






{% highlight html %}

<ej-range-navigator id="RangeNavigator" selected-range-start="SelectedRangeStart">
</ej-range-navigator>

<script type="text/javascript">
    function SelectedRangeStart(args) {
        // Do Something
    }
</script>

{% endhighlight %}

### selectedRangeEnd 




Fires when the selection  ends in the range navigator





{% highlight html %}

<ej-range-navigator id="RangeNavigator" selected-range-end="SelectedRangeEnd">
</ej-range-navigator>

<script type="text/javascript">
    function SelectedRangeEnd(args) {
        // Do Something
    }
</script>

{% endhighlight %}



### scrollEnd



Fires on changes ending the scrollbar position of range navigator.





{% highlight html %}

<ej-range-navigator id="RangeNavigator" scroll-end="ScrollEnd">
</ej-range-navigator>

<script type="text/javascript">
    function ScrollEnd(args) {
        // Do Something
    }
</script>

{% endhighlight %}


