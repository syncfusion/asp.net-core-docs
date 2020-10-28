---
layout: post
title: Asynchronous Upload | UploadBox | ASP.NET Core | Syncfusion
description: asynchronous upload
platform: aspnet-core
control: UploadBox
documentation: ug
---

# Asynchronous Upload

The AsyncUpload property is Boolean type, which allow us to upload and remove files asynchronously.When multiple files are chosen in Asynchronous upload,files will be uploaded one by one to the server.User interaction with the page will not be interrupted at the time of upload.User can also remove the file even after uploading.This is the best way of file upload when compared to synchronous so by default UploadBox works with asynchronous upload option only. To achieve this, set the AsyncUpload property to ‘true’. The default value of AsyncUpload property is ‘true’.

The following steps guide you in uploading the file asynchronously.

In the VIEW page, add the below code to configure the UploadBox element.

{% highlight CSHTML %}

<ej-upload-box id="UploadDefault" save-url="//mvc.syncfusion.com/Services/FileUpload/UploadBox/saveFiles" remove-url="//mvc.syncfusion.com/Services/FileUpload/UploadBox/removeFiles" async-upload="true"></ej-upload-box>

{% endhighlight %}