---
layout: post
title: Customize the size and appearance of single or multiple Diagram pages
description: How to customize the size and appearance of the Diagram pages?
platform: aspnet-core
control: Diagram
documentation: ug
---


# Page Settings 

Page settings enable to customize the appearance, width, and height of the Diagram page.

![](Page-Settings_images/Page-Settings_img1.png)

## Page size and appearance

The size and appearance of the Diagram pages can be customized with the `PageSettings` property. 

The `PageWidth` and `PageHeight` properties of page settings define the size of the page. In addition to that, you can customize the appearance of the page with a set of appearance specific properties.
To explore those properties, refer [Page Settings](http://help.syncfusion.com/cr/aspnetmvc/Syncfusion.JavaScript.DataVisualization.Models.Diagram.PageSettings.html  "Page Settings").

You can also customize the appearance of off-page regions with the property `BackgroundColor`.

The following code illustrates how to customize the page size and the appearance of page and off-page.

{% highlight razor %}

    <ej-diagram id="diagram" width="900px" height="600px">
      <e-page-settings page-width="500" page-height="500" page-border-width="4" page-background-color="white" page-border-color="lightgray" page-margin="25" page-orientation="Portrait" show-page-break="true" multiple-page="true"></e-page-settings>
    </ej-diagram>
    
{% endhighlight %}


![](Page-Settings_images/Page-Settings_img2.png)

![](Page-Settings_images/Page-Settings_img3.png)

N> When the PageWidth and PageHeight are not specified, the rectangular region that completely fits all nodes and connectors are considered as page size.

## MultiplePage and PageBreaks

When MultiplePage is enabled, size of the page dynamically increases or decreases in multiples of page width and height and completely fits diagram within the page boundaries. Page Breaks is used as a visual guide to see how pages are split into multiple pages.

![](Page-Settings_images/Page-Settings_img4.png)

`MultiplePage` and `ShowPageBreak` properties of page settings allow you to enable/disable multiple pages and page breaks respectively.
The following code illustrates how to enable multiple page and page break lines.

{% highlight razor %}

    <ej-diagram id="diagram" width="900px" height="600px">
      <e-page-settings show-page-break="true" multiple-page="true"></e-page-settings>
    </ej-diagram>

{% endhighlight %}

## Boundary Constraints

 Diagram provides support to restrict/customize the interactive region, out of which the elements cannot be dragged, resized or rotated. 
 `BoundaryConstraints` property of page settings allows you to customize the interactive region. To explore the boundary constraints, refer refer [Boundary Constraints](https://help.syncfusion.com/cr/aspnetmvc/Syncfusion.JavaScript.DataVisualization.Models.Diagram.PageSettings.html#Syncfusion_JavaScript_DataVisualization_Models_Diagram_PageSettings_BoundaryConstraints "Boundary Constraints").

The following code example illustrates how to define boundaryConstraints.

{% highlight razor %}

    <ej-diagram id="diagram" width="900px" height="600px">
      <e-page-settings boundary-constraints="Diagram"></e-page-settings>
    </ej-diagram>
    
{% endhighlight %}