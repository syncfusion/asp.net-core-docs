---
layout: post
title: Exporting | PivotGrid | ASP.NET Core | Syncfusion
description: This document illustrates that how to define exporting and its customization in ASP.NET Core PivotGrid control
platform: aspnet-core
control: PivotGrid
documentation: ug
---

# Exporting

The pivot grid control can be exported to the following file formats:

* Microsoft Excel
* Microsoft Word
* PDF

To perform the exporting operation, the **"Syncfusion.EJ.Export"** dependency library should be referred in the application.

The  control can be exported with the help of **“exportPivotGrid”** method by passing the method name and file name as parameters. Refer to the following code snippet:

{% highlight CSHTML %}

    <ej-pivot-grid id="PivotGrid1" is-responsive="true" load="Load">
        <e-data-source>
            <e-pivot-rows>
                <e-row-field field-name="Country" field-caption="Country"></e-row-field>
            </e-pivot-rows>
            <e-pivot-columns>
                <e-column-field field-name="Date" field-caption="Date"></e-column-field>
            </e-pivot-columns>
            <e-pivot-values>
                <e-value-field field-name="Amount" field-caption="Amount"></e-value-field>
            </e-pivot-values>
        </e-data-source>
    </ej-pivot-grid>

    <ej-button id="ExportBtn" width="100px" height="30px" type="Button" text="Export" click="exportButtonClick" />

    <script type="text/javascript">

        function exportButtonClick(args) {
            var pGridObj = $('#PivotGrid1').data("ejPivotGrid");
            pGridObj.exportPivotGrid("ExcelExport","fileName");
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
        }
   </script>

{% endhighlight %}

The **"Syncfusion.EJ.Export"** namespace should be imported and the following method should be added in the MVC controller file of the application:

{% highlight c# %}

//...
using Syncfusion.EJ.Export;

private IHttpContextAccessor _contextAccessor;

public PivotGridController(IHttpContextAccessor contextAccessor)
{
    _contextAccessor = contextAccessor;
}

public ActionResult ExcelExport()
{
    PivotGridExcelExport pGrid = new PivotGridExcelExport();
    var context = _contextAccessor.HttpContext;
    var args = context.Request.Form.ElementAt(0).Value;
    string fileName = "Sample";
    return pGrid.ExportToExcel(fileName, args, context.Response);
}

{% endhighlight %}

## Excel export

The pivot grid allows you to export its content to Excel document for future archival, references, and analysis purposes. This can be achieved with the help of **"ExportToExcel"** method by passing the file name as parameter.

{% highlight js %}

    <script type="text/javascript">

       function exportButtonClick(args)
       {
          var pGridObj = $('#PivotGrid1').data("ejPivotGrid");
          pGridObj.exportPivotGrid("ExcelExport","fileName");
       }

   </script>

{% endhighlight %}

The following method should be added in the MVC controller file of the application:

{% highlight c# %}

public ActionResult ExcelExport()
{
    PivotGridExcelExport pGrid = new PivotGridExcelExport();
    var context = _contextAccessor.HttpContext;
    var args = context.Request.Form.ElementAt(0).Value;
    string fileName = "Sample";
    return pGrid.ExportToExcel(fileName, args, context.Response);
}

{% endhighlight %}

## Word export

The pivot grid allows you to export its content to Word document for future archival, references, and analysis purposes. This can be achieved with the help of **"ExportToWord"** method by passing the file name as parameter.

{% highlight js %}

    <script type="text/javascript">

       function exportButtonClick(args)
       {
          var pGridObj = $('#PivotGrid1').data("ejPivotGrid");
          pGridObj.exportPivotGrid("WordExport","fileName");
       }

   </script>

{% endhighlight %}

The following method should be added in the MVC controller file of the application:

{% highlight c# %}

        public ActionResult WordExport()
        {
            PivotGridWordExport pGrid = new PivotGridWordExport();
            var context = _contextAccessor.HttpContext;
            var args = context.Request.Form.ElementAt(0).Value;
            string fileName = "Sample";
            return pGrid.ExportToWord(fileName, args, context.Response);
        }

{% endhighlight %}

## PDF export

The pivot grid allows you to export its content to PDF document for future archival, references, and analysis purposes. This can be achieved with the help of **"ExportToPDF"** method by passing the file name as parameter.

{% highlight js %}

    <script type="text/javascript">

       function exportButtonClick(args)
       {
          var pGridObj = $('#PivotGrid1').data("ejPivotGrid");
          pGridObj.exportPivotGrid("PDFExport","fileName");
       }

   </script>

{% endhighlight %}

The following method should be added in the MVC controller file of the application:

{% highlight c# %}

public ActionResult PDFExport()
{
    PivotGridPDFExport pGrid = new PivotGridPDFExport();
    var context = _contextAccessor.HttpContext;
    var args = context.Request.Form.ElementAt(0).Value;
    string fileName = "Sample";
    return pGrid.ExportToPDF(fileName, args, context.Response);
}

{% endhighlight %}

The following screenshot shows the pivot grid control exported to an Excel document:

![Export-Excel](Exporting_images/ExportOLAPExcel.png)

The following screenshot shows the pivot grid control exported to a Word document:

![Export-Word](Exporting_images/ExportOLAPWord.png)

The following screenshot shows the pivot grid control exported to a PDF document:

![Export-PDF](Exporting_images/ExportOLAPPDF.png)

N> Grand total and sub-totals can be hidden while exporting the document.