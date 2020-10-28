---
layout: post
title: Getting-Started | PivotGrid | ASP.NET Core | Syncfusion
description: getting started
platform: aspnet-core
control: PivotGrid
documentation: ug
---

# Getting started

>**Important**
Starting with v16.2.0.x, if you refer to Syncfusion assemblies from trial setup or from the NuGet feed, include a license key in your projects. Refer to this [link](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to learn about registering Syncfusion license key in your ASP.NET Core application to use our components.

Refer the [Getting Started](/aspnet-core/getting-started) page of the introduction part to know more about the basic system requirements and the steps to configure the Syncfusion components in an ASP.NET Core application.

Ensure whether all the necessary dependency packages are included within the *bower.json* file as mentioned [here](/aspnet-core/getting-started#configure-syncfusion-components-in-aspnet-core-application), so that the required scripts and CSS to render the pivot grid control will be installed and loaded into the mentioned location (**wwwroot -> lib**) within your project.

Also, check whether the assembly dependency package **Syncfusion.EJ.Pivot**  is added within the *project.json* file.

Now, refer to the necessary scripts and CSS files in your *_Layout.cshtml* page from the **wwwroot -> lib -> syncfusion-javascript** folder.

{% highlight cshtml %}

<html>
<head>
    <environment names="Development">
        <link rel="stylesheet" href="~/lib/bootstrap/dist/css/bootstrap.css" />
        <link rel="stylesheet" href="~/css/site.css" />
        <link href="~/lib/syncfusion-javascript/Content/ej/web/default-theme/ej.web.all.min.css" rel="stylesheet" />
        <link href="~/lib/syncfusion-javascript/Content/ej/web/responsive-css/ej.responsive.css" rel="stylesheet" />
    </environment>
</head>
<body>

    <environment names="Development">
        <script src="~/lib/jquery/dist/jquery.js"></script>
        <script src="~/lib/bootstrap/dist/js/bootstrap.js"></script>
        <script src="~/js/site.js" asp-append-version="true"></script>
        <script src="~/lib/syncfusion-javascript/Scripts/jsrender.min.js"></script>
        <script src="~/lib/syncfusion-javascript/Scripts/ej/web/ej.web.all.min.js"></script>
    </environment>

</body>
</html>

{% endhighlight %}

It is necessary to define the following namespace within the *_viewImports.cshtml* page to make use of the pivot grid control with the tag helper support.

{% highlight cshtml %}

@using Syncfusion.JavaScript
@addTagHelper "*, Syncfusion.EJ"
@addTagHelper "*, Syncfusion.EJ.Pivot"

{% endhighlight %}

N> Script manager should be defined at the bottom of the *_Layout.cshtml* page.

## Relational

This section covers the information required to populate a simple pivot grid with the relational data source.

### Initialize pivot grid

Before initializing the pivot grid, empty the contents of the Index.cshtml file under Views > Home folder and add the following codes:

{% highlight cshtml %}

<ej-pivot-grid id="PivotGrid1"></ej-pivot-grid>

{% endhighlight %}

### Populate pivot grid with data

This section illustrates how to populate the pivot grid control by using a sample JSON data as shown below:

{% highlight cshtml %}

<ej-pivot-grid id="PivotGrid1" load="onload"></ej-pivot-grid>

<script type="text/javascript">
function onload(args) {
    args.model.dataSource.data = [
                    { Amount: 100, Country: "Canada", Date: "FY 2005", Product: "Bike", Quantity: 2, State: "Alberta" },
                    { Amount: 200, Country: "Canada", Date: "FY 2006", Product: "Van", Quantity: 3, State: "British Columbia" },
                    { Amount: 300, Country: "Canada", Date: "FY 2007", Product: "Car", Quantity: 4, State: "Brunswick" },
                    { Amount: 150, Country: "Canada", Date: "FY 2008", Product: "Bike", Quantity: 3, State: "Manitoba" },
                    { Amount: 200, Country: "Canada", Date: "FY 2006", Product: "Car", Quantity: 4, State: "Ontario" },
                    { Amount: 100, Country: "Canada", Date: "FY 2007", Product: "Van", Quantity: 1, State: "Quebec" },
                    { Amount: 200, Country: "France", Date: "FY 2005", Product: "Bike", Quantity: 2, State: "Charente-Maritime" },
                    { Amount: 250, Country: "France", Date: "FY 2006", Product: "Van", Quantity: 4, State: "Essonne" },
                    { Amount: 300, Country: "France", Date: "FY 2007", Product: "Car", Quantity: 3, State: "Garonne (Haute)" },
                    { Amount: 150, Country: "France", Date: "FY 2008", Product: "Van", Quantity: 2, State: "Gers" },
                    { Amount: 200, Country: "Germany", Date: "FY 2006", Product: "Van", Quantity: 3, State: "Bayern" },
                    { Amount: 250, Country: "Germany", Date: "FY 2007", Product: "Car", Quantity: 3, State: "Brandenburg" },
                    { Amount: 150, Country: "Germany", Date: "FY 2008", Product: "Car", Quantity: 4, State: "Hamburg" },
                    { Amount: 200, Country: "Germany", Date: "FY 2008", Product: "Bike", Quantity: 4, State: "Hessen" },
                    { Amount: 150, Country: "Germany", Date: "FY 2007", Product: "Van", Quantity: 3, State: "Nordrhein-Westfalen" },
                    { Amount: 100, Country: "Germany", Date: "FY 2005", Product: "Bike", Quantity: 2, State: "Saarland" },
                    { Amount: 150, Country: "United Kingdom", Date: "FY 2008", Product: "Bike", Quantity: 5, State: "England" },
                    { Amount: 250, Country: "United States", Date: "FY 2007", Product: "Car", Quantity: 4, State: "Alabama" },
                    { Amount: 200, Country: "United States", Date: "FY 2005", Product: "Van", Quantity: 4, State: "California" },
                    { Amount: 100, Country: "United States", Date: "FY 2006", Product: "Bike", Quantity: 2, State: "Colorado" },
                    { Amount: 150, Country: "United States", Date: "FY 2008", Product: "Car", Quantity: 3, State: "New Mexico" },
                    { Amount: 200, Country: "United States", Date: "FY 2005", Product: "Bike", Quantity: 4, State: "New York" },
                    { Amount: 250, Country: "United States", Date: "FY 2008", Product: "Car", Quantity: 3, State: "North Carolina" },
                    { Amount: 300, Country: "United States", Date: "FY 2007", Product: "Van", Quantity: 4, State: "South Carolina" }
    ];
}
</script>

{% endhighlight %}

The JSON data is set to the **"data"** property present in the **"e-data-source"** object. The **"e-data-source"** object allows you to set both data source and fields that should be displayed in the row, column, value, and filter section of the pivot grid control.

{% highlight cshtml %}

<ej-pivot-grid id="PivotGrid1" load="onload">
    <e-data-source>
        <e-pivot-rows>
            <e-row-field field-name="Country" field-caption="Country"></e-row-field>
        </e-pivot-rows>
        <e-pivot-columns>
            <e-column-field field-name="Product" field-caption="Product"></e-column-field>
        </e-pivot-columns>
        <e-pivot-values>
            <e-value-field field-name="Amount" field-caption="Amount"></e-value-field>
        </e-pivot-values>
    </e-data-source>
</ej-pivot-grid>

{% endhighlight %}

The above code will generate a simple pivot grid with "Country" field in the row, "Product" field in column, and "Amount" field in the value section.

![ASP NET Core pivot grid control with relational mode](Getting-Started_images/purejs.png)

### Apply sorting

You can sort a field to an ascending or descending order by using the `sort-order` property. Sorting is applicable only for row and column fields. By default, fields are arranged in the ascending order.

{% highlight cshtml %}

<ej-pivot-grid id="PivotGrid1" load="onload">
    <e-data-source>
        <e-pivot-rows>
            <e-row-field field-name="Country" field-caption="Country" sort-order="Descending"></e-row-field>
        </e-pivot-rows>
        <e-pivot-columns>
            <e-column-field field-name="Product" field-caption="Product"></e-column-field>
        </e-pivot-columns>
        <e-pivot-values>
            <e-value-field field-name="Amount" field-caption="Amount"></e-value-field>
        </e-pivot-values>
    </e-data-source>
</ej-pivot-grid>

{% endhighlight %}

![Sorting in ASP NET pivot grid control](Getting-Started_images/purejssorting.png)

### Sort row/column by date

You can sort a field in ascending or descending order according to date type by using the **sort-order** property. Sorting is applicable only for the row and column fields. By default, fields are arranged in the ascending order.

N> To apply sorting by date, you need to specify the `format` and `format-string` in the field.

{% highlight cshtml %}

<ej-pivot-grid id="PivotGrid1" load="onload">
    <e-data-source>
        <e-pivot-rows>
            <e-row-field field-name="Date" field-caption="Date" format="date" format-string="dd-MM-yyy" sort-order="Descending"></e-row-field>
        </e-pivot-rows>
        <e-pivot-columns>
            <e-column-field field-name="Day" field-caption="Day" format="date" format-string="ddd" sort-order="Ascending"></e-column-field>
        </e-pivot-columns>
        <e-pivot-values>
            <e-value-field field-name="Amount" field-caption="Amount"></e-value-field>
        </e-pivot-values>
    </e-data-source>
</ej-pivot-grid>

<script type="text/javascript">
function onload(args) {
    args.model.dataSource.data = [
            { Amount: 100, Date: "5-1-2017", Day: "Wednesday" },
            { Amount: 200, Date: "1-2-2017", Day: "Sunday" },
            { Amount: 300, Date: "1-1-2018", Day: "Thursday" },
            { Amount: 150, Date: "5-1-2018", Day: "Wednesday" },
            { Amount: 200, Date: "1-2-2017", Day: "Thursday" },
            { Amount: 100, Date: "1-1-2018", Day: "Sunday" },
            { Amount: 200, Date: "5-1-2017", Day: "Wednesday" },
            { Amount: 250, Date: "1-2-2017", Day: "Sunday" }
            //....
        ];
}
</script>

{% endhighlight %}

![Sort by date in ASP NET Core pivot grid control](Getting-Started_images/sortbydate.png)

### Apply summary types

Allow you to specify the required summary type to be used in summary cells of the pivot grid. **"Sum"** is the default summary type. Following are the summary types that are supported:

* Sum
* Average
* Count
* Min
* Max

{% highlight cshtml %}

<ej-pivot-grid id="PivotGrid1" is-responsive="true" load="onload">
    <e-data-source>
        <e-pivot-rows>
            <e-row-field field-name="Country" field-caption="Country"></e-row-field>
        </e-pivot-rows>
        <e-pivot-columns>
            <e-column-field field-name="Product" field-caption="Product"></e-column-field>
        </e-pivot-columns>
        <e-pivot-values>
            <e-value-field field-name="Amount" field-caption="Amount" summary-type="Average"></e-value-field>
            <e-value-field field-name="Quantity" field-caption="Quantity" summary-type="Count"></e-value-field>
        </e-pivot-values>
    </e-data-source>
</ej-pivot-grid>

{% endhighlight %}

![Summary types in ASP NET Core pivot grid control](Getting-Started_images/purejssummarytype.png)

## OLAP

This section covers the information required to populate a simple pivot grid with the OLAP data source.

### Initialize pivot grid

Before initializing the pivot grid, empty the contents of Index.cshtml file under Views > Home folder and add the following codes:

{% highlight cshtml %}

<ej-pivot-grid id="PivotGrid1"></ej-pivot-grid>

{% endhighlight %}

### Populate pivot grid with data source

Initializes the OLAP data source for pivot grid control as shown below:

{% highlight cshtml %}

<ej-pivot-grid id="PivotGrid1">
    <e-data-source catalog="Adventure Works DW 2008 SE" cube="Adventure Works" data="//bi.syncfusion.com/olap/msmdpump.dll">
        <e-pivot-rows>
            <e-row-field field-name="[Date].[Fiscal]"></e-row-field>
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
    </e-data-source>
</ej-pivot-grid>

{% endhighlight %}

The above code will generate a simple pivot grid with "Fiscal" field in the row, "Customer Geography" field in the column, and "Internet Sales Amount" field in the value section.

![ASP NET Core pivot grid control with OLAP client mode](Getting-Started_images/Olap.png)
