---
title: Drag and Drop Support | FileExplorer | ASP.NET Core | Syncfusion
description: Drag and Drop option in FileExplorer
platform: Asp.Net Core
control: FileExplorer
documentation: UG
keywords: Drag and drop option
---

# Drag and Drop Support

The file explorer allows the files to move from one folder to another by using drag and drop. It also supports uploading a file by dragging it from Windows Explorer to a folder in the file explorer control.

You can enable or disable this support by using the “**AllowDragAndDrop**” API of FileExplorer.

The [dragStart](https://help.syncfusion.com/api/js/ejfileexplorer#events:dragstart), [drag](https://help.syncfusion.com/api/js/ejfileexplorer#events:drag), [dragStop](https://help.syncfusion.com/api/js/ejfileexplorer#events:dragstop) and [drop](https://help.syncfusion.com/api/js/ejfileexplorer#events:drop) events occur in the mentioned order when a drag and drop operation is performed.

In the view page, add “FileExplorer” helper and specify the drag and drop option as specified in the following:

{% highlight CSHTML %}

<ej-file-explorer id="file" path="wwwroot/images/FileExplorer" ajax-action="@Url.Content("FileActionDefault")" allow-drag-and-drop="false">
    <e-file-ajax-settings>
        <e-download url="/FileExplorer/Download{0}"></e-download>
        <e-get-image url="/FileExplorer/GetImage{0}"></e-get-image>
        <e-upload url="/FileExplorer/Upload{0}"></e-upload>
    </e-file-ajax-settings>
</ej-file-explorer>

{% endhighlight %}

