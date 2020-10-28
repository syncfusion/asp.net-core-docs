---
layout: post
title: Getting Started | SplitButton | ASP.NET Core | Syncfusion
description: getting started 
platform: aspnet-core
control: SplitButton
documentation: ug
---

# Getting Started 

This section explains briefly about how to create a Split Button in ASP.NET Core application.

## Create your first Split Button in ASP.NET Core

The HTML button element and the <UL>, <LI> can be easily configured as Essential ASP.NET Core Split Button control.  The basic rendering of Essential ASP.NET Core Split Button is achieved by using default functionality. Initially the TargetID is a mandatory one, without this field it acts as normal button on two sides.

### Create Split Button Control in ASP.NET Core

Essential ASP.NET Core Split Button control contains built-in features such as Click and different option choosing. You can easily create the Split Button control by using Tag helper as follows.

1. You can create a .NetCore Project with the help of the given [ASP.NET Core-Getting Started](https://help.syncfusion.com/aspnet-core/getting-started) documentation.
2. Add the following code to the corresponding View page to render Split Button.


   ~~~ cshtml

/*ej-Tag Helper code to render SplitButton*/   

	<ej-split-button id="sbutton" text="Save" show-rounded-corner="true" size="Large" target-id="target" />

   ~~~

{% highlight CSHTML%}

/*Razor code to render SplitButton*/

    @{Html.EJ().SplitButton("sbutton").Text("Save").ShowRoundedCorner(true).Size(ButtonSize.Large).TargetID("target").Render();}

{% endhighlight %}

N> To render the SplitButton Control you can use either Razor or Tag helper code as given in the above code snippet.
  

3. Add the following <UL>, <LI> elements to render Split Button with popup option.


   ~~~ cshtml
   
   <ul id="target">

		<li><span>Open</span></li>

		<li><span>Save</span></li>

		<li><span>Delete</span></li>

	</ul>      

   ~~~
  

Output of the above scripts,



![](Getting-Started_images/Getting-Started_img1.png)



