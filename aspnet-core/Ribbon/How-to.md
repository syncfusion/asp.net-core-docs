---
layout: post
title:  Get-Ribbon-object
description: get ribbon object
documentation: ug
platform: aspnet-core
keywords: get ribbon object,ribbon get ribbon object
---

# How to

## Get Ribbon object

After Ribbon initialization, Ribbon object is stored in a container element of Ribbon and it can be accessed for further processing. 

{% highlight js %}

    // "defaultRibbon" is Id of Ribbon control
     var ribbonObject = $("#defaultRibbon").ejRibbon("instance");

       [or]

     var ribbonObject = $("#defaultRibbon").data("ejRibbon");

{% endhighlight %}



