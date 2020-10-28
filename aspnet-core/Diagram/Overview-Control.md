---
layout: post
title: Overview Control | Diagram | ASP.NET MVC | Syncfusion
description: overview control
platform: ejmvc
control: Diagram
documentation: ug
---

# Overview Control

**Overview** control allows you to see a preview or an overall view of the entire content of a Diagram. This helps you to look at the overall picture of a large Diagram and also to navigate, pan, or zoom, on a particular position of the page.

![](Overview-Control_images/Overview-Control_img1.png)

When you work on a very large Diagram, you may not know the part you are actually working on, or navigation from one part to another might be difficult. One solution for navigation is to zoom out the entire Diagram and find where you are. Then, you can zoom in a particular area you want to. This solution is not suitable when you need some frequent navigation.

Overview control solves these problems by showing you a preview, that is, an overall view of the entire Diagram. A rectangle indicates viewport of the Diagram. Navigation becomes easy by dragging this rectangle.

## Create overview

The `SourceID` property of overview should be set with the corresponding Diagram ID for you need the overall view. The following code illustrates how to create overview. 


{% highlight html %}

    //Initializes overview
    <div float="right">
            <div id="sampleProperties">
                <div class="prop-grid">
                    <div class="row">
                        <div class="col-md-3">
                            Overview
                        </div>
                    </div>
                    <div class="row">
                        <ej-overview id="overview" source-id="diagram" width="100%" height="300px"></ej-overview>
                    </div>
                </div>
            </div>
        </div>
    <div>

    @Html.EJ().Diagram("Diagram1", ViewData["diagramModel"] as Syncfusion.JavaScript.DataVisualization.Models.DiagramProperties)

    </div>
 
{% endhighlight %}
 

## Zoom and Pan

In overview, the view port of the Diagram is highlighted with a red colored rectangle. Diagram can be zoomed/panned by interacting with that. You can interact with overview as follows. 

* Resize the rectangle - Zooms in/out the Diagram
* Drag the rectangle - Pans the Diagram
* Click at a position - Navigates to the clicked region
* Choose a particular region by clicking and dragging - Navigates to the specified region

The following image shows how the Diagram is zoomed/panned with overview.

![](Overview-Control_images/Overview-Control_img2.png)
 

