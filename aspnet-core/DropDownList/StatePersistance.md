---
layout: post
title: State Persistance with DropDownList control for Syncfusion ASP.NET Core
description: State Persistence support to DropDownList control for Syncfusion ASP.NET Core
platform: aspnet-core
control: DropDownList
documentation: ug
keywords: Persistence, DropDownList, dropdown, State Persistence
---

# State Persistence

DropDownList stores its model is local storage by defining the property EnablePersistence).
You can sustain the below given functionalities in DropDownList by enabling persistence property,

* Selected items value in the textbox 
* Item’s selection state in the popup list 

Control model will be stored in local storage / cookies of browser before page refreshes and reinitialized with the restored model after refresh.
The following properties are not included while maintaining DropDownList’s state in local storage to keep localStorage compact.

* Fields
* Data source
* Query 

{% tabs %}

	{% highlight CSHTML %}

    <form id="form1">

        <ej-drop-down-list id="customerList" datasource="ViewBag.datasource" enable-persistence="true">
            <e-drop-down-list-fields text="Text" value="Value" />
        </ej-drop-down-list>
        <br /><br />
        <input type="submit" value="Get Value" />

    </form>

	{% endhighlight %}
    
    {% highlight c# %}
        public ActionResult Index()
        {
            List<Data> DropDownData = new List<Data>();
            DropDownData.Add(new Data { Value = "item1", Text = "ListItem 1" });
            DropDownData.Add(new Data { Value = "item2", Text = "ListItem 2" });
            DropDownData.Add(new Data { Value = "item3", Text = "ListItem 3" });
            DropDownData.Add(new Data { Value = "item4", Text = "ListItem 4" });
            DropDownData.Add(new Data { Value = "item5", Text = "ListItem 5" });
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