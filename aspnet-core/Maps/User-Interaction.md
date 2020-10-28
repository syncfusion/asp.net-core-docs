---
layout: post
title: Interactive features of Maps control for Asp.Net Core
description: Learn how to enables the effective interaction on Map elements
platform: aspnet-core
control: Maps
documentation: ug
---

# User Interaction

Options like zooming, panning and map selection enable the effective interaction on Map elements.

## Map Selection

Each shape in the Map can be selected and deselected during interaction with shapes. 

The `selection-color` property is used to get or set the selected shape color. The `selection-stroke` and `selection-stroke-width` properties are used to customize the selected shape border.

You can select the shape by tapping the shape. The single selection is enabled by the `enable-selection` property of shape layer. When `enable-selection` is set to false, the shapes cannot be selected. 



{% highlight CSHTML %}

<ej-map id="maps">
<e-layers >
<e-layer  shape-data-path="mapData" enable-selection="true">
<e-shape-settings auto-fill="false"  selection-color="#BC5353"
stroke="white" selection-stroke="white" fill="#9CBF4E"
selection-stroke-width="2" value-path="population">
</e-shape-settings>
</e-layer>
</e-layers>
</ej-map>

	

{% endhighlight %}



![](User-Interaction_images/User-Interaction_img1.png)


## MultiSelection

This feature enables you to select multiple Map shapes on mouse taps accompanied by "`Ctrl`" key press. For this feature to get enabled, set the property `selection-mode` as "_multiple_" along with `enable-selection` property.

{% highlight js %}

<ej-map id="maps">
<e-layers >
<e-layer  shape-data-path="mapData" enable-selection="true" selection-mode="multiple">
</e-layer>
</e-layers>
</ej-map>
	
{% endhighlight %}

![](User-Interaction_images/User-Interaction_img5.png)


## Dragging On Selection

This feature enables you to select the shapes by dragging over the shapes. While dragging over the shapes, a rectangle is generated and the shapes that come within the rectangle is selected.

You can enable this feature by setting the property `dragging-on-selection` in the `e-layers` to "_True_".

{% highlight js %}

<ej-map id="maps"  dragging-on-selection="true">
</ej-map>

{% endhighlight %}

![](User-Interaction_images/User-Interaction_img4.png)


## Zooming

The zooming feature enables you to zoom in and out of the Map to show in-depth information. It is controlled by the `Level` property of the Map. When the zoom level of the Map control is increased, the Map is zoomed in. When the zoom level is decreased, then the Map is zoomed out.

### Properties

The following properties are related to the zooming feature of the Maps control:

* Level
* EnableZoom
* MinValue
* MaxValue

### Level

The `e-level` property determines the Map’s scale size when zooming. The default value of `Level` is 1. 

N> The  level cannot be less than 1.

### EnableZoom

The `enable-zoom` property enables or disables the zooming feature. 

### MinValue

The `min-value` property is used to set the minimum zoom level of the Map. 

### MaxValue

The `max-value` property is used to set the maximum zoom level of the Map.



{% highlight CSHTML %}

<ej-map id="maps" >
 <e-zoom-settings enable-zoom="true" max-value="20" min-value="1"></e-zoom-settings>
</ej-map>

{% endhighlight %}

### Additional Options to Zoom the Map

Maps can be zoomed by using the following options also,

* Zoom method.
* Mouse scroll.
* Mouse double tap.
* Shape selection
* Position

### By using Zoom method

You can zoom the Maps by using `Zoom` method. The `Zoom` method contains parameter zoom value. The Map can be zoomed or scaled based on zoom value parameter.

{% highlight CSHTML %}
 
	$("#map").ejMap("zoom", 2);

{% endhighlight %}


### By using mouse scroll

You can zoom the Map with mouse events by using mouse scroll. When the mouse is scrolled up, the Map is zoomed in and when the mouse is scrolled down, the Map is zoomed out.

### By using mouse double tap

When the map is double-tapped by using mouse, the zoom in operation is performed. 

![](User-Interaction_images/User-Interaction_img2.png)


### By using Shape Selection

Map shape is zoomed to the whole map area on the shape selected. Animation can be applied for that zooming with the `enable-animation` property as true. 

You can enable this feature by setting `enable-zoom-on-selection` property value as ‘_True_’. 

When `enable-zoom-on-selection` property is set to true, then zooming of the Map control is muted on double click.


{% highlight CSHTML %}

  <ej-map id="maps" >
 <e-zoom-settings enable-zoom-on-selection="true"></e-zoom-settings>
</ej-map>

{% endhighlight %}



### Positioning

Depending on the latitude and longitude, you can zoom the Map to the exact position. All locations are considered as latitude and longitude values and the exact location is considered as Map coordinates.

The `NavigateTo` is a method defined that allows you to zoom the Map control to the given location. This method contains three attributes as follows.

_Attribute Table_

<table>
<tr>
<th>
Attribute</th><th>
Type</th><th>
Description</th></tr>
<tr>
<td>
Latitude</td><td>
Double</td><td>
Latitude point of the position </td></tr>
<tr>
<td>
Longitude</td><td>
Double</td><td>
Longitude point of the position</td></tr>
<tr>
<td>
Level</td><td>
Double</td><td>
Zoom level of the map</td></tr>
</table>


{% highlight js %}

	<script type="text/javascript">

		function buttonClick()
		{

	 		$("#map").ejMap("navigateTo", 13, 80, 5);

		}

	</script> 

{% endhighlight %}

### Panning 

The panning feature enables the Map navigation. The `enable-pan` property is used to enable or disable the panning support.

{% highlight CSHTML %}

<ej-map id="maps"  enable-pan="true">
</ej-map>


{% endhighlight %}


### Factor

Specifies the zoom factor for map zoom value, you can use `factor` property.

{% highlight html %}

<ej-map id="mapcontrol" factor=''>
</ej-map> 

{% endhighlight %}




## Navigation Control

Navigation control is built-in with Maps control. With Navigation control, Maps can be panned in any direction and zoomed. It is possible to show or hide the NavigationControl by `enable-navigation` property.

![](User-Interaction_images/User-Interaction_img3.png)


{% highlight CSHTML %}

<ej-map id="maps" >
<e-navigation-control enable-navigation="true"></e-navigation-control>
</ej-map>
  

{% endhighlight %}



### Zoom with Navigation Control

With Navigation control, the Maps can be zoomed. When you click the ZoomIn button, the Map is zoomed in and when you click the ZoomOut button, the Map is zoomed out.

### Panning with Navigation Control

Maps can be panned with Pan buttons (TopPan button, RightPan button, BottomPan button, and LeftPan button). When you click a particular Pan button, the Map is panned on the respective directions.

### Navigation Control Positions

The Navigation control can be positioned in two ways.

* Absolute Position
* Dock Position

#### Absolute Position

Based on the margin values of X and Y-axes, the navigation control can be positioned with the help of the X and Y properties available in `absolute-position`. For positioning the navigation control based on margins corresponding to a Map, `dock-position` value is set as ‘_None_’.

#### Dock Position

The navigation control can be positioned in following locations within the container.

* TopLeft
* TopCenter
* TopRight
* CenterLeft
* Center
* CenterRight
* BottomLeft
* BottomRight
* BottomCenter
* BottomRight
* None

You can set this option by using the` dock-position` property in `NavigationControl`.



{% highlight CSHTML %}

<ej-map id="maps" >
<e-navigation-control enable-navigation="true" orientation="@Orientation.Vertical" 
dock-position="@DockPosition.None">
<e-absolute-position  x="05" y="10" >                          
</e-absolute-position>
</e-navigation-control>
</ej-map>
  
{% endhighlight %}


#### Orientation

Set the `orientation` value for navigation control.


{% highlight html %}

<ej-map id="maps" >
<e-navigation-control enable-navigation="true" orientation="@Orientation.Vertical" 
dock-position="@DockPosition.None">
<e-absolute-position  x="05" y="10" >                          
</e-absolute-position>
</e-navigation-control>
</ej-map>


{% endhighlight %}

#### Content


Specifies the navigation control template for map, you can use `content` property.


{% highlight html %}
 
<ej-map id="maps" >
<e-navigation-control enable-navigation="true" content="">
<e-absolute-position  x="05" y="10" >                          
</e-absolute-position>
</e-navigation-control>
</ej-map>

{% endhighlight %}



### Animation

 **Animation** is enabled or disabled using `enable-animation`property. 

{% highlight html %}

<ej-map id="mapcontrol" enable-animation="true">
</ej-map>

{% endhighlight %}


#### Enable Layer Change Animation 

Enables or Disables the animation for layer change in map, you can use `enable-layer-change-animation` property and the default value is false.


{% highlight html %}
 
{% highlight html %}

<ej-map id="mapcontrol" enable-layer-change-animation="true">
</ej-map>

{% endhighlight %}


{% endhighlight %}


### Responsiveness during browser resize

**Map** is made responsive when resizing the browser by using `is-responsive` property.

{% highlight javascript %}

{% highlight html %}

<ej-map id="mapcontrol" is-responsive="true">
</ej-map>

{% endhighlight %}


{% endhighlight %}




