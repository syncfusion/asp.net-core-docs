---
layout: post
title: Miscellaneous | SplitButton | ASP.NET Core | Syncfusion
description: miscellaneous
platform: aspnet-core
control: SplitButton
documentation: ug
---

# Miscellaneous

## Text

It is necessary to display the user defined text for Split Button. Using text property, you can easily set text content for Split Button.

The following steps explains you the details about rendering the Split Button with specified text.

1. In the VIEW page, add the following button elements to configure Split Button widget

{% highlight CSHTML %}

/*ej-Tag Helper code to render SplitButton*/

//Add the code in the CSHTML page to configure and initialize the control

    @*Set the text for split button control as follows. *@

        <div class="spltspan">
            <ej-split-button id="dropdownbtn" text="signin" size="@ButtonSize.Small" show-rounded-corner="true" target-id="menu1"></ej-split-button>

            <ul id="menu1">

                <li><span>User</span></li>

                <li><span>Guest</span></li>

                <li><span>Admin</span></li>

            </ul>

        </div>

{% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render SplitButton*/

<div class="spltspan">

    @{Html.EJ().SplitButton("dropdownbtn").Text("signin").Size(ButtonSize.Small).TargetID("menu1").ShowRoundedCorner(true).Render();}

    <ul id="menu1">

        <li><span>User</span></li>

        <li><span>Guest</span></li>

        <li><span>Admin</span></li>

    </ul>

</div>


{% endhighlight %}

N> To render the SplitButton Control you can use either Razor or Tag helper code as given in the above code snippet.

Execute the above code to render the following output.

![](Miscellaneous_images/Miscellaneous_img1.png)



## ShowRoundedCorner

Specifies the corner of Split Button in rounded shape. By default, the edges of Split Button is not rounded. To set rounded corner, you can enable show-rounded-corner property.

The following steps explains you the details about rendering the Split Button with rounded corner.

1. In the VIEW page, add the following button elements to configure Split Button widget.

{% highlight CSHTML %}

/*ej-Tag Helper code to render SplitButton*/

//Add the code in the CSHTML page to configure and initialize the control



@*Enable the rounded corner for split button control as follows.*@

        <div class="spltspan">
    
            <ej-split-button id="dropdownbtn" text="login" size="@ButtonSize.Small" show-rounded-corner="true" target-id="menu1"></ej-split-button>

            <ul id="menu1">

                <li><span>User</span></li>

                <li><span>Guest</span></li>

                <li><span>Admin</span></li>

            </ul>

        </div>

{% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render SplitButton*/

<div class="spltspan">

    @{Html.EJ().SplitButton("dropdownbtn").Text("login").Size(ButtonSize.Small).ShowRoundedCorner(true).TargetID("menu1").Render();}

    <ul id="menu1">

        <li><span>User</span></li>

        <li><span>Guest</span></li>

        <li><span>Admin</span></li>

    </ul>

</div>

{% endhighlight %}

Execute the above code to render the following output.

![](Miscellaneous_images/Miscellaneous_img2.png)





