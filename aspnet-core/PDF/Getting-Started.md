---
layout: post
title: Getting Started with ASP.NET Core PDF control | Syncfusion
description: Learn here about getting started with Syncfusion Essential Studio ASP.NET Core PDF control, its elements, and more.
platform: aspnet-core
control: PDF
documentation: UG
---
# Getting Started with ASP.NET Core PDF
Refer the [Getting Started](https://help.syncfusion.com/aspnet-core/gettingstarted/getting-started-1-1-0) page of the introduction part to know more about the basic [system requirements](https://help.syncfusion.com/aspnet-core/gettingstarted/getting-started-1-1-0#system-requirements) and the steps to [configure Syncfusion File Format components](https://help.syncfusion.com/aspnet-core/gettingstarted/getting-started-1-1-0#configure-syncfusion-file-format-components-in-aspnet-core-application) in an ASP.NET Core application. Ensure once whether all the following dependency packages are included within the project.json file as mentioned [here](https://help.syncfusion.com/aspnet-core/gettingstarted/getting-started-1-1-0#configure-syncfusion-file-format-components-in-aspnet-core-application), to create and manipulate the PDF documents using Essential PDF.
To create a PDF document the following assemblies have to be added as reference to the project.

<table>
  <tr>
    <th>Assembly Name</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>Syncfusion.Pdf.AspNet.Core</td>
    <td>This assembly contains the core feature for creating, manipulating and saving PDF documents.</td>
  </tr>
  <tr>
    <td>Syncfusion.Compression.AspNet.Core</td>
    <td>This assembly is required for compressing the internal contents of a PDF document.</td>
  </tr>
</table>

Include the following namespaces in your .cs file as shown below.
{% tabs %}
{% highlight c# %}
using Syncfusion.Pdf;
using Syncfusion.Pdf.Parsing;
using Syncfusion.Pdf.Graphics;
using Syncfusion.Pdf.Grid;
{% endhighlight %}

{% endtabs %}

## Creating a PDF document with simple text

The following code example shows how to create a PDF document with simple text.
{% tabs %}
{% highlight c# %}
//Create a new PDF document.
PdfDocument document = new PdfDocument();
//Add a page to the document.
PdfPage page = document.Pages.Add();
//Create PDF graphics for the page.
PdfGraphics graphics = page.Graphics;
//Set the standard font.
PdfFont font = new PdfStandardFont(PdfFontFamily.Helvetica, 20);
//Draw the text.
graphics.DrawString("Hello World!!!", font, PdfBrushes.Black, new PointF(0, 0));
//Save the document.
document.Save("Output.pdf");
//Close the document.
document.Close(true);
{% endhighlight %}
{% endtabs %}


## Saving the document 

The following code example illustrates how to download the PDF document in browser after saving the document.
{% tabs %}
{% highlight c# %}

//Create a new PDF document

PdfDocument document = new PdfDocument();

//Add a page to the document

PdfPage page = document.Pages.Add();

//Create PDF graphics for the page

PdfGraphics graphics = page.Graphics;

//Draw the rectangle

graphics.DrawRectangle(PdfPens.Black, new RectangleF(0, 0, 100, 100));

//Saving the PDF to the MemoryStream
MemoryStream ms = new MemoryStream();
document.Save(ms);
//If the position is not set to '0' then the PDF will be empty.
ms.Position = 0;

//Download the PDF document in the browser.
FileStreamResult fileStreamResult = new FileStreamResult(ms, "application/pdf");
fileStreamResult.FileDownloadName = "Sample.pdf";
return fileStreamResult;



{% endhighlight %}
{% endtabs %}