---
layout: post
title: Getting Started with ASP.NET Core ReportWriter Control | Syncfusion
description: Learn here about getting started with Syncfusion ASP.NET Core ReportWriter Control, its elements, and more.
platform: aspnet-core
control: ReportWriter
documentation: ug
---

# Getting Started with ASP.NET Core ReportWriter

The report writer is a class library that is used to export the RDL/RDLC report with popular file formats like PDF, Microsoft Word, and Microsoft Excel without previewing the report in web page. This section describes how to export the RDL report to PDF in ASP.NET Core application using the `ReportWriter`.


## Environment setup
Refer to the [installation](https://help.syncfusion.com/aspnet-core/installation-and-upgrade/system-requirements) page to know more about the basic steps required to configure the Syncfusion components to use with ASP.NET Core application. 

N> NuGet package reference will be mostly preferred with ASP.NET Core development to setup the environment without installation. If you missed to explore, refer to the [nuget-package-manager-settings](https://help.syncfusion.com/aspnet-core/visual-studio-integration/nuget-packages) to configure the Syncfusion NuGet source.

### References
You should add the following packages for the report viewer:

<table>
<tr>
<th>
Package</th>
<th>
Purpose
</th>
</tr>
<tr>
<td>Syncfusion.Report.NETStandard</td>
<td>It contains the `ReportWriter` class library to generate file format reports using RDL and RDLC report.</td>
</tr>
<tr>
<td>Syncfusion.Compression.NETStandard</td>
<td>Supports for exporting the report to PDF, Microsoft Word, and Microsoft Excel format. It is a base library for the packages <b>Syncfusion.Pdf.NETStandard</b> , <b>Syncfusion.DocIO.NETStandard</b> and <b>Syncfusion.XlsIO.NETStandard</b>. </td>
</tr>
<tr>
<td>Syncfusion.Pdf.NETStandard</td>
<td>Supports for exporting the report to a PDF.</td>
</tr>
<tr>
<td>Syncfusion.DocIO.NETStandard</td>
<td>Supports for exporting the report to a Word.</td>
</tr>
<tr>
<td>Syncfusion.XlsIO.NETStandard</td>
<td>Supports for exporting the report to an Excel.</td>
</tr>
<tr>
<td>Syncfusion.OfficeChart.NETStandard</td>
<td>It is a base library of the <b>Syncfusion.XlsIO.NETStandard</b> package.</td>
</tr>
<tr>
<td>System.Data.SqlClient</td>
<td>This is an optional package for the report viewer. It should be referred in project when renders the RDL report and which contains the SQL Server and SQL Azure datasource. Also, the package version should be higher of 4.1.0 . </td>
</tr>
</table>


## Generate the PDF file

You should use the `Save` method in `ReportWriter` to generate the PDF document along with information of the report stream, it will return the generated file as `Stream`. The report writer supports generating the files with formats of PDF, Word, and Excel. Here, the sample codes are explained to generate the PDF and the `WriterFormat` is used as PDF.

{% highlight C# %}
public class HomeController : Controller
    {
        // IHostingEnvironment used with sample to get the application data from wwwroot.
        private Microsoft.AspNetCore.Hosting.IHostingEnvironment _hostingEnvironment;

        // IHostingEnvironment initialized with controller to get the data from application data folder.
        public HomeController(Microsoft.AspNetCore.Hosting.IHostingEnvironment hostingEnvironment)
        {
            _hostingEnvironment = hostingEnvironment;
        }

        [HttpPost]
        public IActionResult Pdf()
        {

            string basePath = _hostingEnvironment.WebRootPath;
            // Here, we have loaded the sample report report from application the folder wwwroot. 
            // Invoice.rdl should be there in wwwroot application folder.
            FileStream inputStream = new FileStream(basePath + @"\Invoice.rdl", FileMode.Open, FileAccess.Read);
            Syncfusion.ReportWriter.ReportWriter writer = new Syncfusion.ReportWriter.ReportWriter(inputStream);

            // Steps to generate PDF report using Report Writer. 
            MemoryStream memoryStream = new MemoryStream();
            writer.Save(memoryStream, Syncfusion.ReportWriter.WriterFormat.PDF);

            // Download the generated from client.
            memoryStream.Position = 0;
            FileStreamResult fileStreamResult = new FileStreamResult(memoryStream, "application/pdf");
            fileStreamResult.FileDownloadName = "Invoice.pdf";
            return fileStreamResult;
        }
}

{% endhighlight %}

N> You cannot load the application report with path information in the ASP.NET Core. So, you should load the report as `stream` like an example provided above in the `Pdf` method.

This is an example home page to invoke the Web API from client for the above sample codes:

{% highlight CSHTML %}
    @{Html.BeginForm("Pdf", "Home", FormMethod.Post);
    {
        <div>
            <input type="submit" value="Generate PDF" style="width: 150px;" />
        </div>
    }
        Html.EndForm();
    }
{% endhighlight %}

## Parameters for report 

`SetParameters` methods can be used with report writer to generate the file format report based on parameters. The following sample code explains passing the parameter based on the information received from the client.

{% highlight C# %}
public class HomeController : Controller
    {
        // IHostingEnvironment used with sample to get the application data from wwwroot.
        private Microsoft.AspNetCore.Hosting.IHostingEnvironment _hostingEnvironment;

        // IHostingEnvironment initialized with controller to get the data from application data folder.
        public HomeController(Microsoft.AspNetCore.Hosting.IHostingEnvironment hostingEnvironment)
        {
            _hostingEnvironment = hostingEnvironment;
        }

        [HttpPost]
        public IActionResult Pdf()
        {

            string basePath = _hostingEnvironment.WebRootPath;
            // Here, we have loaded the sample report report from application the folder wwwroot. 
            // Invoice.rdl should be there in wwwroot application folder.
            FileStream inputStream = new FileStream(basePath + @"\Invoice.rdl", FileMode.Open, FileAccess.Read);
            Syncfusion.ReportWriter.ReportWriter writer = new Syncfusion.ReportWriter.ReportWriter(inputStream);

            // Assigning the report parameter based on selected value from user.
            string invoiceID = this.HttpContext.Request.Form["invoiceId"].ToString();

            List<Syncfusion.Report.ReportParameter> parameters = new List<Syncfusion.Report.ReportParameter>();
            Syncfusion.Report.ReportParameter param = new Syncfusion.Report.ReportParameter();
            param.Name = "InvoiceID";
            param.Values = new List<string>() { invoiceID };
            parameters.Add(param);
            writer.SetParameters(parameters);

            // Steps to generate PDF report using Report Writer.
            MemoryStream memoryStream = new MemoryStream();
            writer.Save(memoryStream, Syncfusion.ReportWriter.WriterFormat.PDF);

            // Download the generated from client.
            memoryStream.Position = 0;
            FileStreamResult fileStreamResult = new FileStreamResult(memoryStream, "application/pdf");
            fileStreamResult.FileDownloadName = "Invoice.pdf";
            return fileStreamResult;
        }
}

{% endhighlight %}

This is an example page to invoke the Web API from client for the above sample codes.

{% highlight CSHTML %}
    @{Html.BeginForm("Pdf", "Home", FormMethod.Post);
    {
        <div>
            <input name="invoiceId" value="10255" style="width: 150px;" />
            <input type="submit" value="Generate PDF" style="width: 150px;" />
        </div>
    }
        Html.EndForm();
    }
{% endhighlight %}    

N> The invoice sample report can be obtained from the Syncfusion ASP.NET Core sample browser installed location (wwwroot\reports\invoice.rdl).