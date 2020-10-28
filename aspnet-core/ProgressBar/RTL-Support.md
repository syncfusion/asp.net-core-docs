---
layout: post
title: RTL Support | Progress Bar | ASP.NET Core | Syncfusion
description: rtl support
platform: aspnet-core
control: Progress Bar
documentation: ug
---

## RTL Support

Right-to-left starts from the right of the page and continues to the left. By default, this option is set to ‘false’ in the ProgressBar control. The EnableRTL option allows the ProgressBar control to display it in the right to left direction.

The following steps explain how to enable the RTL property of the ProgressBar control.

1. In the VIEW page, add the below code to render the ProgressBar widget.

{% highlight CSHTML %}

// Add the following code example to the corresponding CSHTML page to render ProgressBar control to display it in the right-to-left direction.

<ej-progress-bar id="progressBar" value="70" text="70%" enable-rtl="true" height="20" width="500"/>

{% endhighlight %}

 The following screenshot displays the output.

![](RTL-Support_images/RTL-Support_img1.png)