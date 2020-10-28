---
title: Resizing | FileExplorer | ASP.NET Core | Syncfusion
description: Resize option in FileExplorer
platform: Asp.Net Core
control: FileExplorer
documentation: UG
keywords: FileExplorer,  Syncfusion, Asp.Net Core FileExplorer, UG document, Resizing
---
# Resizing

The file explorer has the resize support through the resize handle that appears at the right-bottom corner of the footer. By clicking the resize handle the user can resize the file explorer through the UI. While resizing, the dimension of the file explorer is automatically adjusted.

The resize behavior can be enabled through the “[EnableResize](http://help.syncfusion.com/js/api/ejfileexplorer#members:enableresize)” property.

In the view page, add FileExplorer helper with resizable option as shown in the following:
    
{% highlight CSHTML %}
    
<ej-file-explorer id="file" path="wwwroot/images/FileExplorer" ajax-action="@Url.Content("FileActionDefault")" enable-resize="true">
    <e-file-ajax-settings>
        <e-download url="/FileExplorer/Download{0}"></e-download>
        <e-get-image url="/FileExplorer/GetImage{0}"></e-get-image>
        <e-upload url="/FileExplorer/Upload{0}"></e-upload>
    </e-file-ajax-settings>
</ej-file-explorer>

{% endhighlight %}
    
## Responsiveness

By enabling the “[IsResponsive](http://help.syncfusion.com/js/api/ejfileexplorer#members:isresponsive)” property, you can make the file explorer as responsive. While resizing the file explorer component, the inner content and toolbar items are automatically adjusted to equalize the size. The toolbar items are displayed in the Dropdown on enabling the responsive. Otherwise, it floats to the next line to equalize the space.

In the view page, add FileExplorer helper with responsive option.
    
{% highlight CSHTML %}

<ej-file-explorer id="file" path="wwwroot/images/FileExplorer" ajax-action="@Url.Content("FileActionDefault")" is-responsive="true" enable-resize="true">
    <e-file-ajax-settings>
        <e-download url="/FileExplorer/Download{0}"></e-download>
        <e-get-image url="/FileExplorer/GetImage{0}"></e-get-image>
        <e-upload url="/FileExplorer/Upload{0}"></e-upload>
    </e-file-ajax-settings>
</ej-file-explorer>

        
{% endhighlight %}
    
## Restriction on resize

You can restrict the dimension of the FileExplorer by setting the “[MinHeight](http://help.syncfusion.com/js/api/ejfileexplorer#members:minheight)”, “[MaxHeight](http://help.syncfusion.com/js/api/ejfileexplorer#members:maxheight)”,  “[MinWidth](http://help.syncfusion.com/js/api/ejfileexplorer#members:minwidth)” and “[MaxWidth](http://help.syncfusion.com/js/api/ejfileexplorer#members:maxwidth)” properties while resizing the FileExplorer.

In the view page, add FileExplorer helper and set resize option within the particular region.
    
{% highlight CSHTML %}

<ej-file-explorer id="file" path="wwwroot/images/FileExplorer" ajax-action="@Url.Content("FileActionDefault")" min-height="200px" max-height="400px" min-width="300px" max-width="1200px" is-responsive="true" enable-resize="true">
    <e-file-ajax-settings>
        <e-download url="/FileExplorer/Download{0}"></e-download>
        <e-get-image url="/FileExplorer/GetImage{0}"></e-get-image>
        <e-upload url="/FileExplorer/Upload{0}"></e-upload>
    </e-file-ajax-settings>
</ej-file-explorer>

{% endhighlight %}
    
