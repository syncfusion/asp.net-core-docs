---
layout: post
title:  SubTotal Hiding | PivotGrid | ASP.NET Core | Syncfusion
description: SubTotal Hiding
platform: aspnet-core
control: PivotGrid
documentation: ug
---

# Sub total hiding

N> This feature is applicable only for the relational data source.

You can hide the **Sub Total** for respective fields in rows and columns by setting the `show-sub-total` property to `false`.

## Client Mode

{% highlight CSHTML %}

<ej-pivot-grid id="PivotGrid1" load="onload">
    <e-data-source>
        <e-pivot-rows>
            <e-row-field field-name="Date" field-caption="Date" show-sub-total="false"></e-row-field>
            <e-row-field field-name="Product" field-caption="Product"></e-row-field>
        </e-pivot-rows>
        <e-pivot-columns>
            <e-column-field field-name="Country" field-caption="Country"></e-column-field>
        </e-pivot-columns>
        <e-pivot-values>
            <e-value-field field-name="Amount" field-caption="Amount"></e-value-field>
            <e-value-field field-name="Quantity" field-caption="Quantity"></e-value-field>
        </e-pivot-values>
    </e-data-source>
</ej-pivot-grid>
{% endhighlight %}

![SubTotal hiding support in ASP NET Core pivot grid control](SubTotal-Hiding_images/SubTotal.png)
