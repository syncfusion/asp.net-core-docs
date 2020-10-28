---
layout: post
title: Add gridlines behind nodes and connectors to ease alignments
description: How to add gridlines behind nodes and connectors?
platform: aspnet-core
control: Diagram
documentation: ug
---

# Gridlines

**Gridlines** are the pattern of lines drawn behind the Diagram elements. It provides a visual guidance while dragging or arranging the objects on the Diagram surface.

## Customize the gridlines visibility

The `SnapSettings.SnapConstraints` enables you to show/hide the gridlines. The following code example illustrates how to show or hide gridlines.

{% highlight razor %}

    <div>
      <ej-diagram id="diagram" width="900px" height="600px"></ej-diagram>
    </div>
    
{% endhighlight %}

{% highlight razor %}

    <ej-diagram id="diagram" width="900px" height="600px">
      <e-snap-settings snap-constraints="ShowLines"></e-snap-settings>
    </ej-diagram>
    
{% endhighlight %}


![](Gridlines_images/Gridlines_img1.png)

To show only horizontal/vertical gridlines or to hide gridlines, refer to [Constraints](https://help.syncfusion.com/cr/aspnetmvc/Syncfusion.JavaScript.DataVisualization.Models.Diagram.SnapSettings.html#Syncfusion_JavaScript_DataVisualization_Models_Diagram_SnapSettings_SnapConstraints "Constraints")

## Appearance

You can customize the appearance of the gridlines by using a set of predefined properties. To explore those properties, refer to [Gridlines](http://help.syncfusion.com/cr/aspnetmvc/Syncfusion.JavaScript.DataVisualization.Models.Diagram.GridLines.html "Gridlines")
The `HorizontalGridLines` and `VerticalGridLines` properties allow to customize the appearance of the gridlines. The following code example illustrates how to customize the appearance of gridlines.

{% highlight razor %}

    <ej-diagram id="diagram" width="900px" height="600px">
      <e-snap-settings snap-constraints="ShowLines">
        <e-horizontal-grid-lines line-color="blue" line-dash-array="2 2"></e-horizontal-grid-lines>
        <e-vertical-grid-lines line-color="blue" line-dash-array="2 2"></e-vertical-grid-lines>
      </e-snap-settings>
    </ej-diagram>
    
{% endhighlight %}

![](Gridlines_images/Gridlines_img4.png)

### Line Intervals

Thickness and the space between gridlines can be customized by using `LinesInterval` property. In the linesInterval collections, values at the odd places are referred as the thickness of lines and the values at the even places are referred as the space between gridlines.

The following code example illustrates how to customize the thickness of lines and the line intervals.

{% highlight c# %}

public ActionResult Index()
{
    List<decimal> intervals = new List<decimal>();
    intervals.Add(1.25m);
    intervals.Add(14);
    intervals.Add(0.25m);
    intervals.Add(15);
    intervals.Add(0.25m);
    intervals.Add(15);
    intervals.Add(0.25m);
    intervals.Add(15);
    intervals.Add(0.25m);
    intervals.Add(15);
    ViewBag.intervals = intervals;
    return View();
}

{% endhighlight %}

{% highlight razor %}

    <ej-diagram id="diagram" width="900px" height="600px">
      <e-snap-settings snap-constraints="ShowLines">
        <e-horizontal-grid-lines line-color="blue" line-dash-array="2 2" lines-interval="ViewBag.intervals"></e-horizontal-grid-lines>
        <e-vertical-grid-lines line-color="blue" line-dash-array="2 2" lines-interval="ViewBag.intervals"></e-vertical-grid-lines>
      </e-snap-settings>
    </ej-diagram>

{% endhighlight %}

![](Gridlines_images/Gridlines_img2.png)

# Snapping

## Snap To Lines

This feature allows the Diagram objects to snap to the nearest intersection of gridlines while being dragged or resized. This feature enables easier alignment during layout or design.

Snapping to gridlines can be enabled/disabled with the `SnapSettings.SnapConstraints`. The following code example illustrates how to enable/disable the snapping to gridlines.

{% highlight razor %}

    <ej-diagram id="diagram" width="900px" height="600px">
      <e-snap-settings snap-constraints="SnapToLines"></e-snap-settings>
    </ej-diagram>
    
{% endhighlight %}

To enable/disable snapping to horizontal/vertical lines, refer to [Constraints](https://help.syncfusion.com/cr/aspnetmvc/Syncfusion.JavaScript.DataVisualization.Models.Diagram.SnapSettings.html#Syncfusion_JavaScript_DataVisualization_Models_Diagram_SnapSettings_SnapConstraints "Constraints")

## Customization of Snap Intervals

By default, the objects are snapped towards the nearest gridline. The gridline or position towards where the diagram object snaps can be customized with the property, `snapInterval`. The following code example illustrates how to customize the snap intervals.

{% highlight c# %}

public ActionResult Index()
{
    List<decimal> intervals = new List<decimal>();
    intervals.Add(10);
    ViewBag.intervals = intervals;
    return View();
}

{% endhighlight %}

{% highlight razor %}

    <ej-diagram id="diagram" width="900px" height="600px">
      <e-snap-settings snap-constraints="All">
        <e-horizontal-grid-lines snap-interval="ViewBag.intervals"></e-horizontal-grid-lines>
        <e-vertical-grid-lines snap-interval="ViewBag.intervals"></e-vertical-grid-lines>
      </e-snap-settings>
    </ej-diagram>

{% endhighlight %}

## Snap To Objects

The snap-to-object provides visual cues to assist with aligning and spacing Diagram elements. A node can be snapped with its neighboring objects based on certain alignments. Such alignments are visually represented as smart guides.

The `EnableSnapToObject` property allows you to enable/disable smart guides. The following code example illustrates how to enable/disable the smart guides.

{% highlight razor %}

    <ej-diagram id="diagram" width="900px" height="600px">
      <e-snap-settings enable-snap-to-object="true"></e-snap-settings>
    </ej-diagram>
    
{% endhighlight %}

![](Gridlines_images/Gridlines_img4.png)