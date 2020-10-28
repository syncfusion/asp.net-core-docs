---
layout: post
title: Toolbar Customization | Syncfusion
description: toolbar customization
platform: aspnet-core
control: ReportViewer
documentation: ug
---

# Toolbar Customization

The ReportViewer has an option to show or hide items in the toolbar. To customize the toolbar items, use the ReportViewer’s `toolbarSettings` property.


The following code example illustrates how to hide the parameter block in ReportViewer for ASP.NET Core platform.

{% highlight javascript %}

    <ej-report-viewer id="reportviewer1" report-service-url="../Home" processing-mode="Remote" toolbar-settings="ViewBag.toolbarSettings">    
    </ej-report-viewer>

{% endhighlight %}

{% highlight c# %}

       public ActionResult Index()
        {
            ViewBag.toolbarSettings = new Syncfusion.JavaScript.Models.ReportViewer.ToolbarSettings();
            ViewBag.toolbarSettings.Items = Syncfusion.JavaScript.ReportViewerEnums.ToolbarItems.All
                                               & ~Syncfusion.JavaScript.ReportViewerEnums.ToolbarItems.Parameters;
            return View();
        }

{% endhighlight %}



