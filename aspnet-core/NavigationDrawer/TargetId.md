---
layout: post
title: TargetId | NavigationDrawer | ASP.NET Core | Syncfusion
description: targetid
platform: aspnet-core
control: NavigationDrawer
documentation: ug
---

# TargetId

This property is used to define the target Id for Navigation Drawer. The drawer opens while you click on the specified target element.



{% highlight CSHTML %}



<div class="row">
    <div class="cols-sample-area" style="padding: 0px; position: relative; margin: 0px; min-height: 451px;">
        <div>
            <div>
                <div id="container">
             
                    <ej-navigation-drawer id="navpane" direction="Left" type="Overlay" position="Fixed" enable-list-view="true" target-id="butdrawer">
                        <e-list-view-settings width="300" />
                        <e-content-template>
                            <ul>
                                <li data-ej-text="Home"></li>
                                <li data-ej-text="Profile"></li>
                                <li data-ej-text="Photos"></li>
                                <li data-ej-text="Location"></li>
                            </ul>
                        </e-content-template>
                    </ej-navigation-drawer>
                </div>
            </div>
        </div>
    </div>
</div>
<ej-button id="butdrawer" text="Open drawer" />
<style>
    #butdrawer{
        margin-top:20px;
        margin-left:200px;
 
    }
</style>


{% endhighlight %}



The following screenshots illustrates the output.

![](TargetId_images/TargetId_img1.png)





![](TargetId_images/TargetId_img2.png)



