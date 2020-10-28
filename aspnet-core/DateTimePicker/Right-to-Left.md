---
layout: post
title: Right to Left | DateTimePicker | ASP.NET Core | Syncfusion
description: right-to-left
platform: aspnet-core
control: DateTimePicker
documentation: ug
---

# Right-to-Left

RTL control supports right-to-left functionality and features for languages that work right-to-left for selecting and editing date and time. You can change your popup and textbox display to read right-to-left. Arabic and Hebrew are written from right to left. The customer who has a right to left writing style can use this feature. You can achieve this in your DateTimePicker by using enable-rtl property. Setting this property to “true” allows you to write in the right to left format. Position of the toolbars are also changed to right to left.

1. Add the following code in your CSHTML page to render DateTimePicker widget.

{% highlight CSHTML %}

/*ej-Tag Helper code to render DateTimePicker*/
   
        @*Add the following code example to the corresponding CSHTML page to render DateTimePicker widget with right to left appearance*@

        <ej-date-time-picker id="DateTime" enable-rtl="true" ></ej-date-time-picker>

{% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render DateTimePicker*/

        @{Html.EJ().DateTimePicker("DateTime").EnableRTL(true).Render();}

{% endhighlight %}

N> To render the DateTimePicker Control you can use either Razor or Tag helper code as given in the above code snippet.

   
  



2. The following screenshot displays the output for the above code.

   ![](Right-to-Left_images/Right-to-Left_img1.png)

   Showcase of DateTimePicker with Right to Left appearance
   {:.caption}





