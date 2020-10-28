---
layout: post
title: Sorting with Grid widget for Syncfusion Essential Core
description: How to enable sorting and its functionalities
platform: aspnet-core
control: Grid
documentation: ug
---
# Sorting

The Grid control has support to sort data bound columns in ascending or descending order. This can be achieved by setting the `allow-sorting` property as `true`. 

To dynamically sort a particular column, click on its column header. The order switch between ascending and descending each time you click a column header for sorting.

The following code example describes the above behavior.

{% tabs %}
{% highlight  razor %}

<ej-grid id="Grid" allow-paging="true" allow-sorting="true">
    <e-datamanager url="//js.syncfusion.com/demos/ejServices/Wcf/Northwind.svc/Orders/?$top=45" cross-domain="true" offline="true"></e-datamanager>
    <e-columns>
        <e-column field="OrderID" ></e-column>
        <e-column field="EmployeeID"></e-column>
        <e-column field="ShipCity"></e-column>
        <e-column field="ShipCountry" ></e-column>
        <e-column field="Freight"></e-column>
    </e-columns>
</ej-grid>

{% endhighlight  %}
{% highlight c# %}

public partial class GridController : Controller
    {
        // GET: /<controller>/
        public ActionResult Sorting()
        {
            return View();
        }
    }

{% endhighlight  %}
{% endtabs %} 
The following output is displayed as a result of the above code example.

![](Sorting_images/Sorting_img1.png)

## Initial sorting

Through `sorted-columns` property of `sort-settings`, you can sort the columns while initializing the grid itself. You need to specify the `field` (Columns) name and `direction` in the `sorted-columns`.

N> 1. For `direction` property you can assign either the `string` value ("Descending") or `enum` value (`SortOrder.Descending). 
N> 2. You can add multiple columns in `sorted-columns` for multi column sorting while initializing the grid itself.

The following code example describes the above behavior.

{% tabs %}
{% highlight  razor %}

<ej-grid id="Grid" allow-paging="true" allow-sorting="true">
    <e-datamanager url="//js.syncfusion.com/demos/ejServices/Wcf/Northwind.svc/Orders/?$top=45" cross-domain="true" offline="true"></e-datamanager>
    <e-sort-settings>
        <e-sorted-columns>
            <e-sorted-column field="EmployeeID" direction="Descending"></e-sorted-column>
        </e-sorted-columns>
    </e-sort-settings>
    <e-columns>
        <e-column field="OrderID" ></e-column>
        <e-column field="EmployeeID"></e-column>
        <e-column field="ShipCity"></e-column>
        <e-column field="ShipCountry" ></e-column>
        <e-column field="Freight"></e-column>
    </e-columns>
</ej-grid>

{% endhighlight  %}
{% highlight c# %}

public partial class GridController : Controller
    {
        // GET: /<controller>/
        public ActionResult Sorting()
        {
            return View();
        }
    }

{% endhighlight  %}
{% endtabs %} 

The following output is displayed as a result of the above code example.

![](Sorting_images/Sorting_img2.png)

## Multi-column sorting

Sort multiple columns in grid by setting the `allow-multi-sorting` property as true. The sorting order is displayed in the header while doing multi sorting.

You can sort more than one column by pressing the "Ctrl key + mouse left click" on the column header. To clear sorting for particular column, press the "Shift + mouse left click". 

N> The `allow-sorting` must be true while enabling multi sort.

The following code example describes the above behavior.

{% tabs %}
{% highlight  razor %}
<ej-grid id="Grid" allow-paging="true" allow-sorting="true" allow-multi-sorting="true">
    <e-datamanager url="//js.syncfusion.com/demos/ejServices/Wcf/Northwind.svc/Orders/?$top=45" cross-domain="true" offline="true"></e-datamanager>
    <e-sort-settings>
        <e-sorted-columns>
            <e-sorted-column field="EmployeeID" direction="Descending"></e-sorted-column>
             <e-sorted-column field="CustomerID"></e-sorted-column>
        </e-sorted-columns>
    </e-sort-settings>
    <e-columns>
        <e-column field="OrderID" ></e-column>
        <e-column field="EmployeeID"></e-column>
        <e-column field="CustomerID"></e-column>
        <e-column field="ShipCountry" ></e-column>
        <e-column field="Freight"></e-column>
    </e-columns>
</ej-grid>
    
{% endhighlight  %}
{% highlight c# %}
public partial class GridController : Controller
    {
        // GET: /<controller>/
        public ActionResult Sorting()
        {
            return View();
        }
    }

{% endhighlight  %}
{% endtabs %} 

The following output is displayed as a result of the above code example.

![](Sorting_images/Sorting_img3.png)

## Stable sorting

For sorting, grid uses default browser's sort function for better performance. On multi column sorting in some browsers like chrome, the records order will be different due to unstable implementation of sorting algorithm in it. 

To resolve this, you need to set the `ej.support.stableSort` as `false`.

This will tell the "DataManager" to use custom sort function for sorting data. 

Please refer to the [link](https://en.wikipedia.org/wiki/Category:Stable_sorts# "link"), to know more information about stable sort.

The following code example describes the above behavior.

{% tabs %}
{% highlight  razor %}

<ej-grid id="Grid" allow-paging="true" allow-sorting="true" allow-multi-sorting="true">
    <e-datamanager url="//js.syncfusion.com/demos/ejServices/Wcf/Northwind.svc/Orders/?$top=45" cross-domain="true" offline="true"></e-datamanager>
    <e-columns>
        <e-column field="OrderID" ></e-column>
        <e-column field="EmployeeID"></e-column>
        <e-column field="ShipCity"></e-column>
        <e-column field="ShipCountry" ></e-column>
        <e-column field="Freight"></e-column>
    </e-columns>
</ej-grid>

{% endhighlight  %}
{% highlight c# %}

public partial class GridController : Controller
    {
        // GET: /<controller>/
        public ActionResult Sorting()
        {
            return View();
        }
    }

{% endhighlight  %}
{% highlight js %} 
      <script type="text/javascript">
            ej.support.stableSort = true
       </script>
{% endhighlight  %}
{% endtabs %} 

The following output is displayed as a result of the above code example.

![](Sorting_images/Sorting_img4.png)

## Touch options

On using Grid in a touch device, you have an option for multi sorting in single tap on the grid header. By tapping on the grid header, it will show the toggle button in small popup with sort icon. Now tap the button to enable multi sorting in single tap.

Again if you tap the popup symbol, then the single tap multi sorting will be disabled. 

N> The `allow-multi-sorting` and `allow-sorting` should be `true` then only the popup will be shown.

The following code example describes the above behavior.
{% tabs %}
{% highlight  razor %}
<ej-grid id="Grid" allow-paging="true" allow-sorting="true" allow-multi-sorting="true">
    <e-datamanager url="//js.syncfusion.com/demos/ejServices/Wcf/Northwind.svc/Orders/?$top=45" cross-domain="true" offline="true"></e-datamanager>
    <e-columns>
        <e-column field="OrderID" ></e-column>
        <e-column field="EmployeeID"></e-column>
        <e-column field="CustomerID"></e-column>
        <e-column field="ShipCountry" ></e-column>
        <e-column field="Freight"></e-column>
    </e-columns>
</ej-grid>

{% endhighlight  %}
{% highlight c# %}

public partial class GridController : Controller
    {
        // GET: /<controller>/
        public ActionResult Sorting()
        {
            return View();
        }
    }

{% endhighlight  %}
{% endtabs %} 

The following output is displayed as a result of the above code example.

![](Sorting_images/Sorting_img5.png)


N> To get the sorted data of the grid after sorting a column you can refer the [`How To`](https://help.syncfusion.com/aspnet-core/grid/how-to "Getting Datasource of Grid in Sorted Order").
