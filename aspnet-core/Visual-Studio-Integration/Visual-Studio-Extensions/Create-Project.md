---
layout: post
title: Create Project | ASP.NET Core (Essential JS 1) | Syncfusion
description: Syncfusion provides Visual Studio Project Templates for ASP.NET Core platform to create the Syncfusion ASP.NET Core Application using Essential JS 1 components
platform: aspnet-core
control: Syncfusion Extensions
documentation: ug
---

# Create ASP.NET Core application

Syncfusion provides the **Visual Studio Project Templates** for the Syncfusion ASP.NET Core platform to create the Syncfusion ASP.NET Core Application with the Essential JS 1 components.  

I> The Syncfusion ASP.NET Core project templates are available from v15.2.0.40.  

Use the following steps to create the **Syncfusion ASP.NET Core (Essential JS 1) Application** through the **Visual Studio Project Template**:

> Before use the Syncfusion ASP.NET Core (Essential JS 1) Project Template, check whether the **Syncfusion Essential JS1 AspNet Core VSExtensions** installed or not in Visual Studio Extension Manager by clicking on the Tools -> Extensions and Updates -> Installed for Visual Studio 2017 or lower and for Visual Studio 2019 by clicking on the Extensions -> Manage Extensions -> Installed.

1. To create a Syncfusion ASP.NET Core (Essential JS 1) project, follow either one of the options below:

   **Option 1**   
   Click **Syncfusion Menu** and choose **Essential Studio for ASP.NET Core (EJ1) > Create New Syncfusion Project…** in **Visual Studio**.

   ![Choose Syncfusion ASP.NET Core Application from Visual Studio New Project dialog via Syncfusion menu](Create-Project_images/Syncfusion_Menu_ProjectTemplate.png)

   N>In Visual Studio 2019, Syncfusion menu is available under Extensions in Visual Studio menu.

   **Option 2**   
   Choose **File > New > Project** and navigate to **Syncfusion > .NET Core > Syncfusion ASP.NET Core (Essential JS 1) Web Application** in **Visual Studio**.

   ![Choose Syncfusion ASP.NET Core Application from Visual Studio New Project dialog](Create-Project_images/Syncfusion-Project-Templates-img1.png)

2. Name the **Project**, choose the destination location, and set the .NET Framework of the project, and then click **OK**. The Project Configuration Wizard appears.

   N> Minimum target Framework is 4.5.2 for Syncfusion ASP.NET Core Project Templates.
   
3. Choose the options to configure the Syncfusion ASP.NET Core (Essential JS 1) application by using the following Project Configuration dialog.
   
   ![Syncfusion Essential JS 1 ASP.NET Core Project Configuration wizard](Create-Project_images/Syncfusion-Project-Templates-img2.png)

   **Project configurations**

   **Project Type:** Select the type of ASP.NET Core Project, either .NET Core or .NET Framework.

   **.NET Core Version:** Select the version of ASP.NET Core Project.

   ![Select the core version of ASP.NET Core Project](Create-Project_images/Syncfusion-Project-Templates-img3.png)

   **Assets From:** Load the Syncfusion assets to ASP.NET Core Project, either CDN or Installed Location.

   **Theme Selection:** Choose the required theme. The Theme Preview section shows the controls preview before convert into a Syncfusion project.

   ![Choose the required theme for ASP.NET Core Project](Create-Project_images/Syncfusion-Project-Templates-img4.png)

   **Components:** Choose the required Syncfusion components to configure.

   ![Choose the required Syncfusion controls](Create-Project_images/Syncfusion-Project-Templates-img5.png)

4. Click **Create**, the Syncfusion ASP.NET Core (Essential JS 1) Application has been created.

5. The required Syncfusion NuGet packages, Scripts, and CSS have been added to the project.

   ![Required Syncfusion NuGet/Bower packages added to the Syncfusion Essential JS 1 ASP.NET Core project](Create-Project_images/Syncfusion-Project-Templates-img6.png)

   ![Required Syncfusion Scripts and Themes added to the Syncfusion Essential JS 1 ASP.NET Core project](Create-Project_images/Syncfusion-Project-Templates-img7.png)

6. Then, Syncfusion licensing registration required message box will be shown, if you installed the trial setup or NuGet packages since Syncfusion introduced the licensing system from 2018 Volume 2 (v16.2.0.41) Essential Studio release. Navigate to the  [help topic](https://help.syncfusion.com/common/essential-studio/licensing/license-key#how-to-generate-syncfusion-license-key), which is shown in the licensing message box to generate and register the Syncfusion license key to your project. Refer to this [blog](https://blog.syncfusion.com/post/Whats-New-in-2018-Volume-2-Licensing-Changes-in-the-1620x-Version-of-Essential-Studio.aspx) post for understanding the licensing changes introduced in Essential Studio.

   ![Syncfusion license registration information for Syncfusion Essential JS 1 ASP.NET Core project](Create-Project_images/Syncfusion-Project-Templates-img8.jpeg)   


