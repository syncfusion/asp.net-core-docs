---
layout: post
title: Template Support | Toolbar | ASP.NET Core | Syncfusion
description: template support
platform: aspnet-core
control: Toolbar
documentation: ug
---

# Template Support

Template allows you to insert custom or ASP.NET Core controls inside the toolbar items. Also you can design simple drop down buttons listing the items and radio button inside the Toolbar.

Set the list for DropDown control inside a list element and define this element as a Toolbar item. You can use all simple controls as a ToolBar item. For example to add RadioButton and DropDownList to Toolbar, use the following code example.

{% highlight CSHTML %}

//Add this code in your CSHTML page and refer local data section for data source
<ej-toolbar id="toolbar" width="250px">
<e-toolbar-items>
    <e-toolbar-item>
        <e-content-template>
            <div>
                <ej-radio-button id="Radio1" name="rad1" size="Small" checked="false" enabled="true" />
            </div>
        </e-content-template>
    </e-toolbar-item>
    <e-toolbar-item>
        <e-content-template>
            <div>
                <ej-drop-down-list id="selectCar" height="20px" width="100px" target-id="cars" selected-item-index="0"></ej-drop-down-list>
                <div id="cars">
                    <ul>
                        <li>Audi A4</li>
                        <li>Audi A5</li>
                        <li>Audi A6</li>
                        <li>Audi A7</li>
                    </ul>
                </div>
            </div>
        </e-content-template>
    </e-toolbar-item>
</e-toolbar-items>
</ej-toolbar>

{% endhighlight %}

The following screenshot displays a Toolbar with embedded controls.

![](Template-Support_images/Template-Support_img1.png)

Toolbar with Template
{:.caption}