---
layout: post
title: RTL Support | Rotator | ASP.NET Core | Syncfusion
description: rtl support
platform: aspnet-core
control: Rotator
documentation: ug
---

# RTL Support

enable-rtl feature supports to change the left-to-right alignment of the Rotator to right-to-left (RTL). (I.e.) Sets the Rotator to do its actions from right to left. The EnableRTL property sets the Rotator from right to left. The value set to this property is Boolean type.

{% highlight CSHTML %}

/ / Add this code in your CSHTML page and refer local data section for binding Rotator items.

<ej-rotator id="rot" datasource="ViewBag.datasource" slide-height="350px"  slide-width="600px" is-responsive="true" enable-rtl="true">
    <e-rotator-fields text="text" url="url" />
</ej-rotator>)

{% endhighlight %}