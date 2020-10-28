---
layout: post
title: Grouping with grid widget for Syncfusion Essential ASP.NET Core
description: How to enable grouping and its functionalities
platform: aspnet-core
control: Grid
documentation: ug
---
# Grouping

The Grid control has options to group the records based on the required column. When grouping is applied, grouped records are organized into a hierarchical structure to facilitate easier expand and collapse of records. To enable grouping, set the `allow-grouping` property as `true`.

Columns can be grouped by simply dragging the column header and drop on the group drop area or simply click the group button which is displayed in the column. By default, sorting is done while grouping the column.

The following code example describes the previous behavior.
 
{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" allow-grouping="true" datasource="ViewBag.DataSource">
        <e-columns>
            <e-column field="OrderID" header-text="Order ID"></e-column>
            <e-column field="EmployeeID" header-text="Employee ID"></e-column>
            <e-column field="CustomerID" header-text="Customer ID"></e-column>
            <e-column field="ShipCountry" header-text="Ship Country"></e-column>
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

![](Grouping_images/Grouping_img1.png)


## Initial grouping

While initializing the grid itself, there is an option to group the column and display it in a hierarchical structure. To enable initial grouping, set array of column's `field` name to be grouped in `GroupedColumns` property  of `group-settings`.

The following code example describes the previous behavior.
            
{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" allow-grouping="true" group-settings ="@(new GroupSettings { GroupedColumns= new List<string>() { "ShipCountry" } })" datasource="ViewBag.DataSource">
        <e-columns>
            <e-column field="OrderID" header-text="Order ID"></e-column>
            <e-column field="EmployeeID" header-text="Employee ID"></e-column>
            <e-column field="CustomerID" header-text="Customer ID"></e-column>
            <e-column field="ShipCountry" header-text="Ship Country"></e-column>
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

![](Grouping_images/Grouping_img2.png)


## Multi-Column grouping

Group multiple columns by simply drag and drop the columns one by one from column header into group drop area.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" allow-grouping="true" group-settings ="@(new GroupSettings { GroupedColumns= new List<string>() { "ShipCountry","CustomerID"} })" datasource="ViewBag.DataSource">
       <e-columns>
            <e-column field="OrderID" header-text="Order ID"></e-column>
            <e-column field="EmployeeID" header-text="Employee ID"></e-column>
            <e-column field="CustomerID" header-text="Customer ID"></e-column>
            <e-column field="ShipCountry" header-text="Ship Country"></e-column>
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

![](Grouping_images/Grouping_img3.png)


## Group buttons

To do grouping easily without doing drag and drop column header by setting `ShowToggleButton` property of `group-settings` as `true`.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" allow-grouping="true" group-settings ="@(new GroupSettings { ShowToggleButton=true })" datasource="ViewBag.DataSource">
       <e-columns>
            <e-column field="OrderID" header-text="Order ID"></e-column>
            <e-column field="EmployeeID" header-text="Employee ID"></e-column>
            <e-column field="CustomerID" header-text="Customer ID"></e-column>
            <e-column field="ShipCountry" header-text="Ship Country"></e-column>
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

![](Grouping_images/Grouping_img4.png)


## Hide ungroup button

Hide ungroup button from grouped columns which is in the group drop area by setting the `ShowUngroupButton` property of `group-settings` as `false`.

The following code example describes the previous behavior.


{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" allow-grouping="true" group-settings ="@(new GroupSettings { ShowUngroupButton=false })" datasource="ViewBag.DataSource">
       <e-columns>
            <e-column field="OrderID" header-text="Order ID"></e-column>
            <e-column field="EmployeeID" header-text="Employee ID"></e-column>
            <e-column field="CustomerID" header-text="Customer ID"></e-column>
            <e-column field="ShipCountry" header-text="Ship Country"></e-column>
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

![](Grouping_images/Grouping_img5.png)


## Hide grouped column

While grouping a particular column, there is an option to hide the grouped columns from grid. To enable hide grouped column option, set the `ShowGroupedColumn` property of `group-settings` as `false`.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" allow-grouping="true" group-settings ="@(new GroupSettings { ShowGroupedColumn=false })" datasource="ViewBag.DataSource">
        <e-columns>
            <e-column field="OrderID" header-text="Order ID"></e-column>
            <e-column field="EmployeeID" header-text="Employee ID"></e-column>
            <e-column field="CustomerID" header-text="Customer ID"></e-column>
            <e-column field="ShipCountry" header-text="Ship Country"></e-column>
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

![](Grouping_images/Grouping_img6.png)


## AutoSize drop area

Drag any column header and move it to the group drop area, then its portion expands smoothly. Stop this animation by setting the `EnableDropAreaAutoSizing` property of `group-settings` as `false`.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" allow-grouping="true" group-settings ="@(new GroupSettings { EnableDropAreaAutoSizing=false })" datasource="ViewBag.DataSource">
        <e-columns>
            <e-column field="OrderID" header-text="Order ID"></e-column>
            <e-column field="EmployeeID" header-text="Employee ID"></e-column>
            <e-column field="CustomerID" header-text="Customer ID"></e-column>
            <e-column field="ShipCountry" header-text="Ship Country"></e-column>
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

![](Grouping_images/Grouping_img7.png)


## Hide drop area 

To avoid ungrouping or further grouping of a column after an initial column grouping by setting `ShowDropArea` property of `group-settings` as `false`.

The following code example describes the previous behavior.
 
{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" allow-grouping="true" group-settings ="@(new GroupSettings { GroupedColumns= new List<string>() { "ShipCountry" }, ShowDropArea=false })" datasource="ViewBag.DataSource">
       <e-columns>
            <e-column field="OrderID" header-text="Order ID"></e-column>
            <e-column field="EmployeeID" header-text="Employee ID"></e-column>
            <e-column field="CustomerID" header-text="Customer ID"></e-column>
            <e-column field="ShipCountry" header-text="Ship Country"></e-column>
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

![](Grouping_images/Grouping_img8.png)


## Group caption format/group caption template

Using the `CaptionFormat` property of `group-settings` you can render any type of JsRender templates or customizing the group caption text. 

You can use JsRender syntax in the template.For more information about JsRender syntax, please refer to [the link](http://www.jsviews.com/#jsrapi "the link").

N>  1. It's a standard way to enclose the `template` within the `script` tag with `type` as "text/x-jsrender". 
N>  2. Using locale property of `CaptionFormat`, you can only customize the default group caption text.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" allow-grouping="true" action-complete="complete" group-settings ="@(new GroupSettings { CaptionFormat="#template" })" datasource="ViewBag.DataSource">
        <e-columns>
            <e-column field="OrderID" header-text="Order ID"></e-column>
            <e-column field="EmployeeID" header-text="Employee ID"></e-column>
            <e-column field="CustomerID" header-text="Customer ID"></e-column>
            <e-column field="ShipCountry" header-text="Ship Country"></e-column>
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

{% highlight js %}            
     
     <script id="template" type="text/x-jsrender">
                "{{"{{"}}:field{{}}}}-"{{"{{"}}:key{{}}}}
                  <button id="btn" class="btn">Collapse</button>
     </script>

     <script>
             function complete(args) {
                 $(".btn").ejButton({
                 click: "btnClick"
                });
             }
             function btnClick(args) {
                 var gridObj = $("#FlatGrid").data("ejGrid");
                 gridObj.expandCollapse(this.element.parent().prev());
                 $("#btn").ejButton("model.text", args.model.text == "Collapse" ? "Expand" : "Collapse");
             }
    </script>    

{% endhighlight  %}    
   
{% endtabs %}

The following output is displayed as a result of the previous code example.

![](Grouping_images/Grouping_img9.png)

![](Grouping_images/Grouping_img10.png)

## Handling grouped records count in server-side    

When binding remote data to grid with on-demand data loading, only current page data knowledge is available to grid and so grouped records count would be shown based on current Page only. 

This can be rectified when binding data to grid using [UrlAdaptor](https://help.syncfusion.com/aspnet-core/grid/data-adaptors#url-adaptor) of DataManager. The grouped column values should be passed into the `groupDs` property of return object from server-side along with datasource and count.

The following code example describes the above behavior.

{% tabs %}
 
{% highlight razor %}

<ej-grid id="FlatGrid" allow-paging="true" allow-sorting="true" allow-grouping="true" group-settings ="@(new GroupSettings { GroupedColumns= new List<string>() { "EmployeeID" } })">
        <e-datamanager url="/Grid/UrlDataSource" adaptor="UrlAdaptor"></e-datamanager>
        <e-columns>
            <e-column field="OrderID" header-text="Order ID" text-align="Right" width="75"></e-column>
            <e-column field="CustomerID" header-text="Customer ID" width="80"></e-column>
            <e-column field="EmployeeID" header-text="Employee ID" text-align="Right" width="75"></e-column>
            <e-column field="Freight" header-text="Freight" text-align=Right format="{0:C}" width="75"></e-column>
            <e-column field="OrderDate" header-text="Order Date" text-align=Right  format="{0:MM/dd/yyyy}" width="110"></e-column>
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
                   var DataSource = new NorthwindDataContext().OrdersViews.ToList();
                   ViewBag.DataSource = DataSource;
                   return View();
                 }
                public ActionResult UrlDataSource(DataManager dm)
                 {
                    IEnumerable DataSource = new NorthwindDataContext().OrdersViews.ToList();
                    int count = DataSource.AsQueryable().Count();
                    IEnumerable GroupDs = new List<object>(); ;
                    DataOperations ds = new DataOperations();
                    List<string> str = new List<string>();
                    if (dm.Group != null)
                        GroupDs = ds.PerformSelect(DataSource, dm.Group); //Pass grouped column records grouping
                    if (dm.Sorted != null)
                        DataSource = ds.PerformSorting(DataSource, dm.Sorted);
                    DataSource = ds.PerformSkip(DataSource, dm.Skip);
                    DataSource = DataSource.AsQueryable().Take(dm.Take);
                    return Json(new {result = DataSource, count = count, groupDs = GroupDs });
                 }  
             }     
        } 
{% endhighlight  %}   
{% endtabs %}  

The following output is displayed as a result of the above code example.

![](Grouping_images/Grouping_img11.png)