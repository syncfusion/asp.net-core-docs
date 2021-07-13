---
layout: post
title: Data Exploration in ASP.NET Core PivotClient Control | Syncfusion
description: Learn here about data exploration in Syncfusion Essential ASP.NET Core PivotClient Control, and more.
platform: aspnet-core
control: PivotClient
documentation: ug
---

# Data exploration in ASP.NET Core PivotClient Control

## Filtering

### Filtering by member

By clicking the split button of a field, the Member Editor dialog opens through which members are filtered by checking and unchecking the check boxes corresponding to members.

![Member editor filtering in ASP NET Core pivot client control](Data-Exploration_images/relational-filterbymember.png)

 When you click OK, the report will get updated and the pivot grid and pivot chart controls will be refreshed based on the selected members in the Member Editor dialog. The Cancel button is used to cancel the selection.

![Filtered data in ASP NET Core pivot client control](Data-Exploration_images/relational-filter-grouping.png)

The above filter illustrates the members 'Canada' and 'Germany' that are alone included in the grid and chart controls.

## Grouping

The data can be grouped when more than one field element is added to the column or row in the axis element builder. Based on the order of addition, the data is grouped and the report is updated. In the following example, the **Date** dimension values get grouped with respect to **Country** dimension values. Likewise, multiple field members can be grouped by dragging the elements from the pivot field list to the axis element builder.

![Grouping in ASP NET Core pivot client control](Data-Exploration_images/relational-grouping.png)

## Searching

Members can be searched and displayed from the members list in the Member Editor dialog.

![Searching in ASP NET Core pivot client control](Data-Exploration_images/relationalsearchgrouping.png)
