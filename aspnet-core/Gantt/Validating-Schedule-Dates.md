---
layout: post
title: Validating-Schedule-Dates
description: validating schedule dates
platform: aspnet-core
control: Gantt
documentation: ug
---

# Validating Schedule Dates

Validating schedule dates is used to change the schedule start date and end date dynamically. By this support, `schedule-start-date` and `schedule-end-date` can be automatically updated from the data source. When you change the date of any task item to the date that is beyond `schedule-start-date` or `schedule-end-date` through cell editing, taskbar editing, dialog editing or toolbar operation, then the `schedule-start-date` and `schedule-end-date` can be dynamically updated based on that task item’s date.

`prevTimeSpan` and `nextTimeSpan` toolbar items are used to create new time span based on the schedule mode.

{% highlight cshtml %}
    <ej-gantt id="ganttSample" datasource="ViewBag.datasource"
        //...>
        <e-gantt-toolbar-settings show-toolbar="true" toolbar-items="@(new List<string>() { "prevTimeSpan","nextTimeSpan" })">
        </e-gantt-toolbar-settings>
    </ejGantt>
{% endhighlight %}

The following screenshot illustrates the output of the above code.

![](Validating-Schedule-Dates_images/Validating-Schedule-Dates_img1.png)

