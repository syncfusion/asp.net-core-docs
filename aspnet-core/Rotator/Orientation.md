---
layout: post
title: Orientation | Rotator | ASP.NET Core | Syncfusion
description: orientation
platform: aspnet-core
control: Rotator
documentation: ug
---

# Orientation

The Rotator control supports both vertical and horizontal orientations allowing it to fit into any scenario. The Orientation property defines the Orientation where the control is rendered. The value set to this property is enum or string type. It accepts the following values.

* ej.Orientation.Horizontal or “Horizontal”
* ej.Orientation.Vertical  or “Vertical”

The following steps explain you how to set Orientation for the Rotator.

## Horizontal

This property sets the Rotator in horizontal orientation. You can refer the following steps to set horizontal orientation for Rotator control. In Rotator control, the Default value of orientation is Horizontal. 

1. In View, create ul-li list of Rotator items and invoke the Rotator helper.
2. Add the following script in your CSHTML page.

{% highlight CSHTML %}

// Add this code in your CSHTML page and refer local data section for binding Rotator items.



<ej-rotator id="rot" datasource="ViewBag.datasource" slide-height="350px"  slide-width="600px" is-responsive="true" orientation="Horizontal">
    <e-rotator-fields text="text" url="url" />
</ej-rotator>


{% endhighlight %}

## Vertical

This property sets the Rotator in Vertical orientation. You can refer the following steps to set vertical orientation for Rotator control.

1. Create ul-li list of Rotator items and invoke the Rotator helper.
2. Add the following script in your CSHTML page.


{% highlight CSHTML %}

// Add this code in your CSHTML page and refer local data section for binding Rotator items.

@Html.EJ().Rotator("slidercontent").Datasource((IEnumerable<Localdata>)ViewBag.datasource)
.RotatorFields(t => t.Text("Text").Url("Url"))
.SlideWidth("600px").SlideHeight("350px")
.Orientation(Syncfusion.JavaScript.Orientation.Vertical)

{% endhighlight %}