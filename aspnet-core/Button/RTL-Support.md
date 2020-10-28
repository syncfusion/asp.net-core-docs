---
layout: post
title: RTL Support | Button  | ASP.NET Core | Syncfusion
description: rtl support
platform: aspnet-core
control: Button
documentation: ug
---

# RTL Support

In some cases you can use right to left alignment. Here, RTL support is provided using EnableRTL property. In RTL mode when you have more than one content (image/text, image/image) in button, then these content are aligned in right to left format. For example, when text is in left and image is in right position, after applying right to left alignment these position are interchanged.

The following steps explains the details about rendering the button with Right to left alignment support.

1. In the View page, configure the Button widget as follows.


{% highlight CSHTML %}

/*ej-Tag Helper code to render Button*/


@*Add the code in CSHTML page to configure and initialize the control*@



  @* Enable the alignment format for button control as follows.*@

<div class="control">

    <ej-button id="button_rtl" text="button" size="Large" content-type="TextAndImage" show-rounded-corner="true" prefix-icon="e-icon e-login" enable-rtl="true" />

</div>

{% endhighlight  %}

In above mentioned code example PrefixIcon property is used and the icon that is to be on left side, (before text) is rendered on right side as EnableRTL property is used with PrefixIcon.  Consequently, the alignment is changed in right to left order.

{% highlight html %}

/*Razor code to render Button*/

   @{ Html.EJ().Button("button_rtl").Text("button").Size(ButtonSize.Large).ContentType(ContentType.TextAndImage).ShowRoundedCorner(true).PrefixIcon("e-icon e-login").EnableRTL(true).Render(); }

{% endhighlight %}

N> To render the Button Control you can use either Razor or Tag helper code as given in the above code snippet.

Execute the above code to render the following output.

![](RTL-Support_images/RTL-Support_img1.png)

Button in Right to left format
{:.caption}
