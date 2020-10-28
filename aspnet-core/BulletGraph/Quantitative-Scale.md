---
layout: post
title: Quantitative Scale | BulletGraph	 |  Syncfusion
description: quantitative scale
platform: aspnet-core
control: BulletGraph	
documentation: ug
---

# Quantitative Scale

The Quantitative Scale appearance is customized using `e-quantitative-scale-settings` property. It has properties to customize labels, major ticks, minor ticks, comparative measure and performance measure of the bullet graph

## Range for Quantitative Scale

Quantitative Scale range is set using the properties `minimum`, `maximum` and `interval` of `e-quantitative-scale-settings` property. Minimum specifies the start range of the scale, Maximum specifies the end range of scale and interval specifies the number of intervals between start and end range. Default values of Minimum, Maximum and Interval are 0, 10 and 1 respectively. The number of minor ticks (ticks between intervals) are specified using MinorTicksPerInterval property.


{% highlight html %}
<ej-bullet-graph id="Bullets" >
<e-quantitative-scale-settings  maximum="10" minimum="0" >          
</e-quantitative-scale-settings>
</ej-bullet-graph>
{% endhighlight %}

The following screenshot displays a Bullet Graph with start range 0, end range 10 and interval 1 with 4 minor ticks per interval

![](Quantitative-Scale_images/Quantitative-Scale_img1.png)

Bullet Graph quantitative scale with customized range
{:.caption}

## Quantitative scale location

Bullet Graph does not position quantitative scale automatically based on its size or space required for caption text, etc. By default Quantitative scale is positioned at 10 pixels from left and 10 pixels from top. Quantitative scale location is customized as per the requirement using the `e-location` property available in `e-quantitative-scale-settings`.


{% highlight html %}

<ej-bullet-graph id="Bullets" >
<e-quantitative-scale-settings  >
<e-location x="20" y="20"></e-location>        
</e-quantitative-scale-settings>
</ej-bullet-graph>


{% endhighlight %}
The following screenshot displays Bullet Graph with Quantitative scale at 20 pixels from left and 20 pixels from top

![](Quantitative-Scale_images/Quantitative-Scale_img2.png)

Bullet Graph quantitative scale in a specified location
{:.caption}

## Major ticks

Color, size and width of Major tick lines are customized using `e-major-tick-settings` property in QuantitativeScaleSettings. Default value of Size and Width properties are 13 and 2 respectively. Ticks are drawn in black color by default. The property Size represents the height of tick lines and Width represents the width of tick lines and ticks color are customized using Stroke property.


{% highlight html %}

<ej-bullet-graph id="Bullets" >
<e-quantitative-scale-settings  >
<e-major-tick-settings size="15" width="3" color="Gray"></e-major-tick-settings>                </e-quantitative-scale-settings>
</ej-bullet-graph>



{% endhighlight %}

The following screenshot displays Major ticks in gray color with a width of 3 pixels and height 15 pixels

![](Quantitative-Scale_images/Quantitative-Scale_img3.png)

Bullet Graph quantitative scale with customized major ticks
{:.caption}

## Minor ticks

Minor ticks can also be customized similar to major ticks. The properties Stroke, Width and Size of `e-minor-tick-settings` are used to customize Minor ticks in quantitative scale. Stroke specifies the color of ticks, Width specifies the width of ticks and Size specifies the height of the ticks. 
{% highlight html %}

<ej-bullet-graph id="Bullets" >
<e-quantitative-scale-settings  >
<e-minor-tick-settings size="7" width="3" color="Gray"></e-minor-tick-settings>                </e-quantitative-scale-settings>
</ej-bullet-graph>

{% endhighlight %}

The following screenshot displays Bullet Graph with customized Minor ticks in quantitative scale

![](Quantitative-Scale_images/Quantitative-Scale_img4.png)

Bullet Graph quantitative scale with customized minor ticks
{:.caption}

## Tick position

Ticks are positioned below, above or inside the quantitative scale. By default ticks are positioned below the quantitative scale. The `tick-position` property is used to customize the position of ticks in quantitative scale. Ticks can be placed inside the quantitative scale by setting TickPosition to Cross. 
{% highlight html %}

<ej-bullet-graph id="Bullets" >
<e-quantitative-scale-settings tick-position="@TickPosition.Above" >
</e-quantitative-scale-settings>
</ej-bullet-graph>

{% endhighlight %}

The following screenshot displays Bullet Graph with ticks positioned above quantitative scale

![](Quantitative-Scale_images/Quantitative-Scale_img5.png)

Bullet Graph quantitative scale with ticks positioned above
{:.caption}

## Tick Placement

Quantitative scale ticks can be placed either inside or outside the scale using “tick-placement” property. By default ticks are placed outside the scale.


{% highlight html %}

<ej-bullet-graph id="Bullets" >
<e-quantitative-scale-settings tick-placement="@BulletTickPlacement.Inside">
<e-location x="108" y="10"></e-location>
<e-label-settings offset="0" size="10"></e-label-settings>
<e-feature-measures>
<e-feature-measure comparative-measure="6" value="8"></e-feature-measure>
</e-feature-measures>        
</e-quantitative-scale-settings>
<e-caption-settings text="Revenue YTD">
<e-location x="17" y="28"></e-location>
<e-sub-title text="$ in thousands">
<e-location x="10" y="42"></e-location>
</e-sub-title>
</e-caption-settings>
</ej-bullet-graph>


{% endhighlight %}
The following screenshot displays Bullet Graph ticks inside Quantitative Scale

![](Quantitative-Scale_images/Quantitative-Scale_img6.png)

Bullet Graph with ticks inside quantitative scale
{:.caption}

## Quantitative scale labels

Quantitative scale labels are customized with prefix, suffix, font, color and size using `e-label-settings` property. By default, label text is displayed in black color with 12 pixel ‘Segoe UI’ font and there is a padding of 20 pixels space between quantitative scale and labels.


{% highlight html %}

<ej-bullet-graph id="Bullets" >
<e-quantitative-scale-settings>
<e-label-settings stroke="Blue"  label-suffix="K" label-prefix="$" offset="15" size="12">
<e-bullet-font  font-style="bold" font-weight="regular" opacity="0.8"
font-family="Segoe UI">
</e-bullet-font> 
</e-label-settings>
</e-quantitative-scale-settings>
</ej-bullet-graph>



{% endhighlight %}

The following screenshot displays Bullet Graph labels in blue color

![](Quantitative-Scale_images/Quantitative-Scale_img7.png)

Bullet Graph quantitative scale with customized labels
{:.caption}

## Label Placement

Quantitative scale labels can be placed either inside or outside the scale using “label-placement” property. By default labels are placed 15 pixels outside the scale. 
{% highlight cshtml %}

<ej-bullet-graph id="Bullets" >
<e-quantitative-scale-settings label-placement="@BulletLabelPlacement.Inside">
<e-location x="108" y="10"></e-location>
<e-label-settings offset="0" size="10"></e-label-settings>
<e-feature-measures>
<e-feature-measure comparative-measure="6" value="8"></e-feature-measure>
</e-feature-measures>        
</e-quantitative-scale-settings>
<e-caption-settings text="Revenue YTD">
<e-location x="17" y="28"></e-location>
<e-sub-title text="$ in thousands">
<e-location x="10" y="42"></e-location>
</e-sub-title>
</e-caption-settings>
</ej-bullet-graph>


{% endhighlight %}

The following screenshot displays Bullet Graph labels inside Quantitative Scale

![](Quantitative-Scale_images/Quantitative-Scale_img8.png)

Bullet Graph with labels inside quantitative scale
{:.caption}

## Performance measure bar

Performance measure bar is customized using `e-featured-measure-settings` in `e-quantitative-scale-settings` property. Color of the bar is customized using Stroke property and width using Width property. By default bar is drawn in black color with 6 pixels of width.

{% highlight cshtml %}

<ej-bullet-graph id="Bullets" value="5">
<e-quantitative-scale-settings>
<e-featured-measure-settings width="4" stroke="Blue" >
</e-featured-measure-settings>
</e-quantitative-scale-settings>
</ej-bullet-graph>



{% endhighlight %}
The following screenshot displays Bullet Graph with customized Performance measure bar.

![](Quantitative-Scale_images/Quantitative-Scale_img9.png)

Bullet Graph quantitative scale with customized performance measure bar
{:.caption}

## Comparative measure symbol

Comparative symbol color and width are customized using `e-comparative-measure-settings` through `e-quantitative-scale-settings` property. Color of the symbol is customized using `stroke` property and width using `width` property. By default Comparative measure symbol is displayed in black color with a width of 5 pixels. 

{% highlight cshtml %}

<ej-bullet-graph id="Bullets" comparative-measure-value="5">
<e-quantitative-scale-settings>
<e-comparative-measure-settings stroke="Blue" width="4">
</e-comparative-measure-settings>
</e-quantitative-scale-settings>
</ej-bullet-graph>


{% endhighlight %}

The following screenshot displays Bullet Graph with customized Comparative measure value.

![](Quantitative-Scale_images/Quantitative-Scale_img10.png)

Bullet Graph with customized comparative symbol
{:.caption}

## Multiple performance measures comparison

Bullet Graph supports comparing more than one performance at a time, given that all the comparisons are related using FeatureMeasure in `e-quantitative-scale-settings` property. 

{% highlight cshtml %}

<ej-bullet-graph id="Bullets" height="120"  qualitative-range-size="60">
<e-quantitative-scale-settings>
<e-feature-measures>
<e-feature-measure comparative-measure="3" value="6" category="2010">
</e-feature-measure>
<e-feature-measure comparative-measure="6" value="9" category="2011">
</e-feature-measure>
<e-feature-measure comparative-measure="5" value="5" category="2012">
</e-feature-measure>
</e-feature-measures>
<e-location x="50" y="10"></e-location>
</e-quantitative-scale-settings>
<ej-bullet-graph>

{% endhighlight %}
The following screenshot displays Bullet Graph that compares 3 related performance measures.

![](Quantitative-Scale_images/Quantitative-Scale_img11.png)

Bullet Graph with multiple performance measures
{:.caption}