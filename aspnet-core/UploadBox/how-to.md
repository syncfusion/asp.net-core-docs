---
layout: post
title: File Size | UploadBox | ASP.NET Core | Syncfusion
description: How to
platform: aspnet-core
control: UploadBox
documentation: ug
keywords: UploadBox, Grid, template
---

# How To

## Render UploadBox inside column of Grid

UploadBox can be rendered inside the column of a Grid through the template property. Render a div element inside the jsrender template and render this as UploadBox through the template refresh event of the Grid. Map the ID of jsrender script template to the template property of Grid column.

The following code illustrates about how to render UploadBox inside the column of a Grid. 
 
{% highlight html %}

    <ej-grid id="FlatGrid" allow-paging="true" template-refresh="template">
      <e-datamanager url="https://js.syncfusion.com/demos/ejServices/Wcf/Northwind.svc/Orders/?$top=45" offline="true" cross-domain="true"></e-datamanager>
      <e-columns>
        <e-column field="OrderID" header-text="Order ID" text-align="Right" width="75"></e-column>
        <e-column field="CustomerID" header-text="Customer ID" width="80"></e-column>
        <e-column field="EmployeeID" header-text="Employee ID" text-align="Left" width="75"></e-column>
        <e-column field="Freight" header-text="Freight" format="{0:C2}" text-align=Right width="75"></e-column>
        <e-column field="OrderDate" header-text="Order Date" format="{0:MM/dd/yyyy}" text-align=Right width="80"></e-column>
        <e-column header-text="Upload files" template="#Template" width="150"></e-column>
        <e-column field="ShipCity" header-text="Ship City" width="110"></e-column>
      </e-columns>
    </ej-grid>
    <script type="text/x-jsrender" id="Template">
       <div class="Upload" id="Files"></div>
    </script>
    <script type="text/javascript">
     function template(args) {
        $(args.cell).find(".Upload").ejUploadbox({
            saveUrl: "saveUrl",
            removeUrl: "removeUrl"
        });
      }
    </script>

{% endhighlight %}

{% highlight c# %}

        private IHostingEnvironment hostingEnv;

        public ActionResult Index()
        {
          
            return View();
        }

        public HomeController(IHostingEnvironment env)
        {
            this.hostingEnv = env;
        }

        [HttpPost]
        public IActionResult saveUrl(IList<IFormFile> Files)
        {
            long size = 0;
            foreach (var file in Files)
            {
                var filename = ContentDispositionHeaderValue
                                .Parse(file.ContentDisposition)
                                .FileName
                                .Trim('"');
                filename = hostingEnv.WebRootPath + $@"\{filename}"; //get file path 
                size += file.Length;
                using (FileStream stream = System.IO.File.Create(filename))
                {
                    file.CopyTo(stream);
                    stream.Flush();
                }
            }
            return Content("");
        }
        [HttpPost]
        public IActionResult removeUrl(string[] fileNames)
        {
            foreach (var fullName in fileNames)
            {
                var filename = hostingEnv.WebRootPath + $@"\{fullName}"; //get file path
                if (System.IO.File.Exists(filename))
                {
                    System.IO.File.Delete(filename); //delete the file 
                }
            }
            
            return Content("");
        }

{% endhighlight %}

Refer to the sample [here](http://www.syncfusion.com/downloads/support/directtrac/230884/ze/Grid_with_Uploadbox1479644797 )