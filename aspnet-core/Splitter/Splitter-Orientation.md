---
layout: post
title: Splitter Orientation | Splitter | ASP.NET Core | Syncfusion
description: splitter orientation
platform: aspnet-core
control: Splitter
documentation: ug
keywords: orientation
---

# Splitter Orientation

The Splitter supports both vertical and horizontal orientation of the pane. You can declare the orientation by Vertical  and Horizontal.

## Configure Splitter Orientation

 The following steps explain the implementation of Splitter orientation option.

1. In the View page, add the Splitter helper and configure the ‘orientation’ property as shown below.


{% highlight CSHTML %}

<ej-splitter id="outterSplitter" orientation="Vertical" height="250" width="485">
    <e-split-panes>
        <e-split-pane collapsible="true">
            <e-content-template>
               
                <div>

                    <div style="padding: 0px 15px;">

                        <h3 class="h3">Tools </h3>

                        Essential Tools is a collection of user interface components used to create interactive ASP.NET MVC applications.

                    </div>

                </div>
            </e-content-template>
        </e-split-pane>
        <e-split-pane collapsible="true">
            <e-content-Template>
                <div>

                    <div style="padding: 0px 15px;">

                        <h3 class="h3">Grid </h3>

                        Essential MVC Grid offers full featured a Grid control with extensive support for Grouping and the display of hierarchical data.

                    </div>

                </div>
            </e-content-Template>
        </e-split-pane>
    </e-split-panes>
</ej-splitter>


{% endhighlight %}

The output for Splitter with Vertical

![](Splitter-Orientation_images/Splitter-Orientation_img1.png)



The output for Splitter with Horizontal.



![](Splitter-Orientation_images/Splitter-Orientation_img2.png)



