---
title: Virtual Scrolling | FileExplorer | ASP.NET Core | Syncfusion
description: Virtual Scrolling support in FileExplorer control
platform: Asp.Net Core
control: FileExplorer
documentation: UG
keywords: FileExplorer,  Syncfusion, Asp.Net Core FileExplorer, UG document, Virtual Scrolling
---

# Virtual Scrolling

Virtual Scrolling is introduced to provide support for loading files and folders on demand in order to improve performance in FileExplorer when large amount of files are present.

Virtual Scrolling can be enabled by using [VirtualItemCount](https://help.syncfusion.com/api/js/ejfileexplorer#members:virtualitemcount) API. It specifies the total files to be loaded initially, and on each scroll the next set of files are loaded. For eg- If [VirtualItemCount](https://help.syncfusion.com/api/js/ejfileexplorer#members:virtualitemcount) value is given as ”20”, then 20 items are loaded initially and on each scroll the next/previous 20 items are loaded. If the value of [VirtualItemCount](https://help.syncfusion.com/api/js/ejfileexplorer#members:virtualitemcount) is 0, virtual scrolling will be disabled.

N>  Default value of `VirtualItemCount` is 0.


{% highlight CSHTML %}

<ej-file-explorer id="file" path="wwwroot/images/FileExplorer" ajax-action="@Url.Content("FileActionDefault")" virtual-item-count="40">
    <e-file-ajax-settings>
        <e-download url="/FileExplorer/Download{0}"></e-download>
        <e-get-image url="/FileExplorer/GetImage{0}"></e-get-image>
        <e-upload url="/FileExplorer/Upload{0}"></e-upload>
    </e-file-ajax-settings>
</ej-file-explorer>

{% endhighlight %}

