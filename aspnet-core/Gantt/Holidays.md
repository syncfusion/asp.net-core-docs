---
layout: post
title: Holidays
description: holidays
platform: aspnet-core
control: Gantt
documentation: ug
---

# Holidays

Holidays in Gantt control is used to highlight the non-working days in Gantt control and it can be initialized with Gantt control by using the following code example.

{% highlight cshtml %}

<ej-gantt id="ganttSample" datasource="ViewBag.datasource"
    //...>
    <e-holidays>
        <e-holiday day="2/03/2014" label="Public holiday" background="yellowgreen"></e-holiday>
    </e-holidays>
</ejGantt> 

{% endhighlight %}

The following screenshot shows the output of Holidays in Gantt control.

![](Holidays_images/Holidays_img1.png)

