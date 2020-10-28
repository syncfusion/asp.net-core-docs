---
layout: post
title: Populate Data | RangeNavigator | ASP.NET Core | Syncfusion
description: populate data
platform: aspnet-core
control: RangeNavigator
documentation: ug
---

# Populate Data

When you provide data to RangeNavigator, it produces limited set of data. You can populate the RangeNavigator with data using the DataSource and Series properties.

## Add series to the RangeNavigator

The Series property provides access to a collection of all series that are defined explicitly within a RangeNavigator control. Each series is assigned with type and name. It contains collection of data point, each point contains x value and y values. You can add data points to the series through DataSource property by providing field name to get the values from the DataSource in `xName` and `yName` options.

Animation can be enabled by setting `Enable-Animation` property as true and the series color can be customized by using `Fill` property in series.



{% highlight CSHTML %}
 
<div>
<ej-range-navigator id="range" load="loadingData">
	<e-chart-series>
		<e-series name="Product A" type="Line" enable-animation="false" fill="#69D2E7" opacity="0.5">
		</e-series>
	</e-chart-series>
	<e-selected-range-settings start="2010/5/1" end="2011/10/1"></e-selected-range-settings>
</ej-range-navigator>
</div>

<script type="text/javascript">

    function loadingData(sender) {

        data = GetData();

        sender.model.series[0].dataSource = data.Open;

        sender.model.series[0].xName = "XValue",

        sender.model.series[0].yName = "YValue";

    }

    // Method to get data in JSON format

    function GetData() {

        var series1 = [];

        var series2 = [];

        var value = 100;

        var value1 = 120;

        for (var i = 1; i < 730; i++) {

            if (Math.random() > .5) {

                value += Math.random();

                value1 += Math.random();

            }
            else {

                value -= Math.random();

                value1 -= Math.random();

            }

            var point1 = { XValue: new Date(2010, 0, i), YValue: value };

            var point2 = { XValue: new Date(2010, 0, i), YValue: value1 };

            series1.push(point1);

            series2.push(point2);

        }

        data = { Open: series1, Close: series2 };

        return data;

    }

</script>   

{% endhighlight  %}

The following screenshot illustrates the RangeNavigator that is populated with data using DataSource property in series.

![](Populate-Data_images/Populate-Data_img1.png)