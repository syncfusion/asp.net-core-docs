---
layout: post
title: Range | TimePicker | ASP.NET Core | Syncfusion
description: range
platform: aspnet-core
control: TimePicker
documentation: ug
---

# Range

TimePicker widget provide options to set the Range (MinTime & MaxTime) for the time.

## Steps to change MinTime & MaxTime of the TimePicker

The following steps explains you to change the Range of the TimePicker.

1. Add the following code to the corresponding view page to render the TimePicker.



{% highlight html %}

/*ej-Tag Helper code to render TimePicker*/

@*Add the following code example to the corresponding CSHTML page to render TimePicker widget with Min and Max time*@

 <ej-time-picker id="time"  min-time="10:00 AM" max-time="10:00 AM"></ej-time-picker>
 
{% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render TimePicker*/

    @{Html.EJ().TimePicker("time").MinTime("10:00 AM").MaxTime("10:00 PM").Render();}


{% endhighlight %}

N> To render the TimePicker Control you can use either Razor or Tag helper code as given in the above code snippet.


Execute the above code to render the following output.

![](Range_images/Range_img1.png)

Range for TimePicker widget
{:.caption}

