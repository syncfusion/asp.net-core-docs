---
layout: post
title: Globalization--Localization
description: globalization & localization
platform: aspnet-core
control: RangeNavigator
documentation: ug
---

# Globalization & Localization

RangeNavigator supports Localization and Globalization to customize the labels based on a culture specific to a country. The culture defines specific information for the number formats, week and month names, date and time formats etc. 

## Localization

Localization is the process of customizing the user interface based on a culture specific to a particular country or region in order to display regional data.  The culture is represented by a unique string, for example, ―en-US‖ for U.S. English and ―fr-FR‖ for French (common), this is achieved by creating a JavaScript file “rangeNavigatorSource.fr-FR.js” and setting the equivalent word as illustrated in the following code sample.

{% highlight CSHTML %}

ej.datavisualization.RangeNavigator.locale["fr-FR"] = 
{
    intervals: 
	{
        //string to display the intervals on RangeNavigator

        quarter: {longQuarters: "Trimestre", shortQuarters: "T"},

        week: { longWeeks: "Semaine", shortWeeks: "S" }
    }

}

{% endhighlight  %}

Localization is the key feature that provides solutions globally with the help of localized control. 

{% highlight CSHTML %}

<div>
    <ej-range-navigator id="range" load="loadingdata" locale="fr-FR">
        <e-chart-series>
            <e-series name="Product A" type="Line" enable-animation="false" fill="#69D2E7" opacity="0.5">
            </e-series>
        </e-chart-series>
        <e-selected-range-settings start="2010/5/1" end="2011/10/1"></e-selected-range-settings>
    </ej-range-navigator>
</div>

{% endhighlight %}

![](Globalization--Localization_images/Globalization--Localization_img1.png)

## RTL

Right-to-Left or RTL describes the ability of application to handle and responds you to communicate with a right-to-left language, like Arabic or Japanese. EnableRTL property is used to change the rendering format to "Right to Left", by default it renders from "Left to Right" in RangeNavigator. 

{% highlight CSHTML %}

<div>
    <ej-range-navigator id="range" load="loadingdata" enable-rtl="true">
        <e-chart-series>
            <e-series name="Product A" type="Line" enable-animation="false" fill="#69D2E7" opacity="0.5">
            </e-series>
        </e-chart-series>
        <e-selected-range-settings start="2010/5/1" end="2011/10/1"></e-selected-range-settings>
    </ej-range-navigator>
</div>

{% endhighlight  %}

![](Globalization--Localization_images/Globalization--Localization_img2.png)