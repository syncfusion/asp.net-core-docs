---
layout: post
title: Appearance and Styling | Toolbar | ASP.NET Core | Syncfusion
description: appearance and styling 
platform: aspnet-core
control: Toolbar
documentation: ug
---

# Appearance and Styling 

## Adjusting Toolbar size

### Height

The Height property is used to set height of the Toolbar. Set the value to this property as number or string type.

{% highlight CSHTML %}

//Add this code in your CSHTML page and refer local data section for data source

<ej-toolbar id="toolbar" width="250px" height="300px" datasource="ViewBag.datasource">
    <e-toolbar-fields id="iconid" sprite-css-class="spriteCss" />
</ej-toolbar>

{% endhighlight %}

### Width

The Width property is used to set width of the Toolbar. Set the value to this property as number or string type.

{% highlight CSHTML %}

// Add this code in your CSHTML page and refer local data section for data source

<ej-toolbar id="toolbar" width="250px" datasource="ViewBag.datasource">
    <e-toolbar-fields id="iconid" sprite-css-class="spriteCss" />
</ej-toolbar>

{% endhighlight %}

## Enabling Rounded Corner 

The ShowRoundedCorner property is Boolean type, which allows us to enable rounded corner for Toolbar control. Default value of this property is false. You can specify the property ShowRoundedCorner in the script as below,

{% highlight CSHTML%}

// Add this code in your CSHTML page and refer local data section for data source

<ej-toolbar id="toolbar" width="250px" show-rounded-corner="true" datasource="ViewBag.datasource">
    <e-toolbar-fields id="iconid" sprite-css-class="spriteCss" />
</ej-toolbar>

{% endhighlight %}

![](Appearance-and-Styling_images/Appearance-and-Styling_img1.png)

ToolBar control with rounded corner
{:.caption}

## Enabling Separator 

The EnableSeparator property is Boolean type, which allow us to set separator between Toolbar items in Toolbar control. It separates one or more list items. When you want to separate two set of items, then define them in two separate ‘UL’ elements. Default value of EnableSeparator is false.

{% highlight CSHTML %}

//Add this code in your CSHTML page and refer local data section for data source

<ej-toolbar id="toolbar" width="250px" enable-separator="true" datasource="ViewBag.datasource">
    <e-toolbar-fields id="iconid" sprite-css-class="spriteCss" />
</ej-toolbar>

{% endhighlight %}

![](Appearance-and-Styling_images/Appearance-and-Styling_img2.png)

ToolBar control with item separator
{:.caption}

## Themes

You can control the style and appearance of the Toolbar based on CSS classes. In order to apply styles to the Toolbar control, you can refer two files - ej.widgets.core.min.css and ej.theme.min.css. When you refer ej.widgets.all.min.css file, it is not necessary to include the files ej.widgets.core.min.css and ej.theme.min.css in your project, as ej.widgets.all.min.css is the combination of these two. 

By default, there are 12 themes support available for Toolbar control namely

* default-theme
* flat-azure-dark
* fat-lime
* flat-lime-dark
* flat-saffron
* flat-saffron-dark
* gradient-azure
* gradient-azure-dark
* gradient-lime
* gradient-lime-dark
* gradient-saffron
* gradient-saffron-dark

## CssClass 

The CssClass property is used to set root class for Toolbar control theme. Set the value to this property as string type.

{% highlight CSHTML %} 

//Add this code in your CSHTML page and refer local data section for data source

<ej-toolbar id="toolbar" width="250px" css-class="gradient-lime" datasource="ViewBag.datasource">
    <e-toolbar-fields id="iconid" sprite-css-class="spriteCss" />
</ej-toolbar>

{% endhighlight %}

{% highlight css %}

<style>

	.gradient-lime 
	{

		background-color: yellowgreen;

	}

</style>

{% endhighlight %}

![](Appearance-and-Styling_images/Appearance-and-Styling_img3.png)

ToolBar control with CssClass
{:.caption}