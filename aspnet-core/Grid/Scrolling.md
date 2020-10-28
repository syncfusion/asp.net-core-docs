---
layout: post
title: scrolling with Grid widget for Syncfusion Essential ASP.NET Core
description: This section explains about the scrolling and its functionalities like Frozen Rows and Columns, Touch Scroll, Virtual Scroll and the types of Virtual Scroll.
platform: aspnet-core
control: Grid
documentation: ug
---
# Enable Scrolling in Grid

Scrolling can be enabled by setting the `allow-scrolling` as `true`. The height and width can be set to Grid by using the properties `height` and `width` property of the `e-scroll-settings`. 

 N> If `width` and `height` is not defined in the `e-scroll-settings` property then the horizontal and vertical scrollbar is enabled, only when the grid width exceeds the browser width.

The height and width can be set in percentage and pixel. The default value for `height` and `width` in `e-scroll-settings` is 0 and `auto` respectively.

The following code example describes the above behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource" allow-scrolling="true">
      <e-scroll-settings width="400" height="300">
        <e-columns>
            <e-column field="OrderID" ></e-column>
            <e-column field="EmployeeID"></e-column>
            <e-column field="CustomerID"></e-column>
            <e-column field="ShipCity"></e-column>
            <e-column field="ShipCountry"></e-column> 
            <e-column field="ShipAddress"></e-column> 
            <e-column field="ShipPostalCode"></e-column>   
            <e-column field="Freight" format="{0:C}"></e-column>
            
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

![Scrolling](Scrolling_images/Scrolling_img1.png)

## Set width and height in pixel 

To specify the `width` and `height` property of the `e-scroll-settings` in pixel, by setting the pixel value as integer. 

The following code example describes the above behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource" allow-scrolling="true">
      <e-scroll-settings width="500" height="300">
        <e-columns>
            <e-column field="OrderID" ></e-column>
            <e-column field="EmployeeID"></e-column>
            <e-column field="CustomerID"></e-column>
            <e-column field="ShipCity"></e-column>
            <e-column field="ShipCountry"></e-column> 
            <e-column field="ShipAddress"></e-column> 
            <e-column field="ShipPostalCode"></e-column>   
            <e-column field="Freight" format="{0:C}"></e-column>
            
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

![In pixel](scrolling_images/scrolling_img2.png)

## Set width and height in percentage

To specify the `width` and `height` property of  the `e-scroll-settings` in percentage, by setting the percentage value as string.

The following code example describes the above behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource" allow-scrolling="true">
      <e-scroll-settings width=@("70%") height=@("5%")></e-scroll-settings>
        <e-columns>
            <e-column field="OrderID" ></e-column>
            <e-column field="EmployeeID"></e-column>
            <e-column field="CustomerID"></e-column>
            <e-column field="ShipCity"></e-column>
            <e-column field="ShipCountry"></e-column> 
            <e-column field="ShipAddress"></e-column> 
            <e-column field="ShipPostalCode"></e-column>   
            <e-column field="Freight" format="{0:C}"></e-column>
            
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

![In percentage](scrolling_images/scrolling_img3.png)

## Set Width as auto

Specify `width` property of `e-scroll-settings` as auto, then the scrollbar is rendered only when the grid width exceeds the browser window width.

The following code example describes the above behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource" allow-scrolling="true">
      <e-scroll-settings width=@("auto") height="300">
        <e-columns>
            <e-column field="OrderID" ></e-column>
            <e-column field="EmployeeID"></e-column>
            <e-column field="CustomerID"></e-column>
            <e-column field="ShipCity"></e-column>
            <e-column field="ShipCountry"></e-column> 
            <e-column field="ShipAddress"></e-column> 
            <e-column field="ShipPostalCode"></e-column>   
            <e-column field="Freight" format="{0:C}"></e-column>
            
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

![Auto Width](scrolling_images/scrolling_img4.png)

## Frozen columns

Specify the `frozen-columns` property of `e-scroll-settings` to freeze the columns(upto the specified frozenColumns value) at the time of scrolling. Horizontal scrollbar must be enabled while specifying the `frozen-columns` then only you can scroll and see the remaining columns with freeze pane.

N> The `allow-scrolling` must be `true` while specifying `frozen-columns`.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource" allow-scrolling="true">
      <e-scroll-settings width="550" height="300" frozen-columns="2">
        <e-columns>
            <e-column field="OrderID" ></e-column>
            <e-column field="EmployeeID"></e-column>
            <e-column field="CustomerID"></e-column>
            <e-column field="ShipCity"></e-column>
            <e-column field="ShipCountry"></e-column> 
            <e-column field="ShipAddress"></e-column> 
            <e-column field="ShipPostalCode"></e-column>   
            <e-column field="Freight" format="{0:C}"></e-column>
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

![Frozen Columns](scrolling_images/scrolling_img5.png)


### Freeze particular columns:

To freeze selected columns in grid at the time of scrolling, by setting the `is-frozen` property of columns as `true`. The `is-frozen` columns are rendered first in the grid even the columns index is different while declaring the `e-columns` .

The following code example describes the above behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource" allow-scrolling="true">
      <e-scroll-settings width="550" height="400" frozen-columns="2">
        <e-columns>
            <e-column field="OrderID" ></e-column>
            <e-column field="EmployeeID"></e-column>
            <e-column field="CustomerID"></e-column>
            <e-column field="Freight" format="{0:C}" is-frozen="true"></e-column>
            <e-column field="OrderDate" format="{0:dd/MM/yyyy}"></e-column>
            <e-column field="ShipCity"></e-column>
            <e-column field="ShipCountry" is-frozen="true"></e-column> 
            <e-column field="ShipAddress"></e-column> 
            <e-column field="ShipPostalCode"></e-column>   
            
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

![Frozen Column](scrolling_images/scrolling_img6.png)


### Frozen columns alert Messages:

1. If `allow-scrolling` is false while using `frozen-columns`  then "Enable `allow-scrolling` while using frozen Columns" alert message is thrown.
2. If `frozen-columns` is specified out of the grid column view then "Frozen columns should be in grid view area" alert message is thrown.
3. Frozen Rows and Columns are not supported in the following features.
 Grouping
 Row Template
 Detail Template
 Hierarchy Grid 
 Batch Editing
 Virtual Scrolling

If any one of the above feature is enabled along with Frozen Rows and Columns, then "Frozen Columns and Rows are not supported for Grouping, Row Template, Detail Template, Hierarchy Grid and Batch Editing" alert message is thrown.

## Frozen rows

Specify the `frozen-rows` property of `e-scroll-settings` to freeze rows (upto the specified FrozenRows value) at the time of scrolling. Vertical scrollbar must be enabled while specifying the `frozen-rows` then only you can scroll and see the remaining rows with freeze pane.

N> The `allow-scrolling` must be `true` while specifying `frozen-rows` .

The following code example describes the above behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource" allow-scrolling="true">
      <e-scroll-settings width="550" height="400" frozen-rows="4">
        <e-columns>
            <e-column field="OrderID" ></e-column>
            <e-column field="EmployeeID"></e-column>
            <e-column field="CustomerID"></e-column>
            <e-column field="ShipCity"></e-column>
            <e-column field="ShipCountry"></e-column> 
            <e-column field="ShipAddress"></e-column> 
            <e-column field="ShipPostalCode"></e-column>   
            <e-column field="Freight" format="{0:C}"></e-column>
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

![Frozen Rows](scrolling_images/scrolling_img7.png)


## Touch scroll

In touch supported devices you can scroll and show the content by swipe left, right, top and bottom. Disable touch scroll by setting the `enable-touch-scroll` property of `e-scroll-settings` as `false`.

The following code example describes the above behavior.
 
{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource" allow-scrolling="true">
      <e-scroll-settings width="550" height="400" enable-touch-scroll="false">
        <e-columns>
            <e-column field="OrderID" ></e-column>
            <e-column field="EmployeeID"></e-column>
            <e-column field="CustomerID"></e-column>
            <e-column field="ShipCity"></e-column>
            <e-column field="ShipCountry"></e-column> 
            <e-column field="ShipAddress"></e-column> 
            <e-column field="ShipPostalCode"></e-column>   
            <e-column field="Freight" format="{0:C}"></e-column>
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

## Virtual scrolling

The virtual scrolling support allows you to load data that you require (load data based on page size) without buffering the entire huge database. To enable virtual scrolling by setting the `allow-virtual-scrolling` property of `e-scroll-settings` as `true`. 

We also have an enhanced virtual scrolling feature with an improvised virtual scrolling performance. To enable improvised virtual scrolling feature by setting the `enable-virtualization` property of `e-scroll-settings` as true and it doesn't requires the `allow-virtual-scrolling` to enabled. It allows you to load the grid with data while scrolling. In order to enable this, you need to enable the `enable-virtualization` property of the `e-scroll-settings`. Some of the relevant functionalities of this are in the following three.

1.	White space will not be appeared in the Grid. 
2.	Improved page rendering performance. 
3.  It can render nearly 500 thousand records.

It supports two mode of virtualization. They are as follows.

1. Normal Mode
2. Infinite or Continuous Mode

N> Enhanced Virtual Scrolling supports only Normal mode
N> The following features are not supported by virtual scrolling 
N> 1. Grouping
N> 2. Frozen Rows 
N> 3. Cell merging 
N> 4. Detail template 
N> 5. Hierarchy
N> 6. Editing

### Normal mode:

It allows you to load the grid with data while scrolling. This can be achieved by setting the `virtual-scroll-mode` as `Normal`.

The following code example describes the above behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource" allow-scrolling="true">
      <e-scroll-settings width="550" height="300" allow-virtual-scrolling ="true" virtual-scroll-mode="Normal">
        <e-columns>
            <e-column field="OrderID" ></e-column>
            <e-column field="EmployeeID"></e-column>
            <e-column field="CustomerID"></e-column>
            <e-column field="ShipCity"></e-column>
            <e-column field="ShipCountry"></e-column> 
            <e-column field="ShipAddress"></e-column> 
            <e-column field="ShipPostalCode"></e-column>   
            <e-column field="Freight" format="{0:C}"></e-column>
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

![Normal Mode](scrolling_images/scrolling_img8.png)

#### Enhanced virtual scrolling:

In order to enable this, you need to set the `enable-virtualization` property of the `e-scroll-settings` as true. 

The following code example describes the above behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource" allow-scrolling="true">
      <e-scroll-settings width="550" height="300" enable-virtualization="true">
        <e-columns>
            <e-column field="OrderID" ></e-column>
            <e-column field="EmployeeID"></e-column>
            <e-column field="CustomerID"></e-column>
            <e-column field="ShipCity"></e-column>
            <e-column field="ShipCountry"></e-column> 
            <e-column field="ShipAddress"></e-column> 
            <e-column field="ShipPostalCode"></e-column>   
            <e-column field="Freight" format="{0:C}"></e-column>
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

![Virtual Scroll](scrolling_images/scrolling_img10.png)

### Infinite or Continuous mode:

In Infinite or Continuous mode, the data is loaded in grid when the scrollbar reaches the end. You can enable the continuous mode by setting the `virtual-scroll-mode` property as `Continuous`.

The following code example describes the above behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource" allow-scrolling="true">
      <e-scroll-settings width="550" height="300" allow-virtual-scrolling ="true" virtual-scroll-mode="Continuous">
        <e-columns>
            <e-column field="OrderID" ></e-column>
            <e-column field="EmployeeID"></e-column>
            <e-column field="CustomerID"></e-column>
            <e-column field="ShipCity"></e-column>
            <e-column field="ShipCountry"></e-column> 
            <e-column field="ShipAddress"></e-column> 
            <e-column field="ShipPostalCode"></e-column>   
            <e-column field="Freight" format="{0:C}"></e-column>
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

 ![Infinite Mode](scrolling_images/scrolling_img9.png)

