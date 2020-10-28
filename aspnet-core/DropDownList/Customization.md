---
layout: post
title: Customization in DropDownList control for Syncfusion ASP.NET Core
description: Customization in DropDownList control for Syncfusion ASP.NET Core
platform: aspnet-core
control: DropDownList
documentation: ug
keywords: Customization, DropDownList, dropdown, watermark text
---

# Customization

## Adding watermark text

It provides the short description of the expected value in dropdown and will display the text until any item is selected. You can set this text using WatermarkText property.

{% tabs %}

    {% highlight CSHTML %}
        
    <ej-drop-down-list id="customerList" datasource="ViewBag.datasource" watermark-text="Select an Item">
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

![](Customization_images/Customization_img1.png)

![](Customization_images/Customization_img2.png)

## Applying Rounded Corner

You can use ShowRoundedCorner property to add rounded borders to the input and popup elements. By default, rounded corner property is disabled in DropDownList.

{% tabs %}

    {% highlight CSHTML %}

    <ej-drop-down-list id="customerList" datasource="ViewBag.datasource" show-rounded-corner="true">
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

![](Customization_images/Customization_img3.png)

I> The browser support details for rounded corner is given [here](http://www.w3schools.com/cssref/css3_pr_border-radius.asp).

## Enable/Disable the control

The Enabled property is used to indicate whether the control can respond to the user interaction or not. You can disable it by assigning false to this property. When the control is disabled state, you cannot interact with the control.

{% tabs %}

    {% highlight CSHTML %}
    
      <ej-drop-down-list id="customerList" datasource="ViewBag.datasource" enabled="false">
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

![](Customization_images/Customization_img4.png)

## Applying HTML Attributes

Additional HTML attributes can be applied to the control by using HtmlAttributes property. The attributes such as name, required, read-only and disabled are directly applied to the input element of DropDownList, and other attributes such as style, class will be applied to the outer wrapper element of DropDownList.

{% tabs %}

    {% highlight CSHTML %}

    @{
    IDictionary<string, object> attrib = new Dictionary<string, object>();
    attrib.Add("style", "border:1px solid red;");
    }

    <ej-drop-down-list id="customerList" datasource="ViewBag.datasource" html-attributes="attrib">
        <e-drop-down-list-fields text="Text" value="Value" />
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

![](Customization_images/Customization_img5.png)