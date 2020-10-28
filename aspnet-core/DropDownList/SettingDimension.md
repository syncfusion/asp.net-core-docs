---
layout: post
title: Demension in DropDownList control for Syncfusion ASP.NET Core
description: Setting Dimensions to DropDownList control for Syncfusion ASP.NET Core 
platform: aspnet-core
control: DropDownList
documentation: ug
keywords: Auto Sizing, DropDownList, dropdown, popup size

---

# Setting dimensions 

## Control Sizing

### Fixed Size DropDownList control

You can customize the control dimensions using Width and Height properties. Fixed size values can be specified in pixel or percentage values. By default the DropDownList wrapper will be assigned with "143px" Width and "30px" Height.

### Fixed size popup list

You can customize the popup list dimensions using PopupWidth and PopupHeight properties. Fixed size values can be specified in pixel or percentage values. By default popup width is auto and popup height is "152px". 

### Auto Sizing

DropDownList is adaptive to mobile and web layout such that it is adjustable with screen resolution. The textbox will be rendered based on its parent containers dimensions on assigning 100% values to the width property. Default value for PopupWidth is auto, so when you assign 100% to PopupWidth then it will be rendered based on specified range.

### Limit the number of items

You can use ItemsCount property to fetch only the specific number of items from the data source. To fetch the remaining items you can enable [virtual scrolling](databinding#virtual-scrolling) support which loads the data on scrolling the data items in popup list. 

N> By default popup list is shown on DropDownList button click but you can display the list initially by enabling the ShowPopupOnLoad property. 

{% tabs %}

    {% highlight CSHTML %}
        
    <ej-drop-down-list id="customerList" datasource="ViewBag.datasource" show-popup-on-load="true" items-count="3">
        <e-drop-down-list-fields text="Text" value="Value"/>
    </ej-drop-down-list>

	{% endhighlight %}
    
    {% highlight c# %}
    
        public ActionResult Index()
        {
            List<Data> DropdownData = new List<Data>();
            DropdownData.Add(new Data { Value = "item1", Text = "ListItem 1" });
            DropdownData.Add(new Data { Value = "item2", Text = "ListItem 2" });
            DropdownData.Add(new Data { Value = "item3", Text = "ListItem 3" });
            DropdownData.Add(new Data { Value = "item4", Text = "ListItem 4" });
            DropdownData.Add(new Data { Value = "item5", Text = "ListItem 5" });
            ViewBag.datasource=DropDownData;
            return View();
        }
        public class Data
        {
            public string Value { get; set; }
            public string Text { get; set; }
        }
        
    {% endhighlight %}
    
{% endtabs %}

![](SettingDimension_images/SettingDimension_img1.png)

## Popup resizing 

To show a resize handle in the popup list, use EnablePopupResize property. You can customize the resize functionality by setting dimensions to the following properties.

<table>
    <tr>
        <td>
            MinPopupWidth
        </td>
        <td>
            Default value is 0, once set you cannot resize below to the specified width
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            MaxPopupWidth
        </td>
        <td>
            Default value is null, once set you cannot extend beyond to the specified width
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            MinPopupHeight
        </td>
        <td>
            Default value is 0, once set you cannot resize below to the specified height
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            MaxPopupHeight
        </td>
        <td>
            Default value is null, once set you cannot extend beyond to the specified height
            <br/>
        </td>
    </tr>
</table>

{% tabs %}

    {% highlight CSHTML %}        
        
    <ej-drop-down-list id="customerList" datasource="ViewBag.datasource" enable-popup-resize="true" max-popup-height="550px" max-popup-width="550px" min-popup-height="150px" min-popup-width="150px">
        <e-drop-down-list-fields text="Text" value="Value"/>
    </ej-drop-down-list>

	{% endhighlight %}
    
    {% highlight c# %}
    
        public ActionResult Index()
        {
            List<Data> DropdownData = new List<Data>();
            DropdownData.Add(new Data { Value = "item1", Text = "ListItem 1" });
            DropdownData.Add(new Data { Value = "item2", Text = "ListItem 2" });
            DropdownData.Add(new Data { Value = "item3", Text = "ListItem 3" });
            DropdownData.Add(new Data { Value = "item4", Text = "ListItem 4" });
            DropdownData.Add(new Data { Value = "item5", Text = "ListItem 5" });
            ViewBag.datasource=DropDownData;
            return View();
        }
        public class Data
        {
            public string Value { get; set; }
            public string Text { get; set; }
        }
        
    {% endhighlight %}
    
{% endtabs %}

![](SettingDimension_images/SettingDimension_img2.png)

![](SettingDimension_images/SettingDimension_img3.png)