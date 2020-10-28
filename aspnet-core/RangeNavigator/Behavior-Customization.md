---
layout: post
title: Behavior Customization | RangeNavigator | ASP.NET Core | Syncfusion
description: behavior customization
platform: aspnet-core
control: RangeNavigator
documentation: ug
---

# Behavior Customization

RangeNavigator allows you to customize the control using events. You can change the range for selected data of the RangeNavigator using events.

## Deferred update

If you set EnableDeferredUpdate to true, the RangeChanged event gets fired after dragging and dropping the slider. By default the EnableDeferredUpdate is true. If EnableDeferredUpdate is false then the RangeChanged event gets fired while dragging the slider.

{% highlight CSHTML %}
  
<div>
	<ej-range-navigator id="range" load="loadingData" enable-deferred-update="true">
		<e-chart-series>
			<e-series name="Product A" type="Line" fill="#69D2E7">
			</e-series>
		</e-chart-series>
	</ej-range-navigator>
</div>

{% endhighlight  %}

![](Behavior-Customization_images/Behavior-Customization_img1.png)

Deferred update
{:.caption}

## Handle Events

### Loaded: function

This event is handled when the RangeNavigator gets loaded. A parameter sender is passed to the handler. Using sender.model, you can access the RangeNavigator properties. 

{% highlight CSHTML %}

<div>
	<ej-range-navigator id="range" loaded="loadingData">
		<e-chart-series>
			<e-series name="Product A" type="Line" fill="#69D2E7">
			</e-series>
		</e-chart-series>
	</ej-range-navigator>
</div>

<script type="text/javascript">

	function loadingData(sender) 
	{

		 sender.model.isResponsive = false;

	}

</script>         

{% endhighlight  %}

### RangeChanged: function

This event gets fired whenever the selected range changes in RangeNavigator. A parameter sender is passed to the handler. Using sender.selectedRangeSettings, you can access the start and end value of range for the selected region. 

{% highlight CSHTML %}

<div>
	<ej-range-navigator id="range" range-changed="loadingData">
		<e-chart-series>
			<e-series name="Product A" type="Line" fill="#69D2E7">
			</e-series>
		</e-chart-series>
	</ej-range-navigator>
</div>

<script type="text/javascript">

   function loadingData(sender) 
   {

		 console.log(sender.selectedRangeSettings.start);

   }

</script>         
{% endhighlight %}

## Use of ZoomCoordinates

RangeNavigator is used along with the controls like chart and grid to view the selected data. To update chart/grid, whenever the selected range changes in RangeNavigator, you can use RangeChanged event of RangeNavigator and then update the chart/grid with the selected data in this event. 

You can easily update the data for chart by assigning the ZoomFactor and ZoomPosition of the RangeNavigator to the chart axis. 

{% highlight CSHTML %}

<div>
	<ej-range-navigator id="range" range-changed="loadingData">
		<e-chart-series>
			<e-series name="Product A" type="Line" fill="#69D2E7">
			</e-series>
		</e-chart-series>
	</ej-range-navigator>
</div>
<script type="text/javascript">

	// setting zoom factor and position for chart axis in rangeChanged event.

	function loadingData(sender) 
	{

	 var chartObj = $("#container").data("ejChart");

	 if (chartObj != null) 
	 {

		 chartObj.model.axes[0].zoomPosition = sender. zoomPosition;                                                               

		 chartObj.model.axes[0].zoomFactor = sender. zoomFactor;

		}

		$("#container").ejChart("redraw");

	}

</script>         
{% endhighlight  %}

![](Behavior-Customization_images/Behavior-Customization_img2.png)

## Thumb Template

You can customize Thumb template by using LeftThumbTemplate and RightThumbTemplate property. You can add the required template as a “div” element with an “id” to the web page and assign the id or assign the HTML string to this property under NavigatorStyleSettings. 

{% highlight CSHTML %}

<script type="text/x-jsrender" id="left" >

           <svg height="24" width="32" style="fill:#DD4A4A;stroke:black;">

                <path d="M2 2 L2 22 L22 22 L32 12 L22 2 Z" />

           </svg>

</script>

<script type="text/x-jsrender" id="right">

           <svg height="24" width="32" style="fill:#DD4A4A;stroke:black; ">

               <path d="M2 12 L12 22 L32 22 L32 2 L12 2 Z" />

           </svg>

</script>

<div>
	<ej-range-navigator id="range">
		
		// ...              

		<e-navigator-style-settings left-thumb-template="left" right-thumb-template="right"></e-navigator-style-settings>
		// ... 

	</ej-range-navigator>
</div>

{% endhighlight %}

The following screenshot displays the RangeNavigator using thumb template.

![](Behavior-Customization_images/Behavior-Customization_img3.png)


## Value Axis Settings

You can customize the line, `Font` `Size`, gridline, tickline, range, `Range-Padding` and visibility of **Range-Navigator** axis.

To enable the visibility of axis line, you need to set `Visible` property of `AxisLine` in `Value-Axis-Settings`. 

You can customize the axis range by specifying `Min`, `Max` and `Interval` for `Range` property.

The `Major-Grid-Lines` can be enabled by specifying `Visible` property. The `Size`, `Width` and `Visible` property of `Major-Tick-Lines` is used to customize the axis tick lines.

The visibility of `Value-Axis-Settings` is enabled by setting `Visible` property as true. 

{% highlight html %}

<ej-range-navigator id="rangecontainer">
<e-value-axis-settings min="10" max="50" interval="5" size="2" width="2">
<e-major-tick-lines visible="true"></e-major-tick-lines>
<e-major-grid-lines visible="true"></e-major-grid-lines>
</e-value-axis-settings>
</ej-range-navigator>

{% endhighlight %}

## Selected Range Settings

The start and end range values of selected range can be customized using `Start` and `End` property of `SelectedRangeSettings`.

{% highlight html %}

<ej:range-navigator ID="Range1">
<e-selected-range-settings start="" end=""></e-selected-range-settings>               
</ej:range-navigator>  

{% endhighlight %}
