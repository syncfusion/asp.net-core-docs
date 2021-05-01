---
layout: post
title: Getting Started with ASP.NET Core Tooltip control | Syncfusion
description: Learn here about getting started with Syncfusion Essential Studio ASP.NET Core Tooltip control, its elements, and more.
platform: aspnet-core
control: Tooltip
documentation: ug
keywords : Dotnetcore Tooltip,ASP Dotnet Core Tooltip, core Tooltip,aspnetcore Tooltip widget,Dotnetcore Tooltip Appearance,Dotnetcore Tooltip Dimensions
---
# Getting started with ASP.NET Core Tooltip

## Create a Tooltip

Using the following steps, you can create a Tooltip control. The basic rendering of ASP.NET Core Tooltip is achieved with default functionality.



1. You can create a Core Project and add necessary assembly and script with the help of the given [Dotnet Core-Getting Started](https://help.syncfusion.com/aspnet-core/gettingstarted/getting-started-1-1-0) Documentation.



2. Add the mentioned code to the corresponding view page for Tooltip rendering.

{% highlight CSHTML %}

/*ej-Tag Helper code to render Tooltip*/

    <div class="frame">    
        <div class="img" id="sample">
            <a target="_blank" href="image/taj.png">
            <img src="http://aspnetcore.syncfusion.com/images/tooltip/template-05.png" alt="Delphi">
            </a>
            <div class="desc">Delphi Succinctly</div>
        </div>
    </div>

    <ej-tooltip id="sample" content="Learn the fundamentals of Delphi to build a variety of solutions for many devices and platforms.">
    </ej-tooltip>

{% endhighlight %}

{% highlight Razor %}

/*Razor code to render Tooltip*/

    <div class="frame">    
        <div class="img" id="sample1">
            <a target="_blank" href="image/taj.png">
            <img src="http://aspnetcore.syncfusion.com/images/tooltip/template-05.png" alt="Delphi">
            </a>
            <div class="desc">Delphi Succinctly</div>
        </div>
    </div>

    @Html.EJ().Tooltip("sample1").Content("Learn the fundamentals of Delphi to build a variety of solutions for many devices and platforms.")

{% endhighlight %}

N> To render the Tooltip Control you can use either Razor or Tag helper code as given in the above code snippet.

Apply the following style sheet

{% highlight css %}

    <style>
        div.img {
            border: 1px solid #ccc;
            width: 159px;
            height: 213px;
            left: 35%;
            position: relative;
            top: 20%;
        }
        div.img img {
            width: 159px;
            height: 179px;
        }
        div.desc {
            padding: 8px;
            text-align: center;
        }
    </style>
    
{% endhighlight %}

![Getting-Started_images1](Getteing-Started_images/Getteing-Started_img1.jpeg)

## Setting Dimensions

Tooltip dimensions can be set using [width](http://help.syncfusion.com/js/api/ejtooltip#members:width) and [height](http://help.syncfusion.com/js/api/ejtooltip#members:height) API.

{% highlight CSHTML %}
 
 /*ej-Tag Helper code to render Tooltip*/

    <div class="control">
        TypeScript lets you write <a id="testSample"><u> JavaScript</u> </a>the way you really want to.
    </div>

    <ej-tooltip id="testSample" content="JavaScript is the programming language of HTML and the Web." width="100px" height="100px">
    </ej-tooltip>

{% endhighlight %}

{% highlight Razor %}
 
 /*Razor code to render Tooltip*/

    <div class="control">
        TypeScript lets you write <a id="tooltip1"><u> JavaScript</u> </a>the way you really want to.
    </div>

    @Html.EJ().Tooltip("tooltip1").Content("JavaScript is the programming language of HTML and the Web.").Width("100px").Height("100px")
        
{% endhighlight %}

## Tooltip Appearance 

You can configure the appearance of the Tooltip with the title, close button and call out as your application requires.

{% highlight CSHTML %}
 
 /*ej-Tag Helper code to render Tooltip*/

    <div class="img" id="sample2">
        <a target="_blank" href="image/taj.png">
        <img src="http://aspnetcore.syncfusion.com/images/tooltip/template-05.png" alt="Delphi">
        </a>
        <div class="desc">Delphi Succinctly</div>
    </div>

    <ej-tooltip id="sample2" content="Learn the fundamentals of Delphi to build a variety of solutions for many devices and platforms." width="180px" title="Delphi Succinctly" close-mode="Sticky" is-balloon="false">
    </ej-tooltip>

{% endhighlight %}

{% highlight Razor %}
 
 /*Razor code to render Tooltip*/

    <div class="img" id="sample">
        <a target="_blank" href="image/taj.png">
        <img src="http://aspnetcore.syncfusion.com/images/tooltip/template-05.png" alt="Delphi">
        </a>
        <div class="desc">Delphi Succinctly</div>
    </div>

    @Html.EJ().Tooltip("sample").Content("Learn the fundamentals of Delphi to build a variety of solutions for many devices and platforms.").Width("180px").Title("Delphi Succinctly").CloseMode(CloseMode.Sticky).IsBalloon(false)
    
{% endhighlight %}


Apply the following styles to show the Tooltip.

{% highlight css %}

    <style>
        div.img {
            border: 1px solid #ccc;
            float: left;
            box-sizing: border-box;
            height: 200px;
            width: 146px;
        }
        div.img img{
            width: 100%;
            height: 166px;
        }
        div.desc {
            padding: 6px;
            text-align: center;
        }
    </style>
    
{% endhighlight %}

![Getting-Started_images2](Getteing-Started_images/Getteing-Started_img2.jpeg)

