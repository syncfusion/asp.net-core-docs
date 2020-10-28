---
layout: post
title: Searching
description: searching
platform: aspnet-core
control: Gantt
documentation: ug
---
# Searching

The Gantt control for ASP.NET Core has built-in support for searching any content in Gantt.

### Searching for Content Columns

In Gantt we can search the content using the public method searchItem with search key as parameter. Also, we can integrate the search text box in Gantt toolbar, by adding search toolbar item in `e-gantt-toolbar-settings` property.

The following code example shows you how to add search option in Gantt toolbar.

{% highlight cshtml %}

<ej-gantt id="ganttSample" datasource="ViewBag.datasource"
    //...>
    <e-gantt-toolbar-settings show-toolbar="true" toolbar-items="@(new List<string>() { "search" })">
</ejGantt> 

{% endhighlight %}

The following screenshot shows the output of searching for string in Gantt control.

![](Searching_images/Searching_img1.png)

