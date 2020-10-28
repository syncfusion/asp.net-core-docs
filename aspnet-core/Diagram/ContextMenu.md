---
layout: post
title: Add context menu items to ease the execution of frequently used commands
description: How to execute frequently used commands by using context menu items?
platform: ejmvc
control: Diagram
documentation: ug
---

# Context Menu

In graphical user interface (GUI), a context menu is a type of menu that appears when you perform right-click operation. Nested level of context menu items can be created.
Diagram provides some built-in context menu items and allows to define custom menu items.

## Default Context Menu

The `EnableContextMenu` property helps you to enable/disable the context menu. Diagram provides some default context menu items to ease the execution of some frequently used commands.
The following code illustrates how to enable the default context menu items.

{% highlight c# %}

                //Disables the context menu
                <ej-diagram id="diagram" width="1000px" height="600px" enable-context-menu="false">

{% endhighlight %}

![](ContextMenu_images/Contextmenu_img1.png)

## Customize Context Menu

Apart from the default context menu items, you can define some additional context menu items. Those additional items have to be defined and added to `ContextMenu.Items`. Sub menu items for context menu can set using `ContextMenu.Items.SubItems`
The following code example illustrate how to add custom context menu items.

{% highlight c# %}
                
                    var item = $("#DiagramContent").ejDiagram("instance").model.contextMenu.items;
            var item1 = [];
            for (var i = 0; i < item.length; i++) {
                item1.push($.extend(true, {}, item[i]));
            }

    items = [
                    {
                        name: "zoomType", text: "zoom",
                        subItems: [
                            { name: "zoomin", text: "ZoomIn" },
                            { name: "zoomout", text: "ZoomOut" },
                            
                        ]
                    },
    ]

    $("#DiagramContent").ejDiagram({
                contextMenu: {
                    items: item1,
                },
                        });


{% endhighlight %}

When you want to display only your custom context menu items, you can set true to the `showCustomMenuItemsOnly` property.

Icons of context menu items can be customized by overriding the default context menu item style.
The following code example illustrates how to customize the icon of context menu items.

{% highlight css %}

    #Zoom_image {
        background-image: url("zoom.png");
    }

    #ZoomIn_image {
        background-image: url("zoom-in.png");
    }

    #ZoomOut_image {
        background-image: url("zoom-out.png");
    }

{% endhighlight %}

![](ContextMenu_images/Contextmenu_img2.png)

## Context Menu Events

You would be notified with events when you try to open the context menu items(`contextMenuBeforeOpen`) and when you click the menu items(`contextMenuClick`). The following code example illustrates how to define those events.

{% tabs %}
{% highlight c# %} 

    $("#DiagramContent").ejDiagram({
                contextMenuBeforeOpen: contextMenuBeforeOpening,
                contextMenuClick: contextMenuClicked
            });

	
{% endhighlight %}

{% highlight js %} 

    function contextMenuBeforeOpen(args) {
        //do your custom action here.
    }

    function contextMenuClick(args) {
        switch (args.text) {
            case "zoom":
                //do your custom action here.
            break;
        }
    }
{% endhighlight %}
{% endtabs %}
