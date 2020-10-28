---
layout: post
title: Getting-Started | ReportDesigner | ASP.NET Core | Syncfusion
description: getting started
platform: aspnet-core
control: ReportDesigner
documentation: ug
---

# Getting Started with ASP.NET Core Application

This section explains briefly about how to create a **ReportDesigner** in your web application with **ASP.NET Core**.

## Environment setup
Refer the [Getting Started](/aspnet-core/gettingstarted/getting-started-1-1-0) page of the Introduction part to know more about the basic system requirements and the steps to configure the Syncfusion components in an ASP.NET Core application.

N> NuGet package reference will be mostly preferred with ASP.NET Core development to setup the environment without installation, if you missed to explore then refer to the [nuget-package-manager-settings](/aspnet-core/nuget-packages) to configure the Syncfusion NuGet source.

## Create your first ReportDesigner application in ASP.NET Core 

### References
You should add the following packages for the report designer:

<table>
<tr>
<th>
Package</th>
<th>
Purpose
</th>
</tr>
<tr>
<td>Syncfusion.EJ.AspNet.Core</td>
<td>Builds the report designer controls with the tag helper.</td>
</tr>
<tr>
<td>Syncfusion.EJ.ReportDesigner.AspNet.Core</td>
<td>Builds the server-side implementations.</td>
</tr>
<tr>
<td>System.Data.SqlClient</td>
<td>This is an optional package for the report designer. It should be referred in project when renders the RDL report and which contains the SQL Server and SQL Azure datasource. Also, the package version should be higher of 4.1.0 . </td>
</tr>
</table>

If we install the above NuGet packages, it automatically add the below ReportDesigner dependent NuGet file in your application,

<table>
<tr>
<th>
Package</th>
<th>
Purpose
</th>
</tr>
<tr>
<td>Syncfusion.EJ</td>
<td>Builds the report designer controls with the tag helper.</td>
</tr>
<tr>
<td>Syncfusion.EJ.ReportViewer.AspNet.Core</td>
<td>Builds the server-side implementations.</td>
</tr>
<tr>
<td>Syncfusion.Report.Net.Core</td>
<td>It is a base library for the <b>Syncfusion.EJ.ReportDesigner.AspNet.Core</b> and <b>Syncfusion.EJ.ReportViewer.AspNet.Core</b>package.</td>
</tr>
<tr>
<td>Syncfusion.Compression.Net.Core</td>
<td>Supports for exporting the report to PDF, Microsoft Word, and Microsoft Excel format. It is a base library for the packages <b>Syncfusion.Pdf.Net.Core</b> , <b>Syncfusion.DocIO.Net.Core</b> and <b>Syncfusion.XlsIO.Net.Core</b>. </td>
</tr>
<tr>
<td>Syncfusion.Pdf.Net.Core</td>
<td>Supports for exporting the report to a PDF.</td>
</tr>
<tr>
<td>Syncfusion.DocIO.Net.Core</td>
<td>Supports for exporting the report to a Word.</td>
</tr>
<tr>
<td>Syncfusion.XlsIO.Net.Core</td>
<td>Supports for exporting the report to an Excel.</td>
</tr>
<tr>
<td>Syncfusion.OfficeChart.Net.Core</td>
<td>It is a base library of the <b>Syncfusion.XlsIO.Net.Core package</b>.</td>
</tr>
<tr>
<td>Newtonsoft.Json</td>
<td>Serialize and deserialize the data for report designer. It is a mandatory package for the report designer, and the package version should be higher of 10.0.1 for NET Core 2.0 and others should be higher of 9.0.1.</td>
</tr>
</table>

N> Please ensure all the above dependent packages are added properly after the NuGet package installation completed.

### Styles and scripts

Ensure whether all the necessary dependency scripts and style packages are included within the *bower.json* file as mentioned [here](/aspnet-core/getting-started#configure-syncfusion-components-in-aspnet-core-application), so that the required scripts and CSS will be installed and loaded into the mentioned location (**wwwroot -> lib**) within your project.

Now, refer to the necessary scripts and CSS files in your *_Layout.cshtml* page from the **wwwroot -> lib -> syncfusion-javascript** folder.

N> Include the below mentioned scripts and CSS references under the appropriate environment. (For eg: If your environment is "Development", then refer the scripts and CSS files under the tag *environment names="Development"*). Refer all the required external and internal scripts only once in the page with proper order. Refer this [link](https://help.syncfusion.com/js/control-initialization#adding-the-required-javascript-files) to know about order of script reference.   

{% highlight cshtml %}

<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>@ViewData["Title"] - ReportDesignerDemo</title>
    <environment include="Development">
        <link href="~/lib/syncfusion-javascript/Content/ej/web/default-theme/ej.web.all.min.css" rel="stylesheet" />
        <link href="~/lib/syncfusion-javascript/Content/ej/web/default-theme/ej.reportdesigner.min.css" rel="stylesheet" />
        <link href="~/lib/syncfusion-javascript/Content/ej/web/responsive-css/ej.responsive.css" rel="stylesheet" />
        <link href="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.37.0/codemirror.min.css" rel="stylesheet" />
        <link href="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.37.0/addon/hint/show-hint.min.css" rel="stylesheet" />
    </environment>  
</head>
<body>
    <environment include="Development">
        <script src="~/lib/jquery/dist/jquery.js"></script>
        <script src="~/scripts/jquery-1.10.2.min.js"></script>
        <script src="~/scripts/jquery.easing.1.3.min.js"></script>
        <script src="~/lib/syncfusion-javascript/Scripts/jsrender.min.js"></script>
        <script src="~/lib/syncfusion-javascript/Scripts/ej/web/ej.web.all.min.js"></script>
        <script src="~/lib/syncfusion-javascript/Scripts/ej/web/ej.reportdesigner.min.js"></script>
        <script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.37.0/codemirror.min.js" type="text/javascript"></script>
        <script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.37.0/addon/hint/show-hint.min.js" type="text/javascript"></script>
        <script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.37.0/addon/hint/sql-hint.min.js" type="text/javascript"></script>
        <script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.37.0/mode/sql/sql.min.js" type="text/javascript"></script>

    </environment>   

    @RenderSection("Scripts", required: false)
    <ej-script-manager/>

</body>
</html>
{% endhighlight %}

N> Script manager must be defined at the bottom of the *_Layout.cshtml* page.

### Tag helper

It is necessary to define the following namespace within the *_viewImports.cshtml* page to initialize the report designer component with the tag helper support.

{% highlight cshtml %}

    @addTagHelper *, Microsoft.AspNetCore.Mvc.TagHelpers
    @using Syncfusion.JavaScript
    @addTagHelper "*, Syncfusion.EJ"

{% endhighlight %}

## Add control with page

You can use the <ej-report-designer> tag to add the report designer control. For an example, the Index.cshtml page can be replaced with the following code by removing the existing codes to add the report designer.

{% highlight CSHTML %}

@{
    ViewData["Title"] = "Reports";
}
<ej-report-designer id="reportdesigner1" service-url="../Home" />

<script type="text/javascript">
        var isSubmit = true;
        $(function () {
            $(document.body).bind('submit', $.proxy(formSubmit, this));
            $(window).bind('beforeunload', $.proxy(windowUnload, this));           
        });

        function controlInitialized(args) {
            var designer = $('#reportdesigner1').data('ejReportDesigner');
            designer.isCoreService = true;
        }

        function formSubmit(args) {
            isSubmit = false;
        }

        function windowUnload(args) {
            var designer = $('#reportdesigner1').data('ejReportDesigner');
            if (designer.hasReportChanges() && isSubmit) {
                return 'Changes you made may not be saved';
            }
            isSubmit = true;
        }
</script>

<ej-script-manager></ej-script-manager>
{% endhighlight %}

N> **service-url** must be provided in ReportDesigner initialization in order to process the report in controller.

## Add controller for Report Designer
 
The ASP.NET Core Report Designer uses WebApi services to process the report file and get the request from control.

#### Inherit IReportDesignerController
 
The ApiController should inherit the `IReportDesignerController` and to process the report file. The interface `IReportDesignerController` contains the required actions and helper methods declaration to process the report. The `ReportDesignerHelper` and `ReportHelper` class contains helper methods that helps to process Post/Get request from control and return the response to control.

Please add the following code example in `ReportDesignerController.cs`.

{% highlight c# %}
    public partial class HomeController : Controller, IReportDesignerController
    {
        private IMemoryCache _cache;
        private IHostingEnvironment _hostingEnvironment;


        public HomeController(IMemoryCache memoryCache, IHostingEnvironment hostingEnvironment)
        {
            _cache = memoryCache;
            _hostingEnvironment = hostingEnvironment;
        }

        public ActionResult Index()
        {
            return View();
        }

        public IActionResult Error()
        {
            return View();
        }

        public string GetFilePath(string fileName)
        {
            string targetFolder = this._hostingEnvironment.WebRootPath + "\\";
            targetFolder += "Cache";

            if (!Directory.Exists(targetFolder))
            {
                Directory.CreateDirectory(targetFolder);
            }

            if (!Directory.Exists(targetFolder + "\\" + ReportDesignerHelper.EJReportDesignerToken))
            {
                Directory.CreateDirectory(targetFolder + "\\" + ReportDesignerHelper.EJReportDesignerToken);
            }

            var folderPath = targetFolder + "\\" + ReportDesignerHelper.EJReportDesignerToken + "\\";
            return folderPath + fileName;
        }

        public object GetImage(string key, string image)
        {
            return ReportDesignerHelper.GetImage(key, image, this);
        }

        public object GetResource(ReportResource resource)
        {
            return ReportHelper.GetResource(resource, this, _cache);
        }

        public void OnInitReportOptions(ReportViewerOptions reportOption)
        {

        }

        public void OnReportLoaded(ReportViewerOptions reportOption)
        {

        }

        [HttpPost]
        public object PostDesignerAction([FromBody] Dictionary<string, object> jsonResult)
        {
            return ReportDesignerHelper.ProcessDesigner(jsonResult, this, null, this._cache);
        }

        public object PostFormDesignerAction()
        {
            return ReportDesignerHelper.ProcessDesigner(null, this, null, this._cache);
        }

        public object PostFormReportAction()
        {
            return ReportHelper.ProcessReport(null, this, this._cache);
        }

        [HttpPost]
        public object PostReportAction([FromBody] Dictionary<string, object> jsonResult)
        {
            return ReportHelper.ProcessReport(jsonResult, this, this._cache);
        }

        public bool UploadFile(IFormFile httpPostedFile)
        {
            string targetFolder = this._hostingEnvironment.WebRootPath + "\\";
            string fileName = !string.IsNullOrEmpty(ReportDesignerHelper.SaveFileName) ? ReportDesignerHelper.SaveFileName : Path.GetFileName(httpPostedFile.FileName);
            targetFolder += "Cache";

            if (!Directory.Exists(targetFolder))
            {
                Directory.CreateDirectory(targetFolder);
            }

            if (!Directory.Exists(targetFolder + "\\" + ReportDesignerHelper.EJReportDesignerToken))
            {
                Directory.CreateDirectory(targetFolder + "\\" + ReportDesignerHelper.EJReportDesignerToken);
            }
            using (var reader = new StreamReader(httpPostedFile.OpenReadStream()))
            {
                string contentAsString = reader.ReadToEnd();
                byte[] bytes = System.Text.Encoding.ASCII.GetBytes(contentAsString);
                if (System.IO.File.Exists(targetFolder + "\\" + ReportDesignerHelper.EJReportDesignerToken + "\\" + fileName))
                {
                    System.IO.File.Delete(targetFolder + "\\" + ReportDesignerHelper.EJReportDesignerToken + "\\" + fileName);
                }
                System.IO.File.WriteAllBytes(targetFolder + "\\" + ReportDesignerHelper.EJReportDesignerToken + "\\" + fileName, bytes);
                reader.Close();
                reader.Dispose();
            }
            return true;
        }

        [HttpPost]
        public void UploadReportAction()
        {
            ReportDesignerHelper.ProcessDesigner(null, this, this.Request.Form.Files[0], this._cache);
        }

        public FileModel GetFile(string filename, bool isOverride)
        {
            throw new NotImplementedException();
        }

        public List<FileModel> GetFiles(FileType fileType)
        {
            throw new NotImplementedException();
        }

    }
{% endhighlight %}

N> Specify the created controller name (Home) in **service-url** to initialization ReportDesigner in ASP.NET Core.

## Run the application

Run the sample application and you can see the ReportDesigner on the page as displayed in the following screenshot:

![Getting-Started](images/Getting-Started_img1.png)

## Sample Application

We have prepared a ReportDesigner ASP.NET Core sample application. Refer to the below link for sample application download,
http://www.syncfusion.com/downloads/support/directtrac/general/ze/ReportDesigner_ASP.NETCore-692277106.zip 

N> Sample application is prepared using **16.3.0.21** version NuGet and Script files. Update the NuGet packages and script file to your required version.
