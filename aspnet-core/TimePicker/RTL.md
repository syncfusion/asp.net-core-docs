---
layout: post
title: RTL | TimePicker | ASP.NET Core | Syncfusion
description: rtl
platform: aspnet-core
control: TimePicker
documentation: ug
---

# RTL

This feature supports to change the left-to-right alignment of the TimePicker widget to right-to-left when set the EnableRTL as true. By default EnableRTL value is set as “false”. The custom template TimePicker also supports RTL.

## Enabling Right-To-Left Support

The following steps explains you in enabling the right-to-left property for the TimePicker.

1. Add the following code to the corresponding view page to render the TimePicker.   


{% highlight CSHTML %}

/*ej-Tag Helper code to render TimePicker*/

@*Add the following code example to the corresponding CSHTML page to render TimePicker widget with right to left apperence*@
 
 <ej-time-picker id="time" enable-rtl="true"></ej-time-picker>
 

{% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render TimePicker*/

    @{Html.EJ().TimePicker("time").EnableRTL(true).Render();}

{% endhighlight %}

N> To render the TimePicker Control you can use either Razor or Tag helper code as given in the above code snippet.


The following screenshot illustrates a TimePicker control when EnableRTL is set to “true”



![](RTL_images/RTL_img1.png)

TimePicker template with RTL support
{:.caption}

