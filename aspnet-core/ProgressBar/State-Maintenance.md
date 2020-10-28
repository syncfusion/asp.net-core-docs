---
layout: post
title: State Maintenance | Progress Bar | ASP.NET Core | Syncfusion
description: state maintenance
platform: aspnet-core
control: Progress Bar
documentation: ug
---

## State Maintenance

Save current model value to cookies for State Maintenance. While refreshing the ProgressBar widget, page retains the model value applied from browser cookies. By default, the ‘EnablePersistence’ property is set to ‘false’ in the ProgressBar.

The following steps explain the State Maintenance in the ProgressBar control.

1. In the VIEW page, add the below code to render the ProgressBar widget.

{% highlight CSHTML  %}

// Add the following code example to the corresponding CSHTML page to enable the state maintenance in the ProgressBar control.

<ej-progress-bar id="progressBar" value="70" text="70%" enable-persistence="true" height="20" width="500"/>
    
{% endhighlight %}

The following screenshot displays the output.

![](State-Maintenance_images/State-Maintenance_img1.png)