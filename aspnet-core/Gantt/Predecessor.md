---
layout: post
title: Predecessor
description: Predecessor
platform: aspnet-core
control: Gantt
documentation: ug
---

# Predecessor

## Predecessor offset with duration units

In Gantt, predecessor offset can be defined with the following duration units, 

* Day
* Hour
* Minute

We can define offset with various offset duration units for predecessors by using below code example

{% highlight c# %}
List<DefaultData> list = new List<DefaultData>();
    list.Add(new DefaultData() {
            //...
            Predecessor = "3FS+2d" 
        },
        new DefaultData(){
            //...
            Predecessor = "3FS+16h"
        },  
        new DefaultData()
        {
            //...
            Predecessor = "3FS+960m"
        },
        //...
{% endhighlight %}

{% highlight cshtml %}

<ej-gantt id="ganttSample" datasource="ViewBag.datasource"
    //...
    predecessor-mapping="Predecessor">
</ejGantt> 

{% endhighlight %}

The following screen shot depicts the duration unit support in the predecessor offset.

![](Predecessor_images/Predecessor_img1.png)


