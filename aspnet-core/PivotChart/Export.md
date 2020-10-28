---
layout: post
title: Exporting | PivotChart | ASP.NET Core | Syncfusion
description: This document illustrates that how to define exporting and its customization in ASP.NET Core PivotChart control
platform: aspnet-core
control: PivotChart
documentation: ug
---

# Exporting

The pivot chart control can be exported to following file formats:

* Microsoft Excel
* Microsoft Word
* PDF
* Image

To perform the exporting operation, the **"Syncfusion.EJ.Export"** dependency library should be referred in the application.

The pivot chart control can be exported with the help of **“exportPivotChart”** method by passing the method name and the file name as parameters. Refer to the following code snippet:

{% highlight CSHTML %}

    <ej-pivot-chart id="PivotChart1" is-responsive="true" load="Load" pre-render="preRender">
        <e-data-source>
            <e-pivot-rows>
                <e-row-field field-name="Product" field-caption="Product"></e-row-field>
                <e-row-field field-name="Date" field-caption="Date"></e-row-field>
            </e-pivot-rows>
            <e-pivot-columns>
                <e-column-field field-name="Country" field-caption="Country"></e-column-field>
            </e-pivot-columns>
            <e-pivot-values>
                <e-value-field field-name="Amount" field-caption="Amount"></e-value-field>
            </e-pivot-values>
        </e-data-source>
        <e-common-series-options type="Column" enable-animation="true">
            <e-chart-tooltip visible="true"></e-chart-tooltip>
        </e-common-series-options>
        <e-size width="100%" height="460px"></e-size>
        <e-primary-x-axis>
            <e-title text="Date - Fiscal"></e-title>
        </e-primary-x-axis>
        <e-primary-y-axis>
            <e-title text="Amount"></e-title>
        </e-primary-y-axis>
        <e-legend row-count="1"></e-legend>
    </ej-pivot-chart>

    <ej-button id="ExportBtn" width="100px" height="30px" type="Button" text="Export" click="exportBtnClick" />

    <script type="text/javascript">

        function exportButtonClick(args) {
            var PivotChartObj = $('#PivotChart1').data("ejPivotChart");
            var ChartObj = $("#" + PivotChartObj._id + "Container").data("ejChart");
            ChartObj.model.border.opacity = 1;
            ChartObj.redraw();
            PivotChartObj.exportPivotChart("ExportToExcel", "Sample", ej.PivotChart.ExportOptions.Excel);
        }

            function Load(args) {
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
            loadTheme(args);
        }
   </script>

{% endhighlight %}

The **"Syncfusion.EJ.Export"** namespace should be imported and the following method should be added in the MVC controller file of the application:

{% highlight c# %}

//...
using Syncfusion.EJ.Export;

private IHttpContextAccessor _contextAccessor;

public PivotChartController(IHttpContextAccessor contextAccessor)
{
    _contextAccessor = contextAccessor;
}

public ActionResult ExportToExcel()
{
    PivotChartExcelExport pivotChart = new PivotChartExcelExport();
    var context = _contextAccessor.HttpContext;
    var args = context.Request.Form.ElementAt(0).Value;
    Dictionary<string, string> clientParams = JsonConvert.DeserializeObject<Dictionary<string, string>>(args);
    clientParams["fileName"] = "sample";
    return pivotChart.ExportToExcel(clientParams);
}

{% endhighlight %}

## Excel export

The pivot chart allows you to export its content to an Excel document for future archival, references, and analysis purposes. This can be achieved with the help of **"ExportToExcel"** method by passing the file name as parameter.

{% highlight js %}

    <script type="text/javascript">

        function exportButtonClick(args) {
            var PivotChartObj = $('#PivotChart1').data("ejPivotChart");
            var ChartObj = $("#" + PivotChartObj._id + "Container").data("ejChart");
            ChartObj.model.border.opacity = 1;
            ChartObj.redraw();
            PivotChartObj.exportPivotChart("ExportToExcel", "Sample", ej.PivotChart.ExportOptions.Excel);
        }

    </script>

{% endhighlight %}

The following method should be added in the MVC controller file of the application:

{% highlight c# %}

public ActionResult ExportToExcel()
{
    PivotChartExcelExport pivotChart = new PivotChartExcelExport();
    var context = _contextAccessor.HttpContext;
    var args = context.Request.Form.ElementAt(0).Value;
    Dictionary<string, string> clientParams = JsonConvert.DeserializeObject<Dictionary<string, string>>(args);
    clientParams["fileName"] = "sample";
    return pivotChart.ExportToExcel(clientParams);
}

{% endhighlight %}

## Word export

The pivot chart allows you to export its content to a Word document for future archival, references, and analysis purposes. This can be achieved with the help of **"ExportToWord"** method by passing the file name as parameter.

{% highlight js %}

    <script type="text/javascript">

       function exportButtonClick(args) {
            var PivotChartObj = $('#PivotChart1').data("ejPivotChart");
            var ChartObj = $("#" + PivotChartObj._id + "Container").data("ejChart");
            ChartObj.model.size.width = "700px";
            ChartObj.redraw();
            PivotChartObj.exportPivotChart("ExportToWord", "Sample", ej.PivotChart.ExportOptions.Word);
            ChartObj.model.size.width = "100%";
            ChartObj.redraw();
        }

   </script>

{% endhighlight %}

The following method should be added in the MVC controller file of the application:

{% highlight c# %}

public ActionResult ExportToWord()
{
    PivotChartWordExport pivotChart = new PivotChartWordExport();
    var context = _contextAccessor.HttpContext;
    var args = context.Request.Form.ElementAt(0).Value;
    Dictionary<string, string> clientParams = JsonConvert.DeserializeObject<Dictionary<string, string>>(args);
    clientParams["fileName"] = "sample";
    return pivotChart.ExportToWord(clientParams);
}

{% endhighlight %}

## PDF export

The pivot chart allows you to export its content to a PDF document for future archival, references, and analysis purposes. This can be achieved with the help of **"ExportToPDF"** method by passing the file name as parameter.

{% highlight js %}

    <script type="text/javascript">

       function exportButtonClick(args) {
            var PivotChartObj = $('#PivotChart1').data("ejPivotChart");
            var ChartObj = $("#" + PivotChartObj._id + "Container").data("ejChart");
            ChartObj.model.size.width = "500px";
            ChartObj.redraw();
            PivotChartObj.exportPivotChart("ExportToPDF", "Sample", ej.PivotChart.ExportOptions.PDF);
            ChartObj.model.size.width = "100%";
            ChartObj.redraw();
        }

   </script>

{% endhighlight %}

The following method should be added in the MVC controller file of the application:

{% highlight c# %}

public ActionResult ExportToPDF()
{
    PivotChartPDFExport pivotChart = new PivotChartPDFExport();
    var context = _contextAccessor.HttpContext;
    var args = context.Request.Form.ElementAt(0).Value;
    Dictionary<string, string> clientParams = JsonConvert.DeserializeObject<Dictionary<string, string>>(args);
    clientParams["fileName"] = "sample";
    return pivotChart.ExportToPDF(clientParams);
}

{% endhighlight %}

## Image export

The pivot chart allows you to export its content to an image format for future archival, references, and analysis purposes. The following image formats are supported by the pivot chart:

* PNG
* EMF
* JPG
* GIF
* BMP

This can be achieved with the help of **"ExportToImage"** method by passing the file name and image format (_ExportOptions.PNG_) as parameters.

{% highlight js %}

    <script type="text/javascript">

       function exportButtonClick(args) {
            var PivotChartObj = $('#PivotChart1').data("ejPivotChart");
            var ChartObj = $("#" + PivotChartObj._id + "Container").data("ejChart");
            ChartObj.model.border.opacity = 1;
            ChartObj.redraw();
            PivotChartObj.exportPivotChart("ExportToImage", "Sample", ej.PivotChart.ExportOptions.PNG);
        }

        function preRender(sender) {
            if (sender.model.theme.indexOf("light") > -1 || sender.model.theme == "bootstrap" || sender.model.theme == "material") {
                sender.model.background = "white";
                sender.model.chartArea.background = "white";
            }
            else {
                sender.model.background = "black";
                sender.model.chartArea.background = "black"
            }
        }

   </script>

{% endhighlight %}

The following method should be added in the MVC controller file of the application:

{% highlight c# %}

static string path = "E:\\";

public void ExportToImage()
{
    PivotChartImageExport pivotChart = new PivotChartImageExport();
    var context = _contextAccessor.HttpContext;
    var args = context.Request.Form.ElementAt(0).Value;
    Dictionary<string, string> clientParams = JsonConvert.DeserializeObject<Dictionary<string, string>>(args);
    clientParams.Add("Path", path);
    clientParams["fileName"] = "sample";
    pivotChart.ExportToImage(clientParams);
}

{% endhighlight %}

The following screenshot shows the pivot chart control exported to an Excel document:

![Excel exporting in ASP NET Core pivot chart control](Export_images/Export_ExcelClient.png)

The following screenshot shows the pivot chart control exported to a PDF document:

![PDF exporting in ASP NET Core pivot chart control](Export_images/Export_PDFClient.png)

The following screenshot shows the pivot chart control exported to a Word document:

![Word exporting in ASP NET Core pivot chart control](Export_images/Export_WordClient.png)

The following screenshot shows the pivot chart control exported to a PNG format:

![PNG exporting in ASP NET Core pivot chart control](Export_images/Export_PNGClient.png)