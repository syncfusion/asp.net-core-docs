---
title: Setting dimension
description: Setting dimension for Schedule control
platform: aspnet-core
control: schedule
documentation: ug
keywords: dimension, cell dimension, cell width, cell height 
---
# Setting Dimension

The dimension normally refers to the height and width of the element. With Scheduler, it is possible to set 2 kinds of dimensions.

* Scheduler dimension (Scheduler control height and width)
* Cell dimension (Scheduler cells height and width)

## Scheduler Dimension

The `height` and `width` properties can be defined to set the outer dimension of the Scheduler control.

{% highlight razor %}

<ej-schedule id="Schedule1" width="70%" height="500px" current-date="new DateTime(2015, 11, 8)">
</ej-schedule>

{% endhighlight %}

N> The height and width properties accepts both **Pixel** and **Percentage** values.

## Scheduler Cell Dimensions

### Cell Height

The `cell-height` property allows the Scheduler to set the height of the cells in pixels. The appointment height in vertical mode changes accordingly as per the cell size within which it renders.

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });
}

<ej-schedule id="Schedule1" width="100%" height="525px" cell-height="40px" current-date="new DateTime(2015, 11, 8)">
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}

N> In **Desktop** mode, the default height value of the cells is set to **20px**, whereas for **Mobile** mode – the Scheduler cells are rendered with **40px** by default.

## Cell Auto-Height

The height of the cells specifically in timeline view can be made to adjust automatically based on its exceeding appointment count. It is controlled by an API named `show-overflow-button` which accepts true or false value, denoting whether to enable/disable the cell auto-height adjusting option. To enable this option, set the value of `show-overflow-button` as `false` whereas its default value is `true`.

In **Vertical** view, the same functionality is made applicable only in the **Month View** whereas in **Horizontal** mode, it is applicable in all the views.

{% highlight razor %}

<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 8)" current-view="Month" show-overflow-button="false">
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}

### Cell Width

The `cell-width` property allows the Scheduler to set the width of the cells in pixels. The appointment width adjusts based on the cell width of the Scheduler.

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });
}

<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 8)" cell-width="100px">
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}

N> When the **cell-height** and **cell-width** properties are set with some specific pixel values, the cell size does not adapt to the responsive behavior of the Scheduler while resizing it in desktop/mobile mode.

