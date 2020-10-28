---
layout: post
title: Searching in the DropDownList control for Syncfusion ASP.NET Core
description: Descripes about searching in the DropDownList control for Syncfusion ASP.NET Core
platform: aspnet-core
control: DropDownList
documentation: ug
keywords: DropDownList, dropdown, Server Filtering, Search, Incremental Search, Filter Search

---

# Search

Items are searched based on the keyed in values to the textbox. There are two types of searches,

* Incremental Search
* Filter Search

## Incremental Search

Selects the item in the popup list based on the keyed in value. If the time taken to type exceeds 1000 milliseconds then filtered items will be reset based on the current input value. By default this mode of search is enabled. Incremental search can be case sensitive or case insensitive. To make case sensitive, you can use CaseSensitiveSearch property.

{% tabs %}

	{% highlight CSHTML %}

    <ej-drop-down-list id="dropdown" datasource="ViewBag.datasource" enable-incremental-search="true" case-sensitive-search="true">
        <e-drop-down-list-fields text="Text" value="Value" />
    </ej-drop-down-list>

	{% endhighlight %}
    
    {% highlight c# %}
        public ActionResult Index()
        {
            List<Data> DropDownData = new List<Data>();
            DropDownData.Add(new Data { Value = "emp1", Text = "Adams"});
            DropDownData.Add(new Data { Value = "emp2", Text = "James"});
            DropDownData.Add(new Data { Value = "emp3", Text = "Maria"});
            DropDownData.Add(new Data { Value = "emp4", Text = "Jessica"});
            DropDownData.Add(new Data { Value = "emp5", Text = "Jenneth"});
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

![](Functionalities_images/Functionalities_img8.png)

## Filter search

You can quickly locate specific item within a large data source by filtering matches with a search box. A text box appears in the popup list for searching when EnableFilterSearch property is enabled. By default, filtering returns the matched items list based on text in search textbox. 
You can configure the search filter by using FilterType property that takes SearchFilterType enum values. There is two types of filter options,

* Starts With 
* Contains

N> Items are filtered based on “SearchFilterType.Contains” filter type by default.

{% tabs %}

	{% highlight CSHTML %}

    <ej-drop-down-list id="dropdown" datasource="ViewBag.datasource" enable-filter-search="true" filter-type="@SearchFilterType.StartsWith">
    <e-drop-down-list-fields text="Text" value="Value" />
    </ej-drop-down-list>

	{% endhighlight %}
    
    {% highlight c# %}
        public ActionResult Index()
        {
            List<Data> DropDownData = new List<Data>();
            DropDownData.Add(new Data { Value = "emp1", Text = "Adams", Selected = true });
            DropDownData.Add(new Data { Value = "emp2", Text = "James", Selected = false });
            DropDownData.Add(new Data { Value = "emp3", Text = "Maria", Selected = true });
            DropDownData.Add(new Data { Value = "emp4", Text = "Jessica", Selected = false });
            DropDownData.Add(new Data { Value = "emp5", Text = "Jenneth", Selected = false });
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

![](Functionalities_images/Functionalities_img9.png)

I> When VirtualScrolling enabled with searching, then filter will be applied only on the DropDownList items available at the moment.

## Server Filtering

Server filtering for displaying only a fixed amount of dataset from the whole dataset. In general, DropDownList displays just the data returned from the server. This feature is convenient for you to apply when the user does not want to see the whole dataset in the popup wrapper.
The property enable-server-filtering If set to true, the filtering operations performed in the remote service and returns the result.

{% highlight CSHTML %}

    <div class="ctrllabel">Select a Customer Name</div>
    <ej-drop-down-list id="customerList" width="100%" enable-filter-search="true" enable-server-filtering="true">
        <e-datamanager url="//js.syncfusion.com/demos/ejServices/Wcf/Northwind.svc/Customers" cross-domain="true"></e-datamanager>
        <e-drop-down-list-fields text="ContactName" value="ContactName"/>
    </ej-drop-down-list>

{% endhighlight %}

![](ServerFiltering_images/ServerFiltering_image2.png)

This sample raises the query on Customer service. Returns ContactName records for customers with ContactName containing the string “d”.

![](ServerFiltering_images/ServerFiltering_image1.png)

