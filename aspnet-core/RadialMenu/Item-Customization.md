---
layout: post
title: Syncfusion Radial Menu Item-Customization
description: item-customization
platform: aspnet-core
control: RadialMenu 
documentation: ug
---

## Item Customization

You can customize individual **Radial Menu** items by using the items properties.

### Adding image and text to RadialMenu items

The **image-url** property specifies the URL of the image for the items. **text** attribute is used to specify the item text. Refer to the following code example.

You can add the page content in RTE control by referring this section.

{% highlight cshtml %}

    <ej-radial-menu id="defaultRadialMenu" image-class="imageclass" auto-open="true">
            <e-radial-menu-items >
                   <e-radial-menu-item image-url="http://mvc.syncfusion.com/demos/web/Images/RadialMenu/copy.png" text ="Copy"  enabled="true">
                    </e-radial-menu-item>
                <e-radial-menu-item image-url="http://mvc.syncfusion.com/demos/web/Images/RadialMenu/paste.png" text="Paste">
                   </e-radial-menu-item>
                <e-radial-menu-item image-url="http://mvc.syncfusion.com/demos/web/Images/RadialMenu/redo.png" text="Redo">
                   </e-radial-menu-item>
                <e-radial-menu-item image-url="http://mvc.syncfusion.com/demos/web/Images/RadialMenu/undo.png" text="Undo">
                </e-radial-menu-item>
            </e-radial-menu-items>
        </ej-radial-menu>

{% endhighlight %}

You can display the **Radial Menu** by performing desired action on the target content while selecting the text inside the target. Therefore, call the **radialShow** method in the select action of the content. Refer the following code example and add it to the script.

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

The following screenshot illustrates the output.

![Adding image and text to RadialMenu items](item-customization_images\img1.png)

### Adding events to Radial Menu items

You can specify the click event to corresponding image/text of **Radial Menu** items for performing some specific action. You need to handle the click event in script manually for each item click.

You can add the page content in RTE control by referring to this section

{% highlight css %}

    <ej-radial-menu id="nestedRadialMenu" image-class="imageclass" auto-open="false">
        <e-radial-menu-items>
            <e-radial-menu-item image-url="http://mvc.syncfusion.com/demos/web/Images/RadialMenu/copy.png" text="Copy" click="copy" enabled="true">
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

Add the following script in your code.

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
             function copy(e) {
               rteObj.executeCommand("copy");
            }
             function paste(e) {
            if (ej.browserInfo().name == 'msie')
                rteObj.executeCommand("paste");
            else
                rteObj._openAlert("Your browser doesn't support direct access to the clipboard. Please use the Ctrl+V keyboard shortcut instead of paste operation.");
             }
             function italic(e) {
              rteObj.executeCommand("italic");
             }
             function bold(e) {
             rteObj.executeCommand("bold");
             }
             function center(e) {
              rteObj.executeCommand("justifyCenter");
                }
             function left(e) {
               rteObj.executeCommand("justifyLeft");
                }
            function right(e) {
             rteObj.executeCommand("justifyRight");
                }
            function undo(e) {
            rteObj.executeCommand("undo");
            radialElement.ejRadialMenu("disableItem", "Undo");
            radialElement.ejRadialMenu("enableItem", "Redo");
             }
             function redo(e) {
             rteObj.executeCommand("redo");
            radialElement.ejRadialMenu("disableItem", "Redo");
            radialElement.ejRadialMenu("enableItem", "Undo");
            }
            function unorderedList(e) {
            rteObj.executeCommand("insertunorderedList");
                 }
             function orderedList(e) {
              rteObj.executeCommand("insertorderedList");
            }
    </script>

{% endhighlight %}

Add the following script in your style section to render back image.

{% highlight javascript %}

    <style type="text/css" class="cssStyles">
         .e-radialmenu .imageclass {
            background-image: url("../Images/RadialMenu/main.png");
        }

        .e-radialmenu .backimageclass {
          background-image: url   ("http://mvc.syncfusion.com/demos/web/Images/RadialMenu/Back_button.png");
            }
    </style>

{% endhighlight %}

The following screenshot illustrates the output.

![Adding events to Radial Menu items](item-customization_images\img2.png)


### Badge Customization in Radial Menu Items

You can specify set badges for the items by using badge settings in radial menu. You can set value for badge and enable badge with default value.

The **Enabled** property to enable or disable badges. **Value** attribute is to set the badge value.

{% highlight cshtml %}

  @{ 
        Syncfusion.JavaScript.Models.RadialBadge val = new RadialBadge();
        val.Enabled = true;
        val.Value = 3;
    }

        <ej-radial-menu id="defaultRadialMenu" image-class="imageclass" auto-open="true">
            <e-radial-menu-items >
                   <e-radial-menu-item image-url="http://mvc.syncfusion.com/demos/web/Images/RadialMenu/copy.png" text ="Copy" badge="@val" enabled="true">
                    </e-radial-menu-item>
                <e-radial-menu-item image-url="http://mvc.syncfusion.com/demos/web/Images/RadialMenu/paste.png" text="Paste">
                   </e-radial-menu-item>
                <e-radial-menu-item image-url="http://mvc.syncfusion.com/demos/web/Images/RadialMenu/redo.png" text="Redo">
                   </e-radial-menu-item>
                <e-radial-menu-item image-url="http://mvc.syncfusion.com/demos/web/Images/RadialMenu/undo.png" text="Undo">
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

The following screenshot illustrates the output.

![Badge Customization in Radial Menu Items](item-customization_images\img3.png)

### Slider Customization in Radial Menu Items

You can customize the Radial Menu with slider settings.The **type** property specifies the type of radial menu item, where you can set the type for RadialMenu item.

You can customize the **Radial Menu** slider settings by using the **Ticks**, **StrokeWidth** and **LabelSpace** properties. The **Ticks** property specifies the slider ticks for radial menu item.**StrokeWidth** attribute is used to specify the slider's stroke width value.**LabelSpace** attribute is used to specify the value of slider label space.

Refer to the following code example.

You can add SliderSettings in radial menu items by referring this section.


{% highlight cshtml %}

    @{
    Syncfusion.JavaScript.Models.RadialBadge val = new RadialBadge();
    val.Enabled = true;
    val.Value = 2;
    Syncfusion.JavaScript.Models.RadialMenuSlider stroke = new RadialMenuSlider();
    stroke.StrokeWidth = 1;
    stroke.Ticks=new List<double> { 0, 2, 4, 6, 8, 10, 12, 14 };
    }
     <ej-radial-menu id="nestedRadialMenu" image-class="imageclass" auto-open="false">
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

Add following Code in your view page to render content section of RTE,

{% highlight cshtml %}

    <div id="radialtarget2" class="content-container-fluid">
            <div class="row">
                <div class="cols-sample-area">
                    <textarea id="rteSample2" rows="10" cols="70" style="height: 440px">
                        <p>
                            Model–view–controller (MVC) is a software architecture pattern which separates the representation of information from the user's interaction with it.
                            The model consists of application data, business rules, logic, and functions. A view can be any output representation of data, such as a chart or a diagram.
                            Multiple views of the same data are possible, such as a bar chart for management and a tabular view for accountants.
                            The controller mediates input, converting it to commands for the model or view.The central ideas behind MVC are code reusable and in addition to dividing the application into three kinds of components, the MVC design defines the interactions between them.
                        </p>

                        <p>A controller can send commands to its associated view to change the view's presentation of the model (e.g., by scrolling through a document). It can also send commands to the model to update the model's state (e.g., editing a document).</p>

                        <p>A model notifies its associated views and controllers when there has been a change in its state. This notification allows the views to produce updated output, and the controllers to change the available set of commands. A passive implementation of MVC omits these notifications, because the application does not require them or the software platform does not support them.</p>

                        <p>A view requests from the model the information that it needs to generate an output representation to the user.</p>
                    </textarea>

                    <ej-rte id="rteSample2" show-context-menu="false" create="rteCreate" change="rteChange" select="radialShow" show-toolbar="false">
                    </ej-rte>
                </div>
            </div>
        </div>

{% endhighlight %}

Add the following to perform actions for the icons are availed in RadialMenu,

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
        function copy(e) {
            rteObj.executeCommand("copy");
        }
        function paste(e) {
            if (ej.browserInfo().name == 'msie')
                rteObj.executeCommand("paste");
            else
                rteObj._openAlert("Your browser doesn't support direct access to the clipboard. Please use the Ctrl+V keyboard shortcut instead of paste operation.");
        }
        function font(e) {
            if (!ej.isNullOrUndefined(e.value))
                var val = e.value.toString();
            else {
                var size = e.text.split('Font');
                var val = size[1];
            }
            rteObj.executeCommand("fontSize", val);
        }
        function italic(e) {
            rteObj.executeCommand("italic");
        }
        function bold(e) {
            rteObj.executeCommand("bold");
        }
        function center(e) {
            rteObj.executeCommand("justifyCenter");
        }
        function left(e) {
            rteObj.executeCommand("justifyLeft");
        }
        function right(e) {
            rteObj.executeCommand("justifyRight");
        }
        function undo(e) {
            rteObj.executeCommand("undo");
            radialElement.ejRadialMenu("disableItem", "Undo");
            radialElement.ejRadialMenu("enableItem", "Redo");
        }
        function redo(e) {
            rteObj.executeCommand("redo");
            radialElement.ejRadialMenu("disableItem", "Redo");
            radialElement.ejRadialMenu("enableItem", "Undo");
        }
        function unorderedList(e) {
            rteObj.executeCommand("insertunorderedList");
        }
        function orderedList(e) {
            rteObj.executeCommand("insertorderedList");
        }
    </script>

{% endhighlight %}

Finally add the following in your styles section,

{% highlight css %}

    <style type="text/css" class="cssStyles">
        .e-radialmenu .imageclass {
            background-image: url("../Images/RadialMenu/main.png");
        }

        .e-radialmenu .backimageclass {
            background-image: url("http://mvc.syncfusion.com/demos/web/Images/RadialMenu/Back_button.png");
        }
    </style>

{% endhighlight %}

The following screenshot illustrates the output.

![Slider Customization in Radial Menu Items](item-customization_images\img4.png)
