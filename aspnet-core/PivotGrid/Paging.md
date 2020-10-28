---
layout: post
title: Paging | PivotGrid | ASP.NET Core | Syncfusion
description: paging
platform: aspnet-core
control: PivotGrid
documentation: ug
---

# Paging

Th paging helps to improve the rendering performance of the pivot client control by dividing the large amount of data into sections and displaying one section at a time. You can enable the paging in pivot client by setting the `enable-paging` property to true.

## Using pager

The page size and current page details for each axis can be provided through the `e-pager-options` property within the `e-data-source` property of the pivot grid. The following properties are available to customize the pager options:

* `categorical-page-size`: Specifies the number of categorical columns to be displayed in each page when applying the paging.
* `series-page-size`: Specifies the number of series rows to be displayed in each page when applying the paging.
* `categorical-current-page`: Specifies the page number to be loaded in the categorical axis by default.
* `series-current-page`: Specifies the page number to be loaded in the series axis by default.

The `mode` property of **ej-pivot-pager** is used to specify whether the categorical pager or series pager or both pagers should be displayed.

The following code snippet illustrates how to display both categorical and series pagers:

{% highlight html %}

    <ej-pivot-grid id="PivotGrid1" load="onload" enable-paging="true">
        <e-data-source>
            <e-pivot-rows>
                <e-row-field field-name="Country" field-caption="Country"></e-row-field>
                <e-row-field field-name="State" field-caption="State"></e-row-field>
            </e-pivot-rows>
            <e-pivot-columns>
                <e-column-field field-name="Date" field-caption="Date"></e-column-field>
            </e-pivot-columns>
            <e-pivot-values>
                <e-value-field field-name="Amount" field-caption="Amount"></e-value-field>
                <e-value-field field-name="Quantity" field-caption="Quantity"></e-value-field>
            </e-pivot-values>
            <e-pager-options categorical-page-size="3" categorical-current-page="1" series-page-size="3" series-current-page="1"></e-pager-options>
        </e-data-source>
    </ej-pivot-grid>
    <ej-pivot-pager id="Pager1" target-control-id="PivotGrid1" mode="Both"></ej-pivot-pager>

{% endhighlight %}

### Pager options

The following are the options available in the pager for navigating pages at run-time:

* Move first: Navigates to the first page.
* Move last: Navigates to the last page.
* Move previous: Navigates to the previous page from the current page.
* Move next: Navigates to the next page from the current page.
* Numeric box: Navigates to the desired page by entering an appropriate page number in the numeric box.

![Paging in ASP NET Core pivot grid control](Paging_images/paging.png)

## Using virtual scrolling

Virtual scrolling is a technique that allows you to view the pivot grid information page by page with the use of vertical and horizontal scrollbar. You can enable virtual scrolling in the pivot grid by setting the `enable-virtual-scrolling` property to true. You can also provide the page size and current page details for each axis through the `e-pager-options` property.

{% highlight html %}

    <ej-pivot-grid id="PivotGrid1" load="onload" enable-virtual-scrolling="true">
        <e-data-source>
            <e-pivot-rows>
                <e-row-field field-name="Country" field-caption="Country"></e-row-field>
                <e-row-field field-name="State" field-caption="State"></e-row-field>
            </e-pivot-rows>
            <e-pivot-columns>
                <e-column-field field-name="Date" field-caption="Date"></e-column-field>
            </e-pivot-columns>
            <e-pivot-values>
                <e-value-field field-name="Amount" field-caption="Amount"></e-value-field>
                <e-value-field field-name="Quantity" field-caption="Quantity"></e-value-field>
            </e-pivot-values>
            <e-pager-options categorical-page-size="3" categorical-current-page="1" series-page-size="3" series-current-page="1"></e-pager-options>
        </e-data-source>
    </ej-pivot-grid>

{% endhighlight %}

![Virtual scrolling in ASP NET Core pivot grid control](Paging_images/virtual-scrolling.png)