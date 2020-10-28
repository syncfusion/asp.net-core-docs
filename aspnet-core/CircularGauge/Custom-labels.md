---
layout: post
title: Custom labels | CircularGauge |  Syncfusion
description: custom labels
platform: aspnet-core
control: CircularGauge
documentation: ug
---

# Custom labels

Custom labels are the texts that you can use them in any location of the Gauge.

## Adding Custom Label Collection

Custom labels collection is directly added to the scale object. Refer the following code to add custom labels collection in a Gauge control.

{% highlight CSHTML %}

<ej-circular-gauge id="circulargauge" >
<e-circular-scale-collections>
<e-circular-scales show-labels="true" radius="130" >
<e-custom-label-collections>
<e-circular-custom-labels value="CustomLabel1" color="red" text-angle="10">
<e-custom-position x="180" y="100">
</e-custom-position>
<e-custom-font font-style="bold" font-family="Arial" size="20px">
</e-custom-font>
</e-circular-custom-labels>
</e-custom-label-collections>
</e-circular-scales>
</e-circular-scale-collections>
</ej-circular-gauge>

{% endhighlight %}

### Basic Customization

* You can customize custom labels using the properties such as textAngle, color and font. textAngle attribute is used to display the custom labels in the specified angles and color attribute is used to display the custom labels in specified color. 
* You can use Value attribute to set the text value in the custom labels. To display the custom labels, set showCustomLabels as ‘true’. To set the location of the custom label in Circular Gauge, location property is used. By using x and y axis you can adjust the position of the custom labels.
* Font option is also available on  custom labels. The basic three properties of fonts such as size, family and style can be achieved by size, fontStyle and fontFamily attributes. 


{% highlight CSHTML %}

<ej-circular-gauge id="circulargauge" >
<e-circular-scale-collections>
<e-circular-scales show-labels="true" radius="150" size="2" shadow-offset="10" show-ranges="true" 
show-scale-bar="true">
<e-custom-label-collections>
<e-circular-custom-labels value="CustomLabel1" color="red" text-angle="10">
<e-custom-position x="180" y="100">
</e-custom-position>
<e-custom-font font-style="bold" font-family="Arial" size="20px">
</e-custom-font>
</e-circular-custom-labels>
</e-custom-label-collections>
</e-circular-scales>
</e-circular-scale-collections>
</ej-circular-gauge>


{% endhighlight %}

Execute the above code to render the following output.



![](Custom-labels_images/Custom-labels_img1.png)

Circular Gauge with customized custom label
{:.caption}

## Multiple Custom Labels

You can set multiple custom labels in a single Circular Gauge by adding an array of custom label objects. Refer the following code example for multiple custom label functionality.



{% highlight CSHTML %}

<ej-circular-gauge id="circulargauge" >
<e-circular-scale-collections>
<e-circular-scales show-labels="true" radius="150" size="2" shadow-offset="10" show-ranges="true" 
show-scale-bar="true">
<e-custom-label-collections>
<e-circular-custom-labels value="CustomLabel1" color="red" text-angle="10">
<e-custom-position x="180" y="100">
</e-custom-position>
<e-custom-font font-style="bold" font-family="Arial" size="20px">
</e-custom-font>
</e-circular-custom-labels>
<e-circular-custom-labels value="CustomLabel2" color="green" text-angle="10">
<e-custom-position x="180" y="250">
</e-custom-position>
<e-custom-font font-style="bold" font-family="Arial" size="20px">
</e-custom-font>
</e-circular-custom-labels>
</e-custom-label-collections>
</e-circular-scales>
</e-circular-scale-collections>
</ej-circular-gauge>


{% endhighlight %}

Execute the above code to render the following output.

![](Custom-labels_images/Custom-labels_img2.png)

Circular Gauge with multiple custom labels
{:.caption}


## Outer Custom Label

* Outer Custom Label is used to show custom labels outside the gauge control. The Outer Custom Label can be positioned with API called outerCustomLabelPosition. The value for this API is enumerable type and its possible values are,
1. Right
2. Left
3. Top
4. Bottom
* When a custom label is to be displayed as an Outer Custom Label, set the API customLabelType as Outer. Refer to the following code example to get the Outer Custom Label.
{% tabs %}

{% highlight CSHTML %}

<ej-circular-gauge id="circulargauge" outer-custom-label-position="@OuterCustomLabelPosition.Right" >
<e-circular-tooltip show-label-tooltip="true" show-custom-label-tooltip="true"></e-circular-tooltip>
<e-circular-scale-collections>
<e-circular-scales show-labels="true" radius="130">
<e-custom-label-collections>
<e-circular-custom-labels value="Average Speed">
<e-custom-position x="360" y="30">
</e-custom-position>
<e-custom-font font-style="bold" font-family="Arial" size="20px">
</e-custom-font>
</e-circular-custom-labels>
</e-custom-label-collections>
<e-pointer-collections>
<e-pointers value="60" length="90" ></e-pointers>
</e-pointer-collections>
</e-circular-scales>
</e-circular-scale-collections>
</ej-circular-gauge>

{% endhighlight %}

{% highlight c# %}
public ActionResult Print()
{
	var DataSource = new ScheduleDataDataContext().DefaultSchedules.ToList();
	ViewBag.dataSource = DataSource;return View();
}


{% endhighlight %}
{% endtabs %}

Execute the above code to render the following output.

![](Custom-labels_images/Custom-labels_img3.png)

Circular gauge with outer custom label.
{:.caption}
