---
layout: post
title: Chart size |Chart  | ASP.NET CORE | Syncfusion
description: Learn how to set Chart size and make it responsive. 
platform: aspnet-core
control: Chart
documentation: ug
---

# Chart Dimensions

You can set size for the chart directly on the chart or container of the chart. If you do not specify the size, it takes 450 pixels as the height and window size as its width, by default. 

## Set size for the container

You can customize the chart dimension by setting the width and height for the container element. 

{% highlight cshtml %}

  <div id="container" style="width:820px; height:500px;">
    <ej-chart id="chart" load="onchartload">
      
      // ...

    </ej-chart>
  </div>

{% endhighlight %}


## Set size in pixels

You can also set the chart dimension by using the **Size** property of the chart. 

{% highlight cshtml %}

<ej-chart id="chart"><e-size height="450" width="600"></e-size>
</ej-chart>

{% endhighlight %}

![](Chart-Dimensions_images/Chart-Dimensions_img1.png)

## Setting size relative to the container size

You can specify the chart size in percentage by using the **Size** property. The chart gets its dimension with respect to its container.

{% highlight cshtml %}

 <div id="container" style="width:700px; height:500px">
    
    <ej-chart id="chart"><e-size height="90%" width="80%"></e-size>
    </ej-chart>

  </div>

{% endhighlight %}

![](Chart-Dimensions_images/Chart-Dimensions_img2.png)


## Responsive chart

To resize the Chart when the browser or the chart container is resized, set the **IsResponsive** property to **true**, where the chart adapts to the changes in size of the container.

{% highlight cshtml %}

<ej-chart id="chart" is-responsive="true">
   
      // ...

</ej-chart>

{% endhighlight %}