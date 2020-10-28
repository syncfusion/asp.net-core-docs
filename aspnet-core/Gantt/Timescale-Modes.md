---
layout: post
title: Timescale-Modes
description: timescale modes
platform: aspnet-core
control: Gantt
documentation: ug
---

# Timescale customization

Gantt contains built-in support to switch over various schedule modes. You can achieve this by defining a schedule header type for the Gantt.

## Schedule Header Types

Gantt contains the following built-in schedule header types

* Hour – Minute
* Day – Hour
* Week – Day
* Month – Week
* Year – Month

The following code example illustrates you on how to change the schedule mode.

### Week schedule mode

In the Week schedule mode, the upper part of the schedule header displays the weeks, whereas the bottom half of the header displays the days. Refer the following code example.

{% highlight cshtml %}
    <ej-gantt id="ganttSample" datasource="ViewBag.datasource"
    //...>
        <e-schedule-header-settings week-header-format="MMM dd , yyyy" schedule-header-type="Week" day-header-format="ddd">
        </e-schedule-header-settings>
    </ej-gantt> 
{% endhighlight %}

The following screenshot illustrates the Week Schedule in Gantt control.

![](Timescale-Modes_images/Timescale-Modes_img1.png)

### Month schedule mode

In the Week schedule mode, the upper part of the schedule header displays the Months whereas the bottom header of the schedule displays its corresponding Weeks. Refer the following code example.

{% highlight cshtml %}
    <ej-gantt id="ganttSample" datasource="ViewBag.datasource"
        //...>
        <e-schedule-header-settings week-header-format="M/dd" schedule-header-type="Month" month-header-format="MMM yyyy">
        </e-schedule-header-settings>
     </ej-gantt> 
{% endhighlight %}

The following screenshot illustrates the Month Schedule in Gantt control.

![](Timescale-Modes_images/Timescale-Modes_img2.png)

### Year schedule mode

In the Week schedule mode, the upper schedule header displays the Years, whereas the bottom header displays its corresponding Months. Refer the following code example.

{% highlight cshtml %}

  <ej-gantt id="ganttSample" datasource="ViewBag.datasource"
        //...>
       <e-schedule-header-settings year-header-format="yyyy" schedule-header-type="Year" month-header-format="MMM">
       </e-schedule-header-settings>
  </ej-gantt> 

{% endhighlight %}

The following screen shot shows the Year Schedule in Gantt control.

![](Timescale-Modes_images/Timescale-Modes_img3.png)

### Day schedule mode

In the Week schedule mode, the upper part of the header displays the Days, whereas the bottom schedule header displays its corresponding Hours. Refer the following code example.

{% highlight cshtml %}

  <ej-gantt id="ganttSample" datasource="ViewBag.datasource"
        //...>
      <e-schedule-header-settings day-header-format="dd,MM,yy " schedule-header-type="Day" hour-header-format="HH">
      </e-schedule-header-settings>
   </ej-gantt> 

{% endhighlight %}

The following screenshot illustrates the Day Schedule in Gantt control.

![](Timescale-Modes_images/Timescale-Modes_img4.png)

### Hour schedule mode

An Hour-Minute Schedule Mode tracks the tasks in minutes scale. In this mode, upper schedule header displays hour scale and the lower schedule header displays its corresponding Minutes. The minute split-up in the lower schedule header can be defined by using the `MinutesPerInterval`
enumeration property. The enumeration values of the `minutes-per-interval` are,

* Auto 
* OneMinute
* FiveMinutes
* FifteenMinutes
* ThirtyMinutes

The value `Auto`, automatically calculates the interval depending upon the `schedule-start-date` and `schedule-end-date`, whereas the other enumeration values splits up accordingly.

{% highlight cshtml %}
  <ej-gantt id="ganttSample" datasource="ViewBag.datasource"
        //...
        date-format="M/d/yyyy hh:mm:ss tt"
        duration-unit="Minute">
      <e-schedule-header-settings schedule-header-type="Hour" minutes-per-interval="FiveMinutes">
      </e-schedule-header-settings>
   </ej-gantt> 

{% endhighlight %}

![](Timescale-Modes_images/Timescale-Modes_img5.png)

## Week start day customization

In Gantt, we can customize week start day by using `week-start-day` property.
By default the `week-start-day` will be assigned with 0 which specifies the start day of the week.

In week schedule mode, week starts with Sunday by default. But we can customize the week start day by using below code example
 
{% highlight cshtml %}
  <ej-gantt id="ganttSample" datasource="ViewBag.datasource"
        //...>        
      <e-schedule-header-settings schedule-header-type="Week" week-start-day=2 />    
  </ej-gantt> 
{% endhighlight %}

## Rounding off timescale (schedule) start date

You can able to round off the schedule start date in a project by using the `timescale-start-date-mode` property. It is possible to set the following values to the property,

* Auto
* Month
* Week
* Year

The value `Auto`, automatically calculates the schedule header depending on the datasource values, whereas the other enumeration values rounds off the schedule header accordingly. For Instance, in year schedule if you set `timescale-start-date-mode` as `Month` then the schedule header will start from the immediate month of the schedule instead of starting from beginning of the year.

{% highlight cshtml %}
  <ej-gantt id="ganttSample" datasource="ViewBag.datasource"
        //... >
      <e-schedule-header-settings schedule-header-type="Year" timescale-start-date-mode="Month" >
      </e-schedule-header-settings>
  </ej-gantt>
{% endhighlight %}

![](Timescale-Modes_images/Timescale-Modes_img6.png)

## Customize automatic timescale update action

In Gantt, schedule timeline will be automatically updated when the tasks are edited beyond the schedule start date and end date range. This can be enabled/disabled by using [`update-timescale-view`](/api/js/ejgantt#members:scheduleheadersettings-updatetimescaleview) property.
The following code snippets shows how to prevent the automatic timescale update in Gantt.
 
{% highlight cshtml %}
	<ej-gantt id="ganttSample" datasource="ViewBag.datasource"
        //...>        
		<e-schedule-header-settings schedule-header-type="Week" update-timescale-view="false" />    
	</ej-gantt> 
{% endhighlight %}

The following screenshot shows the output of above code example.

![](Timescale-Modes_images/Timescale-Modes_img7.png)
At Initial load
{:.caption}

![](Timescale-Modes_images/Timescale-Modes_img8.png)
`update-timescale-view` property as `false`
{:.caption}

![](Timescale-Modes_images/Timescale-Modes_img9.png)
`update-timescale-view` property as `true`
{:.caption}

