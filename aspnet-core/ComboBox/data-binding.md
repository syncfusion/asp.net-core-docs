---
layout: post
title: Data Binding in ComboBox control for Syncfusion ASP.NET CORE
description: DataBinding support to ComboBox control for Syncfusion ASP.NET CORE
platform: CORE
control: ComboBox
documentation: ug
keywords: remote data, ComboBox, json data, local data
---

# Data Binding

The ComboBox loads the data either from the local data sources or
remote data services using the `dataSource` property. It supports
the data type of `array` or **DataManager**.

The ComboBox also supports different kinds of data services such as OData, OData V4, and Web API, and data formats such as XML, JSON, and JSONP with the help of `DataManager` adaptors.

| Fields | Type | Description |
|------|------|-------------|
| text |  `string` | Specifies the display text of each list item. |
| value |  `string` | Specifies the hidden data value mapped to each list item that should contain a unique value. |
| groupBy |  `string` | Specifies the category under which the list item has to be grouped. |
| iconCss |  `string` | Specifies the icon class of each list item. |

> When binding complex data to the ComboBox, the fields should be mapped correctly. Otherwise, the selected item remains undefined.

## Binding local data

Local data can be represented in two ways as described below.

### 1. Array of simple data

The ComboBox has the support to load array of primitive data such as strings and numbers. Here, both the value and text field act as the same.

{% highlight CSHTML %}

 @{string[] datasource = new string[] { "Badminton", "Cricket", "Football", "Golf", "Tennis" };
    }

{% endhighlight %}

{% highlight html %}

    <div class="frame">
        <div class="control"> 
        <ej-combo-box id="Localdata" datasource="datasource" placeholder="Select a game">
            <e-combo-box-fields text="text"/>
        </ej-combo-box>
        </div>
    </div>

{% endhighlight %}

Output for array-data combobox control is as follows.

![](Combobox_databinding_images/array_data.png) 

### 2. Array of JSON data

The ComboBox can generate its list items through an array of complex data. For this, the appropriate columns should be mapped to the **fields** property.

In the following example, `Id` column and `Game` column from complex data have been mapped to the `value` field and `text` field, respectively.

{% highlight html %}

<div class="frame">
        <div class="control"> 
        <ej-combo-box id="select" datasource="(IEnumerable<Customer>)ViewBag.datasource" placeholder="Select">
            <e-combo-box-fields text="text"/>
        </ej-combo-box>
        </div>
    </div>

{% endhighlight %}

{% highlight c# %}

  
        List<Customers> customer = new List<Customers>();
        public ActionResult Index()
        {
            customer.Add(new Customers { id = "1", text = "ALFKI" });
            customer.Add(new Customers { id = "2", text = "ANATR" });
            customer.Add(new Customers { id = "3", text = "ANTON" });
            customer.Add(new Customers { id = "4", text = "AROUT" });
            customer.Add(new Customers { id = "5", text = "BERGS" });
            customer.Add(new Customers { id = "6", text = "BLAUS" });
            ViewBag.datasource = customer;
            return View();
        }

       public class Customers
        {
            public string id { get; set; }
            public string text { get; set; }
        }
  {% endhighlight  %}

![](Combobox_databinding_images/local_data.png)

## Binding remote data

The ComboBox supports retrieval of data from the remote data services with the help of **DataManager** component. The **Query** property is used to fetch data from the database and bind it to the ComboBox.

In the following sample, displayed first 6 contacts from the `customer` table of `Northwind` Data Service.


{% highlight html %}

 <div class="frame">
        <div class="control">
            <ej-combo-box id="searchCustomer" query="ej.Query().from('Suppliers').select('SupplierID', 'ContactName')" placeholder="Select a customer" width="100%">
                <e-datamanager url="//js.syncfusion.com/ejServices/wcf/NorthWind.svc/" offline="false" cross-domain="true"></e-datamanager>
                <e-combo-box-fields text="ContactName" value="SupplierID" />
            </ej-combo-box>
        </div>
    </div>

{% endhighlight %}

{% highlight c# %}

public ActionResult Databindingremote()
        {
            return View();
        }

{% endhighlight %}



Output for remote-data combobox control is as follows:


![](Combobox_databinding_images/remote_data.png) 