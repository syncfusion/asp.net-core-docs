---
layout: post
title: Public Methods and Events | DigitalGauge | Syncfusion
description: Public Methods and Events
platform: aspnet-core
control: DigitalGauge
documentation: ug
---

## Methods





### destroy()



To destroy the digital gauge


{% highlight html %}

<ej-digital-gauge id="DigitalGauge">
</ej-digital-gauge>

var gauge = $("#DigitalGauge").data("ejDigitalGauge");
gauge.destroy();
     
{% endhighlight %}







### exportImage(fileName, fileType)


To export Digital Gauge as Image



{% highlight html %}

<ej-digital-gauge id="DigitalGauge">
</ej-digital-gauge>

var gauge = $("#DigitalGauge").data("ejDigitalGauge");
gauge.exportImage();

{% endhighlight %}






### getPosition(itemIndex)


Gets the location of an item that is displayed on the gauge.



{% highlight html %}

<ej-digital-gauge id="DigitalGauge">
</ej-digital-gauge>

var gauge = $("#DigitalGauge").data("ejDigitalGauge");
gauge.getPosition();

{% endhighlight %}






### getValue(itemIndex)

ClientSideMethod getValue Gets the value of an item that is displayed on the gauge


{% highlight html %}

<ej-digital-gauge id="DigitalGauge">
</ej-digital-gauge>

var gauge = $("#DigitalGauge").data("ejDigitalGauge");
gauge.getValue();

{% endhighlight %}







### refresh()


Refresh the digital gauge widget



{% highlight html %}

<ej-digital-gauge id="DigitalGauge">
</ej-digital-gauge>

var gauge = $("#DigitalGauge").data("ejDigitalGauge");
gauge.refresh();

{% endhighlight %}





### setPosition(itemIndex, value)


ClientSideMethod Set Position Sets the location of an item to be displayed in the gauge


{% highlight html %}

<ej-digital-gauge id="DigitalGauge">
</ej-digital-gauge>

var gauge = $("#DigitalGauge").data("ejDigitalGauge");
gauge.setPosition();

{% endhighlight %}





### setValue(itemIndex, value)

ClientSideMethod SetValue Sets the value of an item to be displayed in the gauge.


{% highlight html %}

<ej-digital-gauge id="DigitalGauge">
</ej-digital-gauge>

var gauge = $("#DigitalGauge").data("ejDigitalGauge");
gauge.setValue();

{% endhighlight %}






## Events





### init

Triggers when the gauge is initialized.

{% highlight html %}

<ej-digital-gauge id="DigitalGauge" init="InIt">
</ej-digital-gauge>

<script type="text/javascript">
    function InIt(args) {
        // Do Something
    }
</script>

{% endhighlight %}







### itemRendering

Triggers when the gauge item rendering.


{% highlight html %}

<ej-digital-gauge id="DigitalGauge" item-rendering="ItemRendering">
</ej-digital-gauge>

<script type="text/javascript">
    function ItemRendering(args) {
        // Do Something
    }
</script>

{% endhighlight %}






### load

Triggers when the gauge is start to load.


{% highlight html %} 

<ej-digital-gauge id="DigitalGauge" load="Load">
</ej-digital-gauge>

<script type="text/javascript">
    function Load(args) {
        // Do Something
    }
</script>
      
{% endhighlight %}




### renderComplete

Triggers when the gauge render is completed.


{% highlight html %}

<ej-digital-gauge id="DigitalGauge" render-complete="RenderComplete">
</ej-digital-gauge>

<script type="text/javascript">
    function RenderComplete(args) {
        // Do Something
    }
</script>

{% endhighlight %}






