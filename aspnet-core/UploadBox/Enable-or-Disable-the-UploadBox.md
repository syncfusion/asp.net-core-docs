---
layout: post
title: Enable or Disable the UploadBox | UploadBox | ASP.NET Core | Syncfusion
description: enable or disable the uploadbox 
platform: aspnet-core
control: UploadBox
documentation: ug
---

# Enable or Disable the UploadBox 

The Enabled property is Boolean type, which allow us to set the enable or disable the UploadBox. By default value of Enabled property is true.

The following steps explain the configuration of Enabled property in UploadBox. 

In the VIEW page, add below code to configure the UploadBox element.

{% highlight CSHTML %}
   
<ej-upload-box id="UploadDefault" save-url="//mvc.syncfusion.com/Services/FileUpload/UploadBox/saveFiles" remove-url="//mvc.syncfusion.com/Services/FileUpload/UploadBox/removeFiles" enabled="false"></ej-upload-box>

{% endhighlight %}   

The following screenshot displays the output. 

![](Enable-or-Disable-the-UploadBox_images/Enable-or-Disable-the-UploadBox_img1.png)