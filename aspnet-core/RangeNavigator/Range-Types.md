---
layout: post
title: Range Types | RangeNavigator | ASP.NET Core | Syncfusion
description: range types
platform: aspnet-core
control: RangeNavigator
documentation: ug
---

# Range Types

RangeNavigator control is designed to visualize large number of data and navigate to particular data from the large collection at ease. The data for the RangeNavigator is either numeric values or DateTime values and the ValueType property in RangeNavigator indicates the type of the data that should be passed for the control. By default the ValueType of RangeNavigator is DateTime

* Numeric                   
* DateTime

## Numeric Type

RangeNavigator is also used with numeric data and the ValueType for this data is “numeric” 

{% highlight CSHTML %}
 
<div>
    <ej-range-navigator id="range" load="loadingdata" value-type="Numeric">
        <e-chart-series>
            <e-series name="Product A" type="Line" fill="#69D2E7">
            </e-series>
        </e-chart-series>
        <e-selected-range-settings start="100" end="250"></e-selected-range-settings>
    </ej-range-navigator>
</div>

{% endhighlight  %}

The following screenshot displays the RangeNavigator with numeric data.

![](Range-Types_images/Range-Types_img1.png)


## DateTime

By default the ValueType of the RangeNavigator is “datetime” and represents the DateTime values. 

{% highlight CSHTML %}

<div>
    <ej-range-navigator id="range" load="loadingdata" value-type="Datetime">
        <e-chart-series>
            <e-series name="Product A" type="Line" fill="#69D2E7">
            </e-series>
        </e-chart-series>
        <e-selected-range-settings start="2010/5/1" end="2011/10/1"></e-selected-range-settings>
    </ej-range-navigator>
</div>

{% endhighlight  %}

![](Range-Types_images/Range-Types_img2.png)

## DateTime Intervals

The DateTime range type contains an IntervalType property that sets the DateTime interval to one of the following:

* Years
* Quarters
* Months
* Weeks
* Days 
* Hours

By default IntervalType for higher level labels are Years and for lower level labels its Quarters.

{% highlight CSHTML %}

<div>
    <ej-range-navigator id="range" load="loadingdata" value-type="Datetime">
        <e-chart-series>
            <e-series name="Product A" type="Line" fill="#69D2E7">
            </e-series>
        </e-chart-series>
        <e-selected-range-settings start="2010/5/1" end="2011/10/1"></e-selected-range-settings>
        <e-label-settings>
            <e-higher-level interval-type="Years"></e-higher-level>
            <e-lower-level interval-type="Quarters"></e-lower-level>
        </e-label-settings>
    </ej-range-navigator>
</div>

{% endhighlight  %}

![](Range-Types_images/Range-Types_img3.png)