---
title: Schedule - Views
description: View options available in Scheduler
platform: aspnet-core
control: schedule
documentation: ug
keywords: day, week, workweek, month, timeline, horizontal, custom  
---
# Views

The number of days and its associated appointments are usually grouped together in Scheduler to organize different views. The available view options in Scheduler are as follows,

* Day
* Week
* Workweek
* Month
* Custom View
* Agenda
* Timeline View

Usually these view options are displayed as a toolbar in the date-header section of the Schedule control. The items within the views toolbar can be added/removed based on the value passed to the `views` property. 

By default, the Schedule control’s active view is **Week** view. Also, it is possible to change the active view of the Scheduler by setting `current-view` option with the required view name as depicted below.

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });
}

@{List<string> view = new List<string>() { "Day", "Week", "WorkWeek", "Month" };}
<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 8)" views="view" current-view="Week">
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}


## Day 

It represents a single day Scheduler view (single date display) with all its related appointments.

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });
}

<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 8)" current-view="Day">
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}

## Week

It’s a view displaying a count of 7 days (from Sunday to Saturday) with all its related appointments. The first day of the week can be changed using the `first-day-of-week` API which accepts either the `integer` (Sunday=0, Monday=1, Tuesday=2, etc) or `string` (“Sunday”, “Monday”, etc) or `DayOfWeek` enum type value. The default value of this **first-day-of-week** depends on the current culture (language) used in the Scheduler.

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });
}

<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 8)" current-view="Week" first-day-of-week="DayOfWeek.Monday">
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}

## Work Week 

Work week view displays the working days of the week (count of 5 days) and its associated appointments. It is also possible to customize the days to be displayed in the work week view using `work-week` API which accepts the string array such as ["Monday", "Tuesday", "Wednesday", "Thursday","Friday"]. By default, it renders from Monday to Friday (5 days).

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });
}

@{List<string> workWeek = new List<string>() { "Monday", "Tuesday" ,"Wednesday", "Friday", "Saturday" };}
<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 8)" current-view="Workweek" work-week="workWeek">
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}

## Month

Month view displays the entire days of a particular month and all its related appointments. An alternative way to navigate to a particular date in a day view directly from Month view, clicking on the appropriate month cell date header will do so. If the week date range column is clicked, it will navigate to the corresponding week view.

The next and previous month date cells in the Month view can be shown/hidden on the Scheduler using `show-next-prev-month` property by setting it to *false*.

For example – To set the Month view as current view in Scheduler and to hide the other month days in it, refer the below code example.

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });
}

<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 8)" current-view="Month" show-next-prev-month="false">
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}

N> An appointment directly created in Month view will be considered as an all-day appointment.

## Customizing number of days (Custom View)

The Scheduler can be displayed with the user-specified date ranges, such as 4 days or any specific date ranges instead of default view options, by making use of the `RenderDates` property. This property includes two sub properties namely **Start** and **End**, which accepts the date object or date value in string format to specify the date range. 

To display the custom view option in the toolbar-like view options in the scheduler header area, add the `CustomView` value to the views property array collection as shown below. 

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });
}

@{List<string> view = new List<string>() { "Day", "Week", "WorkWeek", "Month", "CustomView" };}
<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 8)" current-view="CustomView" views="view">
    <e-render-dates start="5/1/2014" end="5/6/2014"></e-render-dates>
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}

When the date difference between the provided start and end date is greater than 7, then the month-like view will get displayed in Vertical Scheduler mode - whereas with the date difference less than 7 days displays the Scheduler with exact count of the specified days.

N> When the `current-date` property of Scheduler is set with a date, that lies beyond the specified custom date range - then the Scheduler navigates to the current date with the mentioned date differences.  

## Agenda

This View option lists out the appointments in a grid-like view for the next 7 days by default from the current date. The count of the number of appointments to be listed in this view can be customized using the `days-in-agenda`.

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });
}

<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 8)" current-view="Agenda">
    <e-agenda-view-settings days-in-agenda="5"></e-agenda-view-settings>
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}

N> In Agenda view, the templates can be applied for the date and time columns. Also, the template passed through the `appointment-template-id` will gets applied to the event column in Agenda view.

## Restriction on View Navigation

It is possible to restrict the users to display only the specific list of views in the Schedule header section and also not to navigate to other views that are not listed. 

**For example**, if the views property is set only with `Month` view – then the Schedule header section displays only the Month option in the view toolbar and also other additional available actions like navigating to day/week view on clicking the month header dates and week date-range is stopped.

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });
}

@{List<string> views = new List<string>() { "Month" };}
<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 8)" views="views" current-view="Month">
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}

N> Even though Week view is the active view in Scheduler by default, if it is not listed in the views collection – then the first listed option in the views collection will be taken as current view of the Scheduler.

## Timeline View

Timeline view displays the day, time and its associated events horizontally arranged from left to right. By default, Scheduler renders in vertical mode and it can be changed to the timeline mode using `orientation` property which accepts both the `string` and `Orientation` enum value.

All the applicable features in Vertical mode works similar with Timeline mode (Horizontal) and only the visualization of the layout changes based on the orientation.

{% highlight razor %}

@using MyProject.Models; // Here MyProject defines your project name to access the model class
@{
    <!-- Datasource for Appointments -->
    List<ScheduleFields> Appoint = new List<ScheduleFields>();
    Appoint.Add(new ScheduleFields { Id = "1", Subject = "Meeting", StartTime = new DateTime(2015, 11, 10, 10, 00, 00), EndTime = new DateTime(2015, 11, 10, 11, 00, 00), Description = "", AllDay = false, Recurrence = false, RecurrenceRule = "" });
}

<ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2015, 11, 8)" orientation="Horizontal">
    <e-appointment-settings datasource="Appoint" id="Id" subject='"Subject"' start-time='"StartTime"' end-time='"EndTime"' description='"Description"' all-day='"AllDay"' recurrence='"Recurrence"' recurrence-rule='"RecurrenceRule"'>
    </e-appointment-settings>
</ej-schedule>

{% endhighlight %}
