---
title: Data binding with Spreadsheet widget for Syncfusion Essential ASP.NET Core
description: How to perform Data Binding and configure its properties like dataSource, query etc.
platform: aspnet-core
control: Spreadsheet
documentation: ug
---
# Data Binding

Spreadsheet can be populated with external datasource using `datasource` property. The `datasource` property can be assigned either with the instance of `e-datamanager` or JSON data array collection. Spreadsheet supports three different kinds of Data binding.

* Local Data
* Remote Data
* HTML Table Data

## Local Data

To bind local data to the Spreadsheet, you can assign a JSON array to the worksheet `datasource` property. The following code illustrates how to bind local data to the Spreadsheet,

{% tabs %}
{% highlight cshtml %}

<ej-spread-sheet id="Spreadsheet">
    <e-sheets>
        <e-sheet datasource="ViewBag.Datasource"></e-sheet>
    </e-sheets>
</ej-spread-sheet>
    
{% endhighlight %}
{% highlight c# %}

namespace MVCSampleBrowser.Controllers
{
    public partial class SpreadsheetController : Controller
    {
        public ActionResult Default()
        {
            List<OrderDetail> lItems = new List<OrderDetail>();
            lItems.Add(new OrderDetail() { OrderID = 10248, CustomerID = "VINET", EmployeeID = 5, ShipCity = "Reims", ShipCountry = "France" });
            lItems.Add(new OrderDetail() { OrderID = 10249, CustomerID = "TOMSP", EmployeeID = 6, ShipCity = "Münster", ShipCountry = "Germany" });
            lItems.Add(new OrderDetail() { OrderID = 10250, CustomerID = "HANAR", EmployeeID = 4, ShipCity = "Rio de Janeiro", ShipCountry = "Brazil" });
            lItems.Add(new OrderDetail() { OrderID = 10251, CustomerID = "VICTE", EmployeeID = 3, ShipCity = "Lyon", ShipCountry = "France" });
            lItems.Add(new OrderDetail() { OrderID = 10252, CustomerID = "SUPRD", EmployeeID = 4, ShipCity = "Charleroi", ShipCountry = "Belgium" });
            ViewBag.Datasource = lItems;
            return View();
        }
    }
}

{% endhighlight %}
{% endtabs %}

The following output is displayed as a result of the above code snippets.
![](Data-Binding_images/Data-Binding_img1.png)

## Remote Data

To bind remote data to the Spreadsheet, you can assign a service data as an instance of `e-datamanager` to the worksheet. The following code illustrates how to bind remote data to the Spreadsheet,

{% highlight cshtml %}

<ej-spread-sheet id="Spreadsheet">
    <e-sheets>
        <e-sheet query="new ej.Query().select(['OrderID', 'CustomerID', 'EmployeeID', 'ShipCity', 'Freight'])
        .take(50)" primary-key="OrderID">
            <e-datamanager url="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/"></e-datamanager>
        </e-sheet>
    </e-sheets>
</ej-spread-sheet>
    
{% endhighlight %}

The following output is displayed as a result of the above code snippets.
![](Data-Binding_images/Data-Binding_img2.png)

### Offline Mode

To avoid sending post back request to server on every action, Spreadsheet allows user to create, update and delete data on client side. To enable this, set `offline` property of `e-datamanager` as `true` to fetch all data from server on initial rendering of Spreadsheet and perform all operation on client side.

The following code illustrates Offline data binding for Spreadsheet,

{% highlight cshtml %}

<ej-spread-sheet id="Spreadsheet">
    <e-sheets>
        <e-sheet query="new ej.Query().select(['OrderID', 'CustomerID', 'EmployeeID', 'ShipCity', 'Freight'])
        .take(50)" primary-key="OrderID">
            <e-datamanager url="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/" offline="true"></e-datamanager>
        </e-sheet>
    </e-sheets>
</ej-spread-sheet>
    
{% endhighlight %}

The following output is displayed as a result of the above code snippets.
![](Data-Binding_images/Data-Binding_img2.png)

## HTML Table Data

An HTML Table element can also be used as the data source of Spreadsheet. To use HTML Table as data source, the table element should be passed to `table` property of `e-datamanager` inside sheet. The following code illustrates how to bind HTML Table data to the Spreadsheet,

{% highlight cshtml %}

<ej-spread-sheet id="Spreadsheet">
    <e-sheets>
        <e-sheet show-header="false">
            <e-datamanager table="#_table1"></e-datamanager>
        </e-sheet>
    </e-sheets>
</ej-spread-sheet>

<script id="_table1" type="text/template">    
    <table id="Table1">
        <thead>
            <tr>
                <th>Laptop</th>
                <th>Model</th>
                <th>Price</th>
                <th>OS</th>
                <th>RAM</th>
                <th>ScreenSize</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>Dell Vostro</td>
                <td>2520</td>
                <td>39990</td>
                <td>Windows 8</td>
                <td>4GB</td>
                <td>15.6</td>
            </tr>
            <tr>
                <td>HP Pavilion Sleekbook</td>
                <td>14-B104AU</td>
                <td>22800</td>
                <td>Windows 8</td>
                <td>2GB</td>
                <td>14</td>
            </tr>
            <tr>
                <td>Sony Vaio</td>
                <td>E14A15</td>
                <td>42500</td>
                <td>Windows 7 Home Premium</td>
                <td>4GB DDR3 RAM</td>
                <td>14</td>
            </tr>
            <tr>
                <td>Lenovo</td>
                <td>Yoga 13</td>
                <td>57000</td>
                <td>Windows 8 RT</td>
                <td>2GB DDR3 RAM</td>
                <td>11.6</td>
            </tr>
            <tr>
                <td>Toshiba</td>
                <td>L850-Y3110</td>
                <td>57700</td>
                <td>Windows 8 SL</td>
                <td>8GB DDR3 RAM</td>
                <td>15.6</td>
            </tr>
        </tbody>
    </table>
</script>
{% endhighlight %}

The following output is displayed as a result of the above code snippets.
![](Data-Binding_images/Data-Binding_img3.png)

## Ways to bind data in Spreadsheet

You can bind data to Spreadsheet in following ways,

* Cell binding
* Range binding
* Sheet binding

### Cell Binding

Spreadsheet can bind data for individual cells in a sheet. The data may contain value, style, format, comment and hyperlink. The individual cell properties are listed below,

<table>
    <tr>
        <th>
            Properties
        </th>
        <th>
            Description
        </th>
    </tr>
    <tr>
        <td>
            index
        </td>
        <td>
            To specify particular cell
        </td>
    </tr>
    <tr>
        <td>
            value
        </td>
        <td>
            To specify value. It may be string, integer, formula etc.
        </td>
    </tr>
    <tr>
        <td>
            e-styles
        </td>
        <td>
            To specify style in the cell
        </td>
    </tr>
    <tr>
        <td>
            e-formats
        </td>
        <td>
            To specify number format in the cell
        </td>
    </tr>
    <tr>
        <td>
            e-comment
        </td>
        <td>
            To specify comment in the cell
        </td>
    </tr>
    <tr>        
        <td>
            e-hyperlink
        </td>
        <td>
            To specify hyperlink in the cell
        </td>
    </tr>
</table>

The individual row properties are listed below,

<table>
    <tr>
        <th>
            Properties
        </th>
        <th>
            Description
        </th>
    </tr>
    <tr>
        <td>
            index
        </td>
        <td>
            To specify particular row
        </td>
    </tr>
    <tr>
        <td>
            height
        </td>
        <td>
            To specify height in the row
        </td>
    </tr>
</table>

You can specify particular row with `index` property and its height with `height` property in the `e-row` property collection. The following code illustrates cell binding in Spreadsheet,

{% highlight cshtml %}

<ej-spread-sheet id="Spreadsheet">
    <e-sheets>
        <e-sheet>
            <e-rows>
                <e-row height="30">
                    <e-cells>
                        <e-cell value="Item Name">
                            <e-styles font-weight="bold" color="#FFFFFF" background-color="#428bca"></e-styles>
                        </e-cell>
                        <e-cell value="Quantity">
                            <e-styles font-weight="bold" color="#FFFFFF" background-color="#428bca"></e-styles>
                        </e-cell>
                        <e-cell value="Price">
                            <e-styles font-weight="bold" color="#FFFFFF" background-color="#428bca"></e-styles>
                        </e-cell>
                        <e-cell value="Amount">
                            <e-styles font-weight="bold" color="#FFFFFF" background-color="#428bca"></e-styles>
                        </e-cell>
                        <e-cell value="Stock Details">
                            <e-styles font-weight="bold" color="#FFFFFF" background-color="#428bca"></e-styles>
                        </e-cell>
                        <e-cell value="Website">
                            <e-styles font-weight="bold" color="#FFFFFF" background-color="#428bca"></e-styles>
                        </e-cell>
                    </e-cells>
                </e-row>
                <e-row>
                    <e-cells>
                        <e-cell value="Casual Shoes">
                            <e-comment value="Casual Footwears with wide variety of colors."></e-comment>
                        </e-cell>
                        <e-cell value="20" index="2">
                            <e-formats type="currency"></e-formats>
                        </e-cell>
                        <e-cell value="=B2*C2">
                            <e-formats type="currency"></e-formats>
                        </e-cell>
                        <e-cell value="OUT OF STOCK"></e-cell>
                        <e-cell value="Amazon">
                            <e-hyperlink web-addr="www.amazon.com"></e-hyperlink>
                        </e-cell>
                    </e-cells>
                </e-row>
                <e-row>
                    <e-cells>
                        <e-cell value="Sports Shoes">
                            <e-styles background-color="#E5F3FF"></e-styles>
                        </e-cell>
                        <e-cell value="20">
                            <e-styles background-color="#E5F3FF"></e-styles>
                        </e-cell>
                        <e-cell value="30">
                            <e-formats type="currency"></e-formats>
                            <e-styles background-color="#E5F3FF"></e-styles>
                        </e-cell>
                        <e-cell value="=B3*C3">
                            <e-formats type="currency"></e-formats>
                            <e-styles background-color="#E5F3FF"></e-styles>
                        </e-cell>
                        <e-cell value="IN STOCK">
                            <e-styles background-color="#E5F3FF"></e-styles>
                        </e-cell>
                        <e-cell value="AliExpress">
                            <e-hyperlink web-addr="www.aliexpress.com"></e-hyperlink>
                            <e-styles background-color="#E5F3FF"></e-styles>
                        </e-cell>
                    </e-cells>
                </e-row>
                <e-row>
                    <e-cells>
                        <e-cell value="Formal Shoes">
                            <e-comment value="Formal Footwears with wide range of sizes."></e-comment>
                        </e-cell>
                        <e-cell value="20"></e-cell>
                        <e-cell value="15">
                            <e-formats type="currency"></e-formats>
                        </e-cell>
                        <e-cell value="=B4*C4">
                            <e-formats type="currency"></e-formats>
                        </e-cell>
                        <e-cell value="OUT OF STOCK"></e-cell>
                        <e-cell value="Amazon">
                            <e-hyperlink web-addr="www.amazon.com"></e-hyperlink>
                        </e-cell>
                    </e-cells>
                </e-row>
                <e-row height="30" index="5">
                    <e-cells>
                        <e-cell>
                            <e-styles background-color="#428bca"></e-styles>
                        </e-cell>
                        <e-cell>
                            <e-styles background-color="#428bca"></e-styles>
                        </e-cell>
                        <e-cell value="Total Amount" index="2">
                            <e-styles font-weight="bold" color="#FFFFFF" background-color="#428bca"></e-styles>
                        </e-cell>
                        <e-cell value="=Sum(D2:D4)">
                            <e-formats type="currency"></e-formats>
                            <e-styles font-weight="bold" color="#FFFFFF" background-color="#428bca"></e-styles>
                        </e-cell>
                        <e-cell>
                            <e-styles background-color="#428bca"></e-styles>
                        </e-cell>
                        <e-cell>
                            <e-styles background-color="#428bca"></e-styles>
                        </e-cell>
                    </e-cells>
                </e-row>
            </e-rows>
        </e-sheet>
    </e-sheets>
</ej-spread-sheet>

{% endhighlight %}

The following output is displayed as a result of the above code snippets.
![](Data-Binding_images/Data-Binding_img4.png)

### Range Binding

Spreadsheet can bind data for one or more range in a sheet using `e-range-settings`. The individual range properties are listed below,

<table>
    <tr>
        <th>
            Properties
        </th>
        <th>
            Description
        </th>
    </tr>
    <tr>
        <td>
            datasource
        </td>
        <td>
            To specify JSON 
        </td>
    </tr>
    <tr>    
        <td>
            query
        </td>
        <td>
            To specify query for {{'`e-datamanager`' | markdownify}}
        </td>
    </tr>
    <tr>
        <td>    
            start-cell
        </td>
        <td>
            To specify start cell of a range
        </td>
    </tr>
    <tr>
        <td>
            primary-key
        </td>
        <td>
            To specify data source primary key
        </td>
    </tr>
    <tr>
        <td>
            show-header
        </td>
        <td>
            To show data source header
        </td>
    </tr>
    <tr>
        <td>
            e-header-styles
        </td>
        <td>
            To specify header styles
        </td>
    </tr>
</table>

The following code illustrates range binding in Spreadsheet

{% tabs %}
{% highlight cshtml %}

<ej-spread-sheet id="Spreadsheet">
    <e-sheets>
        <e-sheet>
            <e-range-settings>
                <e-range-setting datasource="ViewBag.Datasource" show-header="true" start-cell="C2">
                    <e-header-styles font-weight="bold"></e-header-styles>
                </e-range-setting>
            </e-range-settings>
        </e-sheet>
    </e-sheets>
</ej-spread-sheet>
    
{% endhighlight %}
{% highlight c# %}

namespace MVCSampleBrowser.Controllers
{
    public partial class SpreadsheetController : Controller
    {
        public ActionResult Default()
        {
            List<MarkDetail> lItems = new List<MarkDetail>();
            lItems.Add(new MarkDetail() { Name = "VINET", Average = 90, Grade = "S" });
            lItems.Add(new MarkDetail() { Name = "TOMSP", Average = 83, Grade = "A" });
            lItems.Add(new MarkDetail() { Name = "HANAR", Average = 80, Grade = "A" });
            lItems.Add(new MarkDetail() { Name = "VICTE", Average = 93, Grade = "S" });
            lItems.Add(new MarkDetail() { Name = "SUPRD", Average = 60, Grade = "D" });
            lItems.Add(new MarkDetail() { Name = "CHOPS", Average = 71, Grade = "C" });
            lItems.Add(new MarkDetail() { Name = "WELLI", Average = 88, Grade = "A" });
            lItems.Add(new MarkDetail() { Name = "HILLA", Average = 95, Grade = "S" });
            lItems.Add(new MarkDetail() { Name = "ERNSH", Average = 69, Grade = "D" });
            lItems.Add(new MarkDetail() { Name = "CENTC", Average = 77, Grade = "C" });
            lItems.Add(new MarkDetail() { Name = "OTTIK", Average = 95, Grade = "S" });
            lItems.Add(new MarkDetail() { Name = "RATTC", Average = 85, Grade = "A" });
            lItems.Add(new MarkDetail() { Name = "FOLKO", Average = 90, Grade = "A" });
            lItems.Add(new MarkDetail() { Name = "BLONP", Average = 97, Grade = "S" });
            ViewBag.Datasource = lItems;
            return View();
        }
    }
}

{% endhighlight %}
{% endtabs %}
The following output is displayed as a result of the above code snippets.

![](Data-Binding_images/Data-Binding_img5.png)

### Sheet Binding

Spreadsheet can bind data for a sheet. The individual sheet properties are listed below,

<table>
    <tr>
        <th>
            Properties
        </th>
        <th>
            Description
        </th>
    </tr>
    <tr>
        <td>
            datasource
        </td>
        <td>
            To specify JSON 
        </td>
    </tr>
    <tr>
        <td>
            query
        </td>
        <td>
            To specify query for {{'`e-datamanager`' | markdownify}}
        </td>
    </tr>
    <tr>
        <td>
            start-cell
        </td>
        <td>
            To specify start cell of a range
        </td>
    </tr>
    <tr>
        <td>
            primary-key
        </td>
        <td>
            To specify data source primary key
        </td>
    </tr>
    <tr>
        <td>
            show-header
        </td>
        <td>
            To show data source header
        </td>
    </tr>
    <tr>
        <td>
            e-header-styles
        </td>
        <td>
            To specify header styles
        </td>
    </tr>
    <tr>
        <td>
            field-as-column-header
        </td>
        <td>
            To show data source fields in column header
        </td>
    </tr>
</table>

The following code illustrates sheet binding in Spreadsheet

{% highlight cshtml %}

<ej-spread-sheet id="Spreadsheet">
    <e-sheets>
        <e-sheet query="new ej.Query().select(['OrderID', 'CustomerID', 'EmployeeID', 'ShipCity', 'Freight'])
        .take(50)" primary-key="OrderID" field-as-column-header="true">
            <e-datamanager url="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/"></e-datamanager>
        </e-sheet>
    </e-sheets>
</ej-spread-sheet>
    
{% endhighlight %}

The following output is displayed as a result of the above code snippets. 
![](Data-Binding_images/Data-Binding_img6.png)

