---
layout: post
title: Task-scheduling-modes
description: Task scheduling modes
platform: aspnet-core
control: Gantt
documentation: ug
---

# Task Scheduling Modes

Gantt provides support for automatic and manual task scheduling modes. Scheduling mode of a task is used to indicate whether the start and end dates of a task will be automatically validated or not. Using the property `task-scheduling-mode` we can able to change the scheduling mode of a task. The following are the enumeration values that can be set to the property `task-scheduling-mode`

* Auto
* Manual
* Custom

## **Automatically** **Scheduled** **tasks**

When the `task-scheduling-mode` property is set as `Auto` scheduling mode, all the tasks in the project will be rendered as automatically scheduled tasks. Thus the start and end dates of the tasks in the project will be automatically validated. The tasks will be automatically scheduled based on the factors such as dependencies between the tasks, non-working days like holidays and weekends. Tasks automatically recalculate the scheduling date when its predecessor task has been affected. But still we can schedule the tasks and reset the start and end dates by manual editing. Summary tasks will also be automatically scheduled, but its start date, end date and duration values cannot be edited manually. 

{% highlight cshtml %}

<ej-gantt id="ganttSample" datasource="ViewBag.datasource"
    //...
    task-scheduling-mode="Auto">
</ejGantt>

{% endhighlight %}

N> Automatic scheduling mode is the default task scheduling mode in Gantt.

## **Manually** **Scheduled** **tasks**

When the `task-scheduling-mode` property is set as `Manual` scheduling mode, all the tasks in the project will be rendered as manually scheduled tasks. Thus the dates of the tasks will not get validated automatically by the system. The tasks will not get rescheduled and dates will not be recalculated automatically based on the factors such as task dependencies and non-working days and hence manual scheduled tasks will lie on weekends and holidays. We can restrict this mode in predecessor editing alone, that is we can make to automatically validate the dates of the manual tasks on predecessor editing by enabling the property `validate-manual-tasks-on-linking`. By enabling this property, the dates of the manual tasks will recalculate automatically, when its predecessor tasks' dates have been changed.

{% highlight cshtml %}

<ej-gantt id="ganttSample" datasource="ViewBag.datasource"
    //...
    task-scheduling-mode="Manual"
    validate-manual-tasks-on-linking="true">
</ejGantt>

{% endhighlight %}

## **Custom**

When the `task-scheduling-mode` property is set as `Custom`, the scheduling mode for each tasks will be mapped form the data source field. The property `task-scheduling-mode-mapping` is used to map the scheduling mode field from the data source.

{% highlight c# %}

List<DefaultData> list = new List<DefaultData>();
list.Add(new DefaultData()
    {
        Id = 1,
        Name = "Parent Task 1",
        StartDate = "02/23/2014",
        Duration = 5,
        PercentDone = 40,
        IsManual=true
            Children = (new List<DefaultData>()
                { new DefaultData()
                    {
                        Id = 2,
                        Name = "Child Task 1",
                        StartDate = "02/23/2014",
                        Duration = 5,
                        PercentDone = 40
                    },
                    new DefaultData()
                        {
                            Id = 3,
                            Name = "Child Task 2",
                            StartDate = "02/23/2014",
                            Duration = 5,
                            PercentDone = 40,
                            IsManual=true
                            Predescessor = "2"
                        },
     //...
{% endhighlight %}

{% highlight cshtml %}

<ej-gantt id="ganttSample" datasource="ViewBag.datasource"
    //...
    task-scheduling-mode="Custom"
    task-scheduling-mode-mapping="IsManual">
</ejGantt>

{% endhighlight %}

The following screen shot depicts a project with custom scheduling mode, where both automatic and manual scheduling modes are mapped to the tasks.

![](Task-Scheduling-modes_images/Task-Scheduling-modes_img1.png)