---
layout: post
title: Customization | Rating | ASP.NET Core | Syncfusion
description: Customization in Rating widget for Syncfusion Essential Dotnet Core
platform: aspnet-core
control: Rating
documentation: ug 
---

# Rating Customization

## Setting Value

The Value property sets the display value of the Rating. For example, when the Value property is set to 4, the Rating control renders 4 ratings. By default, Value property’s value is one.

The following code example is used to render the Rating control with the customized value.

Add the following code in your view page to render the Rating with the customized value.

{% highlight CSHTML %}

// Add the following code example to the corresponding CSHTML page to render Rating with customized value.

<div id="container" style="border: 1px solid black; width: 300px; padding: 2px">

    <table>

        <tr>
            <td valign="top">Rating:
            
            </td>
            <td>

                <ej-rating id="Rating" value="4"/>
                
            </td>

            </tr>

    </table>

</div>

{% endhighlight %}

The following screenshot illustrates the Rating with custom defined value.

![](Rating-Customization_images/Rating-Customization_img1.png)' 

## Min Value

Rating control provides support for setting the MinimumValue. This is achieved by adding the MinValue property. When the MinValue property is set, the Rating value starts with MinValue+1.

The following code example is used to render the Rating control with minimum rating value specified.

Add the following code in your view page to render the Rating with Minimum value.

{% highlight CSHTML %}

// Add the following code example to the corresponding CSHTML page to render Rating with customized minimum value.

<div id="container" style="width: 300px; padding: 2px">

    <table>

        <tr>

            <td valign="top">Rating:

            </td>

            <td>
 
                <ej-rating id="Rating" min-value="3"/>

            </td>

        </tr>

    </table>

</div>

{% endhighlight %}

The following screenshot Rating value starts with 4 since MinValue value is set as 3.

![](Rating-Customization_images/Rating-Customization_img2.png)

Rating with minimum value as 4
{:.caption}

## Max Value

Rating control provides support for setting Maximum value. This is achieved by adding the MaxValue property. By default, MaxValue is five.

The following code example is used to render the Rating control with maximum rating value specified

Add the following code in your view page to render the Rating with maximum value.

{% highlight CSHTML %}

// Add the following code example to the corresponding CSHTML page to render Rating with customized maximum value.

<div id="container" style="border: 1px solid black; width: 300px; padding: 2px">

    <table>

        <tr>

            <td valign="top">Rating:

            </td>

            <td>
 
                <ej-rating id="Rating" max-value="10"/>

            </td>

        </tr>

    </table>

</div>

{% endhighlight %}

The following screenshot illustrates the Rating with maximum value.

![](Rating-Customization_images/Rating-Customization_img3.png)


## Set Precision

You can set Precision in Rating value between two whole numbers such as 2.5 or 3.7 and it is done by using the property Precision by changing the value to Precision.Half or Precision.Exact. By default, value of Precision is Full.

The following code example is used to render the Rating control with Precision.

Add the following code in your view page to render the Rating with Precision.

{% highlight CSHTML %}

// Add the following code example to the corresponding CSHTML page to render Rating with Precision.

<div id="container" style="border: 1px solid black; width: 300px; padding: 2px">
        <table>
            <tr>
                <td valign="top">
                    Full Precision :
                </td>
                <td>
                    <ej-rating id="fullRating" value="4"/>
                   
                </td>
            </tr>
            <tr>
                <td valign="top">
                    Half Precision :
                </td>
                <td>
                <ej-rating id="halfRating" value="3" precision="@Precision.Half" />
                </td>
            </tr>
            <tr>
                <td valign="top">
                    Exact Precision :
                </td>
                <td>
                    
                    <ej-rating id="exactRating" value="4" precision="@Precision.Exact"/>
                </td>
            </tr>
        </table>
    </div>

{% endhighlight %}

The following screenshot illustrates the Rating with Precision.

![](Rating-Customization_images/Rating-Customization_img4.png)

## Increment Step

Rating control supports customized increment value for Rating. This is achieved by adding the IncrementStep property.

The following code example is used to render the Rating control with customized increment.

Add the following code in your view page to render the Rating with customized increment.

{% highlight CSHTML %}

// Add the following code example to the corresponding CSHTML page to render Rating with customized increment.

<div id="container" style="border: 1px solid black; width: 300px; padding: 2px">

	<table>

		<tr>

			<td valign="top">Rating:

			</td>

			<td>
 
                <ej-rating id="Rating" increment-step="2" max-value="10"/>

			</td>

		</tr>      

	</table>

</div>

{% endhighlight %}

The following screenshot illustrates the Rating with customized increment.

![](Rating-Customization_images/Rating-Customization_img5.png)

![](Rating-Customization_images/Rating-Customization_img6.png)

## Resetting values

Rating control provides support for value reset at runtime. This is achieved by enabling the AllowReset property to true. By default, the property value is set to true.

The following code example is used to render the Rating control with AllowReset.

Add the following code in your view page to render the Rating with AllowReset.

{% highlight CSHTML %}

// Add the following code example to the corresponding CSHTML page to render Rating with allowReset.

<div id="container" style="border: 1px solid black; width: 300px; padding: 2px">

    <table>

        <tr>

            <td valign="top">Rating:

            </td>

            <td>
 
                <ej-rating id="ResetRating" allow-reset="true" />

            </td>

        </tr>  

        <tr>

            <td valign="top">Rating:

            </td>

            <td>

                <ej-rating id="ResetRating" allow-reset="false" />

            </td>

        </tr>    

    </table>

</div> 

{% endhighlight %}

The following illustrates the Rating with allowReset.

![](Rating-Customization_images/Rating-Customization_img7.png)

## Read only

Rating control provides support for changeable or unchangeable values for Rating control. This is achieved by the ReadOnly property. When this property is set to true, the Rating value becomes unchangeable. By default, this property value is set to false.

The following code example is used to render the Rating control with ReadOnly.

Add the following code in your view page to render Rating with readOnly.

{% highlight CSHTML %}

// Add the following code example to the corresponding CSHTML page to render Rating with readOnly.

<div id="container" style="width: 300px; padding: 2px">

    <table>

        <tr>

            <td valign="top">Rating:

            </td>

            <td>
 
                <ej-rating id="Rating" read-only="true" value="2" max-value="10" />
                

            </td>

        </tr>  


    </table>

</div>

{% endhighlight %}

The following screenshot illustrates the Rating with ReadOnly.

![](Rating-Customization_images/Rating-Customization_img8.png)

## Enable or Disable

Rating control provides support to Enable or Disable the control. This is achieved by the Enabled property. By default the property value is True.

The following code example is used to render the Rating control with Enable or Disable support.

Add the following code in your view page to render the Rating with enable or disable support.

{% highlight CSHTML %}

// Add the following code example to the corresponding CSHTML page to render Rating with Enable/Disable support.

<div id="container" style="border: 1px solid black; width: 300px; padding: 2px">

    <table>

        <tr>

            <td valign="top">Rating:

            </td>

            <td>
 
                 <ej-rating id="Rating" enabled="false" />

            </td>

        </tr>

    </table>

</div>
{% endhighlight %}

The following screenshot illustrates the Rating in a disabled form.

![](Rating-Customization_images/Rating-Customization_img9.png)