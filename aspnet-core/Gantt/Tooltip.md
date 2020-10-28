---
layout: post
title: Tooltip
description: Tooltip
platform: aspnet-core
control: Gantt
documentation: Ug
---
# Tooltip

The Gantt has support to display tooltip for both taskbars and for column cells.

## Taskbar and dependency line tooltip

In Gantt, you can enable or disable taskbar and dependency line mouse hover tooltip by using the `enable-taskbar-tooltip` property. The default value of this property was `true`. The following code example shows, how to enable the taskbar and dependency line tooltip in Gantt.

{% highlight cshtml %}

<ej-gantt id="GanttContainer" datasource="ViewBag.datasource"
    //...
    enable-taskbar-tooltip="true">
</ejGantt>

{% endhighlight %}

Taskbar tooltip can be customized by using the `taskbar-tooltip-template` property and  dependency line tooltip can be customized by using the `predecessor-tooltip-template` property, these properties are described briefly in the [customization](/aspnet-core/gantt/customizations) section.

![](Tooltip_images/Tooltip_img3.png)
Taskbar Tooltip
{:.caption}

![](Tooltip_images/Tooltip_img4.png)
Dependency Tooltip
{:.caption}

## Taskbar drag tooltip

It is possible to enable or disable the tooltip while performing editing actions on taskbar (left resizing, right resizing, dragging and progress resizing) by using the `enable-taskbar-drag-tooltip` property. By default, this property is set to `true`. The following code example explains this behavior.

{% highlight cshtml %}

<ej-gantt id="GanttContainer" datasource="ViewBag.datasource"
    //...
    enable-taskbar-drag-tooltip="true">
</ejGantt>

{% endhighlight %}

## Cell tooltip

It is possible to enable or disable the TreeGrid cell tooltip in mouse hover by using the `show-grid-cell-tooltip`  property. By default, this property is set to `true`. The following code example explains how to enable disable this property.

{% highlight cshtml %}

<ej-gantt id="GanttContainer" datasource="ViewBag.datasource"
    //...
    show-grid-cell-tooltip="true">
</ejGantt>

{% endhighlight %}


This tooltip can be customized using the `cell-tooltip-template` property, which is described briefly in the [customization](/aspnet-core/gantt/customizations) section.

![](Tooltip_images/Tooltip_img1.png)

## Tree column (Expander column) tooltip 

It is also possible to display tooltip only for expander column by setting the `show-grid-expand-cell-tooltip` property. The following code example shows you to enable expander column tooltip in Gantt.

{% highlight cshtml %}

<ej-gantt id="GanttContainer" datasource="ViewBag.datasource"
    //...
    show-grid-expand-cell-tooltip="true">
</ejGantt>
{% endhighlight %}

![](Tooltip_images/Tooltip_img2.png)