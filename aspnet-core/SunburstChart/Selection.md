---
layout: post
title: Selection
description: What are the different modes of selection present in the Sunburst Chart
platform: aspnet-core
control: SunburstChart
documentation: ug
---

# Selection 
SunburstChart provides selection support for the points on mouse click. To enable the selection , set the *Enable* property to true in the **e-sunburstchart-selection-settings**. 

{% highlight cshtml %}

<ej-sunburstchart id="SunburstChart" >
<e-sunburstchart-selection-settings enable="true" ></e-sunburstchart-selection-settings>
</ej-sunburstchart>

{% endhighlight %}

![](Selection_images/Selection_img1.png)

 
## Selection Display mode

 You can customize the selected  segment appearance by using color or opacity. You can choose between color or opacity using the **type** selection Settings.

*	selectionByColor – To display the selected segment appearance using color.
*	selectionByOpacity – To display the selected segment appearance using opacity.

{% highlight cshtml %}

<ej-sunburstchart id="SunburstChart" >
<e-sunburstchart-selection-settings enable="true" color="red" type="@SunburstSelectionType.Color"></e-sunburstchart-selection-settings>
</ej-sunburstchart>

 {% endhighlight %}

![](Selection_images/Selection_img2.png)

## Selection Mode

Sunburst chart provides multiple option to represent the selected categories. You can select the segment categories by using the **Mode** property in selectionSettings
*	Child – To selection the child of selected parent.
*	All – To selection the entire categories in group.
*	Parent – To selection the parent of selected child.
*	Single - To selection single item in the category.

### Child
The following code shows how to set the selection type as child 

{% highlight cshtml %}

<ej-sunburstchart id="SunburstChart" >
<e-sunburstchart-selection-settings enable="true" mode="@SunburstSelectionMode.Child">
</e-sunburstchart-selection-settings>
</ej-sunburstchart>


{% endhighlight %}

![](Selection_images/Selection_img3.png)
 
### Parent

The parent mode can be enabled by using the below code 

{% highlight cshtml %}

<ej-sunburstchart id="SunburstChart" >
<e-sunburstchart-selection-settings enable="true" mode="@SunburstSelectionMode.Parent">
</e-sunburstchart-selection-settings>
</ej-sunburstchart>

{% endhighlight %}

![](Selection_images/Selection_img4.png)
 
### Point

To selection the particular segment, the point mode of the selection settings is used.

{% highlight cshtml %}

<ej-sunburstchart id="SunburstChart" >
<e-sunburstchart-selection-settings enable="true" mode="@SunburstSelectionMode.Point">
</e-sunburstchart-selection-settings>
</ej-sunburstchart>

 {% endhighlight %}

![](Selection_images/Selection_img5.png)
 
### All

The following code snippet is used for the all mode of selection settings

{% highlight cshtml %}

<ej-sunburstchart id="SunburstChart" >
<e-sunburstchart-selection-settings enable="true" mode="@SunburstSelectionMode.All">
</e-sunburstchart-selection-settings>
</ej-sunburstchart>


{% endhighlight %}

![](Selection_images/Selection_img6.png)

