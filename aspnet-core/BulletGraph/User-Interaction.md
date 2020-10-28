---
layout: post
title: User Interaction | BulletGraph	 | ASP.NET MVC | Syncfusion
description: user interaction
platform: aspnet-core
control: BulletGraph	
documentation: ug
---

# User Interaction

## Animation

Bullet Graph supports animation that makes the performance measure bar to animate when rendering the Bullet Graph. Animation is enabled or disabled using EnableAnimation property. By default, Animation is enabled in Bullet Graph. 
{% highlight cshtml %}

<ej-bullet-graph id="Bulletgraph"  comparative-measure="5" value="8"
enable-animation="true">
</ej-bullet-graph>    

{% endhighlight %}

## Responsiveness during browser resize

Bullet Graph is made responsive when resizing the browser by using IsResponsive property. By default the value of this property is true in Bullet Graph. 
{% highlight cshtml %}

<ej-bullet-graph id="Bulletgraph"  comparative-measure="5" value="8"
is-responsive="true">
</ej-bullet-graph>    

{% endhighlight %}

Responsiveness of the bullet graph is controlled by using enableResize property.


{% highlight html %}

<ej-bullet-graph id="bullet1" enable-resize="true">         
       
</ej-bullet-graph>

{% endhighlight %}


## Applying same color to all ticks and labels in a range

Background color for qualitative range is applied to major ticks and minor ticks of the Bullet Graph using ApplyRangeStrokeToTicks property. The range colors are applied to labels using ApplyRangeStrokeToLabels property. By default same colors are not applied to a qualitative range and its corresponding ticks or labels. 

{% highlight cshtml %}

<ej-bullet-graph id="Bulletgraph" apply-range-stroke-to-labels="true" 
apply-range-stroke-to-ticks="true" value="8"comparative-measure-value="5" >
<e-qualitative-ranges>
<e-qualitative-range range-end="3.5" range-stroke="DarkRed" range-opacity="0.5">
</e-qualitative-range>
<e-qualitative-range range-end="5" range-stroke="Red" range-opacity="1">
</e-qualitative-range>
<e-qualitative-range range-end="7.5" range-stroke="Blue" range-opacity="0.7">
</e-qualitative-range>
<e-qualitative-range range-end="9" range-stroke="LightGreen" range-opacity="1">
</e-qualitative-range>
<e-qualitative-range range-end="10" range-stroke="Green" range-opacity="1">
</e-qualitative-range>
</e-qualitative-ranges>  
</ej-bullet-graph> 

{% endhighlight %}

![](User-Interaction_images/User-Interaction_img1.png)



## Tooltip

By default Bullet Graph displays Tooltip when mouse is hovered over feature measure bar. Tooltip is enabled or disabled using Visible property in TooltipSettings.

![](User-Interaction_images/User-Interaction_img2.png)

Bullet Graph with tooltip
{:.caption}

Bullet Graph supports Tooltip template instead of defaultTooltip to customize the appearance and contents of Tooltip. The Tooltip template should be a <div> element with display set to ‘none’, so it is displayed only when mouse is placed on feature measure bar. The id value of the <div> element should be provided as value to the Template property in TooltipSettings of Bullet Graph to display the customized <div> element as Tooltip instead of default Tooltip. The values displayed in default Tooltip such as current value, target value and category are accessed in template <div> element by using {{currentValue}}, {{targetValue}} and {{category}} respectively. 

{% highlight cshtml %}

<ej-bullet-graph id="Bulletgraph" value="8"comparitive-measure-value="5"
height="150">
<e-bullet-tooltip-settings visible="true" template="Tooltip">
</e-bullet-tooltip-settings>
</ej-bullet-graph> 

{% endhighlight %}
The following screenshot displays Bullet Graph with a customized Tooltip including a header and contents such as current value and target value in different colors.

![](User-Interaction_images/User-Interaction_img3.png)


Bullet Graph using a tooltip template
{:.caption}
