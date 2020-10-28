---
layout: post
title: Context Menu with grid widget for Syncfusion Essential ASP.NET Core
description: How to enable contextMenu and its functionalities
platform: aspnet-core
control: Grid
documentation: ug
---

# Context Menu

The context menu is used to improve user action with the grid using popup menu. It can be shown by defining the `enable-context-menu` property of `context-menu-settings` as true. Context menu has option to add default items in the `context-menu-items` property of `context-menu-settings` and customized items in the `context-menu-items` property of `context-menu-settings`.

## Default context menu items

Please find the following table for default context menu items and its actions.

 <table>
        <tr>
            <th>
                Section
            </th>
            <th>
                Context menu items.
            </th>
            <th>
                Action
            </th>
        </tr>
        <tr>
            <td rowspan="4">
                Header
            </td>
            <td>
                Sort in Ascending Order.
            </td>
            <td>
                Sort column in Ascending order.
            </td>
        </tr>
        <tr>
            <td>
                Sort in Descending Order.
            </td>
            <td>
                Sort column in Descending order.
            </td>
        </tr>
        <tr>
            <td>
                Group
            </td>
            <td>
                Group the current column.
            </td>
        </tr>
        <tr>
            <td>
                Ungroup
            </td>
            <td>
                Ungroup the current column if already grouped.
            </td>
        </tr>
        <tr>
            <td rowspan="5">
                Body
            </td>
            <td>
                Add Record
            </td>
            <td>
                Start Add new record.
            </td>
        </tr>
        <tr>
            <td>
                Edit Record
            </td>
            <td>
                Start Edit in current record.
            </td>
        </tr>
        <tr>
            <td>
                Delete Record
            </td>
            <td>
                Delete the current record.
            </td>
        </tr>
        <tr>
            <td>
                Save
            </td>
            <td>
                Save the record if Add/Edit record is started.
            </td>
        </tr>
        <tr>
            <td>
                Cancel
            </td>
            <td>
                Cancel Added/Edited state.
            </td>
        </tr>
        <tr>
            <td rowspan="4">
                Pager
            </td>
            <td>
                Next Page
            </td>
            <td>
                Go to Next Page.
            </td>
        </tr>
        <tr>            
            <td>
                Last Page
            </td>
            <td>
                Go to Last page.
            </td>
        </tr>
        <tr>
            <td>
                Previous page
            </td>
            <td>
                Go to previous page.
            </td>
        </tr>
        <tr>
            <td>
                First page
            </td>
            <td>
                Go to first page.
            </td>
        </tr>
 </table>
 
{% tabs %}
{% highlight RAZOR %}

<ej-grid id="FlatGrid" allow-paging="true" allow-sorting="true" allow-grouping="true" datasource="ViewBag.DataSource">
    <e-edit-settings allow-adding="true" allow-editing="true" allow-deleting="true"></e-edit-settings>
    <e-toolbar-settings show-toolbar="true" toolbar-items='@new List<string> {"add","edit","delete","update","cancel"}' />
    <e-context-menu-settings enable-context-menu="true"></e-context-menu-settings>
    <e-columns>
        <e-column field="OrderID" is-primary-key="true" header-text="Order ID"></e-column>
        <e-column field="CustomerID" header-text="CustomerID"></e-column>
        <e-column field="EmployeeID" header-text="Employee ID"></e-column>
        <e-column field="Freight" format="{0:c2}" header-text="Freight"></e-column>
        <e-column field="ShipName" header-text="Ship Name"></e-column>
    </e-columns>
</ej-grid>

{% endhighlight  %}

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

![](Context-Menu_images/ContextMenu_img1.png)
{:caption}

Context menu at header

![](Context-Menu_images/ContextMenu_img2.png)
{:caption}

Context menu at body

![](Context-Menu_images/ContextMenu_img3.png)
{:caption}

Context menu at pager

N> The `allow-grouping`, `allow-sorting` should be enabled to perform default context menu actions in the grid header. The `allow-editing`, `allow-deleting` and `allow-adding` should be enabled to perform default actions in body.




