---
layout: post
title: Read the current scroll status and programmatically pan Diagrams
description: How to read/modify the scroll status of the Diagram?
platform: ejmvc
control: Diagram
documentation: ug
---

# Scroll Settings
The Diagram can be scrolled by using the vertical and horizontal scrollbars. In addition to the scrollbars, you can use mouse wheel to scroll the Diagram. 
Diagram's `ScrollSettings` enables you to read the current scroll status, view port size, current zoom, and zoom factor. It also allows you to scroll the Diagram programmatically. 

## Get current scroll status

Scroll settings allows you to read the scroll status, view port size, and current zoom factor with a set of properties. To explore those properties, see [Scroll Settings](http://help.syncfusion.com/cr/aspnetmvc/Syncfusion.JavaScript.DataVisualization.Models.Diagram.ScrollSettings.html  "Scroll Settings")

## Define scroll status
Diagram allows you to pan the Diagram before loading, so that any desired region of a large Diagram is made to view. You can programmatically pan the Diagram with the `HorizontalOffset` and `VerticalOffset` properties of scroll settings. The following code illustrates how to set pan the Diagram programmatically.

{% highlight c# %}

    // To Enables multiple tools

    var diagram = $("#diagram").ejDiagram({
                    
                    //Sets horizontal and vertical scroll offsets
                    scrollSettings: {
                        horizontalOffset: 100,
                        verticalOffset: 50,
                        zoomFactor: 0.2
                    },
                    //Sets page settings
                pageSettings: {
                        pageWidth: 100,
                        pageHeight: 50,
                        zoomFactor: 0.2
                    },
                    

                });


           

{% endhighlight %}

In the example given below, the vertical scroll bar is scrolled down by 50px and horizontal scroll bar is scrolled to right by 100px. 

![](Scroll-Settings_images/Scroll-Settings_img1.png)

## Update scroll status

You can programmatically change the scroll offsets at runtime by using the client side method `update`. The following code illustrates how to change the scroll offsets and zoom factor at runtime.

{% highlight js %}

    var diagram = $("#diagram").ejDiagram({
                    nodes: nodes,
                    connectors: connectors,
                    //Sets scroll status
                    scrollSettings: {
                        horizontalOffset: 200,
                        verticalOffset: 200,
                        //Sets zoomFactor
                        zoomFactor: 0.5
                    },
                    

                });
                //Updates scroll settings
                diagram.update({ scrollSettings: scrollSettings });

        

        //Updates scroll settings
        diagram.update({ scrollSettings: scrollSettings });

{% endhighlight %}

## AutoScroll 

Autoscroll feature automatically scrolls the Diagram whenever the node or connector is moved beyond the boundary of the Diagram. So that, it is always visible during dragging, resizing, and multiple selection operations. Autoscroll is automatically triggered when any one of the following is done towards the edges of the Diagram.

* Node dragging, resizing 
* Connection editing
* Rubber band selection
* Label dragging

## Autoscroll border

The Autoscroll border is used to specify the maximum distance between the object and Diagram edge to trigger Autoscroll. The default value is set as 15 for all sides (left, right, top, and bottom) and it can be changed by using the `AutoScrollBorder` property of page settings. The following code example illustrates how to set Autoscroll border. 

{% highlight c# %}

    // To Enables multiple tools
    $("#diagram").ejDiagram({
                            nodes: objects,
                            pageSettings: {
                                // Specifies autoscroll border
                                autoScrollBorder: { left: 150, top: 15, right: 15, bottom: 15 }
                            },
                        });

           

{% endhighlight %}

## Scroll limit

The scroll limit allows you to define the scrollable region of the Diagram. It includes the following options.

* Allows to scroll in all directions without any restriction.
* Allows to scroll within the Diagram content.
* Allows to scroll within the specified scrollable area.

`ScrollLimit` property of scroll settings helps to limit the scrolling. For the accepted values of the scrollLimit, refer to 
[Scroll Limit](https://help.syncfusion.com/cr/aspnetmvc/Syncfusion.JavaScript.DataVisualization.Models.Diagram.PageSettings.html#Syncfusion_JavaScript_DataVisualization_Models_Diagram_PageSettings_ScrollLimit "Scroll Limit").

The following code example illustrates how to specify the scroll limit.

{% highlight c# %}

    //Sets the scroll limit
    <e-page-settings scroll-limit="@ScrollLimit.Infinity"></e-page-settings>
           

{% endhighlight %}

## Scrollable Area

You can restrict scrolling beyond any particular rectangular area by using the `ScrollableArea` property of scroll settings. To restrict scrolling beyond any custom region, you have to set the `ScrollLimit` as "Limited". The following code example illustrates how to customize scrollable area.

{% highlight c# %}

                pageSettings: { 
    //Sets scroll limit as limited 
    scrollLimit: "limited",
    //Sets the limited scrollable area
    scrollableArea: { x: 0, y: 0, width: 500, height: 500 }
    }


{% endhighlight %}
