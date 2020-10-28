---
layout: post
title: Series | PivotChart | ASP.NET Core | Syncfusion
description: This document illustrates that how to enable series and its customization in ASP.NET Core PivotChart control
platform: aspnet-core
control: PivotChart
documentation: ug
---

# Series

## Series point customization

By using the `fill` and `border` properties of the chart series, you can customize the series color, border color, and border width of the pivot chart.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1" series-rendering="onSeriesRenders">
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>
<script type="text/javascript">
    function onSeriesRenders(args) {
        this.model.series[0].points[0].fill = "aqua";
        this.model.series[0].points[0].border = {
            color: "black",
            width: 2
        };
    }
</script>

{% endhighlight %}

![Series customization in ASP NET Core pivot chart control](Series_images/Series_img1.png)