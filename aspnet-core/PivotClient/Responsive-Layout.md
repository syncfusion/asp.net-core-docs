---
layout: post
title: Responsive Layout | PivotClient | ASP.NET Core | Syncfusion
description: This document illustrates that how to enable responsive layout rendering in ASP.NET Core PivotClient control
platform: aspnet-core
control: PivotClient
documentation: ug
---

# Responsive layout

The pivot client widget supports responsive rendering based on the target device (desktop and tablet) resolution. It supports resolution up to 1024x600. You can enable responsiveness in the pivot client by setting the `is-responsive` property to true.

{% highlight CSHTML %}

<ej-pivot-client id="PivotClient1" is-responsive="true">
   //..
</ej-pivot-client>

{% endhighlight %}

![Responsive layout of ASP NET Core pivot client control](Responsive-Layout_images/responsive.png)
