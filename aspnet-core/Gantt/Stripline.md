---
layout: post
title: Stripline
description: stripline
platform: aspnet-core
control: Gantt
documentation: ug
---

# Stripline

Stripline in Gantt control is used to highlight the important event in Gantt chart part. By using this feature, you can add the striplines to highlight important days in your project. The following code example shows you how to add the stripline in Gantt control.

{% highlight cshtml %}

<ej-gantt id="ganttSample" datasource="ViewBag.datasource"
    //...>
    <e-strip-lines>
        <e-gantt-strip-line day="01/02/2014" label="Project Release" line-width=2 line-color="Darkblue" line-style="dotted"></e-gantt-strip-line>
    </e-strip-lines>
</ejGantt>

{% endhighlight %}

The following screenshot shows stripline in Gantt control.

![](Stripline_images/Stripline_img1.png)
