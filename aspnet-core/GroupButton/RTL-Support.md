---
layout: post
title: RTL Support | Button | ASP.NET Core | Syncfusion
description: rtl support
platform: aspnet-core
control: GroupButton
documentation: ug
---

## RTL Support

In some cases, where you want to display the content in Right to Left direction, you can use RTL support by using the enable-rtl property. In RTL mode, when you have more than one content (image/text, image/image) in button, then these content are aligned in right to left format. With this property enabled, the Groupbutton items are rendered in reverse order.

In the view page, add the following Groupbutton to configure the Items with Right to left alignment

{% highlight html %}

/*ej-Tag Helper code to render GroupButton*/

<%--Enable the alignment format for GroupButton control as follows--%>

    <ej-group-button id="GroupButton" enable-rtl="true" width="500px">
        <e-group-button-items>
            <e-group-button-item text="Save"></e-group-button-item>
            <e-group-button-item text="Open"></e-group-button-item>
            <e-group-button-item text="Delete"></e-group-button-item>
        </e-group-button-items>
    </ej-group-button>

{% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render GroupButton*/

    @{Html.EJ().GroupButton("GroupButton").Width("500px").EnableRTL(true).Items(item =>
    {
        item.Add().Text("Save");
        item.Add().Text("Open");
        item.Add().Text("Delete");
    }).Render();
    }


{% endhighlight %}

N> To render the GroupButton Control you can use either Razor or Tag helper code as given in the above code snippet.


Here the items are rendered in the reverse order.

![](RTL-Support_images/rtl.png)


