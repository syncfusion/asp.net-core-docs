---
layout: post
title: Rendering modes available in Essential ASP.NET CORE Chart
description: How Essential Chart renders in IE7 and IE8. How to render Essential Chart in a HTML5 Canvas.                    
platform: aspnet-core
control: Chart
documentation: ug
---

# Rendering Modes

Chart supports following three rendering technologies:

   * VML
   * SVG
   * HTML5 canvas

## VML

VML is used to render chart in lower versions of Internet Explorer such as Internet Explorer 7 and Internet Explorer 8. In these two browsers, SVG and Canvas are not supported, and VML is used by default.

**Limitations:**

* Label rotation is not supported.
* Animation is not supported.
* Patterns are not supported.
* Zooming and panning features are not supported.

## SVG

SVG is used to render chart by default for all browsers except Internet Explorer 7 and Internet Explorer 8.

## Canvas

You can switch between SVG and canvas rendering by using **EnableCanvasRendering** option. The canvas rendering is used in the following scenarios:

* Plotting large number of data points.
* Performing high frequency live updates.
 
The following code example illustrates how to enable HTML5 canvas rendering in chart.

{% highlight cshtml %}

  <ej-chart id="container" enable-canvas-rendering="true">
  </ej-chart>

{% endhighlight %}

![](Rendering-Modes_images/Rendering-Modes_img1.png)


**Limitations:**
  
* Animation is not supported.
* 3D charts are not supported.