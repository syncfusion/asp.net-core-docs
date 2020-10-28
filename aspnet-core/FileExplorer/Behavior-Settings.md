---
title: Behavior Settings| FileExplorer | ASP.NET Core | Syncfusion
description: Customize the behavior of FileExplorer
platform: Asp.Net Core
control: FileExplorer
documentation: UG
keywords: FileExplorer, Syncfusion, Asp.Core FileExplorer, UG document, Behavior settings
---

# Behavior Settings

Here are some properties to customize behavior of the file explorer.

## File type restriction

The file explorer control showcase all the files from the filesystem and you can customize the file types that you want to show by using the “[FileTypes](http://help.syncfusion.com/js/api/ejfileexplorer#members:filetypes)” property. It filter the files based on the file extensions.
By default it has the value " \*.\* ", so it allows all the file types. In case of image browser, you can allow the image files only by setting “*.png, *.gif, *.jpg, *.jpeg” and it does not allow the other type of files.
In the view page, add FileExplorer helper and specify the file type restriction as shown in the following:

{% highlight CSHTML %}

<ej-file-explorer id="default" path="wwwroot/images/FileExplorer" ajax-action="@Url.Content("FileActionDefault")" width="100%" is-responsive="true" file-types="*png,*docx" >
<e-file-ajax-settings>
    <e-download url="/FileExplorer/Download{0}"></e-download>
    <e-get-image url="/FileExplorer/GetImage{0}"></e-get-image>
    <e-upload url="/FileExplorer/Upload{0}"></e-upload>
</e-file-ajax-settings>
</ej-file-explorer>

{% endhighlight %}

## Customize the AJAX request settings

As you already know file explorer is a client – server based control and each action performed in the client sends an AJAX request to the server to perform the server side operations. While sending the AJAX request, the AJAX configurations can be customized through the “[AjaxSettings](http://help.syncfusion.com/js/api/ejfileexplorer#members:ajaxsettings)” property.
The [beforeAjaxRequest](https://help.syncfusion.com/api/js/ejfileexplorer#events:beforeajaxrequest) event will be triggered before the AJAX request is performed. You can modify the ajax request in this event.

The following requests are passed during the **client – server** actions:

* Read

* Create folder

* Remove

* Rename

* Paste

* Get details

* Upload

* Download

* Get Image

* Search

The actions “Read, CreateFolder, Remove, Rename, Paste, GetDetails, Search” supports all the jQuery AJAX configurations. The remaining actions “Upload, Download, GetImage” will accepts only the URL.
If you want to customize Read action alone, the AJAX “**Url**” and “**DataType**” should be changed for the “Read” action.

In the view page, add the FileExplorer and specify the AJAX settings for Read request as shown in the following.

{% highlight CSHTML %}

<ej-file-explorer id="default" path="wwwroot/images/FileExplorer" ajax-action="@Url.Content("FileActionDefault")" width="100%" is-responsive="true" >
<e-file-ajax-settings>
    <e-read url="/FileExplorer/Read{0}" datatype="jsonp"></e-read>
    <e-download url="/FileExplorer/Download{0}"></e-download>
    <e-get-image url="/FileExplorer/GetImage{0}"></e-get-image>
    <e-upload url="/FileExplorer/Upload{0}"></e-upload>
</e-file-ajax-settings>
</ej-file-explorer>

{% endhighlight %}