---
layout: post
title: Time Format | TimePicker | ASP.NET Core | Syncfusion
description: time format
platform: aspnet-core
control: TimePicker
documentation: ug
---

# Time Format

TimePicker widget provides you an option to change the TimeFormat property.

## Steps to change Time Format of TimePicker widget

The following steps explains you to change the time format for the TimePicker.

1. Add the following code to the corresponding view page to render the TimePicker.



{% highlight CSHTML %}

/*ej-Tag Helper code to render TimePicker*/

@*Add the following code example to the corresponding CSHTML page to render TimePicker widget with time format*@

<ej-time-picker id="time" time-format="hh:mm:tt ss"></ej-time-picker>
  
{% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render TimePicker*/

    @{Html.EJ().TimePicker("time").TimeFormat("hh:mm:ss tt").Render();}

{% endhighlight %}

N> To render the TimePicker Control you can use either Razor or Tag helper code as given in the above code snippet.

Execute the above code to render the following output.

![](Time-Format_images/Time-Format_img1.png)

TimePicker with TimeFormat.
{:.caption}
