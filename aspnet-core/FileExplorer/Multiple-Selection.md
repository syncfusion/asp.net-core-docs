---
title: Multiple Selection | FileExplorer | ASP.NET Core | Syncfusion
description: Multi selection support in FileExplorer
platform: Asp.Net Core
control: FileExplorer
documentation: UG
keywords: FileExplorer,  Syncfusion, Asp.Net Core FileExplorer, UG document, Multiple selection
---
# Multiple Selection

The file explorer allows the user to select multiple files by enabling the “[AllowMultiSelection](http://help.syncfusion.com/js/api/ejfileexplorer#members:allowmultiselection)” property. The multiple selection can be done by pressing the “**Ctrl”** key or “**Shift”** key. You can select all the files in the directory by pressing “**Ctrl + A**”. The multiple selection is useful for copy pasting multiple files, deleting multiple files, and downloading multiple files. In another way, multiple files can be selected by bringing the mouse down and drag over the desired files. In addition to that, additional files can be selected with the preselected file by holding the ctrl/shift key and drag the mouse over the files. Also, holding the ctrl/shift key and dragging over selected files will unselect the selected files.

The [select](https://help.syncfusion.com/api/js/ejfileexplorer#events:select) event will be triggered when the items of FileExplorer control is selected.
Also [unselect](https://help.syncfusion.com/api/js/ejfileexplorer#events:unselect) event will be triggered when the items of FileExplorer control is unselected.

N>  For selecting files by mouse down and drag method, set the `AllowMultiSelection` property as true.

In the view page, add FileExplorer helper and specify the multi selection as true.
    
{% highlight CSHTML %}

<ej-file-explorer id="file" path="wwwroot/images/FileExplorer" ajax-action="@Url.Content("FileActionDefault")" allow-multi-selection="true">
    <e-file-ajax-settings>
        <e-download url="/FileExplorer/Download{0}"></e-download>
        <e-get-image url="/FileExplorer/GetImage{0}"></e-get-image>
        <e-upload url="/FileExplorer/Upload{0}"></e-upload>
    </e-file-ajax-settings>
</ej-file-explorer>

@*AllowMultiSelection property is true by default*@

{% endhighlight %}
    
## Checkbox option

You can enable or disable the checkbox using the “ShowCheckbox” API of FileExplorer.

In the view page, add FileExplorer helper and disable the checkbox as shown in the following.

{% highlight CSHTML %}

<ej-file-explorer id="file" path="wwwroot/images/FileExplorer" ajax-action="@Url.Content("FileActionDefault")" show-checkbox="false">
    <e-file-ajax-settings>
        <e-download url="/FileExplorer/Download{0}"></e-download>
        <e-get-image url="/FileExplorer/GetImage{0}"></e-get-image>
        <e-upload url="/FileExplorer/Upload{0}"></e-upload>
    </e-file-ajax-settings>
</ej-file-explorer>

{% endhighlight %}
