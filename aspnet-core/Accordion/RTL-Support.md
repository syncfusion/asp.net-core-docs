---
layout: post
title: RTL Support | Accordion  | ASP.NET Core | Syncfusion
description: rtl support
platform: aspnet-core
control: Accordion 
documentation: ug
---

# RTL Support

This feature supports to change the left-to-right alignment of the Accordion control to right-to-left (RTL). 

{% highlight CSHTML %}

// In the View page, configure Accordion with corresponding data and set EnableRTL property value as true.

<div style="width: 400px; float:left;">
<ej-accordion id="basicAccordion" enable-rtl="true">
    <e-accordion-items>
        <e-accordion-item text="ASP.NET">
            <e-content-template>
                <div>
                    Essential Chart for ASP.NET MVC is a visually stunning, high-performance charting component that is easy to use.
                    It includes 35 chart types ranging from simple column charts to specialized financial charts.
                    The charts are highly customizable and have a powerful data model that makes data binding simple.
                </div>
            </e-content-template>
        </e-accordion-item>
        <e-accordion-item text="ASP.NET MVC">
            <e-content-template>
                <div>
                    The Model-View-Controller (MVC) architectural pattern separates an application into three main components:
                    the model, the view, and the controller. The ASP.NET MVC framework provides an alternative to the ASP.NET Web Forms pattern for creating Web applications. The ASP.NET MVC framework is a lightweight, highly testable presentation framework that (as with Web Forms-based applications) is integrated with existing ASP.NET features, such as master pages and membership-based authentication.
                </div>
            </e-content-template>
        </e-accordion-item>
        <e-accordion-item text="Javascript">
            <e-content-template>
                <div>
                    JavaScript (JS) is an interpreted computer programming language.
                    It was originally implemented as part of web browsers so that client-side scripts could interact with the user, control the browser,
                    communicate asynchronously, and alter the document content that was displayed. More recently, however,
                    it has become common in both game development and the creation of desktop applications.
                </div>
            </e-content-template>
        </e-accordion-item>
    </e-accordion-items>
</ej-accordion>
</div> 

{% endhighlight %}

Output for accordion when “EnableRTL” is set to “true” is as follows,

![](Enabling-RTL-Support_images/Enabling-RTL-Support_img1.png)