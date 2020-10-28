---
layout: post
title: Appearance and Styling | RangeNavigator | ASP.NET Core | Syncfusion
description: appearance and styling
platform: aspnet-core
control: RangeNavigator
documentation: ug
---

# Appearance and Styling

RangeNavigator is enriched with lots of customization options for labels, gridlines and slider to develop high quality graphic rich control.

## Label Placement:

Labels in RangeNavigator are placed inside or outside of the control. You can customize both the higher and lower level labels using LabelPlacement property in label setting of RangeNavigator. By default LabelPlacement is “outside” for the both higher and lower level labels.

The higher level labels font `Color`, `FontFamily`, `FontStyle`, `FontWeight`, `Opacity` and `Size` can be customized using `HigherLevel` property.

The lower level labels font `Color`, `FontFamily`, `FontStyle`, `FontWeight`, `Opacity` and `Size` can be customized using `LowerLevel` property. 


The following screen shot illustrates both the lower and higher level labels that are placed outside the control with LabelPlacement specified as outside. 

{% highlight CSHTML %}

<div>
	<ej-range-navigator id="range" load="loadingData">
		<e-chart-series>
			<e-series name="Product A" type="Line" fill="#69D2E7">
			</e-series>
		</e-chart-series>
		<e-selected-range-settings start="2010/5/1" end="2011/10/1"></e-selected-range-settings>
		<e-label-settings>
			<e-higher-level label-placement="Inside"></e-higher-level>
			<e-lower-level label-placement="Inside"></e-lower-level>
		</e-label-settings>
		</ej-range-navigator>
</div>

{% endhighlight  %}

The following screenshot illustrates a RangeNavigator with labels inside the control after specifying the LabelPlacement as inside.

![](Appearance-and-Styling_images/Appearance-and-Styling_img2.png)

### Customize NavigatorStyleSettings

RangeNavigator is customized using NavigatorStyleSettings properties. You can customize the selected and unselected region color using SelectedRegionColor, UnselectedRegionColor in NavigatorStyleSettings and the thumb of the slider using ThumbColor, ThumbRadius and ThumbStroke in NavigatorStyleSettings.  MajorGridLineStyle and MinorGridLineStyle are used to customize the grid line color and visibility.

### Customize Labels

The visibility of labels are enabled by setting `Visible` in higher level and `Visible` in lower level. The labels can be aligned by specifying `HorizontalAlignment` of higher level style and `HorizontalAlignment` of lower level style.

You can customize the `Border` `Color` and `Width`, `Fill`, `GridLineStyle` `Color`, `DashArray` and `Width`, `Position` property of higher level labels in labelSettings.

You can also customize the `Border` `Color` and `Width`, `Fill`, `GridLineStyle` `Color`, `DashArray` and `Width`, `Position` property for lower level labels of labelSettings.
 

{% highlight CSHTML %}
 
<div>
    <ej-range-navigator id="range">
        <e-navigator-style-settings background="transparent" unselected-region-color="white" selected-region-color="#5EABDE" thumb-radius="10" thumb-color="white">
            <e-border color="Black" width="3"></e-border>
            <e-major-grid-line-style visible="true" color="transparent"></e-major-grid-line-style>
            <e-minor-grid-line-style visible="true" color="transparent"></e-minor-grid-line-style>
        </e-navigator-style-settings>
        <e-label-settings>
            <e-higher-level label-placement="Inside" interval-type="Years"></e-higher-level>
        </e-label-settings>
    </ej-range-navigator>
</div>

{% endhighlight  %}

![](Appearance-and-Styling_images/Appearance-and-Styling_img3.png)

## Themes

RangeNavigator theme is a set of pre-defined options that are applied to the control before each RangeNavigator is instantiated. Following predefined themes are available in RangeNavigator.

1. flat light                  
2. flat dark                  
3. gradient light           
4. gradient dark           
5. azure                      
6. azure dark               
7. lime 
8. lime dark
9. saffron
10. saffron dark
11. gradient azure
12. gradient azure dark
13. gradient lime
14. gradient lime dark
15. gradient saffron

### gradient saffron dark

{% highlight CSHTML %}

<div>
	<ej-range-navigator id="range" load="loadingData" theme="azuredark">
		<e-chart-series>
			<e-series name="Product A" type="Line">
			</e-series>
		</e-chart-series>
		<e-selected-range-settings start="2010/5/1" end="2011/10/1"></e-selected-range-settings>
		</ej-range-navigator>
</div>

{% endhighlight  %}

![](Appearance-and-Styling_images/Appearance-and-Styling_img4.png)