---
layout: post
title: Getting Started with ASP.NET Core GroupButton control | Syncfusion
description: Learn here about getting started with Syncfusion Essential Studio ASP.NET Core GroupButton control, its elements, and more.
platform: aspnet-core
control: GroupButton
documentation: ug
---

# Getting Started with ASP.NET Core GroupButton

## GroupButton initialization

This section explains you briefly on how to create a GroupButton in your application with ASP.NET Core. You can easily create the Button control by using Tag helper as follows.

1. You can create a .NetCore Project with the help of the given [ASP.NET Core-Getting Started](https://help.syncfusion.com/aspnet-core/gettingstarted/getting-started-1-1-0) documentation.
2. Add the following code example to the corresponding view page to render GroupButton.


~~~ html

/*ej-Tag Helper code to render GroupButton*/

<ej-group-button id="GroupButton" width="100%" group-button-mode="@GroupButtonMode.RadioButton" show-rounded-corner="true">
    <e-group-button-items>
        <e-group-button-item text="Day"></e-group-button-item>
        <e-group-button-item text="Week"></e-group-button-item>
        <e-group-button-item text="Month"></e-group-button-item>
    </e-group-button-items>
</ej-group-button>

~~~

{% highlight CSHTML%}

/*Razor code to render GroupButton*/

    @{Html.EJ().GroupButton("GroupButton").GroupButtonMode(GroupButtonMode.RadioButton).ShowRoundedCorner(true).Items(item =>
    {
        item.Add().Text("Day");
        item.Add().Text("Week");
        item.Add().Text("Month");
    }).Render();
    }

{% endhighlight %}

N> To render the GroupButton Control you can use either Razor or Tag helper code as given in the above code snippet.


Also we can use the dataSource, to create the GroupButton which is explained under the dataSource section in this documentation.

