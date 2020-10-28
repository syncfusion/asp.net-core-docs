---
layout: post
title: Quick Access Toolbar | Ribbon | ASP.NET Core | Syncfusion
description: quick access toolbar
platform: aspnet-core
control: Ribbon
documentation: ug
keywords: quick access toolbar,ribbon quick access toolbar
---

# Quick Access Toolbar

Quick Access Toolbar provides the shortcuts to the most commonly used commands by placing the controls at the Quick Access Toolbar section. It can be placed at the top or bottom of the Ribbon.

Set `ShowQAT` as true to enable Quick Access Toolbar in Ribbon. It supports the Button, Split Button, Toggle Button controls. The `QuickAccessMode` is used to change the controls state in Quick Access Toolbar through options as `Toolbar`,`Menu` and `none`. Default value is `none` and QAT toolbar is created with specified controls added in Toolbar.

The `ToolBar` option used to set controls visibility in Quick Access Toolbar.The `Menu` option shows the controls in Quick Access Menu and does not show controls in Quick Access Toolbar.

Once the controls are visible in Toolbar , then controls state will be set as ticked in Quick Access Menu and vice versa.

The client side event for Quick Access Toolbar menu click is ` QatMenuItemClick`.

`More Commands` command provides with Quick Access Menu. This can be customized using `QatMenuItemClick` event, such as to show popup dialog. 

{% highlight CSHTML %}

   <ej-ribbon id="defaultRibbon" width="500" show-qat="true">
        <e-application-tab type=Menu menu-item-id="ribbonmenu">
            <e-menu-settings open-on-click="false">
            </e-menu-settings>
        </e-application-tab>
        <e-tabs>
            <e-tab id="home" text="HOME">
                <e-groups>
                    <e-group text="SplitButton" align-type=Columns>
                        <e-content>
                            <e-contents>
                                <e-content-groups>
                                    <e-content-group id="paste" text="paste" tool-tip="Pastes" type=Button quick-access-mode=ToolBar>
                                        <e-split-button-settings content-type=ImageOnly target-id="split" prefix-icon="e-icon e-ribbon e-ribbonpaste" button-mode=Dropdown arrow-position=Bottom>
                                        </e-split-button-settings>
                                    </e-content-group>
                                </e-content-groups>
                                <e-defaults type=SplitButton width="50" height="70"></e-defaults>
                            </e-contents>
                        </e-content>
                    </e-group>
                    <e-group text="Button" align-type=Rows>
                    <e-content>
                        <e-contents>
                            <e-content-groups>
                                <e-content-group id="italic" text="italic" tool-tip="Italic" type=Button quick-access-mode=ToolBar>
                                    <e-button-settings content-type=ImageOnly default-text="Italic" active-text="Italic" prefix-icon="e-icon e-ribbon e-ribbonitalic">
                                    </e-button-settings>
                                </e-content-group>
                            </e-content-groups>
                        </e-contents>
                    </e-content>
                    </e-group>
                    <e-group text="Toggle" align-type=Columns>
                        <e-content>
                            <e-contents>
                                <e-content-groups>
                                    <e-content-group id="bold" tool-tip="Bold" type=ToggleButton quick-access-mode=ToolBar>
                                        <e-toggle-button-settings content-type=ImageOnly default-prefix-icon="e-icon e-ribbon bold" active-prefix-icon="e-icon e-ribbon bold" default-text="Bold" active-text="Bold">
                                        </e-toggle-button-settings>
                                    </e-content-group>
                                </e-content-groups>
                            </e-contents>
                        </e-content>
                    </e-group>
                </e-groups>
            </e-tab>
        </e-tabs>
     </ej-ribbon>
     <ul id="ribbonmenu">
        <li>
            <a>FILE</a>
            <ul>
                <li><a>New</a></li>
            </ul>
        </li>
     </ul>
     <ul id="split">
        <li><a>Paste</a></li>
     </ul>
   
   @section StyleSection{
   <link href="@Url.Content("~/css/ejthemes/ribbon-css/ej.icons.css")" rel="stylesheet" />
    <style>
       .e-ribbon .e-rbnquickaccessbar .e-ribbonpaste:before {
            font-size: 27px;
            left: -5px;
            top: -6px;
        }
        .e-ribbon .e-ribbonpaste:before {
            font-family: 'ej-ribbonfont';
            content: "\e169";
            font-size: 36px;
            position: relative;
            left: -9px;
            top: -4px;
        }
        .e-ribbon .e-ribbonitalic:before ,.e-ribbon .bold:before{
            font-family: 'ej-ribbonfont';
            font-size: 16px;
            left: -1px;
            position: relative;
            top: -1px;
        }
         .e-ribbon .e-ribbonitalic:before ,.e-ribbon .bold:before{
            content: "\e163";
        }
        .e-ribbon .bold:before {
            content: "\e15a";
        }
        .e-ribbon .e-rbnquickaccessbar .e-undo::before {
            font-size: 18px;
            line-height: 12px;
            text-indent: -3px;
        }    
    </style>
  }

{% endhighlight %}

![](Quick-Access-Toolbar_images/Quick-Access-Toolbar_img1.png)
