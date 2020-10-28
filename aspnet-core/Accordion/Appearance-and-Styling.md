---
layout: post
title: Appearance and Styling | Accordion  | ASP.NET Core | Syncfusion
description: appearance and styling
platform: aspnet-core
control: Accordion 
documentation: ug
---

# Appearance and Styling

## Adjusting Accordion size

You can customize the Accordion panel height using HeightAdjustMode property. It can be set to enum values like content, fill or auto. By default HeightAdjustMode is set to content so the panel height is adjusted to the content size.

### Configure Height of Accordion panel

The following code explains to configure the height of the Accordion content panel.

{% highlight CSHTML %}

// In the View page, configure Accordion with corresponding data and define HeightAdjustMode.

<div style="width:400px">
<ej-accordion id="basicAccordion" height-adjust-mode="Fill">
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

Output for Accordion control when panel height is set to auto so that the maximum content height and Fill for minimum content height in all the panels is as follows.

![](Appearance-and-Styling_images/Appearance-and-Styling_img1.png)


## Rounded corner

You can customize the shape of the Accordion widget from regular rectangular shape to rounded rectangle shape enabling RoundedCorner property that is set to false by default.

### Enabling Rounded corner property

The following code explains you in enabling the ShowRoundedCorner property for an Accordion control.

{% highlight CSHTML %}

// In the View page, configure Accordion with corresponding data and enable the ShowRoundedCorner property for it.

<div style="width: 400px; float:left;">
  <ej-accordion id="basicAccordion" show-rounded-corner="true">
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

Output for accordion widget when “ShowRoundedCorner” is set to “true” is as follows.

![](Appearance-and-Styling_images/Appearance-and-Styling_img2.png)


## Customize Accordion icon

Accordion widget allows you to customize the icons using CustomIcon option that has two properties header and SelectedHeader. By default, the classes of header and selectedHeader are e-collapse and e-expand respectively. By setting the desired CSS class names for these properties as required overrides the default icons with customized icons.

### Configuring custom icon for Accordion

The following code explains you the configuration of icon for an Accordion control.

{% highlight CSHTML %}

// In the View page, configure Accordion with corresponding data and set the “e-arrowheaddown” and “e-arrowheadup” classes to Header and SelectedHeader properties.  “E-arrowheaddown” and “e-arrowheadup” are available in ej.widgets.core.min.css file.

<div style="width: 400px; float:left;">
<ej-accordion id="basicAccordion">
    <e-custom-icon header="e-arrowhead-down" selected-header="e-arrowheadup" />
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

Output for Accordion widget with customized icons is as follows.

![](Appearance-and-Styling_images/Appearance-and-Styling_img3.png)

## Animation Options

### Set animation

By default the Animation for expanding and collapsing is enabled. To remove the Animation you can set the EnableAnimation property to false. This restricts customizing animations as well. By default EnableAnimation is set to true.

Following code disables Animation for Accordion.

{% highlight CSHTML %}

<ej-accordion id="basicAccordion" enable-animation="false">
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

{% endhighlight %}

### Expand and collapse speed

This feature allows you to set the speed for expanding and collapsing the Accordion panels. By default it is set to 300 in milliseconds. By configuring the animation speed you can optimize the delay in loading the panel content.

The following code sample sets value for ExpandSpeed and CollapseSpeed properties,

{% highlight CSHTML %}

// The following code example sets values for ExpandSpeed and CollapseSpeed properties.

<ej-accordion id="basicAccordion" collapse-speed="1000" expand-speed="600">
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

{% endhighlight  %}

## Theme

You can control the style and appearance of Accordion control based on CSS classes. In order to apply styles to the Accordion control, you can refer two files, ej.widgets.core.min.css and ej.theme.min.css. When you refer ej.widgets.all.min.css file, then it is not necessary to include the files ej.widgets.core.min.css and ej.theme.min.css in your project, as ej.widgets.all.min.css is the combination of these two. 

By default, there are 13 themes support available for Accordion control namely

* default-theme
* flat-azure-dark
* fat-lime
* flat-lime-dark
* flat-saffron
* flat-saffron-dark
* gradient-azure
* gradient-azure-dark
* gradient-lime
* gradient-lime-dark
* gradient-saffron
* gradient-saffron-dark
* bootstrap-theme

## CSS class

CSS class can be used to customize the Accordion control appearance. Define a CSS class as you’re your requirement and assign the class name to CssClass property. The custom CSS class must override the predefined CSS styles applied in the Accordion control.

<table>
<tr>
<th>
Class or Element name</th><th>
Description</th></tr>
<tr>
<td>
.e-acrdn</td><td>
Base class that is added to the Accordion wrapper div element where the custom CSS class will also be added</td></tr>
<tr>
<td>
h3</td><td>
Header element for the Accordion panel</td></tr>
<tr>
<td>
span .e-icon</td><td>
Accordion icon in the header that change on expand and collapse panels</td></tr>
<tr>
<td>
.e-content</td><td>
Class for the div element that holds the Accordion panel’s content.</td></tr>
</table>

### Configure Accordion using CSS class

The following code allows you to configure CSS class for an Accordion widget.

{% highlight CSHTML %}

// In the View page, configure Accordion with corresponding data and set the CssClass property with corresponding CSS class name.

<div style="width: 400px; float:left;">

<ej-accordion id="basicAccordion" css-class="customCss">
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

Define CSS class for customizing the Accordion.

{% highlight css %}

<style class="cssStyles">

         .customCss
         {
            font-style: italic;

            text-align:justify;
         }

         .customCss span.e-icon {
            display: none !important;
         }

         .customCss h3
         {
             text-decoration:underline;

             text-align:center;
         }

    </style>

{% endhighlight %}

Output for Accordion with customized CSS property to hide the Accordion icon and format its content is as follows.

![](Appearance-and-Styling_images/Appearance-and-Styling_img4.png)