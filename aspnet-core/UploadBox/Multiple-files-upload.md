---
layout: post
title: Multiple files upload | UploadBox | ASP.NET Core | Syncfusion
description: multiple files upload
platform: aspnet-core
control: UploadBox
documentation: ug
---

# Multiple files upload

The UploadBox widget provides support to upload multiple files spontaneously. The MultipleFilesSelection property enables you to select multiple files while browsing.  To achieve this, set the MultipleFilesSelection property to ‘true’. The data type is Boolean.

N> The Multiple file selection supports all the latest versions of browser except Internet Explorer 9 and its previous versions.

The following steps explain the configuration of MultipleFilesSelection property in UploadBox. 

In the VIEW page, add the below code  to configure the UploadBox element.

{% highlight CSHTML %}

<ej-upload-box id="UploadDefault" save-url="//mvc.syncfusion.com/Services/FileUpload/UploadBox/saveFiles" remove-url="//mvc.syncfusion.com/Services/FileUpload/UploadBox/removeFiles" multiple-files-selection="true"></ej-upload-box>

{% endhighlight %}

The following screenshot displays the output.

![](Multiple-files-upload_images/Multiple-files-upload_img1.png)

![](Multiple-files-upload_images/Multiple-files-upload_img2.png)