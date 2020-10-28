---
layout: post
title: Paging | PivotClient | ASP.NET Core | Syncfusion
description: This document illustrates that how to define paging with respective to the modes in ASP.NET Core  PivotClient control
platform: aspnet-core
control: PivotClient
documentation: ug
---

# Paging

Paging helps to improve the rendering performance of the pivot client control by dividing the large amount of data into sections and displaying one section at a time. You can enable the paging in the pivot client by setting the `enable-paging` property to true.

## Using pager

The page size and current page details for each axis can be provided through the `e-pager-options` property within the `e-data-source` property of pivot client. The following properties are available to customize the pager options:

* `categorical-page-size`: Specifies the number of categorical columns to be displayed in each page when applying the paging.
* `series-page-size`: Specifies the number of series rows to be displayed in each page when applying the paging.
* `categorical-current-page`: Specifies the page number to be loaded in the categorical axis by default.
* `series-current-page`: Specifies the page number to be loaded in the series axis by default.

{% highlight CSHTML %}

    <ej-pivot-client id="PivotClient1" enable-complete-data-export="true" title="OLAP Browser" enable-paging="true" before-export="Export" render-success="setChartProperties" load-report="reportSettings" fetch-report="reportSettings" save-report="reportSettings">
        <e-size width="910px"></e-size>
        <e-data-source catalog="Adventure Works DW 2008 SE" cube="Adventure Works" data="//bi.syncfusion.com/olap/msmdpump.dll">
            <e-pivot-rows>
                <e-row-field field-name="[Date].[Date]"></e-row-field>
            </e-pivot-rows>
            <e-pivot-columns>
                <e-column-field field-name="[Customer].[Customer Geography]"></e-column-field>
            </e-pivot-columns>
            <e-pivot-values>
                <e-value-field axis="Column">
                    <e-measures>
                        <e-measure-items field-name="[Measures].[Internet Sales Amount]"></e-measure-items>
                    </e-measures>
                </e-value-field>
            </e-pivot-values>
            <e-pager-options categorical-page-size="3" categorical-current-page="1" series-page-size="3" series-current-page="1"></e-pager-options>
        </e-data-source>
    </ej-pivot-client>

{% endhighlight %}

### Pager options

The following are the options available in the pager for navigating pages at run-time:

* Move first: Navigates to the first page.
* Move last: Navigates to the last page.
* Move previous: Navigates to the previous page from the current page.
* Move next: Navigates to the next page from the current page.
* Numeric box: Navigates to the desired page by entering an appropriate page number in the numeric box.

![Paging in ASP NET Core pivot client control](Paging_images/paging.png)

## Using virtual scrolling

The virtual scrolling is a technique that allows you to view the pivot client information page by page by using the vertical and horizontal scrollbar. You can enable the virtual scrolling in pivot client by setting the `enable-virtual-scrolling` property to true. You can also provide the page size and current page details for each axis through the `e-pager-options` property.

{% highlight CSHTML %}

    <ej-pivot-client id="PivotClient1" title="OLAP Browser" enable-virtual-scrolling="true"  load="onLoad">
        <e-size width="910px"></e-size>
        <e-data-source catalog="Adventure Works DW 2008 SE" cube="Adventure Works" data="//bi.syncfusion.com/olap/msmdpump.dll">
            <e-pivot-rows>
                <e-row-field field-name="[Date].[Date]"></e-row-field>
            </e-pivot-rows>
            <e-pivot-columns>
                <e-column-field field-name="[Customer].[Customer Geography]"></e-column-field>
            </e-pivot-columns>
            <e-pivot-values>
                <e-value-field axis="Column">
                    <e-measures>
                        <e-measure-items field-name="[Measures].[Internet Sales Amount]"></e-measure-items>
                    </e-measures>
                </e-value-field>
            </e-pivot-values>
            <e-pager-options categorical-page-size="3" categorical-current-page="1" series-page-size="3" series-current-page="1"></e-pager-options>
        </e-data-source>
    </ej-pivot-client>

{% endhighlight %}

![Virtual scrolling in ASP NET Core pivot client control](Paging_images/virtual-scrolling.png)