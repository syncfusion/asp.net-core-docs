---
layout: post
title: Indicators | lineargauge | Syncfusion
description: indicators
platform: aspnet-core
control: lineargauge
documentation: ug
---

# Indicators

Indicators simply indicates the current status of the pointer. Indicators are in several formats such as in shape format, textual format and image format.

## Setting Dimension

* You can enable indicators by setting showIndicators to ‘true’ in scale collection. The height and width property for the indicators are used to specify the area allocated to the indicator for the width and height respectively. 
* You can use the position collection to position the indicators along X and Y axis. X specifies horizontal position in indicators whereas Y specifies vertical position in indicators. Indicators are of several types such as, dimensions like circle, rectangle, rounded rectangle, text and image. By using the type property it can be applied. For image type imageUrl property is used.



{% highlight cshtml %}

<ej-linear-gauge id="LinearGauge" enable-animation="false" value="78" >
<e-frame
 background-image-url="../images/gauge/Gauge_linear_light.png" ></e-frame>
<e-linear-scale-collections>
<e-linear-scales width="0" maximum="300" major-interval-value="30" minor-interval-value="5" 
background-color="transparent" show-bar-pointers="false" length="310">
<e-linear-position x="51" y="50"></e-linear-position>
<e-border color="transparent" width="1"></e-border>
<e-linear-tick-collections>
<e-linear-ticks type="@TickType.MajorInterval"  width="2" height="14">
<e-distance-from-scale x="7" y="0"></e-distance-from-scale>
</e-linear-ticks>
<e-linear-ticks type="@TickType.MinorInterval"  width="1" >
<e-distance-from-scale x="7" y="0"></e-distance-from-scale>
</e-linear-ticks>
</e-linear-tick-collections>
<e-linear-indicator-collections>
<e-linear-indicators type="@IndicatorType.Circle" height="10" width="10" >
<e-linear-position x="55" y="100"></e-linear-position>
</e-linear-indicators>
</e-linear-indicator-collections>
</e-linear-scales>
</e-linear-scale-collections>
</ej-linear-gauge> 

{% endhighlight %}



Execute the above code to render the following output.

![](Indicators_images/Indicators_img1.png)



## State Ranges

State ranges are used to specify the indicator behavior in the certain region. startValue and endValue are used to set the range bound for the pointer. Whenever the pointer crosses the specified region, the indicator attributes are applied for the ranges.



{% highlight cshtml %}

<ej-linear-gauge id="LinearGauge" enable-animation="false" value="78" >
<e-frame
 background-image-url="../images/gauge/Gauge_linear_light.png" ></e-frame>
<e-linear-scale-collections>
<e-linear-scales width="0" maximum="300" major-interval-value="30" minor-interval-value="5" 
background-color="transparent" show-bar-pointers="false" length="310">
<e-linear-position x="51" y="50"></e-linear-position>
<e-border color="transparent" width="1"></e-border>
<e-linear-tick-collections>
<e-linear-ticks type="@TickType.MajorInterval"  width="2" height="14">
<e-distance-from-scale x="7" y="0"></e-distance-from-scale>
</e-linear-ticks>
<e-linear-ticks type="@TickType.MinorInterval"  width="1" >
<e-distance-from-scale x="7" y="0"></e-distance-from-scale>
</e-linear-ticks>
<e-linear-tick-collections>
<e-linear-indicator-collections>
<e-linear-indicators type="@IndicatorType.Circle" height="10" width="10">
<e-linear-position x="55" y="10"></e-linear-position>
<e-state-range-collections>
<e-state-ranges state-range-background-color="#02A258" state-range-start-value="0" 
state-range-end-value="200" state-range-border-color="#02A258"></e-state-ranges>
<e-state-ranges state-range-background-color="grey" state-range-start-value="200"
state-range-end-value="300" state-range-border-color="Grey"></e-state-ranges>
</e-state-range-collections>
</e-linear-indicators>
</e-linear-indicator-collections>
</e-linear-scales>
</e-linear-scale-collections>
</ej-linear-gauge> 


{% endhighlight %}

Execute the above code to render the following output.

![](Indicators_images/Indicators_img2.png)



Color and Appearance

The backgroundColor and borderColor sets the appearance behavior for the indicators. You can apply this only if it lies within the state ranges. Otherwise default behavior will be applied.


{% highlight cshtml %}

<ej-linear-gauge id="LinearGauge" enable-animation="false" value="78" >
<e-frame
 background-image-url="../images/gauge/Gauge_linear_light.png" ></e-frame>
<e-linear-scale-collections>
<e-linear-scales width="0" maximum="300" major-interval-value="30" minor-interval-value="5" 
background-color="transparent" show-bar-pointers="false" length="310">
<e-linear-position x="51" y="50"></e-linear-position>
<e-border color="transparent" width="1"></e-border>
<e-linear-tick-collections>
<e-linear-ticks type="@TickType.MajorInterval"  width="2" height="14">
<e-distance-from-scale x="7" y="0"></e-distance-from-scale>
</e-linear-ticks>
<e-linear-ticks type="@TickType.MinorInterval"  width="1" >
<e-distance-from-scale x="7" y="0"></e-distance-from-scale>
</e-linear-ticks>
<e-linear-tick-collections>
<e-linear-indicator-collections>
<e-linear-indicators type="@IndicatorType.Circle" height="10" width="10">
<e-linear-position x="55" y="10"></e-linear-position>
<e-state-range-collections>
<e-state-ranges state-range-background-color="#91B64E" state-range-start-value="0" 
state-range-end-value="200" state-range-border-color="#91B64E"></e-state-ranges>
</e-state-range-collections>
</e-linear-indicators>
</e-linear-indicator-collections>
</e-linear-scales>
</e-linear-scale-collections>
</ej-linear-gauge> 

{% endhighlight %}

Execute the above code to render the following output.

![](Indicators_images/Indicators_img3.png)



## Font options

The basic font options available for the textual type indicators in the Linear Gauge such as Size, font style and font family are achieved by the properties size, fontStyle and fontFamily.



{% highlight cshtml %}

<ej-linear-gauge id="LinearGauge" enable-animation="false" value="78" >
<e-frame
 background-image-url="../images/gauge/Gauge_linear_light.png" ></e-frame>
<e-linear-scale-collections>
<e-linear-scales width="0" maximum="300" major-interval-value="30" minor-interval-value="5" 
background-color="transparent" show-bar-pointers="false" length="310" show-ranges="true">
<e-linear-position x="51" y="50"></e-linear-position>
<e-border color="transparent" width="1"></e-border>
<e-linear-tick-collections>
<e-linear-ticks type="@TickType.MajorInterval"  width="2" height="14">
<e-distance-from-scale x="7" y="0"></e-distance-from-scale>
</e-linear-ticks>
<e-linear-ticks type="@TickType.MinorInterval"  width="1" >
<e-distance-from-scale x="7" y="0"></e-distance-from-scale>
</e-linear-ticks>
<e-linear-tick-collections>
<e-linear-indicator-collections>
<e-linear-indicators type="@IndicatorType.text"  height="10" width="10">
<e-text-location x="55" y="100"></e-text-location>
<e-font size="15px" font-family="Arial" font-style="Bold"></e-font>
<e-state-range-collections>
<e-state-ranges  state-range-start-value="0" state-range-text="Safe"
state-range-end-value="200" state-range-text-color="#94C361"></e-state-ranges>
<e-state-ranges  state-range-start-value="200" state-range-text="Caution"
state-range-end-value="250" state-range-text-color="#F9CF67"></e-state-ranges>
<e-state-ranges  state-range-start-value="250" state-range-text="Danger"
state-range-end-value="300" state-range-text-color="#F89B83"></e-state-ranges>
</e-state-range-collections>
</e-linear-indicators>
</e-linear-indicator-collections>
<e-linear-range-collections>
<e-linear-ranges end-value="200" start-value="0" range-background-color="#94C361" start-width="5" end-width="5">
<e-border color="#94C361"></e-border>
</e-linear-ranges>
<e-linear-ranges end-value="250" start-value="200" range-background-color="#F9CF67" start-width="5" end-width="5">
<e-border color="#F9CF67"></e-border>
</e-linear-ranges>
<e-linear-ranges end-value="300" start-value="250" range-background-color="#F89B83" start-width="5" end-width="5">
<e-border color="#F89B83"></e-border>
</e-linear-ranges>
</e-linear-range-collections>
</e-linear-scales>
</e-linear-scale-collections>
</ej-linear-gauge> 

{% endhighlight %}

Execute the above code to render the following output.

![](Indicators_images/Indicators_img4.png)



## Multiple Indicator

You can set multiple indicators in a single Linear Gauge by adding an array of indicator objects. Refer the following code example for multiple indicator functionality.



{% highlight cshtml %}

<ej-linear-gauge id="LinearGauge" enable-animation="false" value="78" >
<e-frame
 background-image-url="../images/gauge/Gauge_linear_light.png" ></e-frame>
<e-linear-scale-collections>
<e-linear-scales width="0" maximum="300" major-interval-value="30" minor-interval-value="5" 
background-color="transparent" show-bar-pointers="false" length="310" show-ranges="true">
<e-linear-position x="51" y="50"></e-linear-position>
<e-border color="transparent" width="1"></e-border>
<e-linear-tick-collections>
<e-linear-ticks type="@TickType.MajorInterval"  width="2" height="14">
<e-distance-from-scale x="7" y="0"></e-distance-from-scale>
</e-linear-ticks>
<e-linear-ticks type="@TickType.MinorInterval"  width="1" >
<e-distance-from-scale x="7" y="0"></e-distance-from-scale>
</e-linear-ticks>
<e-linear-tick-collections>
<e-linear-indicator-collections>
<e-linear-indicators type="@IndicatorType.Circle"  height="10" width="10">
<e-linear-position x="35" y="100"></e-text-location>
<e-state-range-collections>
<e-state-ranges state-range-background-color="#02A258" state-range-start-value="0" 
state-range-end-value="200" state-range-border-color="#02A258"></e-state-ranges>
<e-state-ranges state-range-background-color="Grey" state-range-start-value="200" 
state-range-end-value="300" state-range-border-color="Grey"></e-state-ranges>
</e-state-range-collections>
</e-linear-indicators>
// adding second indicator
<e-linear-indicators type="@IndicatorType.Circle"  height="10" width="10">
<e-linear-position x="75" y="100"></e-text-location>
<e-state-range-collections>
<e-state-ranges state-range-background-color="Grey" state-range-start-value="0" 
state-range-end-value="200" state-range-border-color="Grey"></e-state-ranges>
<e-state-ranges state-range-background-color="#02A258" state-range-start-value="200" 
state-range-end-value="300" state-range-border-color="#02A258"></e-state-ranges>
</e-state-range-collections>
</e-linear-indicators>
</e-linear-indicator-collections>
<e-linear-range-collections>
<e-linear-ranges end-value="200" start-value="0" range-background-color="#94C361" start-width="5" end-width="5">
<e-border color="#94C361"></e-border>
</e-linear-ranges>
<e-linear-ranges end-value="250" start-value="200" range-background-color="#F9CF67" start-width="5" end-width="5">
<e-border color="#F9CF67"></e-border>
</e-linear-ranges>
<e-linear-ranges end-value="300" start-value="250" range-background-color="#F89B83" start-width="5" end-width="5">
<e-border color="#F89B83"></e-border>
</e-linear-ranges>
</e-linear-range-collections>
</e-linear-scales>
</e-linear-scale-collections>
</ej-linear-gauge> 

{% endhighlight %}

Execute the above code to render the following output.



![](Indicators_images/Indicators_img5.png)



