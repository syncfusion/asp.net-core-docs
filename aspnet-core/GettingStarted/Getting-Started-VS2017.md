---
layout: post
title: Getting Started | ASP.NET Core | Syncfusion
description: Getting Started.
platform: aspnet-core 
control: Common 
documentation: ug
---


# Getting Started
 
## ASP.NET Core 1.1 Application Using Visual Studio 2017

### System Requirements

To work with ASP.NET Core 1.1 you need to make sure, whether you have installed the following software on your machine

* Visual Studio 2017.
* DotNetCore [1.1 SDK](https://go.microsoft.com/fwlink/?LinkID=835014)

### Configure Syncfusion UI Components in ASP.NET Core Application

You can configure Syncfusion components into an ASP.NET Core Application in following ways.

* Using Syncfusion Project Templates
* Using Syncfusion Project Conversion utility
* Configure the project manually

#### Using Syncfusion Project Templates

Syncfusion provides the **Visual** **Studio** **Project** **Templates** for the Syncfusion ASP.NET Core platform to create Syncfusion ASP.NET Core Web Application.

I> The Syncfusion ASP.NET Core project templates are available from v15.2.0.40.

The following steps help you to create the **Syncfusion** **ASP****.****NET** **Core** **Application** through the **Visual** **Studio** **Project** **Template**.

1. To create a Syncfusion ASP.NET Core (Essential JS 1) project, follow either one of the options below:

   **Option 1:**   
   Click **Syncfusion Menu** and choose **Essential Studio for ASP.NET Core (EJ1) > Create New Syncfusion Project…** in **Visual Studio**.

   ![Choose Syncfusion ASP.NET Core Application from Visual Studio New Project dialog via Syncfusion menu](getting-started_images/Syncfusion_Menu_ProjectTemplate.png)

   N>In Visual Studio 2019, Syncfusion menu available under Extension in Visual Studio menu.

   **Option 2:**   
   Choose **File > New > Project** and navigate to **Syncfusion > .NET Core > Syncfusion ASP.NET Core (Essential JS 1) Web Application** in **Visual Studio**.

   ![Choose Syncfusion ASP.NET Core Application from Visual Studio New Project dialog](getting-started_images/Syncfusion-Project-Templates_img1.png)

2. Name the **Project**, choose the destination location when required and set the Framework of the project, then click **OK**. The Project Configuration Wizard appears.

   N> Minimum target Framework version is 4.5.2 for Syncfusion ASP.NET Core Project Templates.
   
3. Choose the options to configure the Syncfusion ASP.NET Core Application by using the following Project Configuration dialog.

   ## Project configurations:

   **Project Type:** Select the type of ASP.NET Core Project, either .NET Core or .NET Framework.

   **.NET Core Version:** Select the version of ASP.NET Core Project, either ASP.NET Core 1.0 or ASP.NET Core 1.1.

   **Assets From:** Load the Syncfusion assets to ASP.NET Core Project, either Bower, CDN or Installed Location.

   **Theme Selection:** Choose the required Theme.

   **Components:** Choose the Required Syncfusion components to configure.

   ![Syncfusion Essential JS 1 ASP.NET Core Project Configuration wizard](getting-started_images/Syncfusion-Project-Templates_img2.jpeg)
   
4. Once you click Create button, the Syncfusion ASP.NET Core Application is created.

5. Required Syncfusion NuGet/Bower packages, Scripts and CSS are added to the Project.

   ![Required Syncfusion NuGet/Bower packages added to the Syncfusion Essential JS 1 ASP.NET Core project](getting-started_images/Syncfusion-Project-Templates_img3.png)

   ![Required Syncfusion Scripts and Themes added to the Syncfusion Essential JS 1 ASP.NET Core project](getting-started_images/Syncfusion-Project-Templates_img4.jpeg)

6. Then, Syncfusion licensing registration required message box will be shown as follow, if you are installed the trial setup or NuGet packages since Syncfusion introduced the licensing system from 2018 Volume 2 (v16.2.0.41) Essential Studio release. Please navigate to the [help topic](https://help.syncfusion.com/common/essential-studio/licensing/license-key#how-to-generate-syncfusion-license-key) which is shown in the licensing message box to generate and register the Syncfusion license key to your project. Refer to this [blog](https://blog.syncfusion.com/post/Whats-New-in-2018-Volume-2-Licensing-Changes-in-the-1620x-Version-of-Essential-Studio.aspx) post for understanding the licensing changes introduced in Essential Studio.
  
   ![Syncfusion license registration information for Syncfusion Essential JS 1 ASP.NET Core project](getting-started_images/Syncfusion-Project-Templates_img5.png)  

#### Using Syncfusion Project Conversion utility

Syncfusion Project Conversion is a Visual Studio add-in that converts an existing ASP.NET Core application into a Syncfusion ASP.NET Core Web application by adding the required assemblies and resource files.

I> The Syncfusion ASP.NET Core Web Application Project Conversion utility is available from v15.2.0.40.

The following steps help you to use the Syncfusion Project Conversion in the existing ASP.NET Core Web Application.

1. Open an existing Microsoft ASP.NET Core Web Application or create a new Microsoft ASP.NET Core Web Application. 

2. To open Project Conversion Wizard, follow either one of the options below: 

   **Option 1:**  
   Click **Syncfusion Menu** and choose **Essential Studio for ASP.NET Core (EJ1) > Convert to Syncfusion ASP.NET Core Application…** in **Visual Studio**.

   ![Syncfusion Essential JS 1 ASP.NET Core Project Conversion via Syncfusion menu](getting-started_images/Syncfusion_Menu_Project_Conversion.png)

   N> In Visual Studio 2019, Syncfusion menu available under Extension in Visual Studio menu.

   **Option 2:**  
   Right-click the Project from Solution Explorer, select **Syncfusion Essential JS 1**, and then choose **Convert to Syncfusion ASP.NET Core (Essential JS 1) Application...** Refer to the following screenshot for more information.

   ![Syncfusion Essential JS 1 ASP.NET Core Project Conversion add-in](getting-started_images/Project-Conversion_img1.png)

3. Project Conversion Wizard opens to configure the project.

   ![Syncfusion Essential JS 1 ASP.NET Core Project Conversion wizard](getting-started_images/Project-Conversion_img2.jpeg)

   **Choose the assets from:**

   * Bower - Refer to the assets from Bower package manager. 

   * CDN - Refer to the assets from Syncfusion CDN links.

   * Installed Location - Refer to the assets from Syncfusion installed locations.     
   
   ![Choose the required assets for Syncfusion Essential JS 1 ASP.NET Core project](getting-started_images/Project-Conversion_img3.jpeg)
   
   **Choose the Theme:**
   
   The master page of project will be updated based on selected theme. The Theme Preview section shows the controls preview before convert into a Syncfusion project
   
   ![Choose the theme to apply on the master page of the ASP.NET Core project](getting-started_images/Project-Conversion_img4.jpeg)

   **Choose Copy Global Resources:** 
    
   The localization culture files will be shipped into Scripts\ej\i18n directory of the project.

   ![Choose Copy Global Resources to ship the localization culture files for ASP.NET Core project](getting-started_images/Project-Conversion_img14.jpeg)   

4. Choose the required controls from Components section and Click the **Convert** button to convert it into a Syncfusion Project.

   ![Select the required components from the Components selection in the Syncfusion ASP.NET Core Project Conversion Wizard](getting-started_images/ProjectConversion_img5.jpeg)
   
   The **Project Backup** dialog will be opened. If click Yes it will backup the current project before converting it to Syncfusion project. If click No it will convert the project to Syncfusion project without backup. 
   
   ![Syncfusion Essential JS 1 ASP.NET Core Project converson backup dialog](getting-started_images/Project-Conversion_img6.jpeg)

5. The required Syncfusion NuGet/Bower packages, Scripts and CSS are included in the ASP.NET Core Web Application. Refer to the following screenshots for more information.

   ![Required Syncfusion Essential JS 1 ASP.NET Core NuGet/Bower packages](getting-started_images/Project-Conversion_img7.png)

   ![Required Syncfusion Essential JS 1 ASP.NET Core themes and scripts](getting-started_images/Project-Conversion_img8.jpeg)
   
Once you converted your ASP.NET Core Web Application to Syncfusion ASP.NET Core Web Application using Syncfusion Visual Studio Extension, Perform the following steps to render the Syncfusion controls to your project.

1. Include the Syncfusion control snippets to any of the view page of your project. Refer the following screenshot for more information.

   ![Syncfusion Essential JS 1 ASP.NET Core datepicker control code snippet](getting-started_images\Project-Conversion_img11.jpeg)

2. Then run the project and the following output will be displayed.

   ![Syncfusion Essential JS 1 ASP.NET Core datepicker control output](getting-started_images\Project-Conversion_img12.jpeg)
   
   
   I> Refer all the required external and internal scripts only once in the page with proper order. Refer this [link](https://help.syncfusion.com/js/control-initialization#adding-the-required-javascript-files) to know about order of script reference.
   
#### Configure the project manually

The following steps helps to create an ASP.NET Core web application to utilize Syncfusion components.

* Open Visual Studio 2017 to create ASP.NET Core web application.

![create ASP.NET Core web application via New Project Template wizard](getting-started_images/getting-started_img1.png)

*  After project creation, install the Syncfusion NuGet packages in your application by following the below given steps.

> The Syncfusion ASP.NET Core NuGet package can be installed from [https://www.nuget.org/packages/Syncfusion.EJ.AspNet.Core](https://www.nuget.org/packages/Syncfusion.EJ.AspNet.Core)
    
* Right click on your project references and then select “**Manage NuGet Package**” option. 

![install nuget](getting-started-razor-images/image5.png)

* In the new window, choose the “**nuget.org**” from the package source dropdown. And check the “**include prerelease**” option.

* Now, browse and select `Syncfusion.EJ.AspNet.Core` NuGet package from the NuGet solution window and then, install the selected NuGet package in your application.

![Syncfusion Packages will list in Nuget Package Manager](getting-started_images/getting-started_img18.png)

> The ASP.NET Core NuGet packages versioning has been streamlined as 16.1.0.32 in shorter than older versioning (16.1600.0.32) from Volume 1, 2018 service pack 1 release (16.1.0.32). Since all the framework version wise assemblies are grouped into a single package.

> The package **"Syncfusion.EJ.MVC"** renamed into **"Syncfusion.EJ.AspNet.Core"** from Volume 3, 2016 (14.3.0.49) release. The "**preview2-final**" keyword removed our Syncfusion packages naming from Volume 1, 2017 (15.1.0.33) release.

* After successful NuGet installation, open your **bower.json** file and specify our bower name “**syncfusion-javascript**” and the value with *. The * specifies the latest version of our scripts and themes files. After, the bower installation has completed, the project folder structure look like a below structure.

![Project folder structure after bower installation complete](getting-started_images/getting-started_img3.png)

*  Now open **_viewImports.cshtml** file from the views folder and add the following namespace for components references and Tag Helper support.

{% highlight cshtml %}

@using Syncfusion.JavaScript

@addTagHelper "*, Syncfusion.EJ"

{% endhighlight %}

*  Refer the necessary scripts and CSS files in your **layout.cshtml** page from **lib -> syncfusion-javascript** folder.

N> Include the below mentioned scripts and CSS references under the appropriate environment. (For eg: If your environment is "Development", then refer the scripts and CSS files under the tag *environment names="Development"*). Refer all the required external and internal scripts only once in the page with proper order. Refer this [link](https://help.syncfusion.com/js/control-initialization#adding-the-required-javascript-files) to know about order of script reference.

   {% highlight cshtml %}
   
<html>

<head>

<link rel="stylesheet" href="~/lib/bootstrap/dist/css/bootstrap.css" />

<link href="~/lib/syncfusion-javascript/Content/ej/web/bootstrap-theme/ej.web.all.min.css" rel="stylesheet" />

<link href="~/lib/syncfusion-javascript/Content/ej/web/responsive-css/ej.responsive.css" rel="stylesheet" />

<script src="~/lib/jquery/dist/jquery.js"></script>

<script src="~/lib/jsrender/jsrender.min.js"></script>

<script src="~/lib/syncfusion-javascript/Scripts/ej/web/ej.web.all.min.js"></script>

</head>

<body>


</body>

</html>

   {% endhighlight %}

N> jQuery.easing external dependency has been removed from version 14.3.0.49 onwards. Kindly include this jQuery.easing dependency for versions lesser than 14.3.0.49 in order to support animation effects.

*  Add **ScriptManager** to the bottom of the **layout.cshtml** page. The **ScriptManager** used to place our control initialization script in the page.

   {% highlight cshtml %}
   
    <ej-script-manager></ej-script-manager>
	
   {% endhighlight %}

*  Now open your view page to render our Syncfusion components in Tag Helper syntax.   
   
   {% highlight cshtml %}
   
	<ej-date-picker id="datepicker" value="@DateTime.Now"></ej-date-picker>
	
   {% endhighlight %}

*  Finally compile your project, after successful compilation then press F5 key to deploy your project.   

   ![output for your application with syncfusion control](getting-started_images/getting-started_img4.png)
   
### Syncfusion Project Migration

Syncfusion Project Migration is a Visual Studio add-in that allows you to migrate the existing Syncfusion ASP.NET Core Web Application from one Essential Studio version to another version.

I> The Syncfusion ASP.NET Core Web Application Project Migration utility is available from v15.2.0.40.

The following steps help you to migrate your existing Syncfusion ASP.NET Core Web Application. 

1. To open Migration Wizard, follow either one of the options below: 

   **Option 1:**  
   Click **Syncfusion Menu** and choose **Essential Studio for ASP.NET Core (EJ1) > Migrate Project…** in **Visual Studio**.
   
   ![Syncfusion Essential JS 1 ASP.NET Core Project Migration via Syncfusion menu](getting-started_images/Syncfusion_Menu_Project_Migration.png)

   N> In Visual Studio 2019, Syncfusion menu available under Extension in Visual Studio menu.
   
   **Option 2:**  
   Right-click the **Syncfusion ASP.NET Core Web Application** from Solution Explorer and select **Syncfusion Essential JS 1**. Choose **Migrate the Essential JS 1 Project to Another Version...**

   ![Syncfusion Essential JS 1 ASP.NET Core Project Migration add-in](getting-started_images/Project-Migration_img1.png)

2. The **Project Migration** window appears. You can choose the required Essential Studio version that is installed in the machine. 

   ![Syncfusion Essential JS 1 ASP.NET Core Project Migration window](getting-started_images/Project-Migration_img2.jpeg)

3. The **Project Migration** window allows you to configure the following options:

   i. **Essential Studio Version:** Select any version from the list of installed versions.
   
   ii. **Assets From:** Load the Syncfusion assets to ASP.NET Core Project, either Bower, CDN or Installed Location.
   
4. Click the Migrate Button. The **Project Backup** dialog will be opened. If click Yes it will backup the current project before migrate the Syncfusion project. If click No it will migrate the project to required Syncfusion version without backup
   
   ![Syncfusion Essential JS 1 ASP.NET Core Project Migration backup dialog](getting-started_images/Project-Migration_img3.jpeg)
      
5. The Syncfusion NuGet/Bower Packages, Scripts and CSS are updated to the corresponding version in the project.