---
layout: post
title: SSRS Configuration | Syncfusion
description: ssrs configuration
platform: aspnet-core
control: ReportViewer
documentation: ug
---

# SSRS Configuration

The ReportViewer has support to load RDL reports from SSRS server. You have to set your SSRS server URL to ReportViewer’s ReportServiceUrl property and set the relative path of RDL file in SSRS to ReportViewer’s ReportPath property. 

{% highlight javascript %}

    <ej-report-viewer id="reportviewer1" report-service-url="../Home" processing-mode="Remote" ReportServerUrl="http://mvc.syncfusion.com/ReportServer"  ReportPath="/SSRSSamples2/Territory Sales New">    
    </ej-report-viewer>

{% endhighlight %}

## Network Credentials for SSRS

The Network credentials can be given at WebAPI Controller to connect the SSRS server.

{% highlight c# %}

/// <summary>
/// Report Initialization method that is triggered when report begins to process.
/// </summary>
/// <param name="reportOptions">The ReportViewer options.</param>
public void OnInitReportOptions(ReportViewerOptions reportOptions)
{
    //Adds SSRS Server and Database Credentials here.
    reportOptions.ReportModel.ReportServerCredential = new System.Net.NetworkCredential("ssrs", "RDLReport1");
    reportOptions.ReportModel.DataSourceCredentials.Add(new DataSourceCredentials("AdventureWorks", "ssrs1", "RDLReport1"));
}

{% endhighlight %}

N> DataSource credentials must be added to the ReportViewer for Shared DataSources that do not have credentials in the connection string and used in the SSRS Reports.

N> Pure ASP.Net Core project will support only SSRS 2017 server and ASP.NET Core project with the combination .NET framework will render report from all SSRS server version.  

