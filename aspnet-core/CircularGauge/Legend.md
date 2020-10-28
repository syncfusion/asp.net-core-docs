---
layout: post
title: Legend | CircularGauge | ASP.NET Core| Syncfusion
description:  legend
platform: aspnet-core
control: CircularGauge
documentation: ug
---

# Legend

The legend contains the list of the ranges that appear in the circular gauge  

## Legend Visibility

By default, the legend  the legend will not be displayed in the circular gauge. You can enable or disable it by using the **visible** property of the legend.

{% highlight html %}

<ej-circular-gauge id="circularGauge1">
    <e-legend visible="true"></e-legend>
</ej-circular-gauge>

{% endhighlight %}

![](Legend_images/Legend_img1.png)


[Click](http://ng2jq.syncfusion.com/#/circulargauge/legend) here to view the online demo sample for legend .

### Legend Text

The text displayed in the legend can be customized by using the `legendText` property present in the `ranges` of the circular gauge. When the legendText is not specified in the ranges, then the legend item for that particular range will not displayed. By default the legendText value is null . 


{% highlight html %}

<ej-circular-gauge id="circularGauge1">
    <e-scales>
    <e-scale >
    <e-ranges>
    <e-range legend-text="Light air"></e-range>
    </e-ranges>
    </e-scale>
    </e-scales>    
</ej-circular-gauge>

{% endhighlight %}


### Legend Fill and Opacity

You can change the opacity and fill color of legend text using `Opacity` and `Fill` property of legend. 

{% highlight html %}

<ej-circular-gauge id="circularGauge1">
    <e-legend visible="true" fill="blue" opacity="0.5"></e-legend>
</ej-circular-gauge>


{% endhighlight %}



## Position and Align the Legend

By using the `position` property, you can position the legend at *left*, *right*, *top* or *bottom* of the CircularGauge. The legend is positioned at the **bottom** of the circular gauge, by default.

{% highlight html %}

<ej-circular-gauge id="circularGauge1">
    <e-legend visible="true" position="@CircularLegendPosition.Top"></e-legend>
</ej-circular-gauge>

{% endhighlight  %}

![](Legend_images/Legend_img2.png)

### Legend Alignment

You can align the legend to the *center*, *far* or *near* based on its position by using the `alignment` property.

{% highlight html %}

<ej-circular-gauge id="circularGauge1">
     <e-legend visible="true" position="@CircularLegendAlignment.Far"></e-legend>
</ej-circular-gauge>

{% endhighlight %}

![](Legend_images/Legend_img3.png)

## Customization

### Legend shape

To change the legend item, shape, you have to specify the desired shape in the `shape` property of the legend. By default the legend shape is **circle**.It also supports rectangle,diamond,triangle,slider,line,pentagon,trapezoid and wedge shapes.

{% highlight html %}

<ej-circular-gauge id="circularGauge1">
    <e-legend visible="true" shape="@CircularLegendShape.Slider"></e-legend>
</ej-circular-gauge>

{% endhighlight %}

![](Legend_images/Legend_img4.png)


### Legend Item Size and Border

You can change the size of the legend items by using the `width` and `height` properties in the `itemStyle`. To change the legend item border, use `border` property of the legend itemStyle.

{% highlight html %}

<ej-circular-gauge id="circularGauge1">
    <e-legend>
        <e-item-style width="13" height="13" >
            <e-border color="blue" width="2"></e-border>
        </e-item-style>
    </e-legend>
</ej-circular-gauge>

{% endhighlight %}

![](Legend_images/Legend_img5.png)

### Legend size

You can change the default legend size by using the `size` property of the legend.  

{% highlight html %}

<ej-circular-gauge id="circularGauge1">
    <e-legend>
        <e-size width="350" height="100"></e-size>
    </e-legend>
</ej-circular-gauge>

{% endhighlight %}

![](Legend_images/Legend_img6.png)


### Legend Item Padding

You can control the spacing between the legend items by using the `item-padding` option of the legend.  The default value is 20. 

{% highlight html %}

<ej-circular-gauge id="circularGauge1">
    <e-legend item-padding="30">        
    </e-legend>
</ej-circular-gauge>


{% endhighlight %}

![](Legend_images/Legend_img7.png)

### Legend border

You can customize the legend border by using the `border` option in the legend. 

{% highlight html %}

<ej-circular-gauge id="circularGauge1">
    <e-legend>       
        <e-border color="blue" width="2"></e-border>        
    </e-legend>
</ej-circular-gauge>


{% endhighlight %}

![](Legend_images/Legend_img8.png)

### Font of the legend text

The font of the legend item text can be customized by using the `font` property in legend.

{% highlight html %}

<ej-circular-gauge id="circularGauge1">
    <e-legend>       
        <e-font font-family="Arial" font-style="bold" size="18px"></e-border>        
    </e-legend>
</ej-circular-gauge>

{% endhighlight %}


![](Legend_images/Legend_img9.png)

## Events

### Legend Item Render

`legend-item-render` event triggers before rendering the legend items. This event is triggered for each legend item in Circular gauge. You can use this event to customize legend item shape or add custom text to legend item.

{% highlight html %}

<ej-circular-gauge id="circularGauge1" legend-item-render="onLegendItemRender($event)"> 
</ej-circular-gauge>
 
<script>
function onLegendItemRender(sender) {
//Get legend item details on legend item click.
var legendItem = sender.data;
}
</script>

{% endhighlight %}

### Legend Item Click

You can get the legend item details such as *RangeIndex*, *bounds*, *shape* and *series* by subscribing the `legend-item-click` event on the circular gauge. When the legend item is clicked, it triggers the event and returns the legend information. 

{% highlight html %}

<ej-circular-gauge id="circularGauge1" legend-item-click="onLegendClicked($event)"> 
</ej-circular-gauge>
 
  <script>
     function onLegendClicked(sender) {
        //Get legend item details on legend item click.
        var legendItem = sender.data;
     }
 </script>

{% endhighlight %}


