---
layout: post
title: Advanced Filtering in ASP.NET Core PivotClient | Syncfusion
description: This document illustrates that how to define advance filtering and sorting with respective to the modes in ASP.NET Core PivotClient control
platform: aspnet-core
control: PivotClient
documentation: ug
---


# Advanced filtering and sorting

It allows you to filter and sort the field members in the pivot client.

You can enable the "Advanced Filtering and Sorting" option in the pivot client by setting the [`enable-advanced-filter`] property under [`e-data-source`] to true.

{% highlight CSHTML %}

<ej-pivot-client id="PivotClient1">
    <e-data-source enable-advanced-filter="true">
        //..
    </e-data-source>
</ej-pivot-client>

{% endhighlight %}

## Sorting

Sorting provides an option to sort the members of a field in the ascending or descending order.

![Sorting options in ASP NET Core pivot client control](AdvanceFiltering_images/sorting.png)

## Label filtering

Label filtering provides an option to filter the members of a field purely based on their caption.

![Label filtering options in ASP NET Core pivot client control](AdvanceFiltering_images/filtering.png)

![Label filter dialog in ASP NET Core pivot client control](AdvanceFiltering_images/filtering_dialog.png)

## Value filtering

Value filtering provides an option to filter members based on the total values of the appropriate measure between the members of the level.

![Value filtering options in ASP NET Core pivot client control](AdvanceFiltering_images/valuefilter.png)

![Value filter dialog in ASP NET Core pivot client control](AdvanceFiltering_images/valuefilter_dialog.png)
