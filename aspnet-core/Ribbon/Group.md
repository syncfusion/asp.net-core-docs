---
layout: post
title: Group | Ribbon | ASP.NET Core | Syncfusion
description: Group
platform: aspnet-core
control: Ribbon
documentation: ug
keywords: group,ribbon group
---

# Group

Group is a collection of logical content groups that are combined under related Tab. Each group can be defined using content groups or custom content.

## Adding Tab Groups

Group items can be added to Tabs by specifying `Text` and corresponding `Content` to be displayed. The content of group can be specified as either with `Content` collection, `ContentID` or `CustomContent`. You can add tab group dynamically in the ribbon control with given tab index, tab group object and group index position by using [`addTabGroup`](https://help.syncfusion.com/api/js/ejribbon#methods:addtabgroup) method.

### Adding Content

Add content to Group item which is based on `Type` of content specified. The available types are `Button` , `SplitButton`, `ToggleButton`,`Gallery`, and `DropDownList`. 

Groups and defaults settings can be added with the `Content`. You can add group content dynamically in the ribbon control with given tab index, group index, content, content index and sub group index position by using [`addTabGroupContent`](https://help.syncfusion.com/api/js/ejribbon#methods:addtabgroupcontent).

#### _Defaults_

The [`tabs.groups.content.defaults.height`](https://help.syncfusion.com/api/js/ejribbon#members:tabs-groups-content-defaults-height), [`tabs.groups.content.defaults.width`](https://help.syncfusion.com/api/js/ejribbon#members:tabs-groups-content-defaults-width), 
[`tabs.groups.content.defaults.type`](https://help.syncfusion.com/api/js/ejribbon#members:tabs-groups-content-defaults-type), [`tabs.groups.content.defaults.isBig`](https://help.syncfusion.com/api/js/ejribbon#members:tabs-groups-content-defaults-isbig) property to the controls in the [`group`](https://help.syncfusion.com/api/js/ejribbon#members:tabs-groups-content-groups) can be specified commonly.

The `Height` & `Width` applicable to Button, SplitButton, DropDownList ,ToggleButton controls and `IsBig` applicable to only button controls ( button, split , toggle)

#### _Adding Content Groups_

Controls such as button, split button, dropdown list, toggle button, gallery in the subgroup of the Ribbon Tab can be rendered. All of these can be customized using its corresponding settings property such as `ButtonSettings`, `DropdownSettings`, etc.

Custom controls or items (such as table, div etc.) can be added when the `Type` set as `Custom`. `Defaults` control settings of group can be specified for an `individual group` instead of specifying them to Content `Groups ` collection commonly.

`ToolTip` and `CustomTooltip` can be specified for each group controls.

{% highlight html %}

   <ul id="ribbonmenu">
      <li>
         <a>FILE</a>
            <ul>
                <li><a>Open</a></li>
            </ul>
      </li>
   </ul>
   <ul id="pasteSplit">
        <li><a>Paste Special</a></li>
   </ul>
    
{% endhighlight  %}

{% highlight CSHTML %}

   <ej-ribbon id="defaultRibbon" width="500px">
        <e-application-tab type=Menu menu-item-id="ribbonmenu">
        </e-application-tab>
        <e-tabs>
            <e-tab id="home" text="HOME">
                <e-groups>
                    <e-group text="ClipBoard" align-type=Columns>
                        <e-content>
                            <e-contents>
                                <e-content-groups>
                                    <e-content-group id="paste" text="Paste" tool-tip="Paste" is-big="true" type=SplitButton>
                                        <e-split-button-settings button-mode=Dropdown target-id="pasteSplit" content-type=ImageOnly prefix-icon="e-icon e-ribbon e-ribbonpaste">
                                        </e-split-button-settings>
                                    </e-content-group>
                                </e-content-groups>
                            </e-contents>
                        </e-content>
                    </e-group>
                    <e-group text="Font" align-type=Columns>
                        <e-content>
                            <e-contents>
                                <e-defaults width="75" height="30" type=ToggleButton />
                                  <e-content-groups>
                                    <e-content-group id="cut">
                                        <e-toggle-button-settings default-text="Cut" active-text="Cut Over">
                                        </e-toggle-button-settings>
                                    </e-content-group>
                                    <e-content-group id="copy">
                                        <e-toggle-button-settings default-text="Copy" active-text="Copy Over">
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
     
{% endhighlight  %}

![](Group_images/Group_img1.png)

#### _Enable Separator_ 

Separates the control from the next control in the group when group `AlignType` is `Rows`. Set “true” to `EnableSeparator`.

{% highlight html %}

  <ul id="ribbonmenu">
        <li>
            <a>FILE</a>
            <ul>
                <li><a>New</a></li>
                <li><a>Open</a></li>
            </ul>
        </li>
   </ul>
    
 {% endhighlight  %}
 
 {% highlight CSHTML %}

<ej-ribbon id="defaultRibbon" width="500px">
   <e-application-tab type=Menu menu-item-id="ribbonmenu">
   </e-application-tab>
     <e-tabs>
        <e-tab id="home" text="HOME">
            <e-groups>
                <e-group text="New" align-type=Rows>
                    <e-content>
                        <e-contents>
                            <e-content-groups>
                               <e-defaults height="70" type="Button" />
                                <e-content-group id="new" text="New" tool-tip="New" enable-separator="true">
                                    <e-button-settings width="100">
                                    </e-button-settings>
                                </e-content-group>
                                 <e-content-group id="font" text="Font" tool-tip="Font">
                                    <e-button-settings width="150">
                                    </e-button-settings>
                                </e-content-group>
                            </e-content-groups>
                        </e-contents>
                      </e-content>
                 </e-group>
              </e-groups>
        </e-tab>
     </e-tabs>
</ej-ribbon>
 
 {% endhighlight  %}
 
 ![](Group_images/Group_img2.png)
 
### Adding Custom Content 
 
Set group `Type` as `custom` to add custom items such as div, table and custom controls. With type as custom, content can be added in two ways as specified below.

*	HTML contents can be directly added into the groups as string content using `CustomContent`. property

*	Custom template id can be specified to render those specific custom template using `ContentID` property


{% highlight html %}

   <ul id="ribbonmenu">
      <li>
        <a>FILE</a>
        <ul>
            <li><a>New</a></li>
            <li><a>Open</a></li>
        </ul>
      </li>
   </ul>
   <button id='btn'>Using Content ID</button>

{% endhighlight  %}

{% highlight CSHTML %}

   <ej-ribbon id="defaultRibbon" width="500px">
        <e-application-tab type=Menu menu-item-id="ribbonmenu">
        </e-application-tab>
        <e-tabs>
            <e-tab id="home" text="HOME">
                <e-groups>
                    <e-group text="New" type="custom" custom-content="<button id='customContent'>Using Custom Content</button>">
                    </e-group>
                    <e-group text="Data" type="custom" content-id="btn">
                    </e-group>
                </e-groups>
            </e-tab>
        </e-tabs>
   </ej-ribbon>
    
{% endhighlight  %}
 
![](Group_images/Group_img3.png)

## Group Expander

Set [`enableGroupExpander`](https://help.syncfusion.com/api/js/ejribbon#members:tabs-groups-enablegroupexpander) as true to show Group Expander for each group in Tab. These expanders can be customized using [`groupExpand`](https://help.syncfusion.com/api/js/ejribbon#events:groupexpand) event, such as to show popup dialog. To specify tooltip for the group expander of the group [`tabs.groups.groupExpanderSettings`](https://help.syncfusion.com/api/js/ejribbon#members:tabs-groups-groupexpandersettings) and 
[`tabs.groups.groupExpanderSettings.toolTip`](https://help.syncfusion.com/api/js/ejribbon#members:tabs-groups-groupexpandersettings-tooltip) can be used.
  
{% highlight html %}

  <ul id="ribbonmenu">
        <li>
            <a>FILE</a>
            <ul>
                <li><a>New</a></li>
            </ul>
        </li>
   </ul>
   <button id='btn'>Home button</button>   
  
{% endhighlight  %}
  
{% highlight CSHTML %}
  
  <ej-ribbon id="defaultRibbon" width="500px">
        <e-application-tab type=Menu menu-item-id="ribbonmenu">
        </e-application-tab>
        <e-tabs>
            <e-tab id="home" text="HOME">
                <e-groups>
                    <e-group text="New" align-type=Rows type="custom" enable-group-expander="true" content-id="btn">
                    </e-group>
                </e-groups>
            </e-tab>
        </e-tabs>
   </ej-ribbon>
      
  {% endhighlight  %}
  
  ![](Group_images/Group_img4.png)