---
layout: post
title: Template | Rotator | ASP.NET Core | Syncfusion
description: template 
platform: aspnet-core
control: Rotator
documentation: ug
---

# Template 

This Template feature implements in Rotator control. Rotator template will allow you to customize the rendering structure for its li elements. Using template API with data binding can render image, audio or video inside the Rotator control. 

The property template specifies the structure for slide li elements. The default value is null. The value set to this property is string. 


1. Add the below code in your view page to render the Rotator

 
{% highlight CSHTML %}

	// Add the following code in View page to configure Rotator widget
<ej-rotator id="rot" datasource="ViewBag.datasource" slide-height="350px"  is-responsive="true"  template="<div class='image'><img src = ${url} title = ${text} class='image'/> </div>">
    <e-rotator-fields text="text" url="url" />
</ej-rotator>

{% endhighlight %}
          


   
   
   