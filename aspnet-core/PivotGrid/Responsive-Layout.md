---
layout: post
title: Responsive | PivotGrid | ASP.NET Core | Syncfusion
description: This document illustrates that how to define responsive layout rendering in ASP.NET Core PivotGrid control
platform: aspnet-core
control: PivotGrid
documentation: ug
---

# Responsive

The pivot grid and pivot table field list control supports responsive rendering based on the target device (desktop and tablet) resolution. It supports resolution upto 1024x600. You can enable responsiveness in the pivot grid by setting the `is-responsive` property to true.

When resizing the browser, the pivot table field list will be collapsed, and an icon will appear on the left-hand side of the browser. You can toggle its view and perform UI interaction.

{% highlight CSHTML %}

<ej-pivot-grid id="PivotGrid1" is-responsive="true"></ej-pivot-grid>

{% endhighlight %}

![ASP NET Core pivot grid control with normal layout](Responsive-Layout_images/normal.png)

_Normal PivotGrid_

![ASP NET Core pivot grid control with responsive layout](Responsive-Layout_images/responsive.png)

_Responsive PivotGrid_

![ASP NET Core pivot table field list in collapsed state](Responsive-Layout_images/res-schema.png)

_Responsive PivotTable Field List - Collapsed_

![ASP NET Core pivot table field list in expanded state](Responsive-Layout_images/res-schema1.png)

_Responsive PivotTable Field List - Expanded_

