---
layout: post
title: Arrow Position | SplitButton | ASP.NET Core | Syncfusion
description: arrow position
platform: aspnet-core
control: SplitButton
documentation: ug
---

# Arrow Position

To provide a good look and feel for Split Button, position of arrow in Split Button is important. Using arrow-position property, you can easily customize the position of arrow inside Split Button without using any complex CSS. ArrowPosition property is applicable for both Split Button and Dropdown Button. This property represent the position of arrow with menu content.

_List of arrow position_

<table>
<tr>
<td>
Left</td><td>
Support for arrow in left.</td></tr>
<tr>
<td>
Right</td><td>
Support for arrow in right. </td></tr>
<tr>
<td>
Top</td><td>
Support for arrow in top. </td></tr>
<tr>
<td>
Bottom</td><td>
Support for arrow in bottom.</td></tr>
</table>


The following steps explain you the details on rendering the Split Button with above mentioned arrow position options.

1. In the View page, add the following button elements to configure Split Button widget.

{% highlight CSHTML %}

/*ej-Tag Helper code to render SplitButton*/

	<div class="control">

    @*Add the code in the CSHTML page to configure and initialize the control*@

    @*Set the content for split button control as follows. *@

    <table>

        <tr>

            <td class="btnsht">

                <div class="spltspan">

                    <ej-split-button id="spltbutton_normal_imageLeft" text="login" size="@ButtonSize.Medium" show-rounded-corner="true" content-type="@ContentType.TextAndImage" prefix-icon="e-icon e-handup" target-id="Ul11" image-position="@ImagePosition.ImageLeft" arrow-position="@ArrowPosition.Left"></ej-split-button>

                    <ul id="Ul11">

                        <li><span>User</span></li>

                        <li><span>Guest</span></li>

                        <li><span>Admin</span></li>

                    </ul>

                </div>

            </td>

            <td>
                <ej-split-button id="spltbutton_small_imageLeft" text="login" size="@ButtonSize.Small" show-rounded-corner="true" target-id="Ul21" content-type="@ContentType.TextAndImage" prefix-icon="e-icon e-handup" image-position="@ImagePosition.ImageLeft" arrow-position="@ArrowPosition.Top"></ej-split-button>
                <ul id="Ul21">

                    <li><span>User</span></li>

                    <li><span>Guest</span></li>

                    <li><span>Admin</span></li>

                </ul>

            </td>

            <td class="btnsht">
                <ej-split-button id="spltbutton_medium_imageLeft" text="login" size="@ButtonSize.Medium" show-rounded-corner="true" target-id="Ul31" content-type="@ContentType.TextAndImage" prefix-icon="e-icon e-handup" image-position="@ImagePosition.ImageLeft" arrow-position="@ArrowPosition.Bottom"></ej-split-button>

                <ul id="Ul31">

                    <li><span>User</span></li>

                    <li><span>Guest</span></li>

                    <li><span>Admin</span></li>

                </ul>

            </td>

            <td class="btnsht">

                <ej-split-button id="spltbutton_large_imageLeft" text="login" size="@ButtonSize.Large" content-type="@ContentType.TextAndImage" prefix-icon="e-icon e-handup" show-rounded-corner="true" target-id="Ul41" image-position="@ImagePosition.ImageRight" arrow-position="@ArrowPosition.Right"></ej-split-button>

                <ul id="Ul41">

                    <li><span>User</span></li>

                    <li><span>Guest</span></li>

                    <li><span>Admin</span></li>

                </ul>

            </td>
        </tr>

    </table>

</div>

{% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render SplitButton*/

<table>

    <tr>

        <td class="btnsht">

            <div class="spltspan">

                @{Html.EJ().SplitButton("spltbutton_normal_imageLeft").Text("login").ShowRoundedCorner(true).Size(ButtonSize.Medium).ContentType(ContentType.TextAndImage).TargetID("Ul11").PrefixIcon("e-icon e-handup").ArrowPosition(ArrowPosition.Left).ImagePosition(ImagePosition.ImageLeft).ShowRoundedCorner(true).Render(); }

                <ul id="Ul11">

                    <li><span>User</span></li>

                    <li><span>Guest</span></li>

                    <li><span>Admin</span></li>

                </ul>
            </div>

        </td>

        <td>
            @{Html.EJ().SplitButton("spltbutton_small_imageLeft").Text("login").ShowRoundedCorner(true).Size(ButtonSize.Small).ContentType(ContentType.TextAndImage).PrefixIcon("e-icon e-handup").TargetID("Ul21").ShowRoundedCorner(true).ImagePosition(ImagePosition.ImageLeft).ArrowPosition(ArrowPosition.Top).Render(); }

            <ul id="Ul21">

                <li><span>User</span></li>

                <li><span>Guest</span></li>

                <li><span>Admin</span></li>

            </ul>
            </td>
        <td>
            @{Html.EJ().SplitButton("spltbutton_medium_imageLeft").Text("login").ShowRoundedCorner(true).Size(ButtonSize.Medium).ContentType(ContentType.TextAndImage).TargetID("Ul31").PrefixIcon("e-icon e-handup").ShowRoundedCorner(true).ArrowPosition(ArrowPosition.Bottom).ImagePosition(ImagePosition.ImageLeft).Render();}

            <ul id="Ul31">

                <li><span>User</span></li>

                <li><span>Guest</span></li>

                <li><span>Admin</span></li>

            </ul>
        </td>
        <td>
            @{Html.EJ().SplitButton("spltbutton_large_imageLeft").Text("login").ShowRoundedCorner(true).Size(ButtonSize.Large).ContentType(ContentType.TextAndImage).PrefixIcon("e-icon e-handup").TargetID("Ul41").ImagePosition(ImagePosition.ImageRight).ArrowPosition(ArrowPosition.Right).Render();}

            <ul id="Ul41">

                <li><span>User</span></li>

                <li><span>Guest</span></li>

                <li><span>Admin</span></li>

            </ul>
        </td>
</tr>
</table>


{% endhighlight %}

N> To render the SplitButton Control you can use either Razor or Tag helper code as given in the above code snippet.
 

2. Execute the above code to render the following output.



![](Arrow-Position_images/Arrow-Position_img1.png)



