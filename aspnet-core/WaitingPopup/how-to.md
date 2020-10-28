---
layout: post
title: How to section WaitingPopup control for Syncfusion ASP.NET CORE
description: How to
platform: aspnet-core
control: WaitingPopup
documentation: ug
keywords: WaitingPopup, hide, download
---

# How To

## Hide WaitingPopup after file download is complete

While downloading files there will a slight time delay and waiting popup can be displayed during this delay to indicate that some action is in progress. This prevents interaction with the page during this loading time. 

The following code illustrates on how to show and hide WaitingPopup during an excel sheet download. 

{% highlight html %}

     <div id="customWaiting"></div>
      <ej-waiting-popup id="customWaiting" show-on-init="false" />

     <input class="buttonStyle" type="button" value="Run Report" onclick="openReportDialog()"; />

    <script type="text/javascript">
        function openReportDialog() {        
           var temp = $.templates($("#TrackerDialog").html());
           $(temp.render()).ejDialog({ title: "Master Tracker Filters", width: "450px" });
        }
       function runTracker() {
            var instance = $("#customWaiting").data("ejWaitingPopup");
            instance.show();
        $.ajax({
            type: "POST",
            url: "MasterTracker",
            data: { "Id": "test" },
            success: function (data) {
                var instance = $("#customWaiting").data("ejWaitingPopup");
                instance.hide();
                if (data.fileName != "") {
                    window.location.href = "@Url.RouteUrl(new {Controller = "Dialog", Action = "Download"})/?file=" + data.fileName;
                }
             }
         });
       }
    </script>

{% endhighlight %}

{% highlight c# %}

         private readonly IHostingEnvironment _hostingEnvironment;
         public DialogController(IHostingEnvironment hostingEnvironment)
           {
                _hostingEnvironment = hostingEnvironment;
           }
        public ActionResult MasterTracker(string Id)
          {

            ExcelEngine excelEngine = new ExcelEngine();
            IApplication application = excelEngine.Excel;
            application.DefaultVersion = ExcelVersion.Excel2016;

            string basePath = _hostingEnvironment.WebRootPath + @"\XlsIO\master_tracker.xlsx";

            FileStream Tracker = new FileStream(basePath, FileMode.Open);

            IWorkbook workbook = application.Workbooks.Open(Tracker);                        

            DateTime curDate = DateTime.Now;

            string fileName = "master_tracker_" + curDate.Year.ToString().PadLeft(2, '0') + "_" + curDate.Month.ToString().PadLeft(2, '0') + "_" + curDate.Day.ToString().PadLeft(2, '0') + 
                "_" + curDate.Hour.ToString().PadLeft(2, '0') + "_" + curDate.Minute.ToString().PadLeft(2, '0') + "_" + curDate.Second.ToString().PadLeft(2, '0') + "_" + 
                curDate.Millisecond.ToString() + ".xlsx";

            // save to server temp path
            string fullPath = _hostingEnvironment.WebRootPath + @"\XlsIO\Download\" + fileName;

            FileStream outputStream = new FileStream(fullPath, FileMode.Create);
            workbook.SaveAs(outputStream);

            workbook.Close();
            Tracker.Close();
            outputStream.Close();
            excelEngine.Dispose();

            return Json(new { fileName = fileName, errorMessage = "" });            
        }

        public ActionResult Download(string file)
        {
            string fullPath = _hostingEnvironment.WebRootPath + @"\XlsIO\Download\" + file;
            byte[] fileByteArray = System.IO.File.ReadAllBytes(fullPath);
            System.IO.File.Delete(fullPath);
            return File(fileByteArray, "Application/msexcel", "master_tracker.xlsx");
        }

{% endhighlight %}