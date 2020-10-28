---
layout: post
title: Paging with Grid widget for Syncfusion Essential ASP.NET Core
description: How to enable paging and its functionalites.
platform: aspnet-core
control: Grid
documentation: ug
---
# Paging

The grid records can be displayed in paged view, by setting the `allow-paging` property as `true`.

The code snippet to enable paging is as follows.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
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
 
 ![](Paging_images/Paging_img1.png)


## Pager with query string


You can pass the current page information as a query string while navigating to other page. To enable query string, set the `enable-query-string` property of `e-page-settings` as `true`.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
        <e-page-settings enable-query-string="true"> </e-page-settings>
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

 ![](Paging_images/Paging_img2.png)
 
 ## Pager template

Apart from default pager, there is an option to render a specific custom template in a grid pager. To render template in pager, set the `enable-templates` as true. The HTML templates can be specified in the `template` property of `e-page-settings`.

 To prevent the display of default pager, enable the pager `template` by setting the `show-defaults` property of the `e-page-settings` as `false`.

 N> It's a standard way to enclose the `template`  within the `script` tag with `type` as "text/x-jsrender".

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource" create="create">
        <e-page-settings enable-templates="true" template="#template" show-defaults="false"></e-page-settings>
        <e-columns>
            <e-column field="OrderID" header-text="OrderID"></e-column>
            <e-column field="EmployeeID" header-text="EmployeeID"></e-column>
            <e-column field="ShipCity" header-text="ShipCity"></e-column>
            <e-column field="ShipCountry" header-text="ShipCountry"></e-column>
            <e-column field="Freight" header-text="Freight" format="{0:C}"></e-column>
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
            <input id="currentPage" type="text" style="text-align: center; width: 32px; height: 21px; background: white;" value="1" />
            <label>of 200</label>
            <button id="btn">Go to</button>
          </script>
          <script>
            function create(args) {
                     $("#btn").ejButton({
                       click : "btnClick"
                         });
                   }
             function btnClick(args) {
                     var val = $("#currentPage").val();
                     var gridObj = $("#Grid").data("ejGrid");
                      gridObj.gotoPage(args.val);
                  }
           </script>
{% endhighlight  %}
{% highlight css %}

     .e-grid .e-pager .e-pagercontainer {
	       border-width: 0px;
	       overflow: visible;
         }         
{% endhighlight  %} 
{% endtabs %} 
 
The following output is displayed as a result of the previous code example.

![](Paging_images/Paging_img3.png)

## Pager with pageSettings

The default page settings can be customized, such as the [`pageCount`](https://help.syncfusion.com/api/js/ejgrid#members:pagesettings-pagecount "pageCount"), [`pageSize`](https://help.syncfusion.com/api/js/ejgrid#members:pagesettings-pagesize "pageSize")  of the grid's pager by using [`pageSettings`](https://help.syncfusion.com/api/js/ejgrid#members:pagesettings "pageSettings") property of grid control. 

The following code example describes the previous behavior.

{% highlight html %}
<div id="Grid"></div>
{% endhighlight %}

{% highlight javascript %}
$(function () {
	$("#Grid").ejGrid({
		//The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
        dataSource: window.gridData,
        allowPaging: true,
        pageSettings: { pageSize: 8, pageCount:3}
    });
});
{% endhighlight %}

The following output is displayed as a result of the previous code example.

![](paging_images/paging_img7.png)
