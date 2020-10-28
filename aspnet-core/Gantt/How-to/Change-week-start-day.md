---
layout: post
title: Change-Week-start-day
description: Week start day customization
platform: aspnet-core
control: Gantt
documentation: ug
---

# Change week start day in month timescale mode

## Using start date mode as Month

When setting the `timescale-start-date-mode` property as Month, the project will start from the first date of the same month of the first task in a project. Using below code example we can change the week start day of the project start date in month timescale mode.

{% highlight cshtml %}
  <ej-gantt id="ganttSample" datasource="ViewBag.datasource"
        //...
       load="load" >
      <e-schedule-header-settings schedule-header-type="Month" week-start-day=2  
	              week-header-format="M/dd" month-header-format="MMM yyyy" 
				  timescale-start-date-mode="Month" />
    </ej-gantt>
{% endhighlight %}

{% highlight javascript %}
    function load(args) {
        var ganttObj = $("#GanttContainer").data("ejGantt"),
        ganttObj._enableMonthStart = false;
    }
{% endhighlight %}

![](Change-Weekstart-Day-images/image-1.png)

## Using start date mode as Year

When setting the `timescale-start-date-mode` property as Year, the project will start from the first date of the same year to which the first task in a project starts. Using below code example we can change the week start day of the project start date in year timescale mode.

{% highlight cshtml %}
  <ej-gantt id="ganttSample" datasource="ViewBag.datasource"
        //...
       load="load" >
      <e-schedule-header-settings schedule-header-type="Month" timescale-start-date-mode="Year" 
	  week-start-day=5 week-header-format="M/dd" >
      </e-schedule-header-settings>
  </ej-gantt>
{% endhighlight %}

{% highlight javascript %}
    function load(args) {
        var ganttObj = $("#GanttContainer").data("ejGantt"),
        ganttObj._enableMonthStart = false;
    }

{% endhighlight %}

![](Change-Weekstart-Day-images/image-2.png)

By default _enableMonthStart property will be true. Week header in month schedule mode will be rendered with month/year start day. To customize the week start day in month mode we need to set _enableMonthStart as false.
