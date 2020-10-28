---
layout: post
title: Getting-Started
description: getting started
platform: aspnet-core
control: Barcode 
documentation: ug
---

## Getting Started

Refer the [Getting Started](https://help.syncfusion.com/aspnet-core/getting-started) page of the Introduction part to know more about the basic system requirements and the steps to configure the Syncfusion components in an ASP.NET Core application.

Ensure once whether all the necessary dependency packages are included within the bower.json file as mentioned [here](https://help.syncfusion.com/aspnet-core/getting-started#configure-syncfusion-components-in-aspnet-core-application), so that the required scripts to render the Barcode control gets installed and loads into the mentioned location (wwwroot->lib) within your project.

Also, check whether the assembly dependency package Syncfusion.EJ added within the project.json file.

Now, refer the necessary scripts and CSS files into your _Layout.cshtml page from the wwwroot -> lib -> syncfusion-javascript folder. And use the below code snippet to render the Barcode.
{% highlight cshtml %}

<!DOCTYPE html>
<html>
 <head>
   <environment names="Development">
    <link rel="stylesheet" href="~/css/site.css" /> 
   </environment> 
 </head> 
<body> 
   <environment names="Development">
     <script src="~/lib/jquery/dist/jquery.js"></script> 
     <script src="~/js/site.js" asp-append-version="true"></script> 
     <script src="~/lib/syncfusion-javascript/Scripts/ej/web/ej.web.all.min.js"></script> 
  </environment> 
  
   <ej-barcode id="ejBarcode1" text="01234567" symbology-type=Code11 />
</body> 
</html>

{% endhighlight %}

