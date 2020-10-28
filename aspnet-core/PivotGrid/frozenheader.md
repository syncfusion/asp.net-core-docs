---
layout: post
title:  Frozen Header | PivotGrid | ASP.NET Core | Syncfusion
description:  This document illustrates that how to enable frozen header feature and its options in ASP.NET Core PivotGrid control
platform: aspnet-core
control: PivotGrid
documentation: ug
---

# Frozen header

Allows you to freeze the header of the grid so that it will be always visible when scrolling the content with a large number of rows or columns providing a precise view.

{% highlight CSHTML %}

<ej-pivot-grid id="PivotGrid1" >
    <e-frozen-header enable-frozen-headers="true"></e-frozen-header>
</ej-pivot-grid>

{% endhighlight %}

![Frozen header, aka Freeze headers support in ASP NET Core pivot grid control](FrozenHeader_images/row_col_freeze.png)

You can also freeze the row/column headers individually by setting the following properties:

{% highlight CSHTML %}

<ej-pivot-grid id="PivotGrid1" >
    <e-frozen-header enable-frozen-row-headers="true"></e-frozen-header>
</ej-pivot-grid>

{% endhighlight %}

![Frozen row headers in ASP NET Core pivot grid control](FrozenHeader_images/row_freeze.png)

{% highlight CSHTML %}

<ej-pivot-grid id="PivotGrid1" >
    <e-frozen-header enable-frozen-column-headers="true"></e-frozen-header>
</ej-pivot-grid>

{% endhighlight %}

![Frozen column headers in ASP NET Core pivot grid control](FrozenHeader_images/col_freeze.png)