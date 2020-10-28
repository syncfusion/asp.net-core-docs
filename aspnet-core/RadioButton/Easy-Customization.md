---
layout: post
title: Easy Customization | RadioButton | ASP.NET Core | Syncfusion
description: easy customization
platform: aspnet-core
control: RadioButton
documentation: ug
---

# Easy Customization

## Checked status

You have options to set the state of the radio button as either checked or unchecked. When you select any option from the group of radio buttons, a dot mark appears inside the circle. This is called the checked state. Previously selected radio buttons in this group are unselected that is they go to the unchecked state. The checked property is used to set the state of the radio button.

The following steps explain the details about rendering the Radio Button with the checked option

In the CSHTML page, add the following input elements to configure Radio Button widget.



{% highlight CSHTML %}

/*ej-Tag Helper code to render RadioButton*/

// Add the code in CSHTML page to configure Radio Button

@* Here checked and unchecked type of radio buttons are rendered in same group

set checked state of radio button as follows*@

    <ej-radio-button id="radiobutton" name="Gender" size="@RadioButtonSize.Small" checked="true" />

    <label for="Radio_checked" class="clslab">Male</label>

    <br />
    <ej-radio-button id="radiobutton1" name="Gender" size="@RadioButtonSize.Small" checked="false" />

    <label for="Radio_unchecked" class="clslab">Female</label>


{% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render RadioButton*/

    @{Html.EJ().RadioButton("Radio_checked").Name("Gender").Size(RadioButtonSize.Small).Checked(true).Render(); }

    <label for="Radio_checked" class="clslab">Male</label>

    <br />

    @{Html.EJ().RadioButton("Radio_unchecked").Name("Gender").Size(RadioButtonSize.Small).Checked(false).Render();}

    <label for="Radio_unchecked" class="clslab">Female</label>


{% endhighlight %}

N> To render the RadioButton Control you can use either Razor or Tag helper code as given in the above code snippet.

The following image is displayed as the output for the above steps.

![checked status](Easy-Customization_images/Easy-Customization_img1.png)



## Text

Specifies the text content for the radio button. In previous programs, separate labels were created for each radio button. But now you have the option to set the text for radio button using the text property. So here you do not have to add a label tag for each radio button in the HTML code.

The following steps explain the details about rendering the Radio Button with Text and without using the label tag options.

In the CSHTML page, add the following input elements to configure the Radio Button widget.


{% highlight CSHTML %}

/*ej-Tag Helper code to render RadioButton*/

// Add the code in CSHTML page to configure Radio Button

@*radio button with text property*@

    <ej-radio-button id="radiobutton" name="Gender" size="@RadioButtonSize.Small" checked="true" text="Male" />

    <br />
    <ej-radio-button id="radiobutton1" name="Gender" size="@RadioButtonSize.Small" checked="false" text="Female" />

{% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render RadioButton*/

    @{Html.EJ().RadioButton("radiobutton1").Name("Gender").Size(RadioButtonSize.Small).Checked(true).Text("Male").Render(); }

    <br />

    @{Html.EJ().RadioButton("radiobutton1").Name("Gender").Size(RadioButtonSize.Small).Checked(false).Text("Female").Render();}


{% endhighlight %}


The following image is displayed as the output for the above steps.

![text](Easy-Customization_images/Easy-Customization_img2.png)



## Size

You can render the Radio Button in different sizes. There are some predefined size options available for rendering a Radio Button in an easy way. Each size option has different height and width. It mainly avoids the complexity in rendering Radio Button with complex CSS class. 

_Size_

<table>
<tr>
<th>
Property</th><th>
Description</th></tr>
<tr>
<td>
Small</td><td>
Creates radio button with Built-in small size height, width specified.</td></tr>
<tr>
<td>
Medium</td><td>
Creates radio button with Built-in medium size height, width specified.</td></tr>
</table>


The following steps explain the details about rendering Radio Button with different size options.

In the CSHTML page, add the following input elements to configure Radio Button widget.



{% highlight CSHTML %}

/*ej-Tag Helper code to render RadioButton*/

// Add the code in CSHTML page to configure Radio Button

@* small and medium size of radio buttons in same group

By default, here no one radio button is checked*@

    Small size radio buttons<br />
    <ej-radio-button id="radiobutton" name="Gender" size="@RadioButtonSize.Small" checked="true" text="Male" />

    <br />
    <ej-radio-button id="radiobutton1" name="Gender" size="@RadioButtonSize.Small" checked="false" text="Female" />

    <br />
    Medium size radio buttons<br />

    <ej-radio-button id="radiobutton2" name="Gender" size="@RadioButtonSize.Medium" checked="true" text="Male" />

    <br />
    <ej-radio-button id="radiobutton3" name="Gender" size="@RadioButtonSize.Medium" checked="false" text="Female" />


{% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render RadioButton*/

Small size radio buttons<br />

    @{Html.EJ().RadioButton("radiobutton").Name("Gender").Size(RadioButtonSize.Small).Checked(true).Render(); }

    <label for="radiobutton">Male</label>

    <br />

    @{Html.EJ().RadioButton("radiobutton1").Name("Gender").Size(RadioButtonSize.Small).Checked(false).Render(); }

    <label for="radiobutton1">Female</label>

    <br/>

Medium size radio buttons

    <br />

    @{Html.EJ().RadioButton("radiobutton2").Name("Gender1").Size(RadioButtonSize.Medium).Checked(true).Render(); }

    <label for="radiobutton2">Male</label>

    <br/>

    @{Html.EJ().RadioButton("radiobutton3").Name("Gender1").Size(RadioButtonSize.Medium).Checked(false).Render();}

    <label for="radiobutton3">Female</label>


{% endhighlight %}

The following image is displayed as the output for the above steps.

![size](Easy-Customization_images/Easy-Customization_img3.png)



## RTL Support 

In some cases you need to use right-to-left alignment. You can give RTL support by using enable-rtl property.  RTL mode works when you use the Text property in Radio Button. The Radio Buttons and text are aligned in the right-to-left format. For example, when text is right-aligned and Radio Button is left-aligned, after you apply right-to-left alignment, these positions are interchanged. 

The following steps explain the details about rendering the Radio Button with right-to-left alignment support. Here the text property is necessary.

In the CSHTML page, add the following button elements to configure Radio Button widget.

{% highlight CSHTML %}

/*ej-Tag Helper code to render RadioButton*/

// Add the code in CSHTML page to configure Radio Button

@*set radio button with right to left format*@

    <ej-radio-button id="radiobutton" name="Gender" size="@RadioButtonSize.Small" checked="true" text="Male" enable-rtl="true" />

    <br />
    <ej-radio-button id="radiobutton1" name="Gender" size="@RadioButtonSize.Small" checked="false" text="Female" enable-rtl="true" />

{% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render RadioButton*/

    @{Html.EJ().RadioButton("radiobutton").Name("Gender").Size(RadioButtonSize.Small).Checked(true).Text("Male").EnableRTL(true).Render(); }

    @{Html.EJ().RadioButton("radiobutton1").Name("Gender").Size(RadioButtonSize.Small).Checked(false).Text("Female").EnableRTL(true).Render();}



{% endhighlight %}


The following image is displayed as the output for the above steps.

![rtl](Easy-Customization_images/Easy-Customization_img4.png)

## Styles Customization

RadioButton allows you to customize its appearance by using user-defined CSS and custom skin options such as colors and backgrounds. To apply custom themes, use  **CssClass** property. CssClass property sets the root class for RadioButton theme.

By using this CssClass, you can override the existing styles under the theme style sheet. The theme style sheet applies theme-specific styles like colors and backgrounds. From the root class, you can customize the RadioButton control theme.

In the following example, the border color and border width of the active RadioButton is customized through the custom classes to create the success, and danger indication with RadioButton.

{% highlight html %}

<span><b>Agree terms & conditions:</b></span>
<span style="margin-left: 15px">
    <ej-radio-button id="Radio_checked" text="Yes" name="radio1" css-class="success" size="Medium">
    <ej-radio-button id="Radio_unchecked" text="No" name="radio1" css-class="warning" size="Medium">
</span>
<br>
<br>
<span><b>Confirm:</b></span>
<span style="margin-left: 15px">
    <ej-radio-button id="RadioButton3" text="Yes" name="radio2" css-class="success" size="Medium">
    <ej-radio-button id="RadioButton4" text="No" name="radio2" css-class="warning" size="Medium">
</span>

{% endhighlight %}

{% highlight css %}

<style>
        .success .e-spanicon.e-rad-active,
        .success .e-spanicon.e-rad-active:hover {
            border-color: #17ad37;
            border-width: 2px;
        }

        .warning .e-spanicon.e-rad-active,
        .warning .e-spanicon.e-rad-active:hover {
            border-color: #ff6e40;
            border-width: 2px;
        }
    </style>

{% endhighlight %}

![customization](Easy-Customization_images/Easy-Customization_img5.png)