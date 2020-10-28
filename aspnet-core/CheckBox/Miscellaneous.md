---
layout: post
title: Miscellaneous | Checkbox | ASP.NET MVC | Syncfusion
description: miscellaneous
platform: ejmvc
control: Checkbox
documentation: ug
---

# Miscellaneous

## Checkbox Id

Checkbox id is not displayed in user interface. Here, Id mentions the id attribute of the root element of Checkbox control. When you assign a value for Id property, then this older id is replaced by new id. This id value should be unique. 

Set id for Checkbox control as follows.



{% highlight CSHTML %}

/*ej-Tag Helper code to render CheckBox*/

@*set id for checkbox *@

<ej-check-box id="checkbox" text="Checkbox" />

{% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render CheckBox*/

    @{ Html.EJ().CheckBox("checkbox").Text("Checkbox").Render(); }

{% endhighlight %}

N> To render the CheckBox Control you can use either Razor or Tag helper code as given in the above code snippet.

## Checkbox Id Prefix

Id prefix value is the one that is appended to id value. It is used to mention the prefix for the wrapper’s id attribute. When you assign a value for id-prefix property, the older prefix id is replaced by new prefix id. 

Set prefix id for Checkbox control as follows.



{% highlight CSHTML %}

/*ej-Tag Helper code to render CheckBox*/

@*set prefix id for checkbox *@

<ej-check-box id="checkbox"  text="Checkbox" id-prefix="aspnetcore"/>

{% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render CheckBox*/

    @{ Html.EJ().CheckBox("checkbox").Text("Checkbox").IdPrefix("aspnetcore").Render(); }

{% endhighlight %}


## Checkbox Name

The name attribute is used to identify from data after it is submitted to the server. Checkbox also contains name attribute. This name should be a unique one. It is used to receive the Checkbox value. Without using name, you can’t get the particular checkbox values at the time of submitting form.

## Checkbox Value

For Checkbox, the contents of the value property do not appear in the user interface. The value property contains only a meaning when submitting a form. When a Checkbox is in checked state and when the form is submitted, the name of the Checkbox is sent along with the value of the value property (When the checkbox is not checked, no information is sent).

You can set name and value for Checkbox control as follows.



{% highlight CSHTML %}

/*ej-Tag Helper code to render CheckBox*/

@*set name and value for checkbox *@

   <ej-check-box id="checkbox" name="conformation" value="Received"/>

{% endhighlight %}



{% highlight CSHTML%}

/*Razor code to render CheckBox*/

    @{ Html.EJ().CheckBox("checkbox5").Name("conformation").Value("Received").Render(); }

{% endhighlight %}








