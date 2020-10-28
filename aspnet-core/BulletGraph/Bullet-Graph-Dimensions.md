---
layout: post
title: Bullet Graph Dimensions | BulletGraph | Syncfusion
description: bullet graph dimensions
platform: aspnet-core
control: BulletGraph	
documentation: ug
---

# Bullet Graph Dimensions

This section explains you on how to change the dimensions of the Bullet Graph. You can change various dimensions and properties of Bullet Graph like width, height, quantitative scale length, qualitative range size etc. By default, Bullet Graph uses 595 pixel width and 90 pixel height. You can customize width and height of a Bullet Graph using `width` and `height` properties of Bullet Graph respectively.

## Size
{% highlight cshtml %}

<ej-bullet-graph id="Bullets" width="500" height="100">
</ej-bullet-graph>

{% endhighlight %}

In the above code example, width is set as 500 pixel and height is set as 100 pixel. The output of the above code example with dimension 500 * 100 is as follows.



![](Bullet-Graph-Dimensions_images/Bullet-Graph-Dimensions_img1.png)

Bullet Graph
{:.caption}


## Value for performance bar

The feature measure bar value is customized using the `value` property. Default value of this property is 0. 
{% highlight cshtml %}

<ej-bullet-graph id="Bullets" value="5">
</ej-bullet-graph>

{% endhighlight %}

The following screenshot displays Bullet Graph with a performance measure value of 5

![](Bullet-Graph-Dimensions_images/Bullet-Graph-Dimensions_img2.png)

Bullet Graph with performance measure
{:.caption}


## Comparative measure value

The Comparative measure value is set using `comparative-measure-value` property. The default value of this property is 0. 
{% highlight cshtml %}

<ej-bullet-graph id="Bullets" comparative-measure-value="5">
</ej-bullet-graph>

{% endhighlight %}


The following screenshot displays Bullet Graph with comparative measure value of 5



![](Bullet-Graph-Dimensions_images/Bullet-Graph-Dimensions_img3.png)

Bullet Graph with comparative symbol
{:.caption}




## Theme

Bullet Graph Theme is customized using `theme` property. Default value is FlatLight. Bullet Graph supports FlatLight and FlatDark themes. FlatDark theme improves Bullet Graph appearance when background of Bullet Graph container uses dark color like black. 
{% highlight cshtml %}

<ej-bullet-graph id="Bullets" theme="FlatDark">
</ej-bullet-graph>

{% endhighlight %}

The following screenshot displays Bullet Graph with FlatDark theme



![](Bullet-Graph-Dimensions_images/Bullet-Graph-Dimensions_img4.png)

Bullet Graph with theme
{:.caption}
 

## Orientation

Bullet Graph is oriented either horizontally or vertically using `orientation` property. Default value of this property is Horizontal. 

{% highlight cshtml %}

<ej-bullet-graph id="Bullets" width="100" height="550" 
orientation="@Orientation.Vertical" flow-direction="@FlowDirection.Backward">
</ej-bullet-graph>

{% endhighlight %}


## Flow direction

The Flow direction of Bullet Graph is customized using `flow-direction` property. Default value of this property is Forward. Setting Forward renders Bullet Graph left to right and Backward renders from right to left.


{% highlight cshtml %}

<ej-bullet-graph id="Bullets" comparative-measure-value="2"
 flow-direction="@FlowDirection.Backward">
</ej-bullet-graph>

{% endhighlight %}

The following screenshot displays Bullet Graph in a backward direction.

![](Bullet-Graph-Dimensions_images/Bullet-Graph-Dimensions_img5.png)

Bullet Graph in backward flow
{:.caption}


## Qualitative range size

Size of the qualitative range is customized using  `qualitative-range-size` property. Default value of this property is 32. 
{% highlight cshtml %}

<ej-bullet-graph id="Bullets" qualitative-range-size="50">
</ej-bullet-graph>

{% endhighlight %}

The following screenshot displays Bullet Graph with Qualitative range of size 50

![](Bullet-Graph-Dimensions_images/Bullet-Graph-Dimensions_img6.png)

Bullet Graph with customized qualitative range height
{:.caption}



## Quantitative scale length

Length of the quantitative scale is customized using `quantitative-scale-length` property. Default value of this property is 475. 
{% highlight cshtml %}

<ej-bullet-graph id="Bullets" quantitative-scale-length="500">
</ej-bullet-graph>

{% endhighlight %}

The following screenshot displays Bullet Graph with Quantitative scale length of 500

![](Bullet-Graph-Dimensions_images/Bullet-Graph-Dimensions_img7.png)

Bullet Graph with quantitative scale of length 500 pixels
{:.caption}



