---
layout: post
title: Responsive with Grid widget for Syncfusion ASP.NET Core
description: How to set the grid, responsive to screen resolutions
platform: aspnet-core
control: Grid
documentation: ug
---

# Responsive

The Grid control has support for responsive behavior based on client browser's width and height. To enable responsive, the `is-responsive` property should be true. In Desktop and Tablet mode, to render scroller set `min-width` property. Following are three modes of responsive layout available in grid based on client width. 

* Mobile(<321px)
* Tablet (321px to 800px)
* Desktop(>800px)

N> The following features are not supported by Grid's Responsive
N> 1. Virtual Scrolling 
N> 2. Frozen Rows and Frozen Columns 
N> 3. Hierarchy
N> 4. Detail template 

## Mobile layout

If client width is less than 321px, the grid will render in mobile mode. In which, you can see that grid user interface is customized and redesigned for best view in small screens. The customized features includes responsive row rendering, filtering, sorting, searching and editing.

### Responsive row

Enabling responsive row makes the grid to render the record values in vertical order which removes the need for horizontal scrolling to view complete record details. It can be enabled by defining the `enable-responsive-row` property as `true`.

{% tabs %}

{% highlight razor %}

<ej-grid id="FlatGrid" datasource="ViewBag.DataSource" is-responsive="true" enable-responsive-row="true" allow-paging="true">
    <e-page-settings page-count="3" page-size="7"></e-page-settings>
    <e-columns>
        <e-column field="OrderID" header-text="Order ID" is-primary-key="true"></e-column>
        <e-column field="CustomerID" header-text="Customer ID"></e-column>
        <e-column field="EmployeeID" header-text="Employee ID" text-align="Right"></e-column>
        <e-column field="ShipCity" header-text="Ship city"></e-column>
        <e-column field="Freight" header-text="Freight" format="{0:C}"></e-column>
    </e-columns>
</ej-grid>

{% endhighlight %}
{% highlight c# %}

public partial class GridController : Controller
    {

        private NORTHWNDContext _context;

        public GridController(NORTHWNDContext context)
        {
            _context = context;
        }
        // GET: /<controller>/
        public ActionResult Default()
        {
            ViewBag.datasource = _context.Orders.Take(100).ToList();
            return View();
        }
    }
{% endhighlight  %}
{% endtabs %} 


![](Responsive_images/Responsive_img1.png)


W> IE8 and IE9 does not support responsive row. The `ejgrid.responsive.css` should be referred to display Responsive Row.

### Customized features

The customized layout for filtering, sorting, searching and CRUD operations in mobile device can be seen in the following screenshots.

![](Responsive_images/Responsive_img2.png)
{:caption}
Responsive row with Filtering, Sorting and Searching.

![](Responsive_images/Responsive_img3.png)

{:caption}
CRUD in mobile layout

![](Responsive_images/Responsive_img4.png)

{:caption}
Filtering in mobile layout

![](Responsive_images/Responsive_img5.png)
{:caption}

Filtering in mobile layout

![](Responsive_images/Responsive_img6.png)

{:caption}
Sorting in mobile layout

![](Responsive_images/Responsive_img7.png)
{:caption}

Searching in mobile layout

{% tabs %}

{% highlight razor %}

@{ 
    Dictionary<string, object> dict = new Dictionary<string, object>();
    dict.Add("required", true);
    dict.Add("number", true);
    Dictionary<string, object> dict1 = new Dictionary<string, object>();
    dict1.Add("required", true);
}

<ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource" is-responsive="true" enable-responsive-row="true">
    <e-edit-settings allow-adding="true" allow-editing="true" allow-deleting="true"></e-edit-settings>
    <e-toolbar-settings show-toolbar="true" toolbar-items='@new List<string> {"add","edit","delete","update","cancel"}' />
    <e-context-menu-settings enable-context-menu="true"></e-context-menu-settings>
    <e-columns>
        <e-column field="OrderID" is-primary-key="true" header-text="Order ID" text-align=Right validation-rules="dict"></e-column>
        <e-column field="CustomerID" header-text="CustomerID" validation-rules="dict1"></e-column>
        <e-column field="EmployeeID" header-text="Employee ID" text-align="Right" edit-type="Dropdown"></e-column>
        <e-column field="ShipCity" header-text="ShipCity" edit-type="Dropdown"></e-column>
        <e-column field="Freight" header-text="Freight" edit-type="Numeric">
            <e-numeric-edit-options decimal-places="2"></e-numeric-edit-options>
        </e-column>
    </e-columns>
</ej-grid>
    
{% endhighlight %}
{% highlight c# %}

public partial class GridController : Controller
    {

        private NORTHWNDContext _context;

        public GridController(NORTHWNDContext context)
        {
            _context = context;
        }
        // GET: /<controller>/
        public ActionResult Default()
        {
            ViewBag.datasource = _context.Orders.Take(100).ToList();
            return View();
        }
    }

{% endhighlight  %}
{% endtabs %} 

## Tablet Layout

If the client width is between 321px and 800px, then the grid will render in tablet mode. Also, it has customized filtering design to match tablet screen size.

{% tabs %}

{% highlight razor %}

<ej-grid id="FlatGrid" datasource="ViewBag.DataSource" is-responsive="true" allow-paging="true" allow-filtering="true">
    <e-page-settings page-count="3" page-size="8"></e-page-settings>
    <e-filter-settings filter-type="Menu"></e-filter-settings> 
    <e-columns>
        <e-column field="OrderID" header-text="Order ID" is-primary-key="true" text-align="Right" width="90">
        </e-column>
        <e-column field="CustomerID" header-text="Customer ID" width="100"></e-column>
        <e-column field="EmployeeID" header-text="Employee ID" text-align="Right" width="90"></e-column>
        <e-column field="ShipCity" header-text="Ship city" width="120"></e-column>
        <e-column field="Freight" header-text="Freight" width="80" format="{0:c2}"></e-column>
    </e-columns>
</ej-grid>
{% endhighlight %}
{% highlight c# %}
public partial class GridController : Controller
    {

        private NORTHWNDContext _context;

        public GridController(NORTHWNDContext context)
        {
            _context = context;
        }
        // GET: /<controller>/
        public ActionResult Default()
        {
            ViewBag.datasource = _context.Orders.Take(100).ToList();
            return View();
        }
    }
   
{% endhighlight  %}
{% endtabs %} 

![](Responsive_images/Responsive_img8.png)
{:caption}

Default tab layout

![](Responsive_images/Responsive_img9.png)

{:caption}
Filtering design in tab layout.

## Width

By default, the grid is adaptable to its parent container. It can adjust its width of columns based on parent container width. You can also assign them `width` of `columns` in percentage. 

{% tabs %}

{% highlight razor %}

<ej-grid id="FlatGrid" datasource="ViewBag.DataSource">
    <e-columns>
        <e-column field="OrderID" header-text="Order ID" is-primary-key="true" text-align="Right" width=@("10%")>
        </e-column>
        <e-column field="CustomerID" header-text="Customer ID" validation-rules="dict" width=@("15%")></e-column>
        <e-column field="EmployeeID" header-text="Employee ID" text-align="Right" width=@("10%")></e-column>
    </e-columns>
</ej-grid>

{% endhighlight %}
{% highlight c# %}
public partial class GridController : Controller
    {

        private NORTHWNDContext _context;

        public GridController(NORTHWNDContext context)
        {
            _context = context;
        }
        // GET: /<controller>/
        public ActionResult Default()
        {
            ViewBag.datasource = _context.Orders.Take(100).ToList();
            return View();
        }
    }

{% endhighlight  %}
{% endtabs %} 

I>  The `AllowScrolling` should be false while defining width in percentage.

## Min width

Min width is used to maintain minimum width for the grid. To enable min width, `min-width` should be defined. If the grid width is less than `min-width` then the scrollbar will be displayed to maintain minimum width.

{% tabs %}

{% highlight razor %}

<ej-grid id="FlatGrid" datasource="ViewBag.DataSource" allow-paging="true" min-width="700"> 
    <e-columns>
        <e-column field="OrderID" header-text="Order ID" is-primary-key="true" text-align="Right" width="90">
        </e-column>
        <e-column field="CustomerID" header-text="Customer ID" width="100"></e-column>
        <e-column field="EmployeeID" header-text="Employee ID" text-align="Right" width="90"></e-column>
        <e-column field="ShipCity" header-text="Ship city" width="120"></e-column>
        <e-column field="Freight" header-text="Freight" format="{0:C}" width="80"></e-column>
    </e-columns>
</ej-grid>

{% endhighlight %}
{% highlight c# %}

public partial class GridController : Controller
    {

        private NORTHWNDContext _context;

        public GridController(NORTHWNDContext context)
        {
            _context = context;
        }
        // GET: /<controller>/
        public ActionResult Default()
        {
            ViewBag.datasource = _context.Orders.Take(100).ToList();
            return View();
        }
    }

{% endhighlight  %}
{% endtabs %} 

MinWidth set to grid

N> The Grid can be rendered with height responsive by setting the scroll `height`as `100%`. If the grid height is greater than its parent container's height then the vertical scrollbar will be displayed to view the content.

## Priority for columns

Priority makes column to be visible or hidden based on the `priority` value and browser's width to best accommodate the possible columns. To enable the `Priority` for `Columns`, `Priority` needs to be defined in columns collection. These Priority values are from one to six.

{% tabs %}

{% highlight razor %}

<ej-grid id="FlatGrid" datasource="ViewBag.DataSource" allow-paging="true"> 
    <e-columns>
        <e-column field="OrderID" header-text="Order ID" is-primary-key="true" text-align="Right" width="90" priority="1">
        </e-column>
        <e-column field="CustomerID" header-text="Customer ID" width="100" priority="2"></e-column>
        <e-column field="EmployeeID" header-text="Employee ID" text-align="Right" width="90" priority="1"></e-column>
        <e-column field="ShipCity" header-text="Ship city" width="120" priority="3"></e-column>
        <e-column field="Freight" header-text="Freight" format="{0:C}" width="80" priority="4"></e-column>
    </e-columns>
</ej-grid>

{% endhighlight %}
{% highlight c# %}
public partial class GridController : Controller
    {

        private NORTHWNDContext _context;

        public GridController(NORTHWNDContext context)
        {
            _context = context;
        }
        // GET: /<controller>/
        public ActionResult Default()
        {
            ViewBag.datasource = _context.Orders.Take(100).ToList();
            return View();
        }
    }

{% endhighlight  %}
{% endtabs %} 

I> The `ejgrid.responsive.css` should be referred.