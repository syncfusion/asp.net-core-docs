---
title: Getting Started
description: Explains basic operations in XlsIO
platform: aspnet-core
control: XlsIO
documentation: UG
---

# Getting Started

This section explains how to create a simple ASP.NET Core application to create Excel document using XlsIO.

Refer the [Getting Started](/aspnet-core/getting-started) page of the introduction part to know more about the basic system requirements and the steps to configure the Syncfusion components in an ASP.NET Core application.

Ensure once whether all the following dependency packages are included within the project.json file as mentioned [here](/aspnet-core/getting-started#configure-syncfusion-file-format-components-in-aspnet-core-application), to create and manipulate the Excel documents using XlsIO.

<table>
<thead>
<tr>
<th>
Package Name <br/><br/></th><th>
Description<br/><br/></th></tr>
</thead>
<tbody>
<tr>
<td>
Syncfusion.XlsIO.AspNet.Core<br/><br/></td><td>
This package contains the core features needed for creating, reading, manipulating an Excel file.<br/><br/></td></tr>
<tr>
<td>
Syncfusion.Compression.AspNet.Core<br/><br/></td><td>
This package is used to package the Workbook contents.<br/><br/></td></tr>
</tbody>
</table>


## Creating a Hello World sample

The following code example explains how to create a hello world sample.

{% highlight c# %}
using Syncfusion.XlsIO;

//New instance of ExcelEngine is created 

//Equivalent to launching Microsoft Excel with no workbooks open

//Instantiate the spreadsheet creation engine

ExcelEngine excelEngine = new ExcelEngine();

//Instantiate the Excel application object

IApplication application = excelEngine.Excel;

//Assigns default application version

application.DefaultVersion = ExcelVersion.Excel2013;

//A new workbook is created. 

//Equivalent to creating a new workbook in Excel.

//Create a workbook with 1 worksheet.

IWorkbook workbook = application.Workbooks.Create(1);

//Access first worksheet from the workbook.

IWorksheet worksheet = workbook.Worksheets[0];

//Adding text to a cell

worksheet.Range["A1"].Text = "Hello World";

//Defining the ContentType for excel file.

string ContentType = "Application/msexcel";

//Define the file name.

string fileName = "Sample.xlsx";

//Creating stream object.

MemoryStream stream = new MemoryStream();

//Saving the workbook to stream in xlsx format

workbook.SaveAs(stream);

stream.Position = 0;

//Closing the workbook.

workbook.Close();

//Dispose the Excel engine

excelEngine.Dispose();

//Creates a FileContentResult object by using the file contents, content type, and file name.
return File(stream, ContentType, fileName);



{% endhighlight %}