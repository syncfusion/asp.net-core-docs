---
layout: post
title: Getting-Started
description: getting started
platform: aspnet-core
control: FileExplorer
documentation: ug
---

# Getting Started

This section briefly explains about how to create a file explorer in ASP.NET Core platform.

## Create your first file explorer in ASP.NET Core

Create an ASP.NET Core Project and add Syncfusion assembly packages, CSS and scripts with the help of the given [ASP.NET Core-Getting Started](https://help.syncfusion.com/aspnet-core/gettingstarted/getting-started-1-1-0) documentation. After the project creation, create a file explorer in the following ways.

## FileExplorer using tag helper

In View page, add the tag helper as shown in the following.

{% highlight CSHTML %}
<ej-file-explorer id="default" path="wwwroot/images/FileExplorer" ajax-action="@Url.Content("FileActionDefault")">
<e-file-ajax-settings>
    <e-download url="/FileExplorer/Download{0}"></e-download>
    <e-get-image url="/FileExplorer/GetImage{0}"></e-get-image>
    <e-upload url="/FileExplorer/Upload{0}"></e-upload>
</e-file-ajax-settings>
</ej-file-explorer>
{% endhighlight %}

In the above code block, `path` denotes the URL of filesystem that are to be explored in “FileExplorer” and `ajax-action` specifies the URL of server side AJAX handling method that handles the file operations of file explorer control.
The `e-file-ajax-settings` that specifies the URL of the server side AJAX handling method for image preview, file download and upload actions.

So the [path](https://help.syncfusion.com/api/js/ejfileexplorer#members:path), [ajax-action](https://help.syncfusion.com/api/js/ejfileexplorer#members:ajaxaction) and [e-file-ajax-settings](https://help.syncfusion.com/api/js/ejfileexplorer#members:ajaxsettings) for get image, download and upload are mandatory configuration here.

Add the following code example to the corresponding controller page.

The `IHostingEnvironment` interface is used to get the current path. To use the `IHostingEnvironment`, you need to add the namespace `Microsoft.AspNetCore.Hosting` in your controller part.

{% highlight c# %}

public partial class FileExplorerController : Controller
{
       public FileExplorerController(IHostingEnvironment hostingEnvironment)
        {
            this.operation = new FileExplorerOperations(hostingEnvironment.ContentRootPath);
        }


        public ActionResult Download(FileExplorerParams args)
        {
            return operation.Download(args.Path, args.Names);
        }

        public ActionResult Upload(FileExplorerParams args)
        {
            operation.Upload(args.FileUpload, args.Path);
            return Json("");
        }
        public ActionResult GetImage(FileExplorerParams args)
        {
            return operation.GetImage(args.Path);
        }
        public ActionResult FileActionDefault([FromBody] FileExplorerParams args)
        {
                switch (args.ActionType)
                {
                    case "Read":
                        return Json(operation.Read(args.Path, args.ExtensionsAllow));
                    case "CreateFolder":
                        return Json(operation.CreateFolder(args.Path, args.Name));
                    case "Paste":
                        return Json(operation.Paste(args.LocationFrom, args.LocationTo, args.Names, args.Action, args.CommonFiles));
                    case "Remove":
                        return Json(operation.Remove(args.Names, args.Path, args.SelectedItems));
                    case "Rename":
                        return Json(operation.Rename(args.Path, args.Name, args.NewName, args.CommonFiles));
                    case "GetDetails":
                        return Json(operation.GetDetails(args.Path, args.Names));
                    case "Search":
                        return Json(operation.Search(args.Path, args.ExtensionsAllow, args.SearchString, args.CaseSensitive));
                }
                return Json("");
        }
}

{% endhighlight %}

Once you completed the above steps, you will get the output like below.

![](Getting_started_images/getting-started-img1.png)




