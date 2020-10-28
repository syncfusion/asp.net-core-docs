---
layout: post
title: Getting Started | ASP.NET Core | Syncfusion
description: Getting Started with razor pages.
platform: aspnet-core 
control: Common 
documentation: ug
---

# Getting Started

> Starting with v16.2.0.x, if you reference Syncfusion assemblies from trial setup or from the NuGet feed,you also have to include a license key in your projects.
Please refer to this [link](https://help.syncfusion.com/common/essential-studio/licensing/license-key#aspnet-core) to know about registering Syncfusion license key in
your ASP.NET Core application to use our components.

## Create ASP.NET Core application with Razor pages

### System Requirements:

To create an razor application in ASP.NET Core, you need to make sure, whether you have installed the following software on your machine

* Visual Studio 2017.

* DotNetCore [2.x](https://www.microsoft.com/net/download/dotnet-core).

### Configure Syncfusion UI Components in ASP.NET Core Application using NuGet packages:

The following steps helps to create a ASP.NET Core web application to configure our components.

*  Open Visual Studio 2017 to create **ASP.NET Core web application**.

* Select **Installed > Visual C# > .NET Core** and select **ASP.NET Core Web Application** and change the application name and click **OK**.

![create application](getting-started-razor-images/image1.png)

* Choose .NET Core with **ASP.NET Core 2.x** and select **Web Application** template, then click OK. The web application project is successfully created with default ASP.NET Core template.

![template selection](getting-started-razor-images/image2.png)

*  After project creation, install the Syncfusion NuGet packages in your application by following the below given steps.

> The Syncfusion ASP.NET Core NuGet package can be installed from [https://www.nuget.org/packages/Syncfusion.EJ.AspNet.Core](https://www.nuget.org/packages/Syncfusion.EJ.AspNet.Core)
    
* Right click on your project references and then select “**Manage NuGet Package**” option. 

![install nuget](getting-started-razor-images/image5.png)

* In the new window, choose the “**nuget.org**” from the package source dropdown. And check the “**include prerelease**” option.

* Now, browse and select `Syncfusion.EJ.AspNet.Core` NuGet package from the NuGet solution window and then, install the selected NuGet package in your application.

![install nuget](getting-started-razor-images/image3.png)

After installing the packages, Open the **~/Pages/_ViewImports.cshtml** file and import the Syncfusion packages.

{% highlight cshtml %}

    @using Syncfusion.JavaScript
    
    @addTagHelper "*, Syncfusion.EJ"
    
{% endhighlight %}

* Add the client-side resources through CDN or local package in **~/Pages/_Layout.cshtml** layout page.

{% highlight cshtml %}

    <environment include="Development">
        <!-- Essential Studio for JavaScript  theme reference -->
        <link rel="stylesheet" href="//cdn.syncfusion.com/17.1.0.38/js/web/flat-azure/ej.web.all.min.css" />
        <!-- Essential Studio for JavaScript  script references -->
        <script src="//cdn.syncfusion.com/js/assets/external/jsrender.min.js"></script>
        <script src="//cdn.syncfusion.com/17.1.0.38/js/web/ej.web.all.min.js"></script>

    </environment>

{% endhighlight %}

*  Add **ScriptManager** to the bottom of the **layout.cshtml** page. The **ScriptManager** used to place our control initialization script in the page.

    {% highlight cshtml %}
    
        <ej-script-manager></ej-script-manager>
    
    {% endhighlight %}

*  Now open your view page to render our Syncfusion components in Tag Helper syntax.
    
    {% highlight cshtml %}
    
        <ej-date-picker id="datepicker" value="@DateTime.Now"></ej-date-picker>
    
    {% endhighlight %}

*  Finally compile your project, after successful compilation then press F5 key to deploy your project.   

 ![output](getting-started-razor-images/image4.png)
