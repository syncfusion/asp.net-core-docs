---
layout: post
title: Baseline
description: baseline
platform:  aspnet-core
control: Gantt
documentation: ug
---

# Baseline

Baseline is used to describe the original plan of the task and it can be the same as current duration of the task or different. The following code example shows you how to enable baseline in Gantt control.

{% highlight cshtml %}
    <ej-gantt id="ganttSample3" datasource="ViewBag.datasource" 
        //...
        baseline-start-date-mapping="BaselineStartDate"
        baseline-end-date-mapping="BaselineEndDate"
        render-baseline="true">
    </ej-gantt>   

{% endhighlight %}

The following screenshot shows the baseline in Gantt control.

![](Baseline_images/Baseline_img1.png)

