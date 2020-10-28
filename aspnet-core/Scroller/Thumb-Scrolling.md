---
layout: post
title: Thumb Scrolling | Scroller | ASP.NET Core | Syncfusion
description: thumb scrolling
platform: aspnet-core
control: Scroller
documentation: ug
---

# Thumb Scrolling

Normally the scrollbar position can be changed by dragging the scrollbar handle or clicking the arrows. The Scroller control allows you for panning or dragging the scroll content area to drag by dragging inside the scroll content. To achieve this in your Scroller control, enable the enable-touch-scroll to true. By default the value for enable-touch-scroll is true. When you want to prevent the panning or dragging the scroll content area, set enable-touch-scroll as false.

The following steps explains you the configuration of enable-touch-scroll property in Scroller. 

1. In the View page, add a scroller helper to configure the enable-touch-scroll property.

{% highlight CSHTML %}

	// In the CSHTML page, add a <div> element to configure Scroller widget and initialize the control.

    <ej-Scroller id="scrollcontent" height="170" width="350" enable-touch-scroll="false">
        <e-content-template>
            <div>
                @*Wrapper div for Scroller.*@

                <div id="innercontent">
                    @*Content div*@

                    <h3>MVC </h3>

                    <p>

                        Model–view–controller (MVC) is a software architecture pattern which

                        separates the representation of information from the user's interaction

                        with it. The model consists of application data, business rules, logic, and

                        functions. A view can be any output representation of data, such as a chart

                        or a diagram.

                    </p>

                </div>

            </div>

        </e-content-template>
    </ej-Scroller>

{% endhighlight %}

{% highlight CSS %}

<style type="text/css">
    #scrollcontent {
        border: 1px solid grey;
    }
</style>

{% endhighlight %}
   

	The following screenshot displays Scroller control with disabled touch support.

	![](Thumb-Scrolling_images/Thumb-Scrolling_img1.png)

	Scroller control with disabled touch support
	{:.caption}