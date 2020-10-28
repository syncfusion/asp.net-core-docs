---
layout: post
title: Scroller Styles | Scroller | ASP.NET Core | Syncfusion
description: scroller styles
platform: aspnet-core
control: Scroller
documentation: ug
---

# Scroller Styles

The Essential ASP.NET Core Scroller control allows you to customize the look and function of scrollbars. You can vary it significantly by setting the scrollbar button size, scrollbar position, height and width of the Scroller control. This section describes you the custom styles to be used when creating Scroller.

### Button Size

In Scroller control, it allows you to customize the scroll arrows width and height. In horizontal scroller the ButtonSize customizes the top and down arrow and in vertical scroller the button-size customizes the left and right arrow.

### Scroller Size

The scroller-size property is used to customize the scrollbar width and height. It is applicable for both horizontal and vertical scroller.

### Scroll Top

The scroll-top property is used to move the Scroller content and scrollbars in top position with the specified value. It is used for only vertical scroller.

### Scroll Left

The scroll-left property is used to move the Scroller content and scrollbars in left position with the specified value. It is used for only horizontal scroller.

### Height

The height property is used to set the height for Scroller outer wrapper.

### Width

The width property is used to set the Width for Scroller outer wrapper.

In the View page, add the Scroller helper to configure Scroller widget.

{% highlight CSHTML %}

// In the CSHTML page, add a <div> element to configure Scroller widget and initialize the control.

 <ej-Scroller id="scrollcontent" height="170" width="350" scroll-top="20" scroll-left="20" button-size="20">
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

    #innercontent {
        width: 400px;
        padding: 15px;
    }



    #scrollcontent {
        border: 1px solid grey;
    }

</style>
   
{% endhighlight %}

The following screenshot displays the Scroller control with basic styles

![](Scroller-Styles_images/Scroller-Styles_img1.png)

Scroller control rendered with basic styles
{:.caption}