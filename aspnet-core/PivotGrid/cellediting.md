---
layout: post
title: Cell Editing | PivotGrid | ASP.NET Core | Syncfusion
description: This document illustrates that how to enable cell editing feature through API in ASP.NET Core PivotGrid control
platform: aspnet-core
control: PivotGrid
documentation: ug
---

# Cell editing

I> This feature is applicable only for the relational data source.

Cell editing allows you to edit and alter the values in the pivot grid. The summary values will be recreated based on the edited values. By selecting multiple cells (like in cell selection feature), you can edit multiple cells at the same time.

You can enable the cell editing option in the pivot grid by setting the `enable-cell-editing` property to true.

{% highlight CSHTML %}

<ej-pivot-grid id="PivotGrid1" enable-cell-editing="true"></ej-pivot-grid>

{% endhighlight %}

![Cell editing in ASP NET Core pivot grid control](Cell-Editing_images/celleditingclient.png)


