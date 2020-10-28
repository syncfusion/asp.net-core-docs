---
layout: post
title: Report Parameters | Syncfusion
description: report parameters
platform: aspnet-core
control: ReportViewer
documentation: ug
---

# Report Parameters

The ReportViewer has support to set default value of the report Parameters at runtime. The ReportViewer has `parameters` property that is the list of ReportParameter type to add collection of report parameters to it. You can add report parameters when creating ReportViewer control in ASP.NET Core platform.

The following code example illustrates how to set default value for the ReportParameter in controller for ReportViewer.

{% highlight c# %}

        public void OnReportLoaded(ReportViewerOptions reportOption)
        {
            List<ReportParameter> reportParameters = new List<ReportParameter>();
            ReportParameter reportParameter = new ReportParameter();
            reportParameter.Name = "InvoiceID";
            reportParameter.Values.Add("10253");
            reportParameter.Labels.Add("10253");
            reportParameters.Add(reportParameter);
            reportOption.ReportModel.Parameters = reportParameters;
        } 

{% endhighlight %}
