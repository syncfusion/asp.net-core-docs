---
layout: post
title: Legend gives visual guideline for mapping between value and color.
description: How to create and configure legend for HeatMap
platform: aspnet-core
control: HeatMapLegend
documentation: ug
---

# Legend

Legend is a control used to summarize the range of colors in HeatMap. This gives visual guideline for mapping between value and color.

## Create Legend

Legend can be created with color mapping as shown below.

{% highlight razor %}

    <ej-heatmaplegend is-responsive="true" id="heatmapLegend" width="50%" height="50px" legend-mode="Gradient" orientation="Horizontal">
        <e-colorMappingCollection>
            <e-color-mapping color="#fe0002" value="0">
                <e-label text="Poor"></e-label>
            </e-color-mapping>
            <e-color-mapping color="#ffff01" value="3">
                <e-label text="Average"></e-label>
            </e-color-mapping>
            <e-color-mapping color="#13ab11" value="6">
                <e-label text="Good"></e-label>
            </e-color-mapping>
            <e-color-mapping color="#005ba2" value="10">
                <e-label text="Excellent"></e-label>
            </e-color-mapping>
        </e-colorMappingCollection>
    </ej-heatmaplegend>

{% endhighlight %}

Resultant legend will be like following image.

![](Legend_images/Legend_img1.png)
 
## Legend Mode

There are two modes for Legend
* Gradient
* List

### Gradient:

{% highlight razor %}

    <ej-heatmaplegend is-responsive="true" id="heatmapLegend" width="50%" height="50px" legend-mode="Gradient" orientation="Horizontal">             
    </ej-heatmaplegend>
        
{% endhighlight %}

![](Legend_images/Legend_img2.png)

### List:

{% highlight razor %}

    <ej-heatmaplegend is-responsive="true" id="heatmapLegend" width="50%" height="50px" legend-mode="List" orientation="Horizontal">
    </ej-heatmaplegend>
        
{% endhighlight %}

![](Legend_images/Legend_img3.png)

## Orientation

There are 2 types of Orientation, applicable for Gradient and List Mode 
* Horizontal
* Vertical

### Horizontal:

{% highlight razor %}

    <ej-heatmaplegend is-responsive="true" id="heatmapLegend" width="50%" height="50px" legend-mode="List" orientation="Horizontal">
    </ej-heatmaplegend>
        
{% endhighlight %}

![](Legend_images/Legend_img3.png)

### Vertical:

{% highlight razor %}

    <ej-heatmaplegend is-responsive="true" id="heatmapLegend" width="50%" height="50px" legend-mode="List" orientation="Vertical">
    </ej-heatmaplegend>
        
{% endhighlight %}

![](Legend_images/Legend_img4.png)