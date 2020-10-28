---
layout: post
title: Duration-Round-Off
description: Rounding off duration
platform: aspnet-core
control: Gantt
documentation: ug
---

## Round-off start date, end date and duration value on taskbar editing
In Gantt start date, end date and duration values can be round-off as per current `schedule-header-type` value on taskbar resizing and dragging actions. This can be achieved by setting `roundOffDuration` argument value as `true` in `taskbar-editing` event.

The below code example explains how to achieve this requirement. 

{% highlight cshtml %}
<ej-gantt id="ganttSample" datasource="ViewBag.datasource" 
        //...
        taskbar-editing="taskbarEditing">
</ejGantt>
{% endhighlight %}

{% highlight javascript %}
	 function taskbarEditing(args) {
		args.roundOffDuration = true;
	}
{% endhighlight %}

![](Duration-Round-Off_images/OnResizing_img1.png)

Before resizing

{:.caption}

![](Duration-Round-Off_images/AfterResizing_img2.png)

After resizing

{:.caption} 