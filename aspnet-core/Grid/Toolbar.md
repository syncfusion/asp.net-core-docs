---
layout: post
title: Toolbar with Grid widget for ASP.NET Core
description: toolbar 
platform: aspnet-core
control: Grid
documentation: ug
---

# Toolbar

Toolbar can be shown by defining the `show-toolbar` property in `toolbar-settings`. Toolbar has option to add default items in `toolbar-items` and customized items in ` custom-toolbar-items`.

## Default toolbar items

The following table shows default toolbar items and its action. 

<table>
<tr>
<th>
Default toolbar items</th><th>
Action</th></tr>
<tr>
<td>
Add</td><td>
Add a new row</td></tr>
<tr>
<td>
Edit</td><td>
Edit an existing</td></tr>
<tr>
<td>
Delete</td><td>
Delete a row</td></tr>
<tr>
<td>
Update</td><td>
Update edited or added row</td></tr>
<tr>
<td>
Cancel</td><td>
Cancel edited or added row</td></tr>
<tr>
<td>
Search</td><td>
Search text in records</td></tr>
</table>

{% tabs %}
{% highlight C# %}

using System;
using System.Collections.Generic;
using System.Linq;
using System.Web;
using System.Web.Mvc;
using SyncfusionMvcApplication1;
using SyncfusionMvcApplication1.Models;
namespace SyncfusionMvcApplication1.Controllers
{
    public class GridController : Controller
    {
        //
        // GET: /Grid/
        public IActionResult GridFeatures()
        {
            var DataSource = new NorthwindDataContext().OrdersViews.ToList();
            ViewBag.datasource = DataSource;
            return View();
        }
    }
}


{% endhighlight  %}

{% highlight razor %}

<ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
    <e-edit-settings allow-adding="true" allow-editing="true" allow-deleting="true"></e-edit-settings>
    <e-toolbar-settings show-toolbar="true" toolbar-items='@new List<string> {"add","edit","delete","update","cancel"}' />
    <e-context-menu-settings enable-context-menu="true"></e-context-menu-settings>
    <e-columns>
        <e-column field="OrderID" is-primary-key="true" header-text="Order ID" text-align="Right" width="90"></e-column>
        <e-column field="CustomerID" header-text="CustomerID" width="90"></e-column>
        <e-column field="EmployeeID" header-text="Employee ID" text-align="Right" width="80"></e-column>
        <e-column field="Freight" format="{0:c2}" header-text="Freight" text-align="Right"></e-column>
        <e-column field="ShipName" header-text="Ship Name" width="150"></e-column>
    </e-columns>
</ej-grid>

{% endhighlight %}
{% endtabs %}  

![](Toolbar_images/Toolbar_img1.png)


I> The `allow-adding`, `allow-editing` and `allow-deleting` need to be enabled for add, delete, edit, save & cancel in `toolbar-items`. `allow-searching` to be enabled while adding search in toolbar to perform search action.

## Custom Toolbar items

Custom toolbar is used to create your own toolbar items in toolbar. Using the custom-toolbar-items property of toolbar-settings, our own toolbar items can defined. Actions for this customized toolbar item is defined in toolbar-click event.

{% tabs %}
{% highlight C# %}

using System;
using System.Collections.Generic;
using System.Linq;
using System.Web;
using System.Web.Mvc;
using SyncfusionMvcApplication1;
using SyncfusionMvcApplication1.Models;
namespace SyncfusionMvcApplication1.Controllers
{
    public class GridController : Controller
    {
        //
        // GET: /Grid/
        public ActionResult GridFeatures()
        {
            var DataSource = new NorthwindDataContext().OrdersViews.ToList();
            ViewBag.datasource = DataSource;
            return View();
        }
    }
}


{% endhighlight  %}

{% highlight razor %}

<ej-grid id="FlatGrid" datasource="ViewBag.datasource" allow-paging="true" allow-grouping="true" 
         group-settings="@(new GroupSettings { GroupedColumns= new List<string>() { "ShipCity" } })" toolbar-click="onToolBarClick">
   <e-toolbar-settings show-toolbar="true">
       <e-custom-toolbar-items>
           <e-custom-toolbar-item template-id="#Refresh"></e-custom-toolbar-item>
       </e-custom-toolbar-items>
   </e-toolbar-settings>
    <e-columns>
        <e-column field="OrderID" is-primary-key="true" header-text="Order ID" text-align="Right" width="90"></e-column>
        <e-column field="CustomerID" header-text="CustomerID" width="90"></e-column>
        <e-column field="EmployeeID" header-text="Employee ID" text-align="Right" width="80"></e-column>
        <e-column field="Freight" format="{0:c2}" header-text="Freight" text-align="Right"></e-column>
        <e-column field="ShipCity" header-text="Ship City" width="150"></e-column>
    </e-columns>
</ej-grid>

<style type="text/css" class="cssStyles">
    .refresh:before {
        content: "\e677";
    }
</style>

<script id="Refresh" type="text/x-jsrender">
    <a class="e-toolbaricons e-icon refresh" />
</script>

<script type="text/javascript">
    function onToolBarClick(args) {
        this.refreshContent(); //refresh content using grid instance
    }
</script>
{% endhighlight %}
{% endtabs %}  

![](Toolbar_images/Toolbar_img4.png)