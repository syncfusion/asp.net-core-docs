---
layout: post
title: Getting-Started | PivotClient | ASP.NET Core | Syncfusion
description: getting started
platform: aspnet-core
control: PivotClient
documentation: ug
---

# Getting started

>**Important**
Starting with v16.2.0.x, if you refer to Syncfusion assemblies from trial setup or from the NuGet feed, include a license key in your projects. Refer to this [link](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to learn about registering Syncfusion license key in your ASP.NET Core application to use our components.

Refer to the [Getting Started](/aspnet-core/getting-started) page of the introduction part to know more about the basic system requirements and the steps to configure the Syncfusion components in an ASP.NET Core application.

Ensure whether all the necessary dependency packages are included within the *bower.json* file as mentioned [here](/aspnet-core/getting-started#configure-syncfusion-components-in-aspnet-core-application), so that the required scripts and CSS to render the pivot client control will be installed and loaded into the mentioned location (**wwwroot -> lib**) within your project.

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

It is necessary to define the following namespace within the *_viewImports.cshtml* page to make use of the pivot client control with the tag helper support.

{% highlight cshtml %}

@using Syncfusion.JavaScript
@addTagHelper "*, Syncfusion.EJ"
@addTagHelper "*, Syncfusion.EJ.Pivot"

{% endhighlight %}

N> Script manager should be defined at the bottom of the *_Layout.cshtml* page.

## Relational

This section covers the information required to populate a simple pivot client with relational data source.

### Initialize pivot client

Before initializing the pivot client, empty the contents of Index.cshtml file under Views > Home folder and add the following codes:

{% highlight cshtml %}

<ej-pivot-client id="PivotClient1" title="Relational Browser"></ej-pivot-client>

{% endhighlight %}

### Populate pivot client with data

This section illustrates how to populate the pivot client control by using a sample JSON data as shown below:

{% highlight cshtml %}

<ej-pivot-client id="PivotClient1" title="Relational Browser" load="onload"></ej-pivot-client>

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

The JSON data is set to the **"data"** property present in the **"e-data-source"** object. The **"e-data-source"** object allows you to set both the data source and fields that should be displayed in the row, column, value, and filter section of the pivot client control.

{% highlight cshtml %}

<ej-pivot-client id="PivotClient1" title="Relational Browser" load="onload">
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
</ej-pivot-client>

{% endhighlight %}

Now, the pivot client is rendered with pivot chart, and the pivot grid is rendered with “Country” field in the row, “Product” field in the column, and “Amount” field in the value section.

![ASP NET Core pivot client control rendered with relational client mode](Getting-Started_images/purejs.png)

### Summary Types

Allows you to perform calculations over a group of values using `summary-type` option. This property includes several types of aggregations like sum, average, minimum, maximum etc. You can see the totals of PivotClient control with any one of the below mentioned summary types. 

Also, summary type options are added in the context menu of pivot buttons, in values section, to change the resultant summary value dynamically.

 The following summary types have been supported. By default, `sum` is applied.

* Sum
* Average
* Count
* Min
* Max

Refer the following code sample to implement summary type through code behind.

{% highlight cshtml %}

<ej-pivot-client id="PivotClient1" load="onload">
    <e-data-source>
        <e-pivot-rows>
            <e-row-field field-name="Country" field-caption="Country"></e-row-field>
        </e-pivot-rows>
        <e-pivot-columns>
            <e-column-field field-name="Product" field-caption="Product"></e-column-field>
        </e-pivot-columns>
        <e-pivot-values>
            <e-value-field field-name="Amount" field-caption="Amount" summary-type="Count"></e-value-field>
            <e-value-field field-name="Quantity" field-caption="Quantity" summary-type="Min"></e-value-field>
        </e-pivot-values>
    </e-data-source>
</ej-pivot-client>

<script type="text/javascript">
function onload(args) {
    args.model.dataSource.data = pivot_dataset;
}
</script>

{% endhighlight %}

![Summary types in ASP NET Core pivot](Getting-Started_images/client_mode_summary.png)


## OLAP

This section covers the information required to populate a simple pivot client with OLAP data source.

### Initialize pivot client

Before initializing the pivot client, empty the contents of Index.cshtml file under Views > Home folder and add the following codes:

{% highlight cshtml %}

<ej-pivot-client id="PivotClient1" title="OLAP Browser"></ej-pivot-client>

{% endhighlight %}

### Populate pivot grid with data source

Initializes the OLAP data source for the pivot client control as shown below:

{% highlight cshtml %}

<ej-pivot-client id="PivotClient1" title="OLAP Browser">
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
</ej-pivot-client>

{% endhighlight %}

Now, the pivot client is rendered with pivot chart, and the pivot grid is rendered with “Customer Geography” field in the column, “Fiscal” field in the row, and “Internet Sales Amount” field in the value section.

![ASP NET Core pivot client control rendered with OLAP client mode](Getting-Started_images/OlapClientside.png)
