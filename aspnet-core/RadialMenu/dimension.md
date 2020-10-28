---
layout: post
title: Syncfusion Radial Menu Dimension
description: dimension
platform: aspnet-core
control: RadialMenu 
documentation: ug
---

## Dimension

You can customize **Radial Menu** dimension by using **radius** and **position** properties.

### Radius

You can customize the **Radial Menu** size by using the **radius** property. By default, the **Radial Menu** Radius is set as 150px. Refer to the following code example.

{% highlight cshtml %}

    <ej-radial-menu id="defaultRadialMenu" image-class="imageclass" auto-open="true" radius="150">
            <e-radial-menu-items >
                   <e-radial-menu-item image-url="http://mvc.syncfusion.com/demos/web/Images/RadialMenu/font.png" text ="Bold" enabled="true">
                    </e-radial-menu-item>
                <e-radial-menu-item image-url="http://mvc.syncfusion.com/demos/web/Images/RadialMenu/f1.png" text="Italic" >
                   </e-radial-menu-item>
                <e-radial-menu-item image-url="http://mvc.syncfusion.com/demos/web/Images/RadialMenu/redo.png" text="Redo">
                   </e-radial-menu-item>
                <e-radial-menu-item image-url="http://mvc.syncfusion.com/demos/web/Images/RadialMenu/undo.png" text="Undo" >
                </e-radial-menu-item>
            </e-radial-menu-items>
        </ej-radial-menu>

{% endhighlight %}

Add the following script in your code.

{% highlight javascript %}

    <script type="text/javascript">
        var rteObj, radialElement = $('#defaultRadialMenu');
        $(function () {
            if (!(ej.browserInfo().name == "msie" && ej.browserInfo().version < 9)) {
                $("#radialtarget1").parent().css("position", "relative");
            }
            else {
                $("#contentDiv").html("Radial Menu is only supported from Internet Explorer Versioned 9 and above.").css({ "font-size": "20px", "color": "red" });
            }
            $(window).resize(function () {
                if (ej.isMobile() && ej.isPortrait())
                    $('#defaultRadialMenu').css({ "left": 25 })
            });
        });
        function rteCreate(e) {
            rteObj = this;
        }
        function radialShow(e) {
            var target = $("#radialtarget1"), radialRadius = 150, radialDiameter = 2 * radialRadius,
            // To get Iframe positions
                iframeY = e.event.clientY, iframeX = e.event.clientX,
            // To set Radial Menu position within target
                x = iframeX > target.width() - radialRadius ? target.width() - radialDiameter : (iframeX > radialRadius ? iframeX - radialRadius : 0),
                y = iframeY > target.height() - radialRadius ? target.height() - radialDiameter : (iframeY > radialRadius ? iframeY - radialRadius : 0);
            radialElement.ejRadialMenu("setPosition", x, y);
            $('iframe').contents().find('body').blur();
        }
        </script>

{% endhighlight %}

Add the following code in your style section,

{% highlight css %}

    <style type="text/css" class="cssStyles">
        .e-radialmenu .imageclass {
            background-image: url("http://mvc.syncfusion.com/demos/web/Images/RadialMenu/settings.png");
        }
    </style>

{% endhighlight %}

The following screenshot illustrates the **Radial Menu** while clicking on the settings icon.

![Radius](dimension-images/img1.png)

### Position 

To display the **Radial Menu** in the web page in a specific area, we can use the **position** property. By default, the **Radial Menu** Position is set as null. 

Refer to the following code example.

{% highlight cshtml %}

    <ej-radial-menu id="defaultRadialMenu" image-class="imageclass" auto-open="true">
            <e-radial-menu-items >
                   <e-radial-menu-item image-url="http://mvc.syncfusion.com/demos/web/Images/RadialMenu/font.png" text ="Bold" enabled="true">
                    </e-radial-menu-item>
                <e-radial-menu-item image-url="http://mvc.syncfusion.com/demos/web/Images/RadialMenu/f1.png" text="Italic">
                   </e-radial-menu-item>
                <e-radial-menu-item image-url="http://mvc.syncfusion.com/demos/web/Images/RadialMenu/redo.png" text="Redo" >
                   </e-radial-menu-item>
                <e-radial-menu-item image-url="http://mvc.syncfusion.com/demos/web/Images/RadialMenu/undo.png" text="Undo" >
                </e-radial-menu-item>
            </e-radial-menu-items>
        </ej-radial-menu>

{% endhighlight %}

Add the following script in your code.

{% highlight javascript %}

    <script type="text/javascript">
        var rteObj, radialElement = $('#defaultRadialMenu');
        $(function () {
            if (!(ej.browserInfo().name == "msie" && ej.browserInfo().version < 9)) {
                $("#radialtarget1").parent().css("position", "relative");
            }
            else {
                $("#contentDiv").html("Radial Menu is only supported from Internet Explorer Versioned 9 and above.").css({ "font-size": "20px", "color": "red" });
            }
            $(window).resize(function () {
                if (ej.isMobile() && ej.isPortrait())
                    $('#defaultRadialMenu').css({ "left": 25 })
            });
        });
        function rteCreate(e) {
            rteObj = this;
        }
        function radialShow(e) {
            var target = $("#radialtarget1"), radialRadius = 150, radialDiameter = 2 * radialRadius,
            // To get Iframe positions
                iframeY = e.event.clientY, iframeX = e.event.clientX,
            // To set Radial Menu position within target
                x = iframeX > target.width() - radialRadius ? target.width() - radialDiameter : (iframeX > radialRadius ? iframeX - radialRadius : 0),
                y = iframeY > target.height() - radialRadius ? target.height() - radialDiameter : (iframeY > radialRadius ? iframeY - radialRadius : 0);
            radialElement.ejRadialMenu("setPosition", x, y);
            $('iframe').contents().find('body').blur();
        }
        </script>

{% endhighlight %}

Add the following code in your style section,

{% highlight css %}

    <style type="text/css" class="cssStyles">
        .e-radialmenu .imageclass {
            background-image: url("http://mvc.syncfusion.com/demos/web/Images/RadialMenu/settings.png");
        }
    </style>

{% endhighlight %}

The following screenshot illustrates the output while selecting the text in the page.

![Position](dimension-images\img2.png)