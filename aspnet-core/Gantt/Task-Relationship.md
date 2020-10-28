---
layout: post
title: Task-Relationship
description: task relationship
platform: aspnet-core
control: Gantt
documentation: ug
---

# Task Relationship

You can show the relationship between two tasks in Gantt control. These relationships are categorized into four types based on the start and finish date of the task.

## Start to Start(SS)

You cannot start a task until the other task also starts.

![](Task-Relationship_images/Task-Relationship_img1.png)

## Start to Finish(SF)

You cannot finish a task until the other task is started.

![](Task-Relationship_images/Task-Relationship_img2.png)

## Finish to Start(FS)

You cannot start a task until the other task is completed.

![](Task-Relationship_images/Task-Relationship_img3.png)

## Finish to Finish(FF)

You cannot finish a task until the other task is completed.

![](Task-Relationship_images/Task-Relationship_img4.png)

The following code example shows you how to show the predecessor in the Gantt control.

{% highlight cshtml %}

<ej-gantt id="ganttSample" datasource="ViewBag.datasource"
    //...
    predecessor-mapping="Predecessor">
</ejGantt>
    
{% endhighlight %}

The following screenshot displays the output of the above code. 

![](Task-Relationship_images/Task-Relationship_img5.png)

