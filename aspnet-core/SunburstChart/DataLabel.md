---
layout: post
title: Data Label in EJ 1 ASP.NET Core SunburstChart | Syncfusion
description: You can learn about data label support in Syncfusion ASP.NET Core SunburstChart control and more details.
platform: aspnet-core
control: SunburstChart
documentation: ug
---

# Data Label in ASP.NET Core SunburstChart 

Sunburst data labels are used to display the data related to the segment. It helps to provide the information about the data points to the users.
You can enable or disable the data labels by setting the visible property of the **e-sunburstchart-data-label-settings** to true as shown in the below code

{% highlight cshtml %}

<ej-sunburstchart id="SunburstChart" >
 <e-sunburstchart-data-label-settings visible="true"></e-sunburstchart-data-label-settings>
</ej-sunburstchart>

{% endhighlight %}

![Visual representation of DataLabels using SunburstChart in ASP.NET Core](DataLabel_images/DataLabel_img1.png)

## Label Overflow mode

When you represent huge data with data labels, they may intersect each other. You can avoid this using the *label-overflow-mode* property.

The following properties are used to avoid the overlapping.
*	Trim – To trim the large data labels.
*	Hide – To hide the overlapped data labels.
The following code shows how to set Hide and Trim mode.

{% highlight cshtml %}

<ej-sunburstchart id="SunburstChart" >
<e-sunburstchart-data-label-settings visible="true" 
label-overflow-mode="@SunburstLabelOverflowMode.Hide"></e-sunburstchart-data-label-settings>
</ej-sunburstchart>


 {% endhighlight %}

![Label Overflow mode - Hide using SunburstChart in ASP.NET Core](DataLabel_images/DataLabel_img2.png) 

{% highlight cshtml %}

<ej-sunburstchart id="SunburstChart" >
<e-sunburstchart-data-label-settings visible="true" 
label-overflow-mode="@SunburstLabelOverflowMode.Trim"></e-sunburstchart-data-label-settings>
</ej-sunburstchart>

 {% endhighlight %}

![Label Overflow mode - Trim using SunburstChart in ASP.NET Core](DataLabel_images/DataLabel_img3.png)

## Label Rotation Mode
You can rotate the data label by using *label-rotation-mode* property. By default, the labelRotationMode is set as **angle**. 

The following code shows how to set labelRotationMode as normal and angle.

{% highlight cshtml %}

<ej-sunburstchart id="SunburstChart" >
 <e-sunburstchart-data-label-settings visible="true"
 label-rotation-mode="@SunburstLabelRotationMode.Normal">
</e-sunburstchart-data-label-settings>
</ej-sunburstchart>

 {% endhighlight %}

![Label Rotation Mode - Normal using SunburstChart in ASP.NET Core](DataLabel_images/DataLabel_img4.png)

{% highlight cshtml %}

<ej-sunburstchart id="SunburstChart" >
 <e-sunburstchart-data-label-settings visible="true"
 label-rotation-mode="@SunburstLabelRotationMode.Angle">
</e-sunburstchart-data-label-settings>
</ej-sunburstchart>

{% endhighlight %}

![Label Rotation Mode - Angle using SunburstChart in ASP.NET Core](DataLabel_images/DataLabel_img5.png)
 
## Customizing the data labels

You can customize the appearance of the data point using the `e-sunburstchart-font` property.

{% highlight cshtml %}
<ej-sunburstchart id="SunburstChart" >
<e-sunburstchart-data-label-settings visible="true">
<e-sunburstchart-font color="black" font-weight="Bold" size="15px"></e-sunburstchart-font>
</e-sunburstchart-data-label-settings>
</ej-sunburstchart>
 

{% endhighlight %}

![Customizing the data labels using SunburstChart in ASP.NET Core](DataLabel_images/DataLabel_img6.png)

## Sunburst Chart Title & Subtitle

### Title & TextAlignment

By using the title option, you can add the `title-text` as well as customize its `title-border`, `title-background` and `title-font`.

You can change the title alignment to center, far and near by using the `title-textAlignment` property of the Title.

{% highlight cshtml %}

<ej-sunburstchart id="sunburst">
    <e-title visible="true">
        <e-font color="black" font-weight="bold" size="15px">
            <e-border color="black" width="2"></e-border>
        </e-font>
    </e-title>
</ej-sunburstchart>

{% endhighlight %}


### Sub Title & TextAlignment

By using the subTitle option, you can add the `title-subTitle-text` as well as customize its `title-subTitle-border`, `title-subTitle-background` and `title-subTitle-font`.

{% highlight cshtml %}

<ej-sunburstchart id="sunburst">
    <e-title>
        <e-sub-title visible="true">
            <e-font color="black" font-weight="bold" size="15px">
                <e-border color="black" width="2"></e-border>
            </e-font>
        </e-sub-title>
    </e-title>
</ej-sunburstchart>

{% endhighlight %}

