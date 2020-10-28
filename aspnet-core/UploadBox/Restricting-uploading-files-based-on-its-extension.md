---
layout: post
title: Restricting uploading files based on its extension | UploadBox | ASP.NET Core | Syncfusion
description: restricting uploading files based on its extension
platform: aspnet-core
control: UploadBox
documentation: ug
---

# Restricting uploading files based on its extension

## Allow Extension

Files are filtered before they are uploaded. You can select the files to be filtered by using browse button. The ExtensionsAllow property allows upload of the selected extensions only. You can give multiple extensions by using comma (,).  The data type is string.

N> Prepend dot (.) symbol with extension like “.pdf”.

The following code helps you for the configuration of ExtensionsAllow property in UploadBox. 

{% highlight CSHTML %}

<ej-upload-box id="UploadDefault" save-url="//mvc.syncfusion.com/Services/FileUpload/UploadBox/saveFiles" remove-url="//mvc.syncfusion.com/Services/FileUpload/UploadBox/removeFiles" extensions-allow=".docx,.pdf"></ej-upload-box>

{% endhighlight %}

## Deny Extension

Files are filtered before they are uploaded. You can select the files to be filtered by using browse button. The ExtensionsDeny property denies upload of the selected extensions. You can give multiple extensions by using comma (,).  The data type is string.

N> Prepend dot (.) symbol with extension like “.pdf”.

The following code helps you for the configuration of ExtensionsDeny property in UploadBox

{% highlight CSHTML %}

<ej-upload-box id="UploadDefault" save-url="//mvc.syncfusion.com/Services/FileUpload/UploadBox/saveFiles" remove-url="//mvc.syncfusion.com/Services/FileUpload/UploadBox/removeFiles" extensions-deny=".docx,.pdf"></ej-upload-box>

{% endhighlight %}

N> When **ExtensionsDeny** and **ExtensionsAllow** properties have same file extension, the extension will be allowed.