---
layout: post
title:  GrandTotal Hiding | PivotGrid | ASP.NET Core | Syncfusion
description: GrandTotal Hiding
platform: aspnet-core
control: PivotGrid
documentation: ug
---

# Grand total hiding

Grand total hiding can be classified into three categories as follows:

* Row grand total hiding
* Column grand total hiding
* Both

## Row grand total hiding

You can hide the **Grand Total** in row alone by setting the `enable-row-grand-total` property to `false`.

{% highlight CSHTML %}

<ej-pivot-grid id="PivotGrid1" enable-row-grand-total="false"></ej-pivot-grid>

{% endhighlight %}

![Hiding row totals in ASP NET Core pivot grid control](GrandTotal-Hiding_images/enableRowGrandTotal.png)

## Column grand total hiding

You can hide the **Grand Total** in column alone by setting the `enable-column-grand-total` property to `false`.

{% highlight CSHTML %}

<ej-pivot-grid id="PivotGrid1" enable-column-grand-total="false"></ej-pivot-grid>

{% endhighlight %}

![Hiding column totals in ASP NET Core pivot grid control](GrandTotal-Hiding_images/enableColumnGrandTotal.png)

## Both

You can hide the **Grand Total** in both row and column by setting the `enable-grand-total` property to `false`.

{% highlight CSHTML %}

<ej-pivot-grid id="PivotGrid1" enable-grand-total="false"></ej-pivot-grid>

{% endhighlight %}

![Hiding totals in ASP NET Core pivot grid control](GrandTotal-Hiding_images/enableGrandTotal.png)