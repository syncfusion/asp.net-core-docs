---
layout: post
title: Filtering with grid widget for Syncfusion Essential ASP.NET Core
description: How to enable filtering and its functionalities
platform: aspnet-core
control: grid
documentation: ug
---
# Filtering

Filtering helps to view particular or related records from dataSource which meets a given filtering criteria. To enable filter, set `allow-filtering` property as `true`.   

The Grid supports three types of filter, they are as follows.

1. Filter Bar
2. Menu 
3. Excel

There are four types of filter menu available in all filter types, they are as follows.

1. String 
2. Numeric 
3. Date 
4. Boolean

The corresponding filter menu is opened based on the column type.

N>  1. Need to specify the [`type`](http://help.syncfusion.com/api/js/ejgrid#members:columns-type "type") of column, when first record data value is empty or null otherwise the filter menu is not opened. 
N>  2. The default filter type is Filter bar, when `allow-filtering` is enabled and [`filter-type`](http://help.syncfusion.com/api/js/ejgrid#members:filtersettings-filtertype "filter-type") is not set.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

    <ej-grid id="FlatGrid" allow-paging="true" allow-filtering="true" datasource="ViewBag.DataSource">
        <e-columns>
            <e-column field="OrderID" header-text="Order ID"></e-column>
            <e-column field="EmployeeID" header-text="Customer ID"></e-column>
            <e-column field="CustomerID" header-text="Employee ID"></e-column>
            <e-column field="ShipCountry" header-text="ShipCountry"></e-column>
            <e-column field="Freight" header-text="Freight"></e-column>
        </e-columns>
    </ej-grid>

{% endhighlight  %}
{% highlight c# %}

      namespace MVCSampleBrowser.Controllers
          {
            public class GridController : Controller
              { 
                public IActionResult GridFeatures()
                 {
                   var DataSource = new NorthwindDataContext().OrdersViews.ToList();
                   ViewBag.DataSource = DataSource;
                   return View();
                 }
             }
        } 
{% endhighlight  %}    
{% endtabs %}  

The following output is displayed as a result of the previous code example.

![](filtering_images/filtering_img1.png)


## Menu filter

You can enable menu filter by setting the `filter-type` as `Menu` in `e-filter-settings`

There is an option to show or hide the additional filter options in the menu by setting the `show-predicate` as `true` or `false` in `e-filter-settings` respectively.

A specified range of values can be filtered by using the `between` operator for the column type `number`, `date` and `datetime`.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

    <ej-grid id="FlatGrid" allow-paging="true" allow-filtering="true" datasource="ViewBag.DataSource">
        <e-filter-settings filter-type="Menu"/>
        <e-columns>
            <e-column field="OrderID"  header-text="Order ID"></e-column>
            <e-column field="EmployeeID" header-text="Customer ID"></e-column>
            <e-column field="CustomerID" header-text="Employee ID"></e-column>
            <e-column field="ShipCountry" header-text="ShipCountry"></e-column>
            <e-column field="Freight" header-text="Freight"></e-column>
        </e-columns>
    </ej-grid>     

{% endhighlight  %}
{% highlight c# %}

     namespace MVCSampleBrowser.Controllers
        {
            public class GridController : Controller
              { 
                public IActionResult GridFeatures()
                 {
                    var DataSource = new NorthwindDataContext().OrdersViews.ToList();
                    ViewBag.DataSource = DataSource;
                    return View();
                 }
             }
        } 
{% endhighlight  %}    
{% endtabs %}  

The following output is displayed as a result of the previous code example.

![](filtering_images/filtering_img2.png)

Numeric filter

![](filtering_images/filtering_img3.png)

String filter

![](filtering_images/filtering_img4.png)

Date filter

![](filtering_images/filtering_img5.png)

Boolean filter


## Excel-like filter

You can enable excel menu by setting  `filter-type` as` Excel` in `e-filter-settings`. The excel menu contains an option such as Sorting, Clear filter, submenu for advanced filtering.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

    <ej-grid id="FlatGrid" allow-paging="true" allow-filtering="true" datasource="ViewBag.DataSource">
        <e-filter-settings filter-type="Excel"/>
        <e-columns>
            <e-column field="OrderID"  header-text="Order ID"></e-column>
            <e-column field="EmployeeID" header-text="Customer ID"></e-column>
            <e-column field="CustomerID" header-text="Employee ID"></e-column>
            <e-column field="ShipCountry" header-text="ShipCountry"></e-column>
            <e-column field="Freight" header-text="Freight"></e-column>
        </e-columns>
    </ej-grid>

{% endhighlight  %}
{% highlight c# %}

     namespace MVCSampleBrowser.Controllers
        {
            public class GridController : Controller
              { 
                public IActionResult GridFeatures()
                 {
                   var DataSource = new NorthwindDataContext().OrdersViews.ToList();
                   ViewBag.DataSource = DataSource;
                   return View();
                 }
             }
        } 
{% endhighlight  %}    
{% endtabs %}  

The following output is displayed as a result of the previous code example.

![](filtering_images/filtering_img6.png)

### Filtering between values

By using the custom filter feature of the Excel filter, we can filter between values of the column. The following screenshot depicts the usage of "Between" option of the custom filter dialog.

{% include image.html url="filtering_images/filterbetween_img1.png" caption="Selecting between filter option from Excel filter dialog"%}

{% include image.html url="filtering_images/filterbetween_img2.png" caption="Filtering column for between values"%}

### Checkbox list generation:

By default, the checkbox list is generated from distinct values of the filter column from dataSource which gives an option to search and select the required items.

Also on checkbox list generation, if the number of distinct values are greater than 1000, then the excel filter will display only first 1000 values and show "Not all items shown" label to ensure the best performance on rendering and searching. However this limit has been customized according to your requirement by setting `max-filter-choices` with required limit in integer.

N> 1. Using excel filter events you can change the dataSource of the checkbox list. 
N> 2. `Query` of checkbox list can also be changed using excel filter events.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

    <ej-grid id="FlatGrid" allow-paging="true" allow-filtering="true" datasource="ViewBag.DataSource">
        <e-filter-settings filter-type="Excel" max-filter-choices="4" />
        <e-columns>
            <e-column field="OrderID"  header-text="Order ID"></e-column>
            <e-column field="EmployeeID" header-text="Customer ID"></e-column>
            <e-column field="CustomerID" header-text="Employee ID"></e-column>
            <e-column field="ShipCountry" header-text="ShipCountry"></e-column>
            <e-column field="Freight" header-text="Freight"></e-column>
        </e-columns>
    </ej-grid>
                   
{% endhighlight  %}
{% highlight c# %}

     namespace MVCSampleBrowser.Controllers
        {
            public class GridController : Controller
              { 
                public IActionResult GridFeatures()
                 {
                    var DataSource = new NorthwindDataContext().OrdersViews.ToList();
                    ViewBag.DataSource = DataSource;
                    return View();
                 }
             }
        } 
{% endhighlight  %}    
{% endtabs %}  

The following output is displayed as a result of the previous code example.

![](filtering_images/filtering_img7.png)


### Add current selection to filter checkbox:

When filtering is done multiple times on the same column then the previously filtered values on the column will be cleared. So, to retain the old values `Add current selection to filter` checkbox can be used which is displayed when data is searched in the search bar.

The following image describes the previous mentioned behavior.

![](filtering_images/filtering_img12.png)


### Case sensitivity

To perform filter operation with case sensitive in excel styled filter menu mode by setting `enable-case-sensitivity` as `true`.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

    <ej-grid id="FlatGrid" allow-paging="true" allow-filtering="true" datasource="ViewBag.DataSource">
        <e-filter-settings filter-type="Excel" enable-case-sensitivity="true"/>
        <e-columns>
            <e-column field="OrderID"  header-text="Order ID"></e-column>
            <e-column field="EmployeeID" header-text="Customer ID"></e-column>
            <e-column field="CustomerID" header-text="Employee ID"></e-column>
            <e-column field="ShipCountry" header-text="ShipCountry"></e-column>
            <e-column field="Freight" header-text="Freight"></e-column>
        </e-columns>
    </ej-grid>     
    
{% endhighlight  %}
{% highlight c# %}

     namespace MVCSampleBrowser.Controllers
         {
            public class GridController : Controller
              { 
                public IActionResult GridFeatures()
                 {
                    var DataSource = new NorthwindDataContext().OrdersViews.ToList();
                    ViewBag.DataSource = DataSource;
                    return View();
                 }
             }
        } 
{% endhighlight  %}    
{% endtabs %}  

The following output is displayed as a result of the previous code example.

![](filtering_images/filtering_img8.png)


## Filter bar

The `Filter bar` row is located next to column header of grid. You can filter the records with different expressions depending upon the column type. To show the filter bar row, set the `filter-type` as `FilterBar`.

List of filter bar expressions:

You can enter the following filter expressions manually in the filter bar.

 <table>
        <tr>
            <th>
                Expression
            </th>
            <th>
                Example
            </th>
            <th>
                Description
            </th>
            <th>
                Column Type
            </th>
        </tr>
        <tr>
            <td>
                =
            </td>
            <td>
                = value
            </td>
            <td>
                Equal
            </td>
            <td rowspan="5">
                Numeric
            </td>
        </tr>
        <tr>
            <td>
                != 
            </td>
            <td>
                != value
            </td>
            <td>
                NotEqual
            </td>
           
        </tr>
        <tr>
            <td>
                >
            </td>
            <td>
                > value
            </td>
            <td>
                GreaterThan
            </td>
          
        </tr>
        <tr>
            <td>
                <
            </td>
            <td>
                < value
            </td>
            <td>
                LessThan
            </td>
          
        </tr>
        <tr>
            <td>
                >=
            </td>
            <td>
                >= value
            </td>
            <td>
                GreaterThanOrEqual
            </td>
           
        </tr>
        <tr>
            <td>
                <=
            </td>
            <td>
                <= value
            </td>
            <td>
                LessThanOrEqual
            </td>
           
        </tr>
        <tr>
            <td>
                N/A
            </td>
            <td>
                N/A
            </td>
            <td>
                Always `StartsWith` operator will be used for string filter.
            </td>
            <td>
                String
            </td>
        </tr>
        <tr>
            <td>
                N/A
            </td>
            <td>
                N/A
            </td>
            <td>
                Always `Equal` operator will be used for Date filter. 
            </td>
            <td>
                Date
            </td>
        </tr>
        <tr>
            <td>
                N/A
            </td>
            <td>
                N/A
            </td>
            <td>
                Always `Equal` operator will be used for Boolean filter.
            </td>
            <td>
                Boolean
            </td>
        </tr>
    </table>
	
	
The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

    <ej-grid id="FlatGrid" allow-paging="true" allow-filtering="true" datasource="ViewBag.DataSource">
        <e-filter-settings filter-type="FilterBar"/>
        <e-columns>
            <e-column field="OrderID"  header-text="Order ID"></e-column>
            <e-column field="EmployeeID" header-text="Customer ID"></e-column>
            <e-column field="CustomerID" header-text="Employee ID"></e-column>
            <e-column field="ShipCountry" header-text="ShipCountry"></e-column>
            <e-column field="Freight" header-text="Freight"></e-column>
        </e-columns>
    </ej-grid>    
    
{% endhighlight  %}
{% highlight c# %}

     namespace MVCSampleBrowser.Controllers
        {
            public class GridController : Controller
              { 
                public IActionResult GridFeatures()
                 {
                    var DataSource = new NorthwindDataContext().OrdersViews.ToList();
                    ViewBag.DataSource = DataSource;
                    return View();
                 }
             }
        } 
{% endhighlight  %}    
{% endtabs %}  

The following output is displayed as a result of the previous code example.

![](filtering_images/filtering_img9.png)


Filter bar modes:

This specifies the grid to start the filter action while typing in the filter bar or after pressing the enter key based on the `filter-bar-mode`.There are two types of `filter-bar-mode`, they are as follows.

1. OnEnter
2. Immediate


Filter bar message:

The filter bar message is supported only for the `filter-bar-mode` as 'FilterBar'. The filtered data with column name is displayed in the grid pager itself. By default `show-filter-bar-status` is 'true'.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

    <ej-grid id="FlatGrid" allow-paging="true" allow-filtering="true" datasource="ViewBag.DataSource">
        <e-filter-settings show-filter-bar-status="true" />
        <e-columns>
            <e-column field="OrderID"  header-text="Order ID"></e-column>
            <e-column field="EmployeeID" header-text="Customer ID"></e-column>
            <e-column field="CustomerID" header-text="Employee ID"></e-column>
            <e-column field="ShipCountry" header-text="ShipCountry"></e-column>
            <e-column field="Freight" header-text="Freight"></e-column>
        </e-columns>
    </ej-grid>

{% endhighlight  %}
{% highlight c# %}

       namespace MVCSampleBrowser.Controllers
          {
            public class GridController : Controller
              { 
                public IActionResult GridFeatures()
                 {
                   var DataSource = new NorthwindDataContext().OrdersViews.ToList();
                   ViewBag.DataSource = DataSource;
                   return View();
                 }
              }
           } 
{% endhighlight  %}    
{% endtabs %}  

The following output is displayed as a result of the previous code example.

![](filtering_images/filtering_img10.png)


## Filter operators

The grid controls uses filter operators from `DataManager`, which are used at the time of filtering.

List of Column type and Filter operators.

<table>
        <tr>
            <th>
                Column Type
            </th>
            <th>
                Filter Operators
            </th>
        </tr>
        <tr>
            <td rowspan="6">
                Number
            </td>
            <td>
                FilterOperatorType.GreaterThan
            </td>
        </tr>
        <tr>
           
            <td>
                FilterOperatorType.GreaterThanOrEqual
            </td>
        </tr>
        <tr>
       
            <td>
                FilterOperatorType.LessThan
            </td>
        </tr>
        <tr>
            
            <td>
                FilterOperatorType.LessThanOrEqual
            </td>
        </tr>
        <tr>
           
            <td>
                FilterOperatorType.Equal
            </td>
        </tr>
        <tr>
          
            <td>
                FilterOperatorType.NotEqual
            </td>
        </tr>
        <tr>
            <td rowspan="5">
                String
            </td>
            <td>
                FilterOperatorType.StartsWith
            </td>
        </tr>
        <tr>
          
            <td>
                FilterOperatorType.EndsWith
            </td>
        </tr>
        <tr>
           
            <td>
                FilterOperatorType.Contains
            </td>
        </tr>
        <tr>
           
            <td>
                FilterOperatorType.Equal
            </td>
        </tr>
        <tr>
           
            <td>
                FilterOperatorType.NotEqual
            </td>
        </tr>
        <tr>
            <td rowspan="2">
                Boolean
            </td>
            <td>
                FilterOperatorType.Equal
            </td>
        </tr>
        <tr>
            
            <td>
                FilterOperatorType.NotEqual
            </td>
        </tr>
        <tr>
            <td rowspan="6">
                Date
            </td>
            <td>
                FilterOperatorType.GreaterThan
            </td>
        </tr>
        <tr>
            
            <td>
                FilterOperatorType.GreaterThanOrEqual
            </td>
        </tr>
        <tr>
           
            <td>
                FilterOperatorType.LessThan
            </td>
        </tr>
        <tr>
           
            <td>
                FilterOperatorType.LessThanOrEqual
            </td>
        </tr>
        <tr>
           
            <td>
                FilterOperatorType.Equal
            </td>
        </tr>
        <tr>
          
            <td>
                FilterOperatorType.NotEqual
            </td>
        </tr>
    </table>

## FilterBar template

Usually enabling the `allow-filtering`, will create default textbox in grid filterBar. So, Using [`e-filter-bar-template`] property of `e-columns` we can render any other controls like autocomplete, dropdownList etc in filterbar to filter the grid data for the particular column.  
It has three functions. They are as follows.    

1. `create` - It is used to create the control at time of initialize.
2. `read`   - It is used to read the filter value selected.
3. `write`  - It is used to render the control and assign the value selected for filtering.

The following code example describes the previous behavior.
{% tabs %}

{% highlight razor %}
 <ej-grid  id="FlatGrid" datasource=ViewBag.datasource allow-paging="true" allow-filtering="true">
     <e-columns>
        <e-column field="OrderID" header-text="Order ID" />
        <e-column field="CustomerID" header-text="Customer ID">
            <e-filter-bar-template read="autoComplete_read" create="autoComplete_create" write="autoComplete_write"/>
        </e-column>
        <e-column field="EmployeeID" header-text="Employee ID">
            <e-filter-bar-template read="dropdown_read" write="dropdown_write" />
        </e-column>
        <e-column field="ShipCity" header-text="Ship City" />       
        <e-column field="ShipAddress"  header-text="Ship Address"/>
   </e-columns>
</ej-grid>
{% endhighlight  %}

{% highlight js %}
     <script type="text/javascript">      
    function autoComplete_create(args) {
        return "<input>"
    }
    function autoComplete_write(args) {
        var gridObj = $('#FlatGrid ').data("ejGrid");
        var data = ej.DataManager(gridObj.model.dataSource).executeLocal(new ej.Query().select("CustomerID"));
        args.element.ejAutocomplete({ width: "100%", dataSource: data, enableDistinct: true, focusOut: ej.proxy(args.column.filterBarTemplate.read, this, args) });
    }
    function autoComplete_read(args) {
        this.filterColumn(args.column.field, "equal", args.element.val(), "and", true)
    }
    function dropdown_write(args) {
        var data = [{ text: "clear", value: "clear" }, { text: "1", value: 1 }, { text: "2", value: 2 }, { text: "3", value: 3 }, { text: "4", value: 4 },
                                                        { text: "5", value: 5 }, { text: "6", value: 6 }, { text: "7", value: 7 }, { text: "8", value: 8 }, { text: "9", value: 9 }
        ]
        args.element.ejDropDownList({ width: "100%", dataSource: data, change: ej.proxy(args.column.filterBarTemplate.read, this, args) })
    }
    function dropdown_read(args) {
        if (args.element.val() == "clear") {
            this.clearFiltering(args.column.field);
            args.element.val("")
        }
        this.filterColumn(args.column.field, "equal", args.element.val(), "and", true)
    }
    </script>
{% endhighlight %}

{% highlight c# %}

        namespace MVCSampleBrowser.Controllers
          {
            public class GridController : Controller
              { 
                public IActionResult GridFeatures()
                 {
                   var DataSource = new NorthwindDataContext().OrdersViews.ToList();
                   ViewBag.DataSource = DataSource;
                   return View();
                 }
              }
           } 

{% endhighlight  %}
    
{% endtabs %}

The following output is displayed as a result of the previous code example.


![](filtering_images/filtering_img11.png)
{:caption}
After Filtering
