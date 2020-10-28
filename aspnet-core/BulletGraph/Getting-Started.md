---
layout: post
title: Getting-Started
description: getting started
platform: aspnet-core
control: BulletGraph
documentation: ug
---

# Getting Started

This section explains briefly about how to create a BulletGraph in your ASP.NET Core 1.0.

## Create your first BulletGraph in ASP.NET Core 1.0

This section encompasses the details on how to configure the BulletGraph control in your application. It also allows you to learn how to pass the required data to it and customize its various options according to your requirements.

In the following screenshot, a BulletGraph is used to compare the actual monsoon rainfall received in a state versus its forecasted values for the years ranging from 1988 to 2013.



![](Getting-Started_images/Getting-Started_img1.jpg)


1. Create a <div> tag.
	
   ~~~ html
	
	<div>
	
	</div>
	
   ~~~
   


2. Add the following code in the index.cshtml file to create the BulletGraph control in the View page.

   ~~~ javascript

	<div>

	<ej-bullet-graph id="Bulletgraph">
    </ej-bullet-graph>

	</div>

   ~~~
   

3. Execute the above code to display the BulletGraph. To customize the measure bars in the BulletGraph, you can pass the data either locally or remotely.



![](Getting-Started_images/Getting-Started_img2.png)

### Provide Required Data

You can customize the values of feature and comparative measure bars in a BulletGraph, either locally or remotely. The category data is optional, and it is used to display label values parallel to the measure bars. 

Assign the data in BulletLocalDataBind variable to the DataSource property of BulletGraph as illustrated in the following code example. 


{% highlight C# %}

public IActionResult LocalDataBinding()
{
            bulletLocalData.Add(new BulletLocalDataBind { category = "2013", value = "90", comparativeMeasureValue = "100" });

            bulletLocalData.Add(new BulletLocalDataBind { category = "2012", value = "93", comparativeMeasureValue = "99" });

            bulletLocalData.Add(new BulletLocalDataBind { category = "2011", value = "98", comparativeMeasureValue = "96" });

            bulletLocalData.Add(new BulletLocalDataBind { category = "2010", value = "102", comparativeMeasureValue = "98" });

            bulletLocalData.Add(new BulletLocalDataBind { category = "2009", value = "77", comparativeMeasureValue = "96" });

            bulletLocalData.Add(new BulletLocalDataBind { category = "2008", value = "99", comparativeMeasureValue = "99" });

            bulletLocalData.Add(new BulletLocalDataBind { category = "2007", value = "106", comparativeMeasureValue = "94" });

            bulletLocalData.Add(new BulletLocalDataBind { category = "2006", value = "105", comparativeMeasureValue = "95" });

            bulletLocalData.Add(new BulletLocalDataBind { category = "2005", value = "98", comparativeMeasureValue = "98" });

            bulletLocalData.Add(new BulletLocalDataBind { category = "2004", value = "87", comparativeMeasureValue = "100" });

            bulletLocalData.Add(new BulletLocalDataBind { category = "2003", value = "105", comparativeMeasureValue = "98" });

            bulletLocalData.Add(new BulletLocalDataBind { category = "2002", value = "84", comparativeMeasureValue = "100" });

            bulletLocalData.Add(new BulletLocalDataBind { category = "2001", value = "93", comparativeMeasureValue = "98" });

            bulletLocalData.Add(new BulletLocalDataBind { category = "2000", value = "96", comparativeMeasureValue = "101" });

            bulletLocalData.Add(new BulletLocalDataBind { category = "1999", value = "107", comparativeMeasureValue = "98" });

            bulletLocalData.Add(new BulletLocalDataBind { category = "1998", value = "98", comparativeMeasureValue = "101" });

            bulletLocalData.Add(new BulletLocalDataBind { category = "1997", value = "92", comparativeMeasureValue = "98" });

            bulletLocalData.Add(new BulletLocalDataBind { category = "1996", value = "98", comparativeMeasureValue = "96" });

            bulletLocalData.Add(new BulletLocalDataBind { category = "1995", value = "96", comparativeMeasureValue = "107" });

            bulletLocalData.Add(new BulletLocalDataBind { category = "1994", value = "92", comparativeMeasureValue = "98" });

            bulletLocalData.Add(new BulletLocalDataBind { category = "1993", value = "103", comparativeMeasureValue = "92" });

            bulletLocalData.Add(new BulletLocalDataBind { category = "1993", value = "93", comparativeMeasureValue = "98" });

            bulletLocalData.Add(new BulletLocalDataBind { category = "1991", value = "95", comparativeMeasureValue = "96" });

            bulletLocalData.Add(new BulletLocalDataBind { category = "1990", value = "103", comparativeMeasureValue = "92" });

            bulletLocalData.Add(new BulletLocalDataBind { category = "1989", value = "102", comparativeMeasureValue = "103" });

            bulletLocalData.Add(new BulletLocalDataBind { category = "1988", value = "112", comparativeMeasureValue = "93" });

            ViewBag.datasource = bulletLocalData;

            return View();
}

{% endhighlight %}



Once the DataSource property is assigned with the required values, you can bind the variable names used in the JSON data to the corresponding fields of the BulletGraph as shown in the following code example.


{% highlight CSHTML %}

<ej-bullet-graph id="Bulletgraph">

        <e-fields datasource="ViewBag.datasource" 
                  category-field="category" 
                  feature-measure-field="value" 
                  comparative-measure-field="comparativeMeasureValue">
        </e-fields>

</ej-bullet-graph>

{% endhighlight %}

### Set Default and Scale Values

You can plot any number of measure bars within the BulletGraph by increasing the height and width of the control to locate all the measure bars within the graph. Set the QualitativeRangeSize and QuantitativeScaleLength properties according to the following code example.

By default, the BulletGraph is rendered in the horizontal orientation with its flow direction set to Forward. In this example, to achieve the desired output, change the horizontal orientation to vertical orientation with the flow direction set to Backward.

Minimum, Maximum and Interval values for the QuantitativeScale of the BulletGraph are set, as illustrated in the following code example. The ticks and labels within the scale are also positioned.


{% highlight js %}

<ej-bullet-graph id="Bulletgraph">

        <e-quantitative-scale-settings minimum="70" maximum="130" interval="10" 
                    tick-position="Center">
                    <e-location x="80" y="30"></e-location>
            <e-label-settings position="Above"></e-label-settings>
        </e-quantitative-scale-settings>

</ej-bullet-graph>


{% endhighlight %}


![](Getting-Started_images/Getting-Started_img3.jpg)


The above image illustrates the BulletGraph without any ranges displayed in the background.

### Add Qualitative Ranges

By default, 3 ranges are displayed in the BulletGraph control during the initial rendering of the control with its default values. To customize it, you can set appropriate values for the RangeEnd and RangeStroke properties.  Any number of QualitativeRanges can be added to the control.


{% highlight js %}

<ej-bullet-graph id="Bulletgraph">
        
        <e-qualitative-ranges>
            <e-qualitative-range range-end="90"></e-qualitative-range>
            <e-qualitative-range range-end="110"></e-qualitative-range>
            <e-qualitative-range range-end="130" range-stroke="#CDC9C9"></e-qualitative-range>
        </e-qualitative-ranges>

</ej-bullet-graph>

{% endhighlight %}

After adding QualitativeRanges to the BulletGraph, the control appears as follows.



![](Getting-Started_images/Getting-Started_img4.jpg)


### Ticks and Measure Bars Customization

You can do the following code changes in the quantitative scale to customize the tick size, the color of the feature bar and the comparative measure symbols.


{% highlight js %}

<ej-bullet-graph id="Bulletgraph">

        <e-quantitative-scale-settings minimum="70" maximum="130" interval="10" tick-position="Near">
            <e-location x="80" y="30"></e-location>
            <e-label-settings position="Above"></e-label-settings>
            <e-major-tick-settings size="7" width="1"></e-major-tick-settings>
            <e-minor-tick-settings width="1"></e-minor-tick-settings>
            <e-comparative-measure-settings stroke="#507786"></e-comparative-measure-settings>
            <e-featured-measure-settings stroke="#169DD8"></e-featured-measure-settings>
        </e-quantitative-scale-settings>   

</ej-bullet-graph>

{% endhighlight %}



When you customize the ticks and measure bar, the BulletGraph appears as follows.



![](Getting-Started_images/Getting-Started_img5.jpg)

### Add Caption and Subtitle

You can add the following code example to display an appropriate Caption and Subtitle to the BulletGraph.


{% highlight js %}

<ej-bullet-graph id="Bulletgraph">

        <e-caption-settings text-angle="90" text="Monsoon Rainfall - Actual vs Forecast">
            <e-location x="470" y="270"></e-location>
            <e-bullet-font font-family="Segoe UI" font-weight="regular" size="20px" opacity="1"></e-bullet-font>
            <e-sub-title text-angle="0" text="Rainfall (mm)">
                <e-location x="180" y="4"></e-location>
                <e-bullet-font font-family="Segoe UI" font-weight="regular" size="16px" opacity="1"></e-bullet-font>
            </e-sub-title>
        </e-caption-settings>
        
</ej-bullet-graph>


{% endhighlight %}


The following screenshot displays a BulletGraph with a Caption and Subtitle.



![](Getting-Started_images/Getting-Started_img6.jpg)

### Show Tooltip

You can use a Tooltip in your application to display the values of forecasted rainfall, actual rainfall received in millimeter and also the appropriate year. The Tooltip Visible property is set to True to enable the Tooltip option. To set the template Tooltip, you can pass the template id to it as illustrated in the following code example.


{% highlight cshtml %}

<ej-bullet-graph id="Bulletgraph">

            <e-bullet-tooltip-settings visible="true" template="Tooltip"></e-bullet-tooltip-settings>
            
</ej-bullet-graph>



{% endhighlight %}

{% highlight xml %}

<div id="Tooltip"style="display:none; width:125px;padding-top: 10px;padding-bottom:10px">



<div align="center"style="font-weight:bold">

           Rainfall </div>

<table>

<tr><td>Actual</td>

<td>: {{:currentValue}}mm</td></tr>

<tr><td>Forecast</td>

<td>: {{:targetValue}}mm</td></tr>

<tr><td>Year</td>

<td>: {{:category}}</td></tr>

</table>

</div>

{% endhighlight %}

The following screenshot displays a customized BulletGraph.



![](Getting-Started_images/Getting-Started_img7.jpg)

