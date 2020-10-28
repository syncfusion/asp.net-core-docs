---
layout: post
title: Columns with grid widget for Syncfusion Essential ASP.NET Core
description: columns
platform: aspnet-core
control: Grid
documentation: ug
---

# Columns

The column definitions are used as the DataSource schema in the Grid and it plays vital role in rendering column values in required format and sorting, filtering, editing based on its type. The `field` property of the columns is necessary to map the datasource values in grid columns.

N> 1. The column with `field` which are not in the datasource, then the column values will be displayed as empty.
N> 2. If the `field` name contains "dot" then it is considered as complex binding.


## Auto generation

The columns are automatically generated when `columns` declaration is empty or undefined while initializing the grid. Also, all the columns which are in `dataSource` are bound as a grid `e-columns`.

{% tabs %}
{% highlight razor %}

  <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
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

![](columns_images/columns_img1.png)

### How to set the `is-primary-key` for auto generated columns when editing is enabled:

Using the `data-bound` event, you can set `is-primary-key` value as `true` by two ways. The following code example demonstrates the previous behavior.

1. If primary key "column index" is known then refer to the following code example.

{% tabs %}
{% highlight razor %}

  <ej-grid id="FlatGrid" allow-paging="true" data-bound="dataBound" datasource="ViewBag.DataSource">
  <e-edit-settings allow-editing="true"></e-edit-settings>
  </ej-grid>
  <script type="text/javascript">
        function dataBound(args) {
            var column = args.model.columns[0];
            //(or)
            var column = this.getColumnByIndex(0);
            column.isPrimaryKey = true;
            //Here columns method used to update the particular column
            this.columns(column, "update");
      }
    </script>                
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

2. If primary key "column field name" is known then refer to the following code example.

{% tabs %}
{% highlight razor %}

  <ej-grid id="FlatGrid" allow-paging="true" data-bound="dataBound" datasource="ViewBag.DataSource">
  <e-edit-settings allow-editing="true"></e-edit-settings>
  </ej-grid>
   <script type="text/javascript">
        function dataBound(args) {
            var column = this.getColumnByField("OrderID");
            column.isPrimaryKey = true;
            //Here columns method used to update the particular column
            this.columns(column, "update");
        }
    </script>              
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


## Headers

### Header text

It represents the title for particular column. To enable header text, set `header-text` property of `e-columns`. The following code example describes the previous behavior.

N> If `header-text` is not defined then the `field` name is considered as header text for that particular column. If `field` name and `header-text` also not defined then the column is rendered with "empty" header text.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

    <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
        <e-columns>
            <e-column field="OrderID"  header-text="Order ID"></e-column>
            <e-column field="EmployeeID" header-text="Emp ID"></e-column>
            <e-column field="Freight" header-text="Freight"></e-column>
            <e-column field="ShipCountry" header-text="Country"></e-column>
            <e-column field="ShipCity" header-text="City"></e-column>
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

![](columns_images/columns_img2.png)

### Header text alignment

Align the header text of column header using the `header-text-align` property of the `e-columns`. There are four possible ways to align header text, they are as follows.

1. Right
2. Left
3. Center
4. Justify

N> For `HeaderTextAlign` property you can assign `enum` value (`TextAlign.Right`).

The following code example describes the previous behavior.
 
{% tabs %}
{% highlight razor %}

    <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
        <e-columns>
            <e-column field="OrderID"  header-text="Order ID" ></e-column>
            <e-column field="EmployeeID" header-text="Emp ID" header-text-align="Right"></e-column>
            <e-column field="Freight" header-text="Freight"></e-column>
            <e-column field="ShipCountry" header-text="Country" header-text-align="Center"></e-column>
            <e-column field="ShipCity" header-text="City" header-text-align="Right" ></e-column>
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

![](columns_images/columns_img3.png)


### Header template

The template design that applies on for the column header. To render template, `header-template-id` property of `e-columns`.

The JsRender syntax can be used in the template. For more information about JsRender syntax, please refer [the link](http://www.jsviews.com/#jsrapi "the link").

N> It's a standard way to enclose the `template` within the `script` tag with `type` as `text/x-jsrender`.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

    <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
        <e-columns>
            <e-column field="OrderID"  header-text="Order ID" ></e-column>
            <e-column field="EmployeeID" header-template-id="#empTemplate"></e-column>
            <e-column field="Freight" header-text="Freight"></e-column>
            <e-column field="ShipCountry" header-text="Country"></e-column>
            <e-column field="ShipCity" header-text="City"></e-column>
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
{% highlight js %}
        <script id="empTemplate" type="text/x-jsrender">
          Emp ID
          <span class="e-userlogin e-icon employee"></span>
        </script>
{% endhighlight %}   
{% endtabs %}  



## Text alignment

The content and header text of a particular column can be aligned using the `text-align` property. There are four possible ways to align content and header text of column, they are as follows.

1. Right
2. Left
3. Center
4. Justify

N> 1. For the `text-align` property, `enum` value (`TextAlign.Right`) can be assigned.
N> 2. The `text-align` property will affect both content and header text of the grid.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

    <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
        <e-columns>
            <e-column field="OrderID" text-align="Right"></e-column>
            <e-column field="EmployeeID" text-align="Right"></e-column>
            <e-column field="Freight"text-align="Right"></e-column>
            <e-column field="ShipCountry" text-align="Center"></e-column>
            <e-column field="ShipCity"text-align="Justify"></e-column>
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

![](columns_images/columns_img5.png)

## Format

Format is the process of customizing the particular column data with specified jQuery recognized globalize formats, such as currency, numeric, decimal, percentage or dates. To specify the globalize format, by using Format property of `e-columns`.

The `format` value should be wrapped within "{0:" and "}". (For ex: "{0:C3}"). The [data format](https://github.com/jquery/globalize/tree/v0.1.1#format "data format") strings available for the `Date` and `Number` types.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

    <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
        <e-columns>
            <e-column field="OrderID"></e-column>
            <e-column field="EmployeeID"></e-column>
            <e-column field="Freight" format="{0:C2}"></e-column>
            <e-column field="OrderDate" format="{0:dd/MM/yyyy}"></e-column>
            <e-column field="ShipCity"></e-column>
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

![](columns_images/columns_img6.png)

## Width

The width for a particular column can be specified by setting `width` property of `e-columns` as in pixel (ex: 100) or in percentage (ex: 40%).

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

    <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
        <e-columns>
            <e-column field="OrderID" width=@("10%")></e-column>
            <e-column field="EmployeeID" width=@("15%")></e-column>
            <e-column field="Freight" width="100"></e-column>
            <e-column field="ShipCity" width="150"></e-column>
            <e-column field="ShipCountry" width="100"></e-column>
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

![](columns_images/columns_img7.png)


## Resizing


The `allow-resizing` property enables the grid to set the width to columns based on resizing the grid column manually.


### Resizing modes


`resizeMode` property of `e-resize-settings` is used to change the resizing modes. It indicates whether to define mode of resizing.


<table>
<tr>
<th>Name</th>
<th>Description</th>
</tr>
<tr>
<td class="name">Normal</td>
<td class="description">New column size will be adjusted by all other Columns</td>
</tr>
<tr>
<td class="name">NextColumn</td>
<td class="description">New column Size will be adjusted using next column.</td>
</tr>
<tr>
<td class="name">Control</td>
<td class="description">New column Size will be adjusted using entire control</td>
</tr>
</table>


The following code example describes the above behavior.


{% tabs %}
{% highlight razor %}


<ej-grid id="Grid" datasource=ViewBag.parent allow-resizing="true">
    <e-resize-settings resize-mode="NextColumn"></e-resize-settings>
    <e-columns>
        <e-column field="ShipCity" header-text="Ship City" text-align="Right" width="80"></e-column>
        <e-column field="ShipPostalCode" header-text="Ship Postal Code" width="40"></e-column>
        <e-column field="ShipName" header-text="Ship Name" width="40"></e-column>
        <e-column field="ShipAddress" header-text="Ship Address" width="100"></e-column>
    </e-columns>
</ej-grid>


{% endhighlight  %}
{% highlight c# %}


namespace MVCSampleBrowser.Controllers
{
    public partial class GridController : Controller
    {
      List<Orders> order = new List<Orders>();
        public ActionResult GridFeatures()
        {
            ViewBag.datasource = Orders;
            return View();
        }

    }
}


{% endhighlight  %} 
{% endtabs %} 


## Resize to fit 

The `allow-resize-to-fit` property enable the grid to set width to columns based on maximum width of the particular column's content to facilitate full visibility of data in all the grid rows and this automatic behavior is applicable only for the columns which does not have width specified. 

On columns where "width is defined", double-click on the particular column header's resizer symbol to resize the column to show the whole text. For example, refer to the "ShipCity" column in the below code snippet and output screenshot. 

The following code example describes the previous behavior. 


{% tabs %}
{% highlight razor %}

    <ej-grid id="FlatGrid" allow-paging="true" allow-resize-to-fit="true" datasource="ViewBag.DataSource">
        <e-columns>
            <e-column field="OrderID" width="100"></e-column>
            <e-column field="EmployeeID"></e-column>
            <e-column field="Freight" width="75"></e-column>
            <e-column field="ShipCity" width="50"></e-column>
            <e-column field="ShipAddress"></e-column>
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

![](columns_images/columns_img8.png)


## Reorder

Reordering can be done by drag and drop of the particular column header from one index to another index within the grid. Reordering can be enabled by setting the `allow-reordering` property as `true`.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

    <ej-grid id="FlatGrid" allow-paging="true" allow-reordering="true" datasource="ViewBag.DataSource">
        <e-columns>
            <e-column field="OrderID"></e-column>
            <e-column field="EmployeeID"></e-column>
            <e-column field="ShipCity"></e-column>
            <e-column field="ShipCountry"></e-column>
            <e-column field="Freight"></e-column>
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

![](columns_images/columns_img10.png)

## Visibility

The particular column in the grid view can be hid by setting the `visible` property of it as `false`.

The following code example describes the previous behavior.
 
{% tabs %}
{% highlight razor %}

    <ej-grid id="FlatGrid" allow-paging="true" allow-reordering="true" datasource="ViewBag.DataSource">
        <e-columns>
            <e-column field="EmployeeID"></e-column>
            <e-column field="OrderID" visible="false"></e-column>
            <e-column field="Freight"></e-column>
            <e-column field="ShipCity"></e-column>
            <e-column field="ShipCountry"></e-column>
            
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

![](columns_images/columns_img11.png)


## Unbound Column

You can define the unbound columns in grid by not defining `field` property for that particular. Value for this columns can be populated either manually using `query-cell-info` event or by using `column-template`.

N> Editing, grouping, filtering, sorting, summary and searching support are not available for unbound columns.

The following code example describes the previous behavior. 

{% tabs %}
{% highlight razor %}

    <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
       <e-edit-settings allow-deleting="true"/>
        <e-columns>
            <e-column field="OrderID" is-primary-key="true"></e-column>
            <e-column field="EmployeeID"></e-column>
            <e-column field="CustomerID"></e-column>
            <e-column field="Freight"></e-column>
            <e-column header-text="" format="<a onclick = click(this) href=#>Delete</a>"></e-column>
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
{% highlight js %}
    <script type="text/javascript">
        function click(e) {
            var obj = $("#FlatGrid").data("ejGrid");
            obj.deleteRecord("OrderID", obj.getSelectedRecords()[0]);
        }
    </script>
{% endhighlight  %}
{% endtabs %}  

The following output is displayed as a result of the previous code example.

![](columns_images/columns_img13.png)

## Controlling grid actions

You can control the grid actions of a particular column by setting `allow-sorting`,`allow-grouping`, `allow-filtering` and `allow-editing` properties of it as `false`.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

    <ej-grid id="FlatGrid" allow-paging="true" allow-resizing="true" allow-sorting="true" allow-grouping="true" allow-filtering="true" datasource="ViewBag.DataSource">
       <e-edit-settings allow-editing="true"/>
        <e-columns>
            <e-column field="OrderID" is-primary-key="true"></e-column>
            <e-column field="EmployeeID" allow-editing="false" allow-resizing="false" allow-sorting="false" allow-grouping="false"></e-column>
            <e-column field="Freight"></e-column>
            <e-column field="ShipCity"></e-column>
            <e-column field="ShipCountry"></e-column>
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

## Read only

To make a column as "read-only" then set the `allow-editing` property of `e-columns` as `false`.

The following code example describes the previous behavior. 

{% tabs %}
{% highlight razor %}

    <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
       <e-edit-settings allow-editing="true"/>
        <e-columns>
            <e-column field="OrderID" is-primary-key="true"></e-column>
            <e-column field="EmployeeID" allow-editing="false"></e-column>
            <e-column field="Freight"></e-column>
            <e-column field="ShipCity"></e-column>
            <e-column field="ShipCountry"></e-column>
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

![](columns_images/columns_img15.png)


## Command column

### Default action buttons

Using Command column, you can add `CRUD` action buttons as one of the grid column, through `type` property of `e-column-command`. The `type` property supports the below default buttons.

1. Edit
2. Save
3. Delete
4. Cancel

Through the `e-button-options` property of `e-column-commands`, you can specify all the button options which are supported by Essential Studio ASP.NET MVC button control. 

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

    <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
       <e-edit-settings allow-editing="true" allow-deleting="true" allow-adding="true"/>
        <e-columns>
            <e-column field="OrderID" is-primary-key="true"></e-column>
            <e-column field="EmployeeID"></e-column>
            <e-column field="Freight" edit-type="NumericEdit"></e-column>
            <e-column field="ShipCountry"></e-column>
            <e-column header-Text="Manage Records">
              <e-column-commands>
                <e-column-command type="edit">
                    <e-button-options content-type="TextOnly" text="Edit"></e-button-options>
                </e-column-command>
                <e-column-command type="delete">
                    <e-button-options content-type="TextOnly" text="Delete"></e-button-options>
                </e-column-command>
                <e-column-command type="save">
                    <e-button-options content-type="TextOnly" text="Save"></e-button-options>
                </e-column-command>
                <e-column-command type="cancel">
                    <e-button-options content-type="TextOnly" text="Cancel"></e-button-options>
                </e-column-command>
              </e-column-commands>  
             </e-column>
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

![](columns_images/columns_img17.png)

### Custom buttons

You can add custom button in the command column by specifying the `type` property of `e-column-commands` as `empty` or any other `string` instead of `enum` values.

N> 1. For `type` property, you can assign `string` value (`edit`).
N> 2. In command column you can add only buttons.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

        @(Html.EJ().Grid<Object>("FlatGrid")
                .Datasource((IEnumerable<object>)ViewBag.DataSource)
                .AllowPaging()
                .Columns(col =>
                {
                    col.Field("EmployeeID").Add();
                    col.HeaderText("Employee Details").Commands(command =>
                     {
                        command.Type("detail")
                            .ButtonOptions(new Syncfusion.JavaScript.Models.ButtonProperties()
                            {
                                Text = "Details",
                                Width = "100px",
                                Click = "onClick"
                            }).Add();
                    })                
                .TextAlign(TextAlign.Center)
                .Width(150)
                .Add();
                })
                )   
{% endhighlight  %}
{% highlight c# %}

     namespace MVCSampleBrowser.Controllers
      {
        public class GridController : Controller
         { 
           public ActionResult GridFeatures()
             {
               var DataSource = new NorthwindDataContext().OrdersView.ToList();
               ViewBag.DataSource = DataSource;
               return View();
             }
         }
      }
{% endhighlight  %}
{% endtabs %} 

{% tabs %}
{% highlight razor %}

    <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
         <e-columns>
            <e-column field="EmployeeID"></e-column>
            <e-column header-Text="Employee Details">
              <e-column-commands>
                <e-column-command type="details">
                    <e-button-options content-type="TextOnly" text="Edit"></e-button-options>
                </e-column-command>
              </e-column-commands>  
             </e-column>
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
{% highlight js %}
            <script type="text/javascript">
               function onClick(args) {
                 var grid = $("#FlatGrid").ejGrid("instance");
                 var index = this.element.closest("tr").index();
                 var record = grid.getCurrentViewData()[index];
                 alert("Record Details: " + JSON.stringify(record));
               }
           </script> 
{% endhighlight  %}
{% endtabs %}  

The following output is displayed as a result of the previous code example.

![](columns_images/columns_img18.png)


## Column chooser

Column chooser contains all the columns which are defined in the `e-columns` property, using this you can control the visibility of columns in grid. You can prevent to show the particular column in column chooser by setting `show-in-column-chooser` property of `e-columns` as `false`. It can be shown in the right corner of grid. To enable column chooser, `show-column-chooser` property as `true`. 

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

    <ej-grid id="FlatGrid" allow-paging="true" show-column-chooser="true" datasource="ViewBag.DataSource">
       <e-edit-settings allow-editing="true"/>
        <e-columns>
            <e-column field="OrderID" is-primary-key="true"></e-column>
            <e-column field="EmployeeID" show-in-column-chooser="false"></e-column>
            <e-column field="Freight"></e-column>
            <e-column field="ShipCity"></e-column>
            <e-column field="ShipCountry"></e-column>
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

![](columns_images/columns_img19.png)

## Foreign key column

Lookup data source can be bound to the `data-source` property of `e-columns`. Data `field` and `text` can be set using `foreign-key-field` and `foreign-key-value` property of `e-columns`.

In the `data-source` property, we can bound local and remote data.

I> For foreign key column the sorting and grouping is based on `foreign-key-field` instead of `foreign-key-value`.You can refer [Foreign Key Adaptor](https://help.syncfusion.com/aspnet-core/grid/data-adaptors#foreign-key-adaptor) to sort and group the foreign key column based on `ForeignKeyValue`.

N> In remote data, server should be configured to perform select and filter operations since the grid will try to fetch required columns using select operation and required data using filter operation.

N> To render a Hierarchy Grid with different `foreign-key-field` in parent and child table, click [`here`](https://help.syncfusion.com/aspnet-core/grid/how-to#hierarchy-grid-with-different-foreignkeyfield-in-parent-and-child-table "here").

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

    <ej-grid id="FlatGrid" allow-paging="true" datasource="@ViewBag.DataSource1">
       <e-edit-settings allow-editing="true" allow-adding="true" allow-editing="true"/>
        <e-columns>
            <e-column field="OrderID" is-primary-key="true"></e-column>
            <e-column field="EmployeeID" header-text="first Name" foreign-key-field="EmployeeID" foreign-key-value="FirstName" datasource="@ViewBag.DataSource2"></e-column>
            <e-column field="CustomerID"></e-column>
            <e-column field="Freight"></e-column>
            <e-column field="ShipCity"></e-column>
        </e-columns>
    </ej-grid>
                   
{% endhighlight  %}
{% highlight c# %}

       namespace MVCSampleBrowser.Controllers
        {
         public class GridController : Controller
          { 
           public ActionResult GridFeatures()
             {
                var DataSource1 = new NorthwindDataContext().OrdersViews.ToList();
                ViewBag.DataSource1 = DataSource1;
                var DataSource2 = new NorthwindDataContext().EmployeeViews.ToList();
                ViewBag.DataSource2 = DataSource2;    
                return View();
            }
        }
      }
{% endhighlight  %}
{% endtabs %} 

The following output is displayed as a result of the previous code example.

![](columns_images/columns_img20.png)

## Customize column

You can customize the header and content of that particular column by `css-class` property of the column.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

    <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
        <e-columns>
            <e-column field="OrderID"></e-column>
            <e-column field="CustomerID" css-class="customCss"></e-column>
            <e-column field="EmployeeID"></e-column>
            <e-column field="Freight"></e-column>
        </e-columns>
    </ej-grid>
                   
{% endhighlight  %}
{% highlight c# %}

      namespace MVCSampleBrowser.Controllers
       {
         public class GridController : Controller
          { 
            public ActionResult GridFeatures()
             {
                var DataSource1 = new NorthwindDataContext().OrdersViews.ToList();
                ViewBag.DataSource = DataSource1;
                return View();
             }
          }
       }
{% endhighlight  %}
{% highlight css %}

    .customCss.e-headercell {
        background-color: #2382c3;
        color: white;
        font-family: 'Bell MT';
        font-size: 20px;
    }
    
    .customCss.e-rowcell {
        background-color: #ecedee;
        font-family: 'Bell MT';
        color: red;
        font-size: 20px;
    }
{% endhighlight %}
{% endtabs %} 

The following output is displayed as a result of the previous code example.

![](columns_images/columns_img23.png)

## Type

Used to define the type of the particular column data. If the `type` property of `e-columns` is not specified then its type is automatically defined based on the first row data of that column.

N> The `type` is needed for filtering feature when first row of the data is `null` or `empty`.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

    <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
        <e-columns>
            <e-column field="OrderID"></e-column>
            <e-column field="CustomerID" type="string"></e-column>
            <e-column field="EmployeeID" type="number"></e-column>
            <e-column field="Freight"></e-column>
            <e-column field="ShipCountry"></e-column>
        </e-columns>
    </ej-grid>
                   
{% endhighlight  %}
{% highlight c# %}

       namespace MVCSampleBrowser.Controllers
        {
          public class GridController : Controller
           { 
             public ActionResult GridFeatures()
              {
                var DataSource1 = new NorthwindDataContext().OrdersViews.ToList();
                ViewBag.DataSource = DataSource1;
                return View();
              }
           }
         }
{% endhighlight  %}
{% endtabs %} 

The following output is displayed as a result of the previous code example.

![](columns_images/columns_img24.png)

## Column layout

You can set the grid's columns layout based on either grid width or its columns width using `column-layout` property of it. There are two ways to set the column layout, they are as follows.

1. Auto
2. Fixed

{% tabs %}
{% highlight razor %}

    <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource" column-layout="Fixed">
        <e-columns>
            <e-column field="OrderID" width="80"></e-column>
            <e-column field="EmployeeID" width="80"></e-column>
            <e-column field="ShipCity" width="90"></e-column>
            <e-column field="ShipName" width="110"></e-column>
            <e-column field="ShipCountry" width="100"></e-column>
            <e-column field="Freight" width="80"></e-column>
        </e-columns>
    </ej-grid>
                   
{% endhighlight  %}
{% highlight c# %}

       namespace MVCSampleBrowser.Controllers
        {
          public class GridController : Controller
           { 
             public ActionResult GridFeatures()
              {
                var DataSource1 = new NorthwindDataContext().OrdersViews.ToList();
                ViewBag.DataSource = DataSource1;
                return View();
              }
           }
         }
{% endhighlight  %}
{% endtabs %} 


The following output is displayed as a result of the previous code example.

![](columns_images/columns_img25.png)

