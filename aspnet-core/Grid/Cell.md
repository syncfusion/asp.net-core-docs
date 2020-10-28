---
layout: post
title: Cell with Grid widget for Syncfusion Essential ASP.NET Core
description: How to use and customize the grid cells
platform: aspnet-core
control: Grid
documentation: ug
---

# Cell

## Auto wrap 

The auto wrap enables the Grid to wrap cell content or header content to next line when the content exceeds the boundary of the cell width. To enable auto wrap, set the `allow-text-wrap` property as `true`. 

The mode of auto wrap can be specified using the `wrap-mode` property of `e-text-wrap-settings`. 

The three types of `wrap-mode` available are as follows.
  
 1. Both
 2. Header
 3. Content 
 
N> 1. The `wrap-mode` by default  will be set as `Both`. 
N> 2. While using the `e-text-wrap-settings` then it is must to set the `allow-text-wrap` as `true`.
N> 3. For the `wrapMode` property you can assign `enum` value (`Syncfusion.JavaScript.WrapMode.Both`).
 
## Both

When the `wrap-mode` of `e-text-wrap-settings` property is set as `Both` then the auto wrap will be enabled for both the Grid content and header. 

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" allow-text-wrap="true" datasource="ViewBag.DataSource">
       <e-text-wrap-settings wrap-mode="Both"></e-text-wrap-settings>
        <e-columns>
            <e-column field="OrderID" header-text="OrderID" width="90"></e-column>
            <e-column field="EmployeeID" header-text="EmployeeID" width="100"></e-column>
            <e-column field="Freight" header-text="Freight" width="100"></e-column>
            <e-column field="ShipCity" header-text="ShipCity"  width="90"></e-column>
            <e-column field="ShipAddress" header-text="Ship Address" width="110"></e-column>
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

![Both Wrap Mode](Cell_images/Cell_img1.png)

### Header

When the `wrap-mode` of `e-text-wrap-settings` property is set as `Header` then the auto wrap will be enabled only for the Grid header alone. 

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" allow-text-wrap="true" datasource="ViewBag.DataSource">
       <e-text-wrap-settings wrap-mode="Header"/>
        <e-columns>
            <e-column field="OrderID" header-text="OrderID" width="90"></e-column>
            <e-column field="EmployeeID" header-text="EmployeeID" width="100"></e-column>
            <e-column field="Freight" header-text="Freight" width="100"></e-column>
            <e-column field="ShipCity" header-text="ShipCity"  width="90"></e-column>
            <e-column field="ShipAddress" header-text="Ship Address" width="110"></e-column>
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

![Header Wrap Mode](Cell_images/Cell_img1_1.png)

### Content

When the `wrap-mode` of `e-text-wrap-settings` property is set as `Content` then the auto wrap will be enabled only for Grid content alone. 

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" allow-text-wrap="true" datasource="ViewBag.DataSource">
       <e-text-wrap-settings wrap-mode="Content"/>
        <e-columns>
            <e-column field="OrderID" header-text="OrderID" width="90"></e-column>
            <e-column field="EmployeeID" header-text="EmployeeID" width="100"></e-column>
            <e-column field="Freight" header-text="Freight" width="100"></e-column>
            <e-column field="ShipCity" header-text="ShipCity" width="90"></e-column>
            <e-column field="ShipAddress" header-text="Ship Address" width="110"></e-column>
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

![Content Wrap Mode](Cell_images/Cell_img1_2.png)

## Cell merging

The Grid has options to merge its cells based on the required conditions. This can be enabled by setting the `allow-cell-merging` property as `true` and the merge conditions can be defined in `merge-cell-info` event. In this event, you can get the column details and data of that particular row and column which is helpful in defining conditions. 

You can merge the rows and cells of Grid, using the `rowMerge`, `colMerge` and `merge` functions available in `merge-cell-info` event's argument.

N> The following features are not supported with Cell Merging
N> 1. Normal Mode Editing
N> 2. Inline Mode Editing
N> 3. Inline TemplateForm Mode Editing
N> 4. Grouping
N> 5. Virtual Scrolling
N> 6. Frozen Columns
N> 7. Cell Selection Modes
N> 8. Column Selection

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}
    
     <ej-grid id="FlatGrid" allow-paging="true" allow-cell-merging="true" merge-cell-info ="mergeCellInfo" datasource="ViewBag.DataSource">
         <e-columns>
            <e-column field="OrderID" header-text="OrderID"></e-column>
            <e-column field="EmployeeID" header-text="EmployeeID"></e-column>
            <e-column field="ShipCity" header-text="ShipCity"></e-column>
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
{% highlight c# %}
      <script type="text/javascript">         
        function mergeCellInfo(args)
         {
            if (args.column.field == "EmployeeID" && args.data.OrderID == 10248)
                args.rowMerge(3);
            else if (args.column.field == "ShipCity" && args.data.OrderID == 10252)
                args.colMerge(3);
            else if (args.column.field == "ShipCity" && args.data.OrderID == 10255)
                args.merge(0, 3);
         }
      </script>
{% endhighlight  %}
{% endtabs %}  


The following output is displayed as a result of the previous code example.

![Cell Merging](Cell_images/Cell_img2.png)


## Displaying HTML content

This will help you to show the actual HTML value in Grid content and header. To disable HTML code, set the `disable-html-encode` property of `columns` as true. 

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
        <e-columns>
            <e-column field="OrderID" header-text="OrderID"></e-column>
            <e-column field="CustomerID" header-text="<div>Cust ID</div>" disable-html-encode="true"></e-column>
            <e-column field="EmployeeID" header-text="<div>Employee ID</div>" disable-html-encode="false"></e-column>
            <e-column field="ShipCountry" header-text="ShipCountry"></e-column>
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

![Display HTML](Cell_images/Cell_img4.png)

## Tooltip

When you move the cursor over the particular cell it provides an information about the corresponding cell value.

**Template**

HTML templates can be specified in the `tooltip` property of the particular column cell as a string (HTML element) or ID of the template's HTML element.You can use JsRender syntax in the template. For more information about JsRender syntax, please refer [this link](http://www.jsviews.com/#jsrapi "this link"). 

N> It is a standard way to enclose the template within the `script` tag with `type` as "text/x-jsrender". 
N> The `tooltip` template must contain `value` property to bind the corresponding cell text in tooltip
 
The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
        <e-columns>
            <e-column field="OrderID"></e-column>
            <e-column field="EmployeeID"></e-column>
            <e-column field="ShipCity" tooltip="#colTip"></e-column>
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
{% highlight js %}
      
      <script type="text/template" id="colTip">
          {{"{{"}}:value{{}}}}
      </script>
      
{% endhighlight  %}    
{% endtabs %}  

The following output is displayed as a result of the previous code example.

![Tooltip](Cell_images/Cell_img5.png)

## ClipMode

When the cell value contains a long text that is not fit into the grid column cell, the `clip-mode` property is used. By using the `clip-mode`, the cell value will be displayed with ellipsis or with clipped content when the text overflows inside a column cell.

N> By default the `clip-mode` will be set as `Clip`. 

**List of types**
  
 1. Clip
 2. Ellipsis
 3. EllipsisWithTooltip 
 
### Clip

When the content overflows, the remaining content will be hidden in the particular cell.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
        <e-columns>
            <e-column field="OrderID"></e-column>
            <e-column field="ShipCity"></e-column>
            <e-column field="ShipName" clip-mode="Clip"></e-column>
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

![Clip](Cell_images/Cell_img6.png)
 
### Ellipsis

Ellipsis will be displayed when the content overflows its column width. Here the Tooltip will not be shown for corresponding columns.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
        <e-columns>
            <e-column field="OrderID"></e-column>
            <e-column field="ShipCity"></e-column>
            <e-column field="ShipName" clip-mode="Ellipsis"></e-column>
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

![Ellipsis](Cell_images/Cell_img7.png)

### Ellipsis with tooltip

Ellipsis will be displayed when the content overflows its column width. Here tooltip will be shown only for the corresponding column cells that shows ellipsis.

N> If the `clip-mode` is set as `EllipsisWithTooltip`, then the `tooltip` must be given.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
        <e-columns>
            <e-column field="OrderID"></e-column>
            <e-column field="ShipCity"></e-column>
            <e-column field="ShipName" tooltip="#colTip" clip-mode="EllipsisWithTooltip"></e-column>
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
{% highlight js %}
      
      <script type="text/template" id="colTip">
          {{"{{"}}:value{{}}}}
      </script>
      
{% endhighlight  %}    
{% endtabs %}  

The following output is displayed as a result of the previous code example.

![Ellipsis with Tooltip](Cell_images/Cell_img8.png)
