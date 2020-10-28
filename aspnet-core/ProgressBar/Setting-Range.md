---
layout: post
title: Setting Range | Progress Bar | ASP.NET Core | Syncfusion
description: setting range
platform: aspnet-core
control: Progress Bar
documentation: ug
---

## Setting Range

The range of the ProgressBar is set by using minimum and maximum values. The Minimum value specifies the value where the ProgressBar shows the process to have started. The Maximum value specifies the value where the process is completed. You can set the range by using the ‘MinValue’ and ‘MaxValue’ property.

1. In the VIEW page, add the below code to render the ProgressBar widget.

{% highlight CSHTML  %}

// Add the following code example to the corresponding CSHTML page to render the ProgressBar control with customized range.

<ej-progress-bar id="progressBar" min-value="40" max-value="80" value="80" text="100%" height="20" width="500"/>

{% endhighlight %}

 The following screenshot displays the output.

![](Setting-Range_images/Setting-Range_img1.png)