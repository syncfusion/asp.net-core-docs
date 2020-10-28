---
layout: post
title: Drill Operation | PivotChart | ASP.NET Core | Syncfusion
description: drill operation
platform: aspnet-core
control: PivotChart
documentation: ug
---

# Drill operation

This is a basic feature of the pivot chart through which the amount of information can be limited for a better view. It allows you to drill down to access the detailed level of data or drill up to see the summarized data by using the context menu present in the pivot chart.

Drill up, also called roll up, navigates from the inner most level (having detailed information about member) to any other outer levels by climbing up a concept hierarchy for a dimension.

Drill down, also called roll down, is the reverse of drill up. It navigates from the outer level to inner most level by climbing down the concept hierarchy for the dimension.

![Drill-down option in ASP NET Core pivot chart control](Drill-Operation_images/Drill-Operation_img1.png)


![Dril-up option in ASP NET Core pivot chart control](Drill-Operation_images/Drill-Operation_img2.png)


The "drill-success" event is triggered when you right-click the pivot chart and select any option available from the context menu to perform drill up or drill down operation.

{% highlight cshtml %}

<ej-pivot-chart id="PivotChart1" drill-success="DrillSuccess">
    <e-size width="950px" height="460px"></e-size>
</ej-pivot-chart>

<script type="text/javascript">
    function DrillSuccess(args) {
        alert("Drill Success");
    }
</script>

{% endhighlight %}
