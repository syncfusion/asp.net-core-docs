---
layout: post
title: Editing with Grid widget for Syncfusion Essential ASP.NET Core
description:  How to perform editing and configure edit time functionalities like edit type, edit time controls etc
platform: aspnet-core
control: Grid
documentation: ug
---
# Editing

The Grid control has support for dynamic insertion, updating and deletion of records. You can start the edit action either by double clicking the particular row or by selecting the required row and clicking on Edit icon in toolbar. Similarly, you can add new record to grid either by clicking on insert icon in toolbar or on an external button which is bound to call `addRecord` method of grid.  `Save` and `Cancel` while on edit mode is possible using respective toolbar icon in grid.

Deletion of the record is possible by selecting the required row and clicking on Delete icon in toolbar. 

The primary key for the data source should be defined in `e-columns` definition, for editing to work properly. In `e-columns` definition, particular primary column's `is-primary-key` property should be set to `true`. Refer to the Knowledge base [link](http://www.syncfusion.com/kb/2675/cant-edit-any-row-except-the-first-row-in-grid# "link") for more information.

N> 1. In grid, the primary key column will be automatically set to read only while editing the row, but you can specify primary key column value while adding a new record.
N> 2. The column which is specified as `is-identity` will be in readonly mode both while editing and adding a record. Also, auto incremented value is assigned to that `is-identity` column.

## Toolbar with edit option

Using toolbar which is rendered at the top of the grid header, you can show all the CRUD related action. To enable toolbar and toolbar items, set `show-toolbar` property as true and `toolbar-items`. The default toolbar items are `add`, `edit`, `delete`, `update` and `cancel`.

N> For `toolbar-items` property you can assign either `string` value ("Add") or `enum` value (`Syncfusion.JavaScript.ToolBarItems.Add`).

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
      <e-edit-settings allow-adding="true" allow-editing="true" allow-deleting="true"></e-edit-settings>
      <e-toolbar-settings show-toolbar="true" toolbar-items='@new List<string> {"add","edit","update","cancel"}'/>
        <e-columns>
            <e-column field="OrderID" is-primary-key="true" header-text="Order ID"></e-column>
            <e-column field="CustomerID" header-text="CustomerID"></e-column>
            <e-column field="EmployeeID" header-text="Employee ID"></e-column>
            <e-column field="ShipCity" header-text="Ship City"></e-column>
            <e-column field="ShipCountry" header-text="Ship Country"></e-column>
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

![](Editing_images/Editing_img1.png)

## Cell edit type and its edit options

The edit type of bound column can be customized using `edit-type` property of `e-columns`. The following Essential JavaScript controls are supported by built-in `edit-type`. You can set the `edit-type` based on specific data type of the column. 

* `NumericTextBox` control for integers, double, and decimal data types.
* `DatePicker` control for date data type.
* `DateTimePicker` control for date-time data type.
* `DropDownList` control for list of data type.

Also, you can define the model for all the editTypes controls while editing through EJ TagHelper.

The following table describes the `edit-type` and their corresponding EditOptions of specific data type of the column.

<table>
<tr>
<th>
EditType</th><th>
EditParams</th><th>
Example</th></tr>
<tr>
<td>
NumericTextBox </td><td>
{{ '[TextBoxes](https://help.syncfusion.com/cr/aspnet-core/Syncfusion.JavaScript.Models.EditorProperties.html)' | markdownify }} </td><td>
&lt;ej-numeric-text-box decimal-places="2" /&gt;</td></tr>
<tr>
<td>
DatePicker </td><td>
{{ '[DatePicker](https://help.syncfusion.com/cr/aspnet-core/Syncfusion.JavaScript.Models.DatePickerProperties.html)' | markdownify }} </td><td>
&lt;ej-date-picker button-text="Now"/&gt;</td></tr>
<tr>
<td>
DateTimePicker</td><td>
{{ '[DateTimePicker](https://help.syncfusion.com/cr/aspnet-core/Syncfusion.JavaScript.Models.DateTimePickerProperties.html)' | markdownify }} </td><td>
&lt;ej-date-time-picker allow-edit="false"/&gt;</td></tr>
<tr>
<td>
DropDownList</td><td>
{{ '[DropDownList](https://help.syncfusion.com/cr/aspnet-core/Syncfusion.JavaScript.Models.DropDownListProperties.html)' | markdownify }} </td><td>
&lt;ej-drop-down-list show-checkbox="true"/&gt;</td></tr>
</table>

N> 1. If the `edit-type` is not set, then by default it will display the input element ("string") while editing a column.
N> 2. For `edit-type` property you can assign either `string` value ("Numeric") or `enum` value (`Syncfusion.JavaScript.EditingType.Numeric`).

The following code example describes the previous behavior. 

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
      <e-edit-settings allow-adding="true" allow-editing="true" allow-deleting="true"></e-edit-settings>
      <e-toolbar-settings show-toolbar="true" toolbar-items='@new List<string> {"add","edit","update","cancel"}'/>
        <e-columns>
            <e-column field="OrderID" is-primary-key="true" header-text="Order ID" text-align="Right"></e-column>
            <e-column field="CustomerID" header-text="CustomerID" edit-type="StringEdit"></e-column>
            <e-column field="Freight" edit-type="NumericEdit">
               <ej-numeric-text-box decimal-places="2" />  
            </e-column>
            <e-column field="ShipCity" header-text="Ship City" edit-type="DropdownEdit"></e-column>
            <e-column field="ShipCountry" header-text="Ship Country"></e-column>
            <e-column field="OrderDate" header-text="Order Date" edit-type="Datepicker"format="{0:MM/dd/yyyy}" ></e-column>
            <e-column field="Verified" header-text="Verified" edit-type="BooleanEdit"></e-column>
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

![](Editing_images/Editing_img2.png)

## Cell edit template

On editing the column values, custom editor can be created by using the `edit-template` property of `e-columns`. It has three functions, they are

1. `Create` - It is used to create the control at time of initialize.
2. `Read` - It is used to read the input value at time of save.
3. `Write` - It is used to assign the value to control at time of editing.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
      <e-edit-settings allow-adding="true" allow-editing="true" allow-deleting="true"></e-edit-settings>
      <e-toolbar-settings show-toolbar="true" toolbar-items='@new List<string> {"add","edit","update","cancel"}'/>
        <e-columns>
            <e-column field="OrderID" is-primary-key="true" header-text="Order ID"></e-column>
            <e-column field="CustomerID" header-text="CustomerID"></e-column>
            <e-column field="Freight" header-text="Freight"></e-column>
            <e-column field="ShipCountry" header-text="Ship Country"></e-column>
            <e-column field="ShipPostalCode" header-text="Ship Postal Code">
              <e-edit-template create="create" read="read" write="write"> 
              </e-edit-template>
            </e-column>
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

     <script id="template" type="application/javascript">
        function create() 
            {
	          return $("<input>");
            }
        function write(args) 
	       {
            args.element.ejMaskEdit({
                  maskFormat : "99-99-9999",
                  value : args.rowdata["ShipPostalCode"]
           });
           }
        function read(args) 
	       {
          return args.ejMaskEdit("get_StrippedValue");
          }
    
    </script>
    
{% endhighlight %}   
{% endtabs %}  

The following output is displayed as a result of the previous code example.

![](Editing_images/Editing_img3.png)


## Edit modes

### Inline 

Set the `edit-mode` as `Normal`, then the row itself is changed as edited row.

N> For the `edit-mode` property you can assign either `string` value (`Normal`) or `enum` value (`Syncfusion.JavaScript.EditMode.Normal`).

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
      <e-edit-settings allow-adding="true" allow-editing="true" allow-deleting="true" edit-mode="Normal"></e-edit-settings>
      <e-toolbar-settings show-toolbar="true" toolbar-items='@new List<string> {"add","edit","delete","update","cancel"}'/>
        <e-columns>
            <e-column field="OrderID" is-primary-key="true" header-text="Order ID" text-align="Right"></e-column>
            <e-column field="CustomerID" header-text="Customer ID" edit-type="StringEdit"></e-column>
            <e-column field="Freight" header-text="Freight" edit-type="NumericEdit">
               <e-numeric-edit-options decimal-places="2"></e-numeric-edit-options>  
            </e-column>
            <e-column field="ShipCountry" header-text="Ship Country" edit-type="DropdownEdit"></e-column>
            <e-column field="OrderDate" header-text="Order Date" edit-type="Datepicker" format="{0:MM/dd/yyyy}"></e-column>
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

![](Editing_images/Editing_img4.png)

### Inline form

Set the `edit-mode` as `InlineForm`, then edit form will be inserted next to the row which is to be edited.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
      <e-edit-settings allow-adding="true" allow-editing="true" allow-deleting="true" edit-mode="InlineForm"></e-edit-settings>
      <e-toolbar-settings show-toolbar="true" toolbar-items='@new List<string> {"add","edit","delete","update","cancel"}'/>
        <e-columns>
            <e-column field="OrderID" is-primary-key="true" header-text="Order ID" text-align="Right"></e-column>
            <e-column field="CustomerID" header-text="Customer ID" edit-type="StringEdit"></e-column>
            <e-column field="Freight" header-text="Freight" edit-type="NumericEdit">
               <e-numeric-edit-options decimal-places="2"></e-numeric-edit-options>  
            </e-column>
            <e-column field="ShipCountry" header-text="Ship Country" edit-type="DropdownEdit"></e-column>
            <e-column field="OrderDate" header-text="Order Date" edit-type="Datepicker" format="{0:MM/dd/yyyy}"></e-column>
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

![](Editing_images/Editing_img5.png)


### Inline template form

You can edit any of the fields pertaining to a single record of data and apply it to a template so that the same format is applied to all the other records that you may edit later.

Using this template support, you can edit the fields that are not bound to grid columns.

To edit the records using inline template form, set `edit-mode` as `InlineFormTemplate` and specify the template ID to `inline-form-template-id` property of `e-edit-settings`.

While using template form, you can change the HTML elements to appropriate JS controls based on the column type. This can be achieved by using the `action-complete` event of grid.

N> 1. The `value` attribute is used to bind the corresponding field value while editing.
N> 2. The `name` attribute is used to get the changed field values while saving the edited record.
N> 3. It's a standard way to enclose the `Template` within the `script` tag with `type` as "text/x-jsrender".
N> 4. For the `edit-mode` property you can assign either `string` value (`InlineFormTemplate`) or `enum` value (`Syncfusion.JavaScript.EditMode.InlineTemplateForm`) 

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
      <e-edit-settings allow-adding="true" allow-editing="true" allow-deleting="true" edit-mode="InlineFormTemplate" inline-form-template-id="#template" action-complete="complete"></e-edit-settings>
      <e-toolbar-settings show-toolbar="true" toolbar-items='@new List<string> {"add","edit","delete","update","cancel"}'/>
        <e-columns>
            <e-column field="OrderID" is-primary-key="true" header-text="Order ID" text-align="Right"></e-column>
            <e-column field="CustomerID" header-text="Customer ID" edit-type="StringEdit"></e-column>
            <e-column field="ShipCity" header-text="Ship City" edit-type="DropdownEdit"></e-column>
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
<script id="template" type="text/template">                             
   <table cellspacing="10">
		<tr>
			<td>Order ID</td>
			<td>
				<input id="OrderID" name="OrderID" disabled="disabled" value="{{"{{"}}:OrderID{{}}}}" class="e-field e-ejinputtext" style="width:116px;height:28px" />
            </td>
			<td>Customer ID</td>
			<td>
				<input id="CustomerID" name="CustomerID" value="{{"{{"}}:CustomerID{{}}}}" class="e-field e-ejinputtext" style="width: 116px; height: 28px" />
			</td>
		</tr>
		<tr>
			<td>Employee ID</td>
			<td>
				<input type="text" id="EmployeeID" name="EmployeeID" value="{{"{{"}}:EmployeeID{{}}}}" />
			</td>
			<td>Ship City</td>
			<td>
				<select id="ShipCity" name="ShipCity">
					<option value="Argentina">Argentina</option>
					<option value="Austria">Austria</option>
					<option value="Belgium">Belgium</option>
					<option value="Brazil">Brazil</option>
					<option value="Canada">Canada</option>
					<option value="Denmark">Denmark</option>
				</select>
			</td>
		</tr>
   </table>
 </script>
	    <script>
              function complete(args) {
	             $("#EmployeeID").ejNumericTextbox();
	             $("#Freight").ejNumericTextbox();
	             $("#ShipCity").ejDropDownList();
              }
        </script>
			  
{% endhighlight %}    
{% endtabs %} 

 The following output is displayed as a result of the previous code example.

![](Editing_images/Editing_img6.png)

Before the template elements are converted to JS controls

![](Editing_images/Editing_img7.png)

After the template elements are converted to JS controls using action-complete event.

### Dialog

Set the `edit-mode` as `Dialog` to edit data using a dialog box, which displays the fields associated with the data record being edited.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
      <e-edit-settings allow-adding="true" allow-editing="true" allow-deleting="true" edit-mode="Dialog"></e-edit-settings>
      <e-toolbar-settings show-toolbar="true" toolbar-items='@new List<string> {"add","edit","delete","update","cancel"}'/>
        <e-columns>
            <e-column field="OrderID" is-primary-key="true" header-text="Order ID" text-align="Right"></e-column>
            <e-column field="CustomerID" header-text="Customer ID" edit-type="StringEdit"></e-column>
            <e-column field="Freight" header-text="Freight" edit-type="NumericEdit">
               <e-numeric-edit-options decimal-places="2"></e-numeric-edit-options>  
            </e-column>
            <e-column field="ShipCountry" header-text="Ship Country" edit-type="DropdownEdit"></e-column>
            <e-column field="OrderDate" header-text="Order Date" edit-type="Datepicker" format="{0:MM/dd/yyyy}"></e-column>
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

![](Editing_images/Editing_img8.png)


### Dialog template form

You can edit any of the fields pertaining to a single record of data and apply it to a template so that the same format is applied to all the other records that you may edit later.

Using this template support, you can edit the fields that are not bound to grid columns.

To edit the records using Dialog template form, set  the`edit-mode` as 'DialogTemplate' and specify the template id to `dialog-editor-template-id` property of `e-edit-settings`.

While using template, you can change the elements that are defined in the `template`, to appropriate JS controls based on the column type. This can be achieved by using the `action-complete` event of grid.

N> 1. `value` attribute is used to bind the corresponding field value while editing.
N> 2. `name` attribute is used to get the changed field values while save the edited record. 
N> 3. For `edit-mode` property you can assign either `string` value (`DialogTemplate`) or `enum` value (`Syncfusion.JavaScript.EditMode.DialogTemplate`).

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
      <e-edit-settings allow-adding="true" allow-editing="true" allow-deleting="true" edit-mode="DialogTemplate" dialog-editor-template-id="#template" action-complete="complete"></e-edit-settings>
      <e-toolbar-settings show-toolbar="true" toolbar-items='@new List<string> {"add","edit","delete","update","cancel"}'/>
        <e-columns>
            <e-column field="OrderID" is-primary-key="true" header-text="Order ID" text-align="Right"></e-column>
            <e-column field="CustomerID" header-text="Customer ID" edit-type="StringEdit"></e-column>
            <e-column field="ShipCity" header-text="Ship City" edit-type="DropdownEdit"></e-column>
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
<script id="template" type="text/template">                             
   <table cellspacing="10">
		<tr>
			<td>Order ID</td>
			<td>
				<input id="OrderID" name="OrderID" disabled="disabled" value="{{"{{"}}:OrderID{{}}}}" class="e-field e-ejinputtext" style="width:116px;height:28px" />
            </td>
			<td>Customer ID</td>
			<td>
				<input id="CustomerID" name="CustomerID" value="{{"{{"}}:CustomerID{{}}}}" class="e-field e-ejinputtext" style="width: 116px; height: 28px" />
			</td>
		</tr>
		<tr>
			<td>Employee ID</td>
			<td>
				<input type="text" id="EmployeeID" name="EmployeeID" value="{{"{{"}}:EmployeeID{{}}}}" />
			</td>
			<td>Ship City</td>
			<td>
				<select id="ShipCity" name="ShipCity">
					<option value="Argentina">Argentina</option>
					<option value="Austria">Austria</option>
					<option value="Belgium">Belgium</option>
					<option value="Brazil">Brazil</option>
					<option value="Canada">Canada</option>
					<option value="Denmark">Denmark</option>
				</select>
			</td>
		</tr>
   </table>
 </script>
	    <script>
              function complete(args) {
	             $("#EmployeeID").ejNumericTextbox();
	             $("#Freight").ejNumericTextbox();
	             $("#ShipCity").ejDropDownList();
              }
        </script>
			  
{% endhighlight %}    
{% endtabs %} 

The following output is displayed as a result of the previous code example.

![](Editing_images/Editing_img9.png)

Before the template elements are converted to JS controls.

![](Editing_images/Editing_img10.png)

After the template elements are converted to JS controls using actionComplete event.

### External form

By setting the `edit-mode` as `ExternalForm`, the edit form is opened outside the grid content.

The following code example describes the previous behavior.
 
{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
      <e-edit-settings allow-adding="true" allow-editing="true" allow-deleting="true" edit-mode="ExternalForm"></e-edit-settings>
      <e-toolbar-settings show-toolbar="true" toolbar-items='@new List<string> {"add","edit","delete","update","cancel"}'/>
        <e-columns>
            <e-column field="OrderID" is-primary-key="true" header-text="Order ID" text-align="Right"></e-column>
            <e-column field="CustomerID" header-text="Customer ID" edit-type="StringEdit"></e-column>
            <e-column field="Freight" header-text="Freight" edit-type="NumericEdit">
               <e-numeric-edit-options decimal-places="2"></e-numeric-edit-options>  
            </e-column>
            <e-column field="ShipCountry" header-text="Ship Country" edit-type="DropdownEdit"></e-column>
            <e-column field="OrderDate" header-text="Order Date" edit-type="Datepicker" format="{0:MM/dd/yyyy}"></e-column>
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

![](Editing_images/Editing_img11.png)

Form position:

You can position an External edit form in the following two ways. 

1. Top-right
2. Bottom left

This can be achieved by setting the `form-position` property of `e-edit-settings` as 'TopRight' or 'BottomLeft'.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
      <e-edit-settings allow-adding="true" allow-editing="true" allow-deleting="true" edit-mode="ExternalForm" form-position="TopRight"></e-edit-settings>
      <e-toolbar-settings show-toolbar="true" toolbar-items='@new List<string> {"add","edit","delete","update","cancel"}'/>
        <e-columns>
            <e-column field="OrderID" is-primary-key="true" header-text="Order ID" text-align="Right"></e-column>
            <e-column field="CustomerID" header-text="Customer ID" edit-type="StringEdit"></e-column>
            <e-column field="Freight" header-text="Freight" edit-type="NumericEdit"></e-column>
            <e-column field="ShipCountry" header-text="Ship Country"></e-column>
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

![](Editing_images/Editing_img12.png)


### External template form

You can edit any of the fields pertaining to a single record of data and apply it to a template so that the same format is applied to all the other records that you may edit later.

Using this template support, you can edit the fields that are not bound to grid columns.

To edit the records using External template form, set `edit-mode` as `ExternalFormTemplate` and specify the template id to `external-form-template-id` property of `e-edit-settings`.

While using template, you can change the elements that are defined in the template, to appropriate JS controls based on the column type. This can be achieved by using `action-complete` event of grid.

N> 1. The `value` attribute is used to bind the corresponding field value while editing. 
N> 2. The `name` attribute is used to get the changed field values while save the edited record. 
N> 3. For `edit-mode` property you can assign either `string` value (`ExternalFormTemplate`) or `enum` value (`Syncfusion.JavaScript.EditMode.ExternalFormTemplate`).

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
      <e-edit-settings allow-adding="true" allow-editing="true" allow-deleting="true" edit-mode="ExternalFormTemplate" external-form-template-id="#template" action-complete="complete"></e-edit-settings>
      <e-toolbar-settings show-toolbar="true" toolbar-items='@new List<string> {"add","edit","delete","update","cancel"}'/>
        <e-columns>
            <e-column field="OrderID" is-primary-key="true" header-text="Order ID" text-align="Right"></e-column>
            <e-column field="CustomerID" header-text="Customer ID" edit-type="StringEdit"></e-column>
            <e-column field="ShipCity" header-text="Ship City" edit-type="DropdownEdit"></e-column>
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
<script id="template" type="text/template">                             
   <table cellspacing="10">
		<tr>
			<td>Order ID</td>
			<td>
				<input id="OrderID" name="OrderID" disabled="disabled" value="{{"{{"}}:OrderID{{}}}}" class="e-field e-ejinputtext" style="width:116px;height:28px" />
            </td>
			<td>Customer ID</td>
			<td>
				<input id="CustomerID" name="CustomerID" value="{{"{{"}}:CustomerID{{}}}}" class="e-field e-ejinputtext" style="width: 116px; height: 28px" />
			</td>
		</tr>
		<tr>
			<td>Employee ID</td>
			<td>
				<input type="text" id="EmployeeID" name="EmployeeID" value="{{"{{"}}:EmployeeID{{}}}}" />
			</td>
			<td>Ship City</td>
			<td>
				<select id="ShipCity" name="ShipCity">
					<option value="Argentina">Argentina</option>
					<option value="Austria">Austria</option>
					<option value="Belgium">Belgium</option>
					<option value="Brazil">Brazil</option>
					<option value="Canada">Canada</option>
					<option value="Denmark">Denmark</option>
				</select>
			</td>
		</tr>
   </table>
 </script>
	    <script>
              function complete(args) {
	             $("#EmployeeID").ejNumericTextbox();
	             $("#Freight").ejNumericTextbox();
	             $("#ShipCity").ejDropDownList();
              }
        </script>
			  
{% endhighlight %}    
{% endtabs %} 

The following output is displayed as a result of the previous code example.

![](Editing_images/Editing_img13.png)

Before the template elements are converted to JS controls.

![](Editing_images/Editing_img14.png)

After the template elements are converted to JS controls using actionComplete event.


### Batch / Excel-like

Users can start editing by clicking a cell and typing data into it. Edited cell will be marked while navigating to next cell or any other row, so that you know which fields or cells has been edited. Set the `edit-mode` as `Batch` to enable batch editing.

N> `getBatchChanges` method of grid holds the unsaved record changes.
N> Refer to the KB [link](http://www.syncfusion.com/kb/3016/how-to-suppress-grid-confirmation-messages# "link") for "How to suppress grid confirmation messages" in batch mode.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
      <e-edit-settings allow-adding="true" allow-editing="true" allow-deleting="true" edit-mode="Batch"></e-edit-settings>
      <e-toolbar-settings show-toolbar="true" toolbar-items='@new List<string> {"add","edit","delete","update","cancel"}'/>
        <e-columns>
            <e-column field="OrderID" is-primary-key="true" header-text="Order ID" text-align="Right"></e-column>
            <e-column field="CustomerID" header-text="Customer ID" edit-type="StringEdit"></e-column>
            <e-column field="Freight" header-text="Freight" edit-type="NumericEdit">
               <e-numeric-edit-options decimal-places="2"></e-numeric-edit-options>  
            </e-column>
            <e-column field="ShipCountry" header-text="Ship Country" edit-type="DropdownEdit"></e-column>
            <e-column field="OrderDate" header-text="Order Date" edit-type="Datepicker" format="{0:MM/dd/yyyy}"></e-column>
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

![](Editing_images/Editing_img15.png)


## Confirmation messages

To show the confirm dialog while saving or discarding the Batch changes (discarding during the grid action like filtering, sorting and paging), set the `show-confirm-dialog` as `true`.

N> The `show-confirm-dialog` property is only for Batch editing mode.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
      <e-edit-settings allow-adding="true" allow-editing="true" allow-deleting="true" edit-mode="Batch" show-confirm-dialog="true"></e-edit-settings>
      <e-toolbar-settings show-toolbar="true" toolbar-items='@new List<string> {"add","edit","delete","update","cancel"}'/>
        <e-columns>
            <e-column field="OrderID" is-primary-key="true" header-text="Order ID" text-align="Right"></e-column>
            <e-column field="CustomerID" header-text="Customer ID" edit-type="StringEdit"></e-column>
            <e-column field="Freight" header-text="Freight" edit-type="NumericEdit">
               <e-numeric-edit-options decimal-places="2"></e-numeric-edit-options>  
            </e-column>
            <e-column field="ShipCountry" header-text="Ship Country" edit-type="DropdownEdit"></e-column>
            <e-column field="OrderDate" header-text="Order Date" edit-type="Datepicker" format="{0:MM/dd/yyyy}"></e-column>
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

![](Editing_images/Editing_img16.png)

To show delete confirm dialog while deleting a record, set the `show-delete-confirm-dialog` as true.

N> The `show-delete-confirm-dialog` property is for all type of `edit-mode`.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
      <e-edit-settings allow-adding="true" allow-editing="true" allow-deleting="true" edit-mode="Batch" show-delete-confirm-dialog="true"></e-edit-settings>
      <e-toolbar-settings show-toolbar="true" toolbar-items='@new List<string> {"add","edit","delete","update","cancel"}'/>
        <e-columns>
            <e-column field="OrderID" is-primary-key="true" header-text="Order ID" text-align="Right"></e-column>
            <e-column field="CustomerID" header-text="Customer ID" edit-type="StringEdit"></e-column>
            <e-column field="Freight" header-text="Freight" edit-type="NumericEdit">
               <e-numeric-edit-options decimal-places="2"></e-numeric-edit-options>  
            </e-column>
            <e-column field="ShipCountry" header-text="Ship Country" edit-type="DropdownEdit"></e-column>
            <e-column field="OrderDate" header-text="Order Date" edit-type="Datepicker" format="{0:MM/dd/yyyy}"></e-column>
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

![](Editing_images/Editing_img17.png)


## Column validation

The value of the added or edited record cell can be validated before saving.

The below validation script files are needed when editing is enabled with validation.

1. jquery.validate.min.js
2. jquery.validate.unobtrusive.min.js
 
 
### jQuery validation


You can set validation rules using `validation-rules` property of `e-columns`. The following are jQuery validation methods.

__List__ __of__ __Jquery__ __validation__ __methods__

<table>
<tr>
<th>
Rules</th><th>
Description</th></tr>
<tr>
<td>
required</td><td>
Requires an element.</td></tr>
<tr>
<td>
remote</td><td>
Requests a resource to check the element for validity.</td></tr>
<tr>
<td>
minlength</td><td>
Requires the element to be of given minimum length.</td></tr>
<tr>
<td>
maxlength</td><td>
Requires the element to be of given maximum length.</td></tr>
<tr>
<td>
range</td><td>
Requires the element to be in given value range.</td></tr>
<tr>
<td>
min</td><td>
The element requires a given minimum.</td></tr>
<tr>
<td>
max</td><td>
The element requires a given maximum.</td></tr>
<tr>
<td>
email</td><td>
The element requires a valid email.</td></tr>
<tr>
<td>
url</td><td>
The element requires a valid URL.</td></tr>
<tr>
<td>
date</td><td>
Requires the element to be a date.</td></tr>
<tr>
<td>
dateISO</td><td>
The element requires an ISO date.</td></tr>
<tr>
<td>
number</td><td>
The element requires a decimal number.</td></tr>
<tr>
<td>
digits</td><td>
The element requires digits only.</td></tr>
<tr>
<td>
creditcard</td><td>
Requires the element to be a credit card number.</td></tr>
<tr>
<td>
equalTo</td><td>
Requires the element to be the same as another.</td></tr>
</table>

Grid supports all the standard validation methods of jQuery, please refer the jQuery validation documentation [link](http://jqueryvalidation.org/documentation/# "link") for more information.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
      <e-edit-settings allow-adding="true" allow-editing="true" allow-deleting="true"></e-edit-settings>
      <e-toolbar-settings show-toolbar="true" toolbar-items='@new List<string> {"add","edit","delete","update","cancel"}'/>
        <e-columns>
            <e-column field="OrderID" is-primary-key="true" header-text="Order ID" validation-rules='@(new Dictionary<string,object> { {"required",true}, {"number",true} })' text-align="Right"></e-column>
            <e-column field="CustomerID" header-text="Customer ID" edit-type="StringEdit" validation-rules='@(new Dictionary<string,object> { {"required",true}, {"minlength",3} })'></e-column>
            <e-column field="ShipCity" header-text="Ship City"></e-column>
            <e-column field="Freight" header-text="Freight" edit-type="NumericEdit" validation-rules='@(new Dictionary<string,object> { {"required",true}, {"range","[0,1000]"} })' ></e-column>
            <e-column field="ShipCountry" header-text="Ship Country"></e-column>
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

![](Editing_images/Editing_img18.png)


### Custom validation

In addition to jQuery validation methods, you can also add your own custom validation methods for a specific column. Function call to custom validator function to be mentioned within the `validation-rules` property of `e-columns`. 

Using the `messages` property of `validation-rules` you can specify the error message for that column.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
      <e-edit-settings allow-adding="true" allow-editing="true" allow-deleting="true"></e-edit-settings>
      <e-toolbar-settings show-toolbar="true" toolbar-items='@new List<string> {"add","edit","delete","update","cancel"}'/>
        <e-columns>
            <e-column field="OrderID" is-primary-key="true" header-text="Order ID"  text-align="Right"></e-column>
            <e-column field="CustomerID" header-text="Customer ID" edit-type="StringEdit" validation-rules='@(new Dictionary<string,object> {{"customRegex",5}})'></e-column>
            <e-column field="ShipCountry" header-text="Ship City"></e-column>
            <e-column field="Freight" header-text="Freight" edit-type="NumericEdit" validation-rules='@(new Dictionary<string,object> {{"customCompare",new List <Object>() {0,1000}} })' ></e-column>
            <e-column field="ShipCountry" header-text="Ship Country"></e-column>
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
          
          <script type="text/javascript">
               $(function () {
                  $.validator.addMethod("customCompare", function (value, element, params) {
                  return element.value > params[0] && element.value < params[1];
                }, "Freight value must be between 0 and 1000");

                  $.validator.addMethod("customRegex", function (value, element, params) {
                  if (element.value.length == params)
                  return true;
                  return false;
               }, "Customer ID must be 5 characters");
            });
          </script>
     
{% endhighlight  %}   
{% endtabs %} 

The following output is displayed as a result of the previous code example.

![](Editing_images/Editing_img19.png)


## Persisting data in server

Edited data can be persisted in database using RESTful web services. 

All the CRUD operations in grid are done through DataManager. DataManager have an option to bind all the CRUD related data in server-side. Please refer to the ['link'](https://help.syncfusion.com/aspnet-core/datamanager/overview) to know about the DataManager.

For your information, the ODataAdaptor persists data in server as per OData protocol.

In the below section, we have explained how to get the edited data details at the server-side using URLAdaptor. 


### URL adaptor

You can use the `UrlAdaptor` of DataManager when binding datasource from remote data. At initial load of grid, using url property of DataManager, data are fetched from remote data and bound to grid. You can map CRUD operation in grid to Server-Side Controller action using the properties `insert-url`, `remove-url`, `update-url`, `crud-url` and `batch-url`.

The following code example describes the previous behavior.

{% tabs %}

{% highlight razor %}

        <ej-grid id="FlatGrid" allow-paging="true" >
        <e-datamanager url="Home/DataSource" update-url="Home/Update" insert-url="Home/Insert" remove-url="Home/Delete" adaptor="UrlAdaptor"></e-datamanager>
        <e-toolbar-settings show-toolbar="true" toolbar-items=@(new List<string>() { "Add", "Edit", "Delete","Update","Cancel" }) >
        </e-toolbar-settings>
        <e-edit-settings allow-adding="true" allow-deleting="true" allow-editing="true"></e-edit-settings>
        <e-columns>
            <e-column field="OrderID" header-text="Order ID" is-primary-key="true"></e-column>
            <e-column field="CustomerID" header-text="Customer ID"></e-column>
            <e-column field="EmployeeID" header-text="Employee ID"></e-column>
            <e-column field="Freight" header-text="Freight" edit-type="NumericEdit"></e-column>
            <e-column field="ShipCity" header-text="Ship City"></e-column>
            <e-column field="ShipCountry" header-text="Ship Country"></e-column>
        </e-columns>
    </ej-grid>

{% endhighlight  %}

{% highlight c# %}

    namespace MVCSampleBrowser.Controllers
        {
         public partial class GridController : Controller
             {  // GET: /<controller>/
        private NORTHWNDContext _context;

        public GridController(NORTHWNDContext context)
        {
            _context = context;
        }
        public ActionResult DataSource(DataManager dm)
        {
            IEnumerable DataSource = _context.Orders.ToList();
            DataOperations operation = new DataOperations();
            var count = DataSource.AsQueryable().Count();
            if (dm.Skip > 0)
                DataSource = operation.PerformSkip(DataSource, dm.Skip);
            if (dm.Take > 0)
                DataSource = operation.PerformTake(DataSource, dm.Take);
            return Json(new { result = DataSource, count = count });
        }
        public class DataResult
        {
            public IEnumerable result { get; set; }
            public int count { get; set; }
        }
     } 
{% endhighlight  %}
    
{% endtabs %} 

Also when using the `UrlAdaptor`, you need to return the data as `JSON` and the JSON object must contain a property as `result` with dataSource as its value and one more property `count` with the dataSource total records count as its value.

The grid actions (sorting, filtering, paging, searching, and aggregates) details are obtained in the 'DataManager' class. While initializing the grid, paging only enabled hence in the below screenshot paging details are bound to the DataManager class.


using the 'DataOperations' helper class you can perform grid action at server-side. The in-built methods that we have provided in the DataOperations class are listed below.

1. PerformSorting
2. PerformFiltering
3. PerformSearching
4. PerformSkip
5. PerformTake
6. PerformWhereFilter
7. PerformSelect
8. Execute

### RemoteSave Adaptor:

RemoteSaveAdaptor is used for binding local data and performs all data operations in client-side. It interacts with server-side only for CRUD operations to pass the modified records.

Refer to the following code example

{% highlight razor %}

 <ej-grid id="FlatGrid" allow-paging="true" >
        <e-datamanager json="(IEnumerable<object>)ViewBag.datasource" update-url="Home/Update" insert-url="Home/Insert" remove-url="Home/Delete" adaptor="remoteSaveAdaptor"></e-datamanager>
        <e-toolbar-settings show-toolbar="true" toolbar-items=@(new List<string>() { "Add", "Edit", "Delete","Update","Cancel" }) >
        </e-toolbar-settings>
        <e-edit-settings allow-adding="true" allow-deleting="true" allow-editing="true"></e-edit-settings>
        <e-columns>
            <e-column field="OrderID" header-text="Order ID" is-primary-key="true"></e-column>
            <e-column field="CustomerID" header-text="Customer ID"></e-column>
            <e-column field="EmployeeID" header-text="Employee ID"></e-column>
            <e-column field="Freight" header-text="Freight" edit-type="NumericEdit"></e-column>
            <e-column field="ShipCity" header-text="Ship City"></e-column>
            <e-column field="ShipCountry" header-text="Ship Country"></e-column>
        </e-columns>
    </ej-grid>

{% endhighlight %}

### Accessing CRUD action request details in server-side:

The 'Server-Side' function must be declared with the following parameter name for each editing functionality.

__Parameters__ __Table__

<table>
        <tr>
            <th>
                Action
            </th>
            <th>
                Parameter Name</th>
            <th>
                Example
            </th>
        </tr>
        <tr>
            <td rowspan="2">
                Update,Insert
            </td>
            <td>
                value
            </td>
            <td rowspan="2">
                public ActionResult Update(CRUDModel<Orders> value){ }
            </td>
        </tr>
        <tr>
           
            <td>
                public ActionResult Insert(CRUDModel<Orders> value){ }
            </td>
        </tr>
        <tr>
            <td>
                Remove
            </td>
            <td>
                key
            </td>
            <td>
                public ActionResult Remove(int key){ }
            </td>
        </tr>
        <tr>
            <td>
                Batch Add
            </td>
            <td>
                added
            </td>
            <td rowspan="3">
                public ActionResult BatchUpdate([FromBody]CRUDModel&lt;OrderDetails&gt; myObject) { }
            </td>
        </tr>
        <tr>
            <td>
                Batch Update
            </td>
            <td>
                changed
            </td>
            
        </tr>
        <tr>
            <td>
                Batch Delete
            </td>
            <td>
                deleted
            </td>
           
        </tr>
        <tr>
            <td>
                Crud Update,Crud Insert
            </td>
            <td>
                value, action
            </td>
            <td>
                public ActionResult CrudUrl(CRUDModel<Orders> value, string action){ }
            </td>
        </tr>
        <tr>
            <td>
                Crud Remove
            </td>
            <td>
                action, key, keyColumn
            </td>
            <td>
                public ActionResult CrudUrl(string action, int? key, string keyColumn){ }
            </td>
        </tr>
        <tr>
            <td>
                Crud Remove - Multi Delete
            </td>
            <td>
                action, key, deleted
            </td>
            <td>
                public ActionResult CrudUrl(string action, string key, List &lt;CRUDModel<Orders>&gt; deleted){ }
            </td>
        </tr>
 </table>


	
### Insert record:

Using the `insert-url ` property, you can specify the controller action mapping URL to perform insert operation at server--side.

The following code example describes the previous behavior.

{% highlight c# %}
     
        public ActionResult Insert(CRUDModel<Orders> value)
        {
          order.Insert(order.Count, value.Value);
          return Json(order);
        }
{% endhighlight %}

The newly added record details are bound to the 'value' parameter. Please refer to the following image.


### Update record:

Using the `update-url` property, you can specify the controller action mapping URL to perform save/update operation at server-side.

The following code example describes the previous behavior.

{% highlight c# %}
          
     public ActionResult Update(CRUDModel<Orders> value)
        {
            var ord = value;
            OrderDetails val = order.Where(or => or.OrderID == ord.OrderID).FirstOrDefault();
            val.OrderID = ord.OrderID;
            val.EmployeeID = ord.EmployeeID;
            val.CustomerID = ord.CustomerID;
            val.Freight = ord.Freight;
            val.ShipCity = ord.ShipCity;
            return Json(myObject.Value);
            
        }
{% endhighlight %}

The updated record details are bound to the 'value' parameter. Please refer the below image.


### Delete Record:

Using the ` remove-url` property, you can specify the controller action mapping URL to perform delete operation at server side.

The following code example describes the previous behavior.

{% highlight c# %}
       
       public ActionResult Remove(int key)
        {
	       order.Remove(order.Where(or => or.OrderID == int.Parse(Key.ToString())).FirstOrDefault());
           return Json(value);
        }
{% endhighlight %}

The deleted record primary key value is bound to the 'key' parameter. Please refer to the following image.


### CRUD URL:

Instead of specifying separate controller action method for CRUD (insert, update and delete)operation, using `crud-url` property you can specify the controller action mapping URL to perform all the CRUD operation at server-side using single method.

The action parameter of `crud-url` is used to get the corresponding CRUD action.

The following code example describes the previous behavior.

{% tabs %}

{% highlight razor %}

    <ej-grid id="FlatGrid" allow-paging="true">
        <e-datamanager url="Home/DataSource" crud-url="Home/CrudUpdate" adaptor="@AdaptorType.UrlAdaptor"></e-datamanager>
        <e-toolbar-settings show-toolbar="true" toolbar-items=@(new List<string>() { "Add", "Edit", "Delete","Update","Cancel" }) >
        </e-toolbar-settings>
        <e-edit-settings allow-adding="true" allow-deleting="true" allow-editing="true"></e-edit-settings>
        <e-columns>
            <e-column field="OrderID" header-text="Order ID" is-primary-key="true"></e-column>
            <e-column field="CustomerID" header-text="Customer ID"></e-column>
            <e-column field="EmployeeID" header-text="Employee ID"></e-column>
            <e-column field="Freight" header-text="Freight" edit-type="@EditingType.NumericEdit"></e-column>
            <e-column field="ShipCity" header-text="Ship City"></e-column>
            <e-column field="ShipCountry" header-text="Ship Country"></e-column>
        </e-columns>
    </ej-grid>
   
{% endhighlight  %}

{% highlight c# %}
        public ActionResult CrudUpdate(CRUDModel<Orders> value, string action)
        {
            if (myObject.Action == "update")
            {
                var ord = myObject.Value;
                OrderDetails val = order.Where(or => or.OrderID == ord.OrderID).FirstOrDefault();
                val.OrderID = ord.OrderID;
                val.EmployeeID = ord.EmployeeID;
                val.CustomerID = ord.CustomerID;
                val.Freight = ord.Freight;
                val.ShipCity = ord.ShipCity;               
            }
            if (myObject.Action == "insert")
            {
                order.Insert(order.Count, myObject.Value);
               
            }
            if (myObject.Action == "remove")
            {
                order.Remove(order.Where(or => or.OrderID == int.Parse(myObject.Key.ToString())).FirstOrDefault());
               
            }
            return Json(myObject.Value);
        }
{% endhighlight %}

{% endtabs %} 


N> If you specify `insert-url` along with `crud-url` then while adding `insert-url` only called.


### Batch URL:

The `batch-url` property supports only for batch editing mode. You can specify the controller action mapping URL to perform Batch operation at server-side.

The following code example describes the previous behavior.

{% tabs %}

{% highlight razor %}

        <ej-grid id="FlatGrid" allow-paging="true">
        <e-datamanager url="Home/DataSource" batch-url="Home/BatchUpdate" adaptor="@AdaptorType.UrlAdaptor"></e-datamanager>
        <e-toolbar-settings show-toolbar="true" toolbar-items=@(new List<string>() { "Add", "Edit", "Delete","Update","Cancel" }) >
        </e-toolbar-settings>
        <e-edit-settings allow-adding="true" allow-deleting="true" allow-editing="true"></e-edit-settings>
        <e-columns>
            <e-column field="OrderID" header-text="Order ID" is-primary-key="true"></e-column>
            <e-column field="CustomerID" header-text="Customer ID"></e-column>
            <e-column field="EmployeeID" header-text="Employee ID"></e-column>
            <e-column field="Freight" header-text="Freight" edit-type="@EditingType.NumericEdit"></e-column>
            <e-column field="ShipCity" header-text="Ship City"></e-column>
            <e-column field="ShipCountry" header-text="Ship Country"></e-column>
        </e-columns>
    </ej-grid>

{% endhighlight  %}

{% highlight c# %}

        public ActionResult BatchUpdate([FromBody]CRUDModel<OrderDetails> myObject)
        {
            if (myObject.Changed != null && myObject.Changed.Count > 0)
            {
                foreach (var temp in myObject.Changed)
                {
                    var ord = temp;
                    Order val = order.Where(or => or.OrderID == ord.OrderID).FirstOrDefault();
                    val.OrderID = ord.OrderID;
                    val.EmployeeID = ord.EmployeeID;
                    val.CustomerID = ord.CustomerID;
                    val.Freight = ord.Freight;
                    val.OrderDate = ord.OrderDate;
                    val.ShipCity = ord.ShipCity;
                }
            }
            if (myObject.Added != null && myObject.Added.Count > 0)
            {
                foreach (var temp in myObject.Added)
                {
                    order.Insert(0, temp);
                }
            }
            if (myObject.Deleted != null && myObject.Deleted.Count > 0)
            {
                foreach (var temp in myObject.Deleted)
                {
                    order.Remove(order.Where(or => or.OrderID == temp.OrderID).FirstOrDefault());
                }
            }

            var data = myObject;
            return Json(data);
        }

{% endhighlight %}

{% endtabs %}

## Adding new row position

To add new row in the top or bottom position of grid content, set the `row-position` property of `e-edit-settings` depending on the requirement.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
      <e-edit-settings allow-adding="true" allow-editing="true" allow-deleting="true" row-position="Bottom"></e-edit-settings>
      <e-toolbar-settings show-toolbar="true" toolbar-items='@new List<string> {"add","edit","delete","update","cancel"}'/>
        <e-columns>
            <e-column field="OrderID" is-primary-key="true" header-text="Order ID"></e-column>
            <e-column field="CustomerID" header-text="Customer ID"></e-column>
            <e-column field="ShipCity" header-text="Ship City"></e-column>
            <e-column field="Freight" header-text="Freight" edit-type="NumericEdit"></e-column>
            <e-column field="ShipCountry" header-text="Ship Country"></e-column>
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

![](Editing_images/Editing_img26.png)


## Render with blank row for easy add new

The blank add new row is displayed in the grid content during grid initialization itself to add a new record easily. To enable show add new row by default, set the `show-add-new-row` property of `e-edit-settings` as `true`.

The blank add new row is displayed either in the top or bottom of the corresponding page, its position is based on the `row-position` property of `e-edit-settings`.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
      <e-edit-settings allow-adding="true" allow-editing="true" allow-deleting="true" show-add-new-row="true"></e-edit-settings>
      <e-toolbar-settings show-toolbar="true" toolbar-items='@new List<string> {"add","edit","delete","update","cancel"}'/>
        <e-columns>
            <e-column field="OrderID" is-primary-key="true" header-text="Order ID"></e-column>
            <e-column field="CustomerID" header-text="Customer ID"></e-column>
            <e-column field="ShipCity" header-text="Ship City"></e-column>
            <e-column field="Freight" header-text="Freight" edit-type="NumericEdit"></e-column>
            <e-column field="ShipCountry" header-text="Ship Country"></e-column>
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

![](Editing_images/Editing_img27.png)

N> 1. If it is remote, then the newly added record is placed based on the index from current view data. 
N> 2. If it is local, then the newly added record is added at the top of the page even if the added new `row-position` is mentioned as "Bottom".


## Default column values on add new

While adding new record in grid, there is an option to set the default value for the columns. Using the `default-value` property of `e-columns` you can set the default values for that particular column while editing or adding a new row.

The following code example describes the previous behavior.

{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" datasource="ViewBag.DataSource">
      <e-edit-settings allow-adding="true" allow-editing="true" allow-deleting="true" show-add-new-row="true"></e-edit-settings>
      <e-toolbar-settings show-toolbar="true" toolbar-items='@new List<string> {"add","edit","delete","update","cancel"}'/>
        <e-columns>
            <e-column field="OrderID" is-primary-key="true" header-text="Order ID"></e-column>
            <e-column field="CustomerID" header-text="Customer ID"></e-column>
            <e-column field="ShipCity" header-text="Ship City" default-value="Bern"></e-column>
            <e-column field="Freight" header-text="Freight" edit-type="NumericEdit" default-value="45"></e-column>
            <e-column field="ShipCountry" header-text="Ship Country" default-value="Brazil"></e-column>
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

![](Editing_images/Editing_img28.png)
