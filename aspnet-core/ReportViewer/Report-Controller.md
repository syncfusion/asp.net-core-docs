---
layout: post
title: Report Controller | Syncfusion
description: report controller
platform: aspnet-core
control: ReportViewer
documentation: ug
---

# Report Controller

The ReportViewer uses Web API services to process the report file, process the request from control and to return the processed data to control. The Syncfusion.EJ.ReportViewer assembly has helper APIs to define the service actions and process the service requests. 

## IReportController

The interface `IReportController` has the declaration of action methods that is defined in WebApi Controller for processing the RDL/RDLC files and for processing request from ReportViewer control. The `IReportController` has the following action methods declaration. 

<table>
<tr>
<th>
Methods</th><th>
Description</th></tr>
<tr>
<td>
GetResource</td><td>
Action ([AcceptVerbs("GET")]) method for getting resource for report. </td></tr>
<tr>
<td>
PostReportAction</td><td>
Action (HttpPost) method for posting the request for report process. </td></tr>
<tr>
<td>
PostFormReportAction</td><td>
Action (HttpPost) method for posting the request for report exporting. </td></tr>
<tr>
<td>
OnInitReportOptions</td><td>
Report initialization method that is triggered when report begins to be processed.</td></tr>
<tr>
<td>
OnReportLoaded</td><td>
Report loaded method that is triggered when report and sub report begin loading.</td></tr>
</table>

## ReportHelper

The class `ReportHelper` contains helper methods that helps process Post/Get request from ReportViewer control and returns the response to ReportViewer control. The `ReportHelper` has the following methods. 

<table>
<tr>
<th>
Methods</th><th>
Description</th></tr>
<tr>
<td>
GetResource</td><td>
Returns the report resource for the requested key.</td></tr>
<tr>
<td>
ProcessReport</td><td>
Processes the report request and returns the result.</td></tr>
</table>


{% highlight c# %}

    public partial class HomeController : Controller, IReportController
    {
        private IMemoryCache _cache;
        private IHostingEnvironment _hostingEnvironment;

        public string tabcontol { get; set; }
        internal DateTime StartDate { get; set; }
        internal DateTime EndDate { get; set; }

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

        [HttpPost]
        // Post action to process the report from server based on json parameters and send the result back to the client.
        public object PostReportAction([FromBody] Dictionary<string, object> jsonResult)
        {
            return ReportHelper.ProcessReport(jsonResult, this, this._cache);
        }
               
        [ActionName("GetResource")]
        [AcceptVerbs("GET")]
        // Method will be called from Report Viewer client to get the image src for the Image report item.
        public object GetResource(ReportResource resource)
        {
            return ReportHelper.GetResource(resource, this, _cache);
        }

        [HttpPost]
        // Post action to process the export from server and returns the exported file.
        public object PostFormReportAction()
        {
            return ReportHelper.ProcessReport(null, this, this._cache);
        }

        // Method will be called to initialize the report information to load the report for processing.
        public void OnInitReportOptions(ReportViewerOptions reportOption)
        {
            string basePath = _hostingEnvironment.WebRootPath;
            FileStream inputStream = new FileStream(basePath + @"\ReportRDL\sample.rdl", FileMode.Open, FileAccess.Read);
            reportOption.ReportModel.Stream = inputStream;
            reportOption.ReportModel.ProcessingMode = Syncfusion.EJ.ReportViewer.ProcessingMode.Remote;

        }

        // Method will be called when reported is loaded with internally to start to the layout process.
        public void OnReportLoaded(ReportViewerOptions reportOption)
        {
                    
        }        

    }

{% endhighlight %}



