---
layout: post
title: Animations | NavigationDrawer | ASP.NET Core | Syncfusion
description: animations
platform: aspnet-core
control: NavigationDrawer
documentation: ug
---

# Animations

You can set the transition type of the Navigation Drawer by using type property. The possible transition types are slide and overlay.

* Slide - both navigation panel and content page slides towards left/right direction to view the navigation panel items.
* Overlay - Only the navigation panel slides over the content page to view the navigation panel items. That is, part of the content page is hidden under navigation panel.



N> Transition slide type works only with fixed position.

The default value is Overlay.



{% highlight CSHTML %}


<div class="row">
    <div class="cols-sample-area" style="padding: 0px; position: relative; margin: 0px; min-height: 451px;">
        <div>
            <div>
                <div id="container">
             
                    <ej-navigation-drawer id="navpane" direction="Left" type="Slide" position="Fixed" enable-list-view="true" target-id="butdrawer">
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

<style>
    #butdrawer{
        margin-top:20px;
        margin-left:200px;
 
    }
</style>
  
{% endhighlight %}



The following screenshot illustrates the output.

![](Animations_images/Animations_img2.png)





![](Animations_images/Animations_img3.png)



