---
layout: post
title: Change-Splitter-position
description: change splitter position
platform: aspnet-core
control: Gantt
documentation: ug
---

# Change Splitter position

In Gantt control, Splitter separates the TreeGrid section from the Chart section,and is possible to change the position of the Splitter while loading the Gantt by using the `splitter-position` property, thereby varying the width of the TreeGrid and Chart sections in the control.  `splitter-position` property denotes the percentage of the TreeGrid section’s width to be rendered and this property supports both pixels and percentage values.

The following code example explains how to define the `splitter-position` property in the Gantt.

{% highlight cshtml %}
<ej-gantt id="ganttSample3" datasource="ViewBag.datasource" 
        //...
        splitter-position="50%">
  </ejGantt>
{% endhighlight %}

![](Change-Splitter-position_images/Change-Splitter-position_img2.png)

Gantt with 30 % splitter position
{:.caption}

![](Change-Splitter-position_images/Change-Splitter-position_img3.png)

Gantt with 50% splitter position
{:.caption}

![](Change-Splitter-position_images/Change-Splitter-position_img4.png)

Gantt with 600px splitter position
{:.caption}

