---
layout: post
title: Open and Save in ASP.NET Core Spreadsheet | Syncfusion
description: You can learn about open and save support in Syncfusion ASP.NET Core Spreadsheet control and more details.
platform: aspnet-core
control: Spreadsheet
documentation: ug
--- 

# Open and Save in ASP.NET Core Spreadsheet
The native data format for Spreadsheet is JSON. You can load and store JSON data with Spreadsheet. In Spreadsheet we have [`saveAsJSON`](http://help.syncfusion.com/api/js/ejspreadsheet#methods:saveasjson "saveAsJSON") and [`loadFromJSON`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:loadfromjson "loadFromJSON") method which is used to save Spreadsheet as JSON and same JSON used to render Spreadsheet.

{% highlight javascript %}

function saveAsJSON() {
    var xlObj = $("#Spreadsheet").data("ejSpreadsheet");
    window.xlData = xlObj.saveAsJSON();
}

function loadFromJSON() {
    var xlObj = $("#Spreadsheet").data("ejSpreadsheet");
    xlObj.loadFromJSON(window.xlData);
}   
    
{% endhighlight %}

When you open excel file, it need to be read and converted to client side Spreadsheet model. The converted client side Spreadsheet model is sent as JSON which is used to render Spreadsheet. Similarly, when you save the Spreadsheet, the client Spreadsheet model is sent to the server as JSON for processing and saved. `Server configuration` is used for this process. 

## Open 
The Spreadsheet can open excel documents as like excel application with its data, style, format. To enable open option in Spreadsheet set `allow-import` option to `true`. Since Spreadsheet uses a server side helper to open document, set `import-mapper` in `e-import-settings` to map server action.

{% tabs %}
{% highlight cshtml %}

<ej-spread-sheet id="Spreadsheet" allow-import="true">
    <e-import-settings  import-mapper="Import"></e-import-settings>
</ej-spread-sheet>
    
{% endhighlight %}
{% highlight c# %}

namespace MVCSampleBrowser.Controllers
{
    public partial class SpreadsheetController : Controller
    {
        public ActionResult Default()
        {
            return View();
        }

        public string Import(ImportRequest importRequest)
        {
            return Spreadsheet.Open(importRequest);
        }
    }
}
    
{% endhighlight %}
{% endtabs %}

Following file types can be opened in Spreadsheet

* XLS
* XLSX
* CSV

You can open excel documents in following ways,

1. Initial settings
2. Methods
3. User Interface

### Initial settings
The Spreadsheet can load excel documents initially. The document can be specified either from client side or in server side. To load excel documents initially from client side, set `import-url` in `e-import-settings`. The code snippets for document initial load on client side are as follows,

{% tabs %}
{% highlight cshtml %}

<ej-spread-sheet id="Spreadsheet">
    <e-import-settings  import-mapper="Import" import-url= "http://mvc.syncfusion.com/Spreadsheet/LargeData.xlsx"></e-import-settings>
</ej-spread-sheet>

{% endhighlight %}
{% highlight c# %}

namespace MVCSampleBrowser.Controllers
{
    public partial class SpreadsheetController : Controller
    {
        public ActionResult Default()
        {
            return View();
        }

        public string Import(ImportRequest importRequest)
        {
            return Spreadsheet.Open(importRequest);
        }
    }
}
    
{% endhighlight %}
{% endtabs %}

To load excel documents initially from server side, set `import-on-load`as `true` and assign document stream or URL in the server. The code snippets for document initial load from server side are as follows,

{% tabs %}{% highlight cshtml %}

<ej-spread-sheet id="Spreadsheet">
    <e-import-settings  import-mapper="Import" import-on-load="true"></e-import-settings>
</ej-spread-sheet>

{% endhighlight %}
{% highlight c# %}

namespace MVCSampleBrowser.Controllers
{
    public partial class SpreadsheetController : Controller
    {
        public ActionResult Default()
        {
            return View();
        }

        public string Import(ImportRequest importRequest)
        {
            importRequest.Url = "http://mvc.syncfusion.com/Spreadsheet/LargeData.xlsx";
            return Spreadsheet.Open(importRequest);
        }
    }
}
    
{% endhighlight %}
{% endtabs %}

![Loading excel documents from server side](Open-and-Save_images/Open-and-Save_img1.png)

### Methods
To open an excel document, [`import`](http://help.syncfusion.com/api/js/ejspreadsheet#methods:import "import") method should be called with import options as a parameter. The Spreadsheet can open excel document as a stream or file URL.
 
#### Stream
Spreadsheet can open excel document as a stream and the document stream was either from the client side or it can be specified in server side. The code snippets to open excel document as a stream from client side are as follows,

{% highlight javascript %}

function fileOpen(args) {
    var xlObj = $("#Spreadsheet").data("ejSpreadsheet"),
    stream = args.files[0]; // file stream from ejUploadbox
    xlObj["import"]({ file: stream });
}
    
{% endhighlight %}

The Code snippets to specify excel document as stream in server side are as follows,

{% highlight c# %}

namespace MVCSampleBrowser.Controllers
{
    public partial class SpreadsheetController : Controller
    {
        public string Import(ImportRequest importRequest)
        {
            importRequest.FileStream = getFileStream(); // assign file stream
            return Spreadsheet.Open(importRequest);
        }
    }
}

{% endhighlight %}

#### File URL
Spreadsheet can open excel document from specified URL. The URL can be specified either from client side or in server side. The code snippets to open excel document as URL from client side are as follows,

{% highlight javascript %}

function fileOpen() {
    var xlObj = $("#Spreadsheet").data("ejSpreadsheet");
    xlObj["import"]({Url: "http://mvc.syncfusion.com/Spreadsheet/LargeData.xlsx"});
}
    
{% endhighlight %}

The Code snippets to specify excel document as URL in server side are as follows,

{% highlight c# %}

namespace MVCSampleBrowser.Controllers
{
    public partial class SpreadsheetController : Controller
    {
        public string Import(ImportRequest importRequest)
        {
            importRequest.Url = "http://mvc.syncfusion.com/Spreadsheet/LargeData.xlsx";
            return Spreadsheet.Open(importRequest);
        }
    }
}
    
{% endhighlight %}

### User Interface
You can dynamically open excel document by clicking the file menu in ribbon and choose Open to upload excel file. 

## Save
The Spreadsheet can save its data, style, format into an excel file. To enable save option in Spreadsheet set `allow-exporting` option in `e-export-settings` as `true`. Since Spreadsheet uses server side helper to save documents set `excel-url` in `e-export-settings` option.

{% tabs %}
{% highlight cshtml %}

<ej-spread-sheet id="Spreadsheet">
    <e-export-settings allow-exporting="true" excel-url="ExcelExport" csv-url="CsvExport" ></e-export-settings>
</ej-spread-sheet>
    
{% endhighlight %}
{% highlight c# %}

namespace MVCSampleBrowser.Controllers
{
    public partial class SpreadsheetController : Controller
    {
        public ActionResult Default()
        {
            return View();
        }
        
         public ActionResult ExcelExport(string sheetModel, string sheetData, string password)
        {
            return Spreadsheet.Save(sheetModel, sheetData, "sample", ExportFormat.XLSX);
        }
        public ActionResult CsvExport(string sheetModel, string sheetData, string password)
        {
            return Spreadsheet.Save(sheetModel, sheetData, "sample", ExportFormat.CSV);
        }
    }
}
    
{% endhighlight %}
{% endtabs %}


N> To export as Stream skip file name parameter in Save method. For more details refer below code snippets,
N> Stream stream = Spreadsheet.Save(sheetModel, sheetData, ExportFormat.XLSX, ExcelVersion.Excel2013);

You can save Spreadsheet contents with following file types,

* XLS
* XLSX
* CSV

You can save excel documents in following ways,

1. Methods
2. User Interface

### Methods
To save Spreadsheet document as excel file, [`export`](http://help.syncfusion.com/api/js/ejspreadsheet#methods:xlexport-export "export") method should be called with file type as parameter. The code snippets to save Spreadsheet document are as follows,

{% highlight javascript %}

function saveAsFile() {
    var xlObj = $("#spreadsheet").data("ejSpreadsheet");
    xlObj.XLExport["export"](ej.Spreadsheet.exportType.Excel);
}
    
{% endhighlight %}

### User Interface
You can dynamically save Spreadsheet by clicking file menu in ribbon and choose `SaveAs` option.

## Server dependencies
Import and Export Helper functions are available in the package`Syncfusion.EJ.Export`, which is available in Essential Studio and Essential JavaScript builds. The full list of packages needed for Spreadsheet import and export are as follows.

1. Syncfusion.EJ
2. Syncfusion.EJ.Export
3. Syncfusion.OfficeChart.Portable
4. Syncfusion.Compression.Portable
5. Syncfusion.DocIO.Portable
6. Syncfusion.XlsIO.Portable
7. Syncfusion.Pdf.Portable
    
