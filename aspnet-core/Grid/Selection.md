---
layout: post
title: Selection with Grid widget for Syncfusion Essential ASP.NET Core
description: How to enable selection and its functionalities
platform: aspnet-core
control: Grid
documentation: ug
---
# Selection

Selection provides an interactive support to highlight the row, cell or column that you select. Selection can be done through simple Mouse down or Keyboard interaction. To enable selection, set the `allow-selection` as `true`. 

## Types of selection

The following are the two types of selections available in Grid. 

1. Single 
2. Multiple 

### Single selection

Single selection is an interactive support to select a specific row, cell or column in grid by mouse or keyboard interactions. To enable single selection by setting the `selection-type` property as `single` and also set the `allow-selection` property as `true`.

### Multiple selections

Multiple selections is an interactive support to select a group of rows, cells or columns in grid by mouse or keyboard interactions. To enable multiple selections set the `selection-type`  property as `Multiple` and also set the `allow-selection` property as `true`.

## Row selection

Row selection is enabled by setting the `selection-mode` property of `e-selection-settings` as `row`. For random row selection, press the **"Ctrl + mouse left"** click and for continuous row selection press the **"Shift + mouse left"** click on the grid rows. To unselect selected rows, by press the **"Ctrl + mouse left"** click on selected row.

The following code example describes the above behavior.

{% tabs %}
{% highlight razor %}
   <ej-grid id="FlatGrid" allow-paging="true" allow-selection="true" selection-type="Multiple" datasource="ViewBag.DataSource">
       <e-selection-settings selection-mode="@(new List<string>(){"row"})"></e-selection-settings>
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
{% endtabs %}  


The following output is displayed as a result of the above code example

![](Selection_images/Selection_img1.png)

## Multiple row selection using checkbox column

Select multiple rows in grid by using checkbox column and it can be enabled by setting the column `type` as `checkbox`. It also provides the option to select/deselect all the rows in grid using a checkbox in the corresponding column header.

If the `field` property of Checkbox column is not defined, then it acts as a template column. So `field` property is necessary to perform grid actions like sorting, editing, etc., for the corresponding Checkbox column.

The following code example describes the above behavior.

{% tabs %}
{% highlight razor %}
   <ej-grid id="FlatGrid" allow-paging="true" allow-selection="true" datasource="ViewBag.DataSource">
       <e-columns>
            <e-column type="checkbox" width="50"/>
            <e-column field="OrderID" header-text="Order ID" width="75" text-align="right"></e-column>
            <e-column field="CustomerID" header-text="Customer ID" width="80" ></e-column>
            <e-column field="EmployeeID" header-text="Employee ID" text-align="right" width="75"></e-column>
            <e-column field="Freight" header-text="Freight" text-align="right" width="75" format="{0:C}"></e-column>
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

The following output is displayed as a result of the above code example

![](Selection_images/Selection_img12.png)

## Cell selection

Cell selection is enabled by set `selection-mode` property of `selection-settings` as `cell`. For random cell selection, press **"Ctrl + mouse left"** click and for continuous cell selection, press **"Shift + mouse left"** click on the grid cells. To unselect selected cells, press **"Ctrl + mouse left"** on selected cell click.

The following code example describes the above behavior.

{% tabs %}
{% highlight razor %}
   <ej-grid id="FlatGrid" allow-paging="true" allow-selection="true" selection-type="multiple" datasource="ViewBag.DataSource">
       <e-selection-settings selection-mode="@(new List<string>(){"cell"})"/> 
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
{% endtabs %}  



The following output is displayed as a result of the above code example

![](Selection_images/Selection_img2.png)

### Cell selection mode

There are two types of cell selection available in grid. They are the following.

1. Continuous Selection
2. Box Selection

Box cell selection is to select multiple cells vertically based on the initial column index selection.  

The following code example describes the above behavior.

{% tabs %}
{% highlight razor %}
   <ej-grid id="FlatGrid" allow-paging="true" allow-selection="true" selection-type="multiple" datasource="ViewBag.DataSource">
       <e-selection-settings selection-mode="cell" cell-selection-mode="Box"/> 
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
{% endtabs %}  

 The following output is displayed as a result of the above code example

![](Selection_images/Selection_img3.png)


## Column selection

Column selection can be enabled by setting `selection-mode` property of `e-selection-settings` as `column`. For random column selection, press **"Ctrl + mouse left click"** and for continuous column selection, press **"Shift + mouse left click"** on the top of the column header. To unselect selected columns, press **"Ctrl + mouse left click"** on top of the selected column header.

The following code example describes the above behavior.

{% tabs %}
{% highlight razor %}
   <ej-grid id="FlatGrid" allow-paging="true" allow-selection="true" selection-type="multiple" datasource="ViewBag.DataSource">
       <e-selection-settings selection-mode="@(new List<string>(){"column"})"/> 
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
{% endtabs %}  


The following output is displayed as a result of the above code example

![](Selection_images/Selection_img4.png)


## Touch options

On using the grid in a touch device environment, there is an option for multi selection through single tap on the row and it will shows a popup with multi-selection symbol. Tap the icon to enable multi selection in a single tap.

The following code example describes the above behavior. 

{% tabs %}
{% highlight razor %}
   <ej-grid id="FlatGrid" allow-paging="true" allow-selection="true" selection-type="multiple" datasource="ViewBag.DataSource">
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
{% endtabs %}  

The following output is displayed as a result of the above code example.

![](Selection_images/Selection_img5.png)


## Toggle selection

The Toggle selection allows to perform selection and unselection of the particular row, cell or column. To enable toggle selection, set the `enable-toggle` property of `selection-settings` as `true`. If you click on the selected row, cell or column then it will be unselected and vice versa. 

N> If multi selection is enabled, then in first click on any selected row (without pressing Ctrl key), it will clear multi selection and in second click on the same row, it will be unselected. 

The following code example describes the above behavior. 

{% tabs %}
{% highlight razor %}
   <ej-grid id="FlatGrid" allow-paging="true" enable-row-hover="false" datasource="ViewBag.DataSource">
     <e-selection-settings enable-toggle="true"/>
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
{% endtabs %}  


## Drag Selection

The Drag selection allows to perform selection of the particular rows or cells by performing mouse dragging.  To enable drag selection, set `allow-drag-selection` property of the `e-selection-settings` as `true`. Now you can select the cells or rows in the Grid by dragging the mouse. 

N> The `selection-type` property should be set as `multiple`, to select multiple cells in Grid by mouse dragging. 

The following code example describes the above behavior. 

{% tabs %} 
{% highlight razor %}
    <ej-grid id="FlatGrid" allow-paging="true" enable-row-hover="false" selection-type="Multiple" datasource="ViewBag.DataSource">
     <e-selection-settings selection-mode="@(new List<string>(){"cell"})" allow-drag-selection="true"/> 
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
{% endtabs %}  

The following output is displayed as a result of the above code example.

![](selection_images/Selection_img13.png)