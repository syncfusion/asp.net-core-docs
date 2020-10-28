---
layout: post
title: Orientation | Rating | ASP.NET Core | Syncfusion
description: orientation
platform: aspnet-core
control: Rating
documentation: ug
---

# Orientation

Rating provides support for Vertical orientation. By default Rating renders with Horizontal orientation. You can change the orientation by the Orientation property.

The following code example is used to render the Rating control with Vertical orientation.

Add the following code in your view page to render the Rating with customizedOrientation.



{% highlight CSHTML %}

// Add the following code example to the corresponding CSHTML page to render Rating with customized orientation.

<div id="container" style="border: 1px solid black; width: 300px; padding: 2px">

    <table>

        <tr>

            <td valign="top">Rating:

            </td>

            <td>
 
                <ej-rating id="orientRating" orientation="@Orientation.Vertical"/>

            </td>

        </tr>             

    </table>

</div>
{% endhighlight %}




The following screenshot illustrates the Rating with Vertical orientation.

![](Orientation_images/Orientation_img1.png)



