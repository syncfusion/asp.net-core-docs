---
layout: post
title: Create Samples | ASP.NET Core (Essential JS 1) | Syncfusion
description: Sample Creator is the utility that allows you to create Syncfusion ASP.NET Core Projects along with the samples based on Controls and Features selection
platform: aspnet-core
control: Syncfusion Extensions
documentation: ug
---

# Create Samples

The Syncfusion Sample Creator is a utility that allows you to create the Syncfusion ASP.NET Core (Essential JS 1) Projects with sample code of required Syncfusion component features and configuration of Syncfusion controls.

I> The Syncfusion ASP.NET Core Sample Creator utility is available from v15.2.0.40.

Use the following steps to create the Syncfusion ASP.NET Core (Essential JS 1) Application through the Sample Creator utility:

1. To launch ASP.NET Core (Essential JS 1) Sample Creator application, follow either one of the options below: 

   **Option 1:**   
   Click **Syncfusion Menu** and choose **Essential Studio for ASP.NET Core (EJ1) > Launch Sample Creator…** in **Visual Studio**.
   
   ![launch the Sample Creator via Syncfusion menu](Create-Samples_images/Syncfusion_Menu_SampleCreator.png)

   N> In Visual Studio 2019, Syncfusion menu is available under Extensions in Visual Studio menu.

   **Option 2:**  
   Launch the Syncfusion ASP.NET Core (Essential JS 1) Control Panel. Select the Sample Creator button to launch the ASP.NET Core (Essential JS 1) Sample Creator application. Refer to the following screenshot for more information.

   ![Syncfusion Essential Studio Essential JS 1 ASP.NET Core control panel to launch the Sample Creator](Create-Samples_images/SampleCreator-img1.png)

2. ASP.NET Core (Essential JS 1) Sample Creator lists the Syncfusion controls and its features

   ![Syncfusion Essential JS 1 ASP.NET Core Sample Creator wizard](Create-Samples_images/SampleCreator-img2.png)

   **Controls Selection:** Choose the required controls. The controls are grouped with Syncfusion products, and the controls are grouped product wise.

   ![Syncfusion Essential JS 1 ASP.NET Core Sample Creator Controls selection](Create-Samples_images/SampleCreator-img3.jpeg)

   **Feature Selection:** Based on the controls, the feature is enabled to choose the features of the corresponding controls.

   ![Syncfusion Essential JS 1 ASP.NET Core Sample Creator Features selection](Create-Samples_images/SampleCreator-img4.png)

   **Project configurations**

   1. You can configure the following project details in the Sample Creator.

      * **Project Type:** Select the type of ASP.NET Core Project, either .NET Core or .NET Framework.
   
      * **ASP.NET Core Version:** Select the version of ASP.NET Core Project.
        
        ![Select the version of ASP.NET Core Project](Create-Samples_images/SampleCreator-img10.png)

      * **VS Version:** Choose the Visual Studio version.
   
      * **Assets From:** Load the Syncfusion assets to ASP.NET Core Project, either CDN or Installed Location.

      * **Name:** Name your Syncfusion ASP.NET Core Application.

      * **Location:** Choose the target location of your project.

      * **Theme Selection:** Choose the required theme. This section shows the controls preview before creating the Syncfusion project.

      ![Syncfusion Essential JS 1 ASP.NET Core Sample Creator project configuration section](Create-Samples_images/SampleCreator-img5.png)

   2. Click **Create** button. After creating the project, open the project by clicking **Yes**. If you click **No**, the corresponding location of the project will be opened. Refer to the following screenshot for more information.

      ![The project successfully created using Syncfusion Essential JS 1 ASP.NET Core Sample Creator](Create-Samples_images/SampleCreator-img6.png)

   3. The new Syncfusion ASP.NET Core (Essential JS 1) project is created with the resources.

   * Added the required Controllers and View files in the project.

     ![Required View and Class files add in the project for the chosen controls](Create-Samples_images/SampleCreator-img7.png)

   * Included the required Syncfusion ASP.NET Core (Essential JS 1) scripts and theme files.

     ![Required scripts and themes files included in the project](Create-Samples_images/SampleCreator-img9.png)

   * Restored the required Syncfusion NuGet packages for selected controls under dependencies.

     ![Required NuGet packages restored for the selected Syncfusion Essential JS 1 ASP.NET Core controls](Create-Samples_images/SampleCreator-img8.png)
