---
layout: post
title: Miscellaneous | GroupButton | ASP.NET Core | Syncfusion
description: miscellaneous
platform: aspnet-core
control: GroupButton
documentation: ug
---

# Miscellaneous

## Text

You can display your own text for Button. By using the text property, you can easily set text content for button. This text property overwrites the text that is provided on input button element.

In the view page, add the following button elements to configure Button with text



{% highlight html %}

/*ej-Tag Helper code to render GroupButton*/

<%--Set the text for button control as follows--%>

 <ej-group-button id="GroupButton">
    <e-group-button-items>
        <e-group-button-item text="Save"></e-group-button-item>
        <e-group-button-item text="Open"></e-group-button-item>
        <e-group-button-item text="Delete"></e-group-button-item>
    </e-group-button-items>
</ej-group-button>


{% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render GroupButton*/

    @{Html.EJ().GroupButton("GroupButton").Items(item =>
    {
        item.Add().Text("Save");
        item.Add().Text("Open");
        item.Add().Text("Delete");
    }).Render(); }


{% endhighlight %}

N> To render the GroupButton Control you can use either Razor or Tag helper code as given in the above code snippet.


![](Miscellaneous_images/text.png)


## Show Rounded Corner

Customizes the corners of Groupbutton control to be rendered with Rounded corners.

In the view page, add the following button elements to get rounded Button

{% highlight html %}

/*ej-Tag Helper code to render GroupButton*/

<%--Enable the rounded corner for button control as follows--%>

    <ej-group-button id="GroupButton" show-rounded-corner="true"  width="500px">
        <e-group-button-items>
            <e-group-button-item text="Save"></e-group-button-item>
            <e-group-button-item text="Open"></e-group-button-item>
            <e-group-button-item text="Delete"></e-group-button-item>
        </e-group-button-items>
    </ej-group-button>


{% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render GroupButton*/

    @{Html.EJ().GroupButton("GroupButton").ShowRoundedCorner(true).Width("500px").Items(item =>
    {
        item.Add().Text("Save");
        item.Add().Text("Open");
        item.Add().Text("Delete");
    }).Render();
    }

{% endhighlight %}

![](Miscellaneous_images/roundedcorner.png)


