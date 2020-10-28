---
layout: post
title: Working-time-range
description: working time range
platform: aspnet-core
control: Gantt
documentation: ug
---

# Working Time Range

In Gantt control, working hours in a day for a project can be defined by using `e-gantt-day-working-time` property. Based on the working hours, automatic date scheduling and duration validations for a task are performed.

The below code snippet explains on how to define the working time range for the project in Gantt,

{% highlight cshtml %}
    <ej-gantt id="ganttSample" datasource="ViewBag.datasource"
        //...
        task-type="FixedWork">
        <e-gantt-day-working-time-collection>
            <e-gantt-day-working-time from="08:00 AM" to="12:00 PM"></e-gantt-day-working-time>
            <e-gantt-day-working-time from="01:00 PM" to="05:00 PM"></e-gantt-day-working-time>
        </e-gantt-day-working-time-collection>
    </ejGantt>
{% endhighlight %}

N> 1. Individual tasks can lie between any time within the defined working time range of the project.

N> 1. `e-gantt-day-working-time` property is used to define the working time for the whole project.

The following screen shot shows working time range in Gantt control. 

![](Working-time-range_images/Working-time-range_img1.png)

## Highlight working time range

Highlight the working time range with a background color by using the `e-gantt-day-working-time.background` property. You can highlight the non-working time ranges in a day. To do this, set the `highlight-non-working-time` property to `true`. To customize the non-working time background, use the `non-working-background` property.

The following code snippet explains how to define the working time range with background in Gantt.

{% highlight cshtml %}
    <ej-gantt id="ganttSample" datasource="ViewBag.datasource"
        //...
		highlight-non-working-time="true"
        non-working-background="#B7C3D0">
         <e-gantt-day-working-time-collection>
            <e-gantt-day-working-time from="08:00 AM" to="12:00 PM" background="#EBF5FB"></e-gantt-day-working-time>
            <e-gantt-day-working-time from="01:00 PM" to="05:00 PM" background="#EBF5FB"></e-gantt-day-working-time>
        </e-gantt-day-working-time-collection>
    </ejGantt>
{% endhighlight %}

N> The background colors of working time range are highlighted only when the `e-schedule-header-settings.schedule-header-type` value as `Day`.

The following screenshot shows the working time range with background colors.

![](Working-time-range_images/Working-time-range_img2.png)