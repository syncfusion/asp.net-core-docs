---
layout: post
title: Appearance and Styling
description: appearance and styling
platform: aspnet-core
control: RadialMenu 
documentation: ug
---

# Appearance and Styling

You can customize RadialMenu control style and the appearance by using available themes or **css-class** property.

## Theme

In order to apply styles to the RadialMenu control, refer these 2 files namely, ej.widgets.core.min.css and ej.theme.min.css. When you refer ej.web.all.min.css file, it is not necessary to include the files ej.widgets.core.min.css and ej.theme.min.css in your project, as ej.web.all.min.css is the combination of these two.

By default, the following themes support available for RadialMenu component, namely:

* flat-azure
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
* bootstrap
* material
* office-365
* high-contrast 01
* high-contrast 02

## CSS Class

RadialMenu component's appearance can only be customized using its CSS classes. Define CSS class, as per requirement and assign the class name to **css-class** property.

### Configure RadialMenu using CSS class

Define CSS class to customize the RadialMenu control.

{% highlight css %}

    <style type="text/css">

        /* Customize the radialmenu */

       .e-radialmenu .e-default, .e-radialmenu .e-outerdefault.customCss 

       {

         fill:#f00;
       } 

    </style>

{% endhighlight %}

Add the following code in your view page To render RadialMenu component as like in the below screenshot,

{% highlight cshtml %}

    <ej-radial-menu id="nestedradialmenu" image-class="imageclass"  auto-open="false" css-class="customCss">
            <e-radial-menu-items>
                <e-radial-menu-item image-url="http://mvc.syncfusion.com/demos/web/Images/RadialMenu/copy.png" text="Copy" click="copy" enabled="true">
                </e-radial-menu-item>
                <e-radial-menu-item image-url="http://mvc.syncfusion.com/demos/web/Images/RadialMenu/fontsize.png" text="Font" click="font" badge="@val" enabled="true" type="Slider" slider-settings="@stroke">
                </e-radial-menu-item>
                <e-radial-menu-item image-url="http://mvc.syncfusion.com/demos/web/Images/RadialMenu/font.png" text="Bold" click="bold">
                    <e-radial-menu-child-items>
                        <e-radial-menu-child-item image-url="http://mvc.syncfusion.com/demos/web/Images/RadialMenu/f1.png" text="Italic" click="italic"></e-radial-menu-child-item>
                        <e-radial-menu-child-item image-url="http://mvc.syncfusion.com/demos/web/Images/RadialMenu/font.png" text="Bold" click="bold"></e-radial-menu-child-item>
                    </e-radial-menu-child-items>
                </e-radial-menu-item>
                <e-radial-menu-item image-url="http://mvc.syncfusion.com/demos/web/Images/RadialMenu/list.png" text="List" click="unorderedList">
                    <e-radial-menu-child-items>
                        <e-radial-menu-child-item image-url="http://mvc.syncfusion.com/demos/web/Images/RadialMenu/list.png" text="Bullets" click="unorderedList"></e-radial-menu-child-item>
                        <e-radial-menu-child-item image-url="http://mvc.syncfusion.com/demos/web/Images/RadialMenu/l5.png" text="Numbering" click="orderedList"></e-radial-menu-child-item>
                    </e-radial-menu-child-items>
                </e-radial-menu-item>
                <e-radial-menu-item image-url="http://mvc.syncfusion.com/demos/web/Images/RadialMenu/paste.png" text="Paste" click="paste">
                </e-radial-menu-item>
                <e-radial-menu-item image-url="http://mvc.syncfusion.com/demos/web/Images/RadialMenu/undo.png" text="Undo" click="undo">
                    <e-radial-menu-child-items>
                        <e-radial-menu-child-item image-url="http://mvc.syncfusion.com/demos/web/Images/RadialMenu/undo.png" text="Undo" click="undo"></e-radial-menu-child-item>
                        <e-radial-menu-child-item image-url="http://mvc.syncfusion.com/demos/web/Images/RadialMenu/redo.png" text="Redo" click="redo" enabled="false"></e-radial-menu-child-item>
                    </e-radial-menu-child-items>
                </e-radial-menu-item>
                <e-radial-menu-item image-url="http://mvc.syncfusion.com/demos/web/Images/RadialMenu/align.png" text="Alignment" click="center">
                    <e-radial-menu-child-items>
                        <e-radial-menu-child-item image-url="http://mvc.syncfusion.com/demos/web/Images/RadialMenu/a1.png" text="Left" click="left"></e-radial-menu-child-item>
                        <e-radial-menu-child-item image-url="http://mvc.syncfusion.com/demos/web/Images/RadialMenu/a2.png" text="Right" click="right" enabled="false"></e-radial-menu-child-item>
                    </e-radial-menu-child-items>
                </e-radial-menu-item>
            </e-radial-menu-items>
        </ej-radial-menu>

{% endhighlight %}

Add the following code in your Script section,

{% highlight javascript %}

    <script type="text/javascript">
        var rteObj, rteEle = $("#rteSample2"), radialEle = $('#nestedradialmenu');
        $(function () {
            if (!(ej.browserInfo().name == "msie" && ej.browserInfo().version < 9)) {
                $("#radialtarget2").parent().css("position", "relative");
            }
            else {
                $("#contentDiv").html("Radial Menu is only supported from Internet Explorer Versioned 9 and above.").css({ "font-size": "20px", "color": "red" });
            }
            $(window).resize(function(){
                if(ej.isMobile() && ej.isPortrait())
                    $('#nestedradialmenu').css({ "left": 25 })
            });
        });
        function rteCreate(e) {
            rteObj = this;
        }
        function radialShow(e) {
            var target = $("#radialtarget2"), radialRadius = 150, radialDiameter = 2 * radialRadius,
            // To get Iframe positions
                iframeY = e.event.clientY, iframeX = e.event.clientX,
            // To set Radial Menu position within target
                x = iframeX > target.width() - radialRadius ? target.width() - radialDiameter : (iframeX > radialRadius ? iframeX - radialRadius : 0),
                y = iframeY > target.height() - radialRadius ? target.height() - radialDiameter : (iframeY > radialRadius ? iframeY - radialRadius : 0);
            radialEle.ejRadialMenu("setPosition", x, y);
            $('iframe').contents().find('body').blur();
        }
        function rteChange(e) {
            radialEle.ejRadialMenu("enableItem", "Undo");
        }
     </script>

{% endhighlight %}

Output of RadialMenu configured based on CSS class is as follow,

![](apperance-and-styling-images\img1.png)