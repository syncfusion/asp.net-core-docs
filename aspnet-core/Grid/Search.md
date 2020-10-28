---
layout: post
title: Searching with Grid widget for Syncfusion Essential ASP.NET Core
description: How to enable search option and its functionalities
platform: aspnet-core
control: Grid
documentation: ug
--- 
# Searching

The Grid has an option to search its content using the JavaScript method `search` with search key as parameter. Also, it provides an option to integrate Search text box in grid toolbar, by adding `Search` toolbar item in the `ToolbarItems` property of `ToolbarSettings`.

The following code example describes the above behavior.

{% tabs %} 
{% highlight razor %}

	  @{Html.EJ().Grid<OrdersView>("Searching")
            .Datasource((IEnumerable<object>)ViewBag.datasource)
            .AllowPaging()
            .ToolbarSettings(toolbar =>{ toolbar.ShowToolbar().ToolbarItems(items => { items.AddTool(ToolBarItems.Search); }); })
            .AllowSearching()           
            .Columns(col =>
            {
                col.Field("OrderID").Add();
                col.Field("EmployeeID").Add();   
                col.Field("CustomerID").Add();
                col.Field("ShipCountry").Add(); 
                col.Field("Freight").Add();    
            }).Render();
        }
{% endhighlight  %}
{% highlight c# %}
		
	   namespace MVCSampleBrowser.Controllers
     	 {
          public partial class GridController : Controller
          {
           public IActionResult Searching()
             {
                var DataSource = new NorthwindDataContext().OrdersViews.ToList();
                ViewBag.datasource = DataSource;
                return View();
              }
          }
       }
{% endhighlight  %}
{% endtabs %}

The following output is displayed as a result of the above code example.

![](searching_images/searching_img1.png)


## Initial searching

On initializing the grid, there is an option to display only the searched data in grid. To perform initial searching, define `Fields`, `Operator`, `Key` and `IgnoreCase` in `SearchSettings` property.

 N> The `Key` value must be passed as `string`.

The following code example describes the above behavior.

{% tabs %} 
{% highlight razor %}

	  @{Html.EJ().Grid<OrdersView>("Selection")
            .Datasource((IEnumerable<object>)ViewBag.datasource)
            .AllowPaging()
            .ToolbarSettings(toolbar => { toolbar.ShowToolbar().ToolbarItems(items => { items.AddTool(ToolBarItems.Search); }); })
            .AllowSearching()  
			.SearchSettings(col => { col.Fields(search => { search.Add("CustomerID"); }).Operator(Operator.Contains).Key("ra").IgnoreCase(false); })         
            .Columns(col =>
            {
                col.Field("OrderID").Add();
                col.Field("EmployeeID").Add();   
                col.Field("CustomerID").Add();
                col.Field("ShipCountry").Add(); 
                col.Field("Freight").Add();    
            }).Render();
        }
{% endhighlight  %}
{% highlight c# %}
		
        namespace MVCSampleBrowser.Controllers
     	 {
          public partial class GridController : Controller
          {
           public IActionResult Selection()
             {
                var DataSource = new NorthwindDataContext().OrdersViews.ToList();
                ViewBag.datasource = DataSource;
                return View();
              }
           }
         }
{% endhighlight  %}
{% endtabs %}

The following output is displayed as a result of the above code example.

![](searching_images/searching_img2.png)


List of supported operators in searching.

<table>
 <tr>
<td>
Operator.Equal</td></tr>
<tr>
<td>
Operator.NotEqual</td></tr>
<tr>
<td>
Operator.StartsWith</td></tr>
<tr>
<td>
Operator.EndsWith</td></tr>
<tr>
<td>
Operator.Contains</td></tr>
</table>
