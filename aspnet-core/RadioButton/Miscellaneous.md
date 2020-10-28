---
layout: post
title: Miscellaneous | RadioButton | ASP.NET Core | Syncfusion
description: miscellaneous
platform: aspnet-core
control: RadioButton
documentation: ug
---

# Miscellaneous

## Radio Button ID

Radio Button id is not shown in the user interface. Here Id denotes the Id attribute of the root element of Radio Button control. This Id value is unique. You can give Id through element and through the Id property. When you use two ids for a single radio button at initialization, the element Id is considered.

Set Id for Radio Button control as follows.



{% highlight CSHTML %}

/*ej-Tag Helper code to render RadioButton*/

@*set new id value as follows*@

    <ej-radio-button id="radiobutton"  name="Gender" size="@RadioButtonSize.Small" checked="true"/>

    <br />
    <ej-radio-button id="radiobutton1" name="Gender" size="@RadioButtonSize.Small" checked="false"  />")

{% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render RadioButton*/

    @{Html.EJ().RadioButton("radiobutton").Id("male_type").Name("Gender").Size(RadioButtonSize.Small).Checked(true).Render(); }

    <br />

    @{Html.EJ().RadioButton("radiobutton1").Id("female_type").Size(RadioButtonSize.Small).Checked(false).Name("Gender").Render();}


{% endhighlight %}

N> To render the RadioButton Control you can use either Razor or Tag helper code as given in the above code snippet.

## Radio Button Prefix id

Id prefix value is appended to the element id value. It is used to mention the prefix for the wrapper’s id attribute. When you assign a value for id-prefix property, the older prefix id gets replaced by the new prefix id. 

Setting a new prefix id for Radio Button control is as follows.



{% highlight CSHTML %}

/*ej-Tag Helper code to render RadioButton*/

@*set new idPrefix  value as follows*@

    <ej-radio-button id="radiobutton"  name="Gender" size="@RadioButtonSize.Small" checked="true" id-prefix="sync_" text="Male" enable-rtl="true" />

    <br />
    <ej-radio-button id="radiobutton1" name="Gender" size="@RadioButtonSize.Small" checked="false" id-prefix="sync_" text="Female" enable-rtl="true" />


{% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render RadioButton*/

    @{Html.EJ().RadioButton("radiobutton").IdPrefix("sync_").Name("Gender").Size(RadioButtonSize.Small).Checked(true).Text("Male").EnableRTL(true).Render(); }

    <br />

    @{Html.EJ().RadioButton("radiobutton1").IdPrefix("sync_").Name("Gender").Size(RadioButtonSize.Small).Checked(false).Text("Female").EnableRTL(true).Render(); }


{% endhighlight %}


## Radio Button Name

The Name setting tells you where a Radio Button belongs. When you select one button, all other buttons in the same group are unselected. You can have only one group of Radio Buttons on each page.

The Name attribute is also used to identify form data after it has been submitted to the server, or for reference of form data using JavaScript on the client’s side. Only form elements with a Name attribute have their values passed, when submitting a form.

## Radio Button Value

The Value setting defines what can be submitted when checked.

For Radio Buttons, the contents of the value property do not appear in the user interface. The value property only has meaning when submitting a form. If a radio button is in the checked state when the form is submitted, the name of the Radio Button is sent along with the value of the value property, if the radio button is not checked, no information is sent.

To identify, on the server side, which one was checked, give different values for radio buttons in the same group, 

Set name and value for each radio button control as follows.


{% highlight CSHTML %}

/*ej-Tag Helper code to render RadioButton*/

@*set name and value for each radio button as follows*@
    <ej-radio-button id="radiobutton"  name="Gender" size="@RadioButtonSize.Small" checked="true"  value="Male" />

    <br />
    <ej-radio-button id="radiobutton1" name="Gender" size="@RadioButtonSize.Small" checked="false" value="Female" />

{% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render RadioButton*/

    @{Html.EJ().RadioButton("radiobutton").Name("Gender").Value("male").Size(RadioButtonSize.Small).Checked(true).Render();}

    <br />

    @{Html.EJ().RadioButton("radiobutton1").Name("Gender").Value("female").Size(RadioButtonSize.Small).Checked(false).Render();}


{% endhighlight %}

