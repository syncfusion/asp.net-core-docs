---
layout: post
title: Advanced Filtering | PivotGrid | ASP.NET Core | Syncfusion
description: This document illustrates that how to define advance filtering and sorting with respective to the modes in ASP.NET Core PivotGrid control
platform: aspnet-core
control: PivotGrid
documentation: ug
---

# Advanced filtering and sorting

It allows you to filter and sort the field members in the pivot grid.

In client mode, you can enable the advanced filtering and sorting option in the pivot grid by setting the [`enable-advanced-filter`] property to true.

{% highlight html %}

<ej:PivotGrid ID=" PivotGrid1" enable-advanced-filter="true" runat="server"></ej:PivotGrid>

{% endhighlight %}

## Sorting

Sorting provides an option to sort the members of a field in an ascending or descending order.

![Sorting options in ASP NET Core pivot grid control](AdvanceFiltering_images/sorting.png)

## Label filtering

Label filtering provides an option to filter the members of a field purely based on their caption.

![Label filtering options in ASP NET Core pivot grid control](AdvanceFiltering_images/filtering.png)

![Label filter dialog in ASP NET Core pivot grid control](AdvanceFiltering_images/filtering_dialog.png)


## Value filtering

Value filtering provides an option to filter members based on the total values of the appropriate measure between the members of the level.

![Value filtering options in ASP NET Core pivot grid control](AdvanceFiltering_images/valuefilter.png)

![Value filter dialog in ASP NET Core pivot grid control](AdvanceFiltering_images/valuefilter_dialog.png)
