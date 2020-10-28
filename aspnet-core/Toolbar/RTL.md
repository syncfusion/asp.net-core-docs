---
layout: post
title: RTL | Toolbar | ASP.NET Core | Syncfusion
description: rtl
platform: aspnet-core
control: Toolbar
documentation: ug
---

# RTL

EnableRTL property is Boolean type, which allow us to change the left-to-right alignment of the Toolbar to right-to-left (RTL) that sets the Toolbar to do its actions from right to left. Default value of EnableRTL is false. You can specify the EnableRTL property in the script as below, 

{% highlight CSHTML %}

// Add this code in your CSHTML page and refer local data section for data source

<ej-toolbar id="toolbarJson" enable-rtl="true" width="250px" dataSource="ViewBag.datasource">
	<e-toolbar-fields id="iconid" sprite-css-class="spriteCss">
</ej-toolbar>

{% endhighlight %}


![](RTL_images/RTL_img1.png)

Toolbar from RTL
{:.caption}