---
layout: post
title: Work-field
description: work field
platform: aspnet-core
control: Gantt
documentation: ug
---

# Work

Work is the total labor hours necessary to complete a task, and its value depends on the number of resources assigned to the task and the duration of the task. Work can be measured in hours, days and minutes, and it is measured in ‘hours’ scale by default and this can be changed by using the `work-unit` property.

The below code snippet explains how to change `work-unit` property in Gantt.

{% highlight cshtml %}
    <ej-gantt id="ganttSample" datasource="ViewBag.datasource"
        //...
        work-unit="Minute">
    </ejGantt>
{% endhighlight %}

Note: 

* Work will be displayed as __0__ __hours__ if there is no resource assigned to the task.
* A resource will work __8__ __hours__ a day on the task assigned.

# Task type 

The work, duration and resource unit fields of a task depends upon each other values and will change automatically on editing any one of these fields. But we can also set these field’s values as constant using the taskType property. The following values can be set to the type property,

**Fixed Duration** - Duration task field will remain constant while updating resource unit or work field.

**Fixed Work**      - Work field will remain constant while updating resource unit or duration fields.

**Fixed Unit**         - Resource units will remain constant while updating duration or work field.

The following code snippet explains how to set `task-type` property in Gantt,

{% highlight cshtml %}
    <ej-gantt id="ganttSample" datasource="ViewBag.datasource"
        //...
        task-type="FixedWork">
    </ejGantt>
{% endhighlight %}

Following table explains how the work, duration and resource unit fields will gets updated on changing any of the fields

<table>
<tr>
<td>
Task Type</td><td>
Changes in Duration</td><td>
Changes in Work</td><td>
Changes in Resource units</td></tr>
<tr>
<td>
Fixed Duration</td><td>
Work field updates</td><td>
Resource unit updates</td><td>
Work field updates</td></tr>
<tr>
<td>
Fixed Work</td><td>
Resource unit updatesNote: For manually scheduled task work will update</td><td>
Duration field updatesNote: For manually scheduled task resource unit updates</td><td>
Duration will updateNote: For manually scheduled task work field updates</td></tr>
<tr>
<td>
Fixed Unit</td><td>
Work field updates</td><td>
Duration field updatesNote: For manually scheduled task resource unit updates</td><td>
Duration will updateNote: For manually scheduled task work field updates</td></tr>
</table>
Note: 

* __Fixed__ __Unit__ is the default taskType in Gantt.
* The above calculations are not applicable for Milestones.

# Effort driven tasks

The effortDriven field is used to define whether the total labor hours or the work need to split or to be extended among the resources when adding or removing a resource to a task.

Note:

* Effort driven field is effective only on adding or removing a resource in a task 

The below table illustrates the effects of effort driven field with `task-type` property

<table>
<tr>
<td>
Task Type</td><td>
Effort driven tasks</td><td>
Task without effort driven</td></tr>
<tr>
<td>
Fixed Duration</td><td>
Resource unit updates</td><td>
Work field updates</td></tr>
<tr>
<td>
Fixed Work</td><td>
Duration field updatesNote: For Fixed Work effort driven is always true.In this task type the effort driven field is non-editable</td><td>
Not applicable</td></tr>
<tr>
<td>
Fixed Unit</td><td>
Duration field updates</td><td>
Work field updates</td></tr>
</table>
Notes:

* The above calculations will not be considered for Milestones.
* For manually scheduled task effort driven will not be considered while adding or removing resources.
* For manually scheduled task the taskType and effortDriven fields are non-editable.
* When assigning a first resource for the task the effortDriven and taskType fields are not considered, the work field alone will be calculated.

The following screen shot depicts the work, task type and effort driven fields in Gantt.

![](WorkField_images/WorkField_img1.png)

