---
layout: post
title: RTL Support | UploadBox | ASP.NET Core | Syncfusion
description: rtl support 
platform: aspnet-core
control: UploadBox
documentation: ug
---

# RTL Support 

The EnableRTL property is Boolean type, which allow us to change of left-to-right alignment of the UploadBox widget to right-to-left (RTL). That is, it sets the UploadBox to right-to-left actions. Default value of EnableRTL property is false. 

The following steps explain the configuration of EnableRTL property in UploadBox. 

In the VIEW page, add the below code to configure the UploadBox element.

{% highlight CSHTML %}

<ej-upload-box id="UploadDefault" save-url="//mvc.syncfusion.com/Services/FileUpload/UploadBox/saveFiles" remove-url="//mvc.syncfusion.com/Services/FileUpload/UploadBox/removeFiles" enable-rtl="true"></ej-upload-box>

{% endhighlight %}

The following screenshot displays the output.

![](RTL-Support_images/RTL-Support_img1.png)