---
layout: post
title: Number format | PivotGrid | ASP.NET Core | Syncfusion
description: This document illustrates that how to define number formats and its types in ASP.NET Core PivotGrid control
platform: aspnet-core
control: PivotGrid
documentation: ug
---

# Number format

I> This feature is applicable only for the relational data source at client mode.

Allows you to specify the required number format to be used in values of the pivot grid by setting the `format` option. Following are the supported number formats:

* number
* decimal
* currency
* percentage
* date
* time
* scientific
* accounting
* fraction
* string

{% highlight CSHTML %}

<ej-pivot-grid id="PivotGrid1" load="onload">
    <e-data-source>
        <e-pivot-rows>
            <e-row-field field-name="State" field-caption="State"></e-row-field>
            <e-row-field field-name="Country" field-caption="Country"></e-row-field>
        </e-pivot-rows>
        <e-pivot-columns>
            <e-column-field field-name="Product" field-caption="Product"></e-column-field>
        </e-pivot-columns>
        <e-pivot-values>
            <e-value-field field-name="Amount" field-caption="Amount" format="currency"></e-value-field>
            <e-value-field field-name="Quantity" field-caption="Quantity" format="decimal"></e-value-field>
        </e-pivot-values>
    </e-data-source>
</ej-pivot-grid>

 {% endhighlight %}

![Number formatting in ASP NET Core pivot grid relational client mode](Number-Format_images/Numberformat.png)

