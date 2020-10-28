---
layout: post
title: Syncfusion Radial Menu Image-Customization
description: image-customization
platform: aspnet-core
control: RadialMenu 
documentation: ug
---

## Image Customization

You can customize the **Radial Menu’s** center and back images by using the **image-class** and **back-image-class** properties. Every menu item can be added with image using **image-url** property. By using this **image-class** attribute, you can customize the **Radial Menu** center image. 

Sub-Items are also supported in the **Radial Menu**. To navigate Sub-Items, click the arrows in the outer ring and it displays the corresponding sub-items group. Clicking the center button when a sub-items group is shown, displays the items on the previous level. Nested **Radial Menu** has the second level back button. In this case, you can use the **back-image-class** attribute to change your second level back button. **back-image-class** is used to customize the **nestedRadialMenu** back image. Refer to the following code example.

You can add the page content with text-area by referring to this section.

{% highlight cshtml %}

    @{
    Syncfusion.JavaScript.Models.RadialBadge val = new RadialBadge();
    val.Enabled = true;
    val.Value = 2;
    Syncfusion.JavaScript.Models.RadialMenuSlider stroke = new RadialMenuSlider();
    stroke.StrokeWidth = 1;
    stroke.Ticks=new List<double> { 0, 2, 4, 6, 8, 10, 12, 14 };
    }
     <ej-radial-menu id="nestedRadialMenu" image-class="imageClass" auto-open="false">
            <e-radial-menu-items>
                <e-radial-menu-item image-url="http://mvc.syncfusion.com/demos/web/Images/RadialMenu/copy.png" text="Copy" click="copy" enabled="true">
                </e-radial-menu-item>
                <e-radial-menu-item image-url="http://mvc.syncfusion.com/demos/web/Images/RadialMenu/fontsize.png" text="Font" click="font" badge="@val" enabled="true" type="Slider" slider-settings="@stroke" >
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

Add the following code in your script section,

{% highlight javascript %}

    <script type="text/javascript">
        var rteObj, rteElement = $("#rteSample2"), radialElement = $('#nestedRadialMenu');
        $(function () {
            if (!(ej.browserInfo().name == "msie" && ej.browserInfo().version < 9)) {
                $("#radialtarget2").parent().css("position", "relative");
            }
            else {
                $("#contentDiv").html("Radial Menu is only supported from Internet Explorer Versioned 9 and above.").css({ "font-size": "20px", "color": "red" });
            }
            $(window).resize(function(){
                if(ej.isMobile() && ej.isPortrait())
                    $('#nestedRadialMenu').css({ "left": 25 })
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
            radialElement.ejRadialMenu("setPosition", x, y);
            $('iframe').contents().find('body').blur();
        }
        function rteChange(e) {
            radialElement.ejRadialMenu("enableItem", "Undo");
        }

{% endhighlight %}

Add this into style section,

{% highlight css %}

    <style type="text/css" class="cssStyles">
        .e-radialmenu .imageClass
        {
            background-image: url("mvc.syncfusion.com/demos/web/Images/RadialMenu/main.png");
        }
        
        .e-radialmenu .backImageClass
        {
            background-image: url("mvc.syncfusion.com/demos/web/Images/RadialMenu/Back_button.png");
        }
    </style>


{% endhighlight %}

The following screenshot illustrates the output.

![Image Customization](image-customization_images\img1.png)

Radial Menu - Image Customization – Main menu
{:.caption}

When you click the arrow, it navigates to the child item as illustrated in the following screenshot.

![Image Customization](image-customization_images\img2.png)

Radial Menu- Image Customization – Child menu 
{:.caption}