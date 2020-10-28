---
layout: post
title: Globalization and Localization with Grid widget for ASP.NET Core
description: How to use globalization and localization 
platform: aspnet-core
control: Grid
documentation: ug
---

# Globalization and localization

## Localization

All text in grid can be localized using `ej.Grid.Locale` object. Find the following table with list of properties and its value in the locale object.

<table>
<tr>
<th>
Locale key words </th><th>
Text</th></tr>
<tr>
<td>
EmptyRecord</td><td>
No records to display.</td></tr>
<tr>
<td>
PagerInfo</td><td>
{0} of {1} pages ({2} items)</td></tr>
<tr>
<td>
GroupDropArea</td><td>
Drag a column header here to group its column.</td></tr>
<tr>
<td>
DeleteOperationAlert</td><td>
No records selected for delete operation.</td></tr>
<tr>
<td>
EditOperationAlert</td><td>
No records selected for edit operation.</td></tr>
<tr>
<td>
SaveButton</td><td>
Save</td></tr>
<tr>
<td>
OKButton</td><td>
OK</td></tr>
<tr>
<td>
CancelButton</td><td>
Cancel</td></tr>
<tr>
<td>
EditFormTitle</td><td>
Details of</td></tr>
<tr>
<td>
AddFormTitle</td><td>
Add New Record</td></tr>
<tr>
<td>
GroupCaptionFormat</td><td>
{{"{{"}}:headerText{{}}}}: {{"{{"}}:key{{}}}} - {{"{{"}}:count{{}}}} {{"{{"}}if count == 1 {{}}}} item {{"{{"}}else{{}}}} items {{"{{"}}/if{{}}}}</td></tr>
<tr>
<td>
BatchSaveConfirm</td><td>
Are you sure you want to save changes?</td></tr>
<tr>
<td>
BatchSaveLostChanges</td><td>
Unsaved changes will be lost. Are you sure you want to continue?</td></tr>
<tr>
<td>
ConfirmDelete</td><td>
Are you sure you want to Delete Record?</td></tr>
<tr>
<td>
FrozenColumnsViewAlert</td><td>
Frozen columns should be in grid view area.</td></tr>
<tr>
<td>
FrozenColumnsScrollAlert</td><td>
Enable allowScrolling while using frozen Columns.</td></tr>
<tr>
<td>
FrozenNotSupportedException</td><td>
Frozen Columns and Rows are not supported for Grouping, Row Template, Detail Template, Hierarchy Grid and Batch Editing.</td></tr>
<tr>
<td>
Add</td><td>
Add</td></tr>
<tr>
<td>
Edit</td><td>
Edit</td></tr>
<tr>
<td>
Delete</td><td>
Delete</td></tr>
<tr>
<td>
Update</td><td>
Update</td></tr>
<tr>
<td>
Cancel</td><td>
Cancel</td></tr>
<tr>
<td>
Done</td><td>
Done</td></tr>
<tr>
<td>
Columns</td><td>
Columns</td></tr>
<tr>
<td>
PrintGrid</td><td>
Print</td></tr>
<tr>
<td>
ExcelExport</td><td>
Excel Export</td></tr>
<tr>
<td>
WordExport</td><td>
Word Export</td></tr>
<tr>
<td>
PdfExport</td><td>
PDF Export</td></tr>
<tr>
<td>
StringMenuOptions</td><td>
[{text: "StartsWith",value: "StartsWith"},{text: "EndsWith",value: "EndsWith"},{text: "Contains",value: "Contains"},{text: "Equal",value: "Equal"},{text: "NotEqual",value: "NotEqual"}]</td></tr>
<tr>
<td>
NumberMenuOptions</td><td>
[{text: "LessThan",value: "LessThan"},{text: "GreaterThan",value: "GreaterThan"},{text: "LessThanOrEqual",value: "LessThanOrEqual"},{text: "GreaterThanOrEqual",value: "GreaterThanOrEqual"},{text: "Equal",value: "Equal"},{text: "NotEqual",value: "NotEqual"}]</td></tr>
<tr>
<td>
PredicateAnd</td><td>
AND</td></tr>
<tr>
<td>
PredicateOr</td><td>
OR</td></tr>
<tr>
<td>
Filter</td><td>
Filter</td></tr>
<tr>
<td>
FilterMenuCaption</td><td>
Filter Value</td></tr>
<tr>
<td>
FilterbarTitle</td><td>
's filter bar cell</td></tr>
<tr>
<td>
MatchCase</td><td>
Match Case</td></tr>
<tr>
<td>
Clear</td><td>
Clear</td></tr>
<tr>
<td>
ResponsiveFilter</td><td>
Filter</td></tr>
<tr>
<td>
ResponsiveSorting</td><td>
Sort</td></tr>
<tr>
<td>
Search</td><td>
Search</td></tr>
<tr>
<td>
DatePickerWaterMark</td><td>
Select date</td></tr>
<tr>
<td>
EmptyDataSource</td><td>
DataSource must not be empty at initial load since columns are generated from dataSource in AutoGenerate Column grid.</td></tr>
<tr>
<td>
True</td><td>
True</td></tr>
<tr>
<td>
False</td><td>
False</td></tr>
<tr>
<td>
UnGroup</td><td>
Click here to ungroup</td></tr>
<tr>
<td>
AddRecord</td><td>
Add Record</td></tr>
<tr>
<td>
EditRecord</td><td>
Edit Record</td></tr>
<tr>
<td>
DeleteRecord</td><td>
Delete Record</td></tr>
<tr>
<td>
Save</td><td>
Save</td></tr>
<tr>
<td>
Grouping</td><td>
Grouping</td></tr>
<tr>
<td>
Ungrouping</td><td>
Ungrouping</td></tr>
<tr>
<td>
SortInAscendingOrder</td><td>
Sort In Ascending Order</td></tr>
<tr>
<td>
SortInDescendingOrder</td><td>
Sort In Descending Order</td></tr>
</table>


## Pager Localization

Paging in Grid can also be localized using the `ej.Pager.Locale` object. Please find the table with list of properties and its value in locale object.

<table>
<tr>
<th>
Locale key words </th><th>
Text</th></tr>
<tr>
<td>
PagerInfo</td><td>
{0} of {1} pages ({2} items)</td></tr>
<tr>
<td>
firstPageTooltip</td><td>
Go to first page</td></tr>
<tr>
<td>
lastPageTooltip</td><td>
Go to last page</td></tr>
<tr>
<td>
nextPageTooltip</td><td>
Go to next page</td></tr>
<tr>
<td>
previousPageTooltip</td><td>
Go to previous page</td></tr>
<tr>
<td>
nextPagerTooltip</td><td>
Go to next Pager</td></tr>
<tr>
<td>
previousPagerTooltip</td><td>
Go to previous Pager</td></tr>
</table>


{% tabs %}
{% highlight razor %}

   <ej-grid id="FlatGrid" allow-paging="true" allow-grouping="true" locale="de-DE" group-settings ="@(new GroupSettings { EnableDropAreaAnimation=false })" datasource="ViewBag.DataSource">
         <e-columns>
            <e-column field="OrderID" is-primary-key="true" header-text="Order ID" width="75" text-align="Right"></e-column>
            <e-column field="CustomerID" header-text="Customer ID" width="95"></e-column>
            <e-column field="EmployeeID" header-text="Employee ID" width="95" text-align="Right"></e-column>
            <e-column field="Freight" header-text="Freight" text-align="Right" width="75" format="{0:C}"></e-column>
            <e-column field="ShipCity" header-text="ShipCity" width="80"></e-column>
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

 ej.Grid.Locale["de-DE"] = {
    EmptyRecord: "Keine Aufzeichnungen angezeigt",
    GroupDropArea: "Ziehen Sie eine Spaltenüberschrift hier",
    DeleteOperationAlert: "Keine Einträge für Löschvorgang ausgewählt",
    EditOperationAlert: "Keine Einträge für Bearbeiten Betrieb ausgewählt",
    SaveButton: "Speichern",
    CancelButton: "stornieren",
    EditFormTitle: "Korrektur von",
    GroupCaptionFormat: "{{"{{"}}:field{{}}}}: {{"{{"}}:key{{}}}} - {{"{{"}}:count{{}}}} {{"{{"}}if count == 1{{}}}}Beiträge{{"{{"}}else{{}}}}Beiträges{{"{{"}}/if{{}}}}",
    UnGroup: "Klicken Sie hier, um die Gruppierung aufheben"
 };
 ej.Pager.Locale["de-DE"] = {
    pagerInfo: "{0} von {1} Seiten ({2} Beiträge)",
    firstPageTooltip: "Zur ersten Seite",
    lastPageTooltip: "Zur letzten Seite",
    nextPageTooltip: "Zur nächsten Seite",
    previousPageTooltip: "Zurück zur letzten Seite",
    nextPagerTooltip: "Zum nächsten Pager",
    previousPagerTooltip: "Zum vorherigen Pager"
 };
 
 </script>
{% endhighlight  %}
{% endtabs %}  


![](Localization_images/Globalizationandlocalization._img1.png)

I> You need to change pager locale in `ej.Pager.Locale` object.

## Excel-filter Localization


All text in Excel-filter can be localized using the `ej.ExcelFilter.Locale` object. Please find the table with list of properties and its value in locale object.

<table>
<tr>
<th>
Locale key words </th><th>
Text</th></tr>
<tr>
<td>
SortNoSmaller</td><td>
Sort Smallest to Largest</td></tr>
<tr>
<td>
SortNoLarger</td><td>
Sort Largest to smallest</td></tr>
<tr>
<td>
SortTextAscending</td><td>
Sort A to Z</td></tr>
<tr>
<td>
SortTextDescending</td><td>
Sort Z to A</td></tr>
<tr>
<td>
SortDateOldest</td><td>
Sort By Oldest</td></tr>
<tr>
<td>
SortDateNewest</td><td>
Sort By Newest</td></tr>
<tr>
<td>
SortByColor</td><td>
Sort By Color</td></tr>
<tr>
<td>
SortByCellColor</td><td>
Sort By Cell Color</td></tr>
<tr>
<td>
SortByFontColor:</td><td>
Sort By Font Color:</td></tr>
<tr>
<td>
FilterByColor</td><td>
Filter By Color</td></tr>
<tr>
<td>
SortColorOptions:</td><td>
[{ id: 1, background:"#FFFFFF"}, {id: 2, background:"#5EABDA"}],</td></tr>
<tr>
<td>
CustomSort</td><td>
Custom Sort</td></tr>
<tr>
<td>
FilterColorOptions</td><td>
{ id: 1, background:"#FFFFFF"}, {id: 2, background:"#5EABDA"}],</td></tr>
<tr>
<td>
FilterByCellColor</td><td>
Filter By Cell Color</td></tr>
<tr>
<td>
FilterByFontColor</td><td>
Filter By Font Color</td></tr>
<tr>
<td>
ClearFilter</td><td>
Clear Filter</td></tr>
<tr>
<td>
NumberFilter</td><td>
Number Filter</td></tr>
<tr>
<td>
TextFilter</td><td>
Text Filter</td></tr>
<tr>
<td>
DateFilter</td><td>
Date Filter</td></tr>
<tr>
<td>
DateTimeFilter</td><td>
Date Time Filters</td></tr>
<tr>
<td>
GuidFilter</td><td>
Guid Filters</td></tr>
<tr>
<td>
StringMenuOptions</td><td>
[{ text:"Equal",value:"equal"},{ text:"Not Equal", value:"notequal"},{ text:"Starts With",value:"startswith"}, { text:"Ends With",value:"endswith"},{ text:"Contains",value:"contains"}, {text:"Custom Filter", value:"customfilter"}],</td></tr>
<tr>
<td>
NumberMenuOptions</td><td>
[{text:"Equal",value:"equal"}, {text:"Not Equal",value:"notequal"}, { text:"Less Than",value:"lessthan"}, {text:"Less Than Or Equal", value:"lessthanorequal"}, {text:"Greater Than",value:"greaterthan"},{ text:"Greater Than Or Equal", value:"greaterthanorequal"}, { text:"Between",value:"between"},{ text:"Custom Filter", value:"customfilter"}]</td></tr>
<tr>
<td>
DateMenuOptions</td><td>
[{ text:"Equal", value:"equal"}, {text:"Not Equal",value:"notequal"},{text:"Less Than",>value:"lessthan"}, {text:"Less Than Or Equal",value:"lessthanorequal"}, {text:"Greater Than",value:"greaterthan"},{text:"Greater Than Or Equal", value:"greaterthanorequal"}, { text:"Between",value:"between"},{ text:"Custom Filter", value:"customfilter"}]</td></tr>
<tr>
<td>
DatetimeMenuOptions</td><td>
[{ text: "Equal", value: "equal" }, { text: "Not Equal", value: "notequal" }, { text: "Less Than", value: "lessthan" }, { text: "Less Than Or Equal", value: "lessthanorequal" }, { text: "Greater Than", value: "greaterthan" }, { text: "Greater Than Or Equal", value: "greaterthanorequal" }, { text: "Between", value: "between" }, { text: "Custom Filter", value: "customfilter" }]</td></tr>
<tr>
<td>
Top10MenuOptions</td><td>
[{ text:"Top", value:"top"},{text:"Bottom", value:"bottom"}]</td></tr>
<tr>
<td>GuidMenuOptions</td>
<td>[{ text: "Equal", value: "equal" }, { text: "Not Equal", value: "notequal" }, { text: "Custom Filter", value: "customfilter" }]</td>
</tr>
<tr>
<td>
title</td><td>
Custom Filter</td></tr>
<tr>
<td>
PredicateOr</td><td>
OR</td></tr>
<tr>
<td>
PredicateAnd</td><td>
AND</td></tr>
<tr>
<td>
OK</td><td>
OK</td></tr>
<tr>
<td>
MathCase</td><td>
Match Case</td></tr>
<tr>
<td>
Cancel</td><td>
Cancel</td></tr>
<tr>
<td>
NoResult</td><td>
No Match Found</td></tr>
<tr>
<td>
CheckBoxStatusMsg</td><td>
Not all items showing</td></tr>
<tr>
<td>
DatePickerWaterMark</td><td>
Select date</td></tr>
<tr>
<td>
DateTimePickerWaterMark</td><td>
Select date time</td></tr>
<tr>
<td>
True</td><td>
True</td></tr>
<tr>
<td>
False</td><td>
False</td></tr>
<tr>
<td>
SelectAll</td><td>
Select All</td></tr>
<tr>
<td>
Blanks</td><td>
Blanks</td></tr>
<tr>
<td>
Showrowswhere</td><td>
Show rows where</td></tr>
<tr>
<td>
NumericTextboxWaterMark</td><td>
Enter value</td></tr>
<tr>
<td>
Search</td><td>
Search</td></tr>
<tr>
<td>
AddToFilter</td><td>
Add current selection to filter</td></tr>
</table>
Please find the code

{% tabs %}
{% highlight razor %}

    <ej-grid id="FlatGrid" allow-paging="true" allow-filtering="true" locale="de-DE" datasource="ViewBag.DataSource">
        <e-filter-settings filter-type="Excel"/>
         <e-columns>
            <e-column field="OrderID" is-primary-key="true" header-text="Order ID" width="75" text-align="Right"></e-column>
            <e-column field="CustomerID" header-text="Customer ID" width="95"></e-column>
            <e-column field="EmployeeID" header-text="Employee ID" width="95" text-align="Right"></e-column>
            <e-column field="Freight" header-text="Freight" text-align="Right" width="75" format="{0:C}"></e-column>
            <e-column field="ShipCity" header-text="ShipCity" width="80"></e-column>
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
  ej.ExcelFilter.Locale["de-DE"] = {
      SortNoSmaller: "Art Anzahl kleiner",
      SortNoLarger: "Art Anzahl größer",
      SortTextAscending: "Sortieren aufsteigend Text",
      SortTextDescending: "Sortieren absteigend Text",
      SortDateOldest: "Sortieren Datum Älteste",
      SortDateNewest: "Datum sortieren Neueste",
      ClearFilter: "Filter löschen",
      DateFilter: "Datum Filter"
  }
 
</script>
{% endhighlight  %}
{% endtabs %}  

![](Localization_images/Globalizationandlocalization._img2.png)


## Globalization

The `ej.globalize` library is used to globalize numeric values in grid control using `format` property in `e-columns`. Globalize values will be automatically used when `locale` property is set with locale string value for example `en-US`.

{% tabs %}
{% highlight razor %}

    <ej-grid id="FlatGrid" allow-paging="true" allow-filtering="true" locale="de-DE" datasource="ViewBag.DataSource">
        <e-filter-settings filter-type="Excel"/>
         <e-columns>
            <e-column field="OrderID" is-primary-key="true" header-text="Order ID" width="75" text-align="Right"></e-column>
            <e-column field="CustomerID" header-text="Customer ID" width="95"></e-column>
            <e-column field="EmployeeID" header-text="Employee ID" width="95" text-align="Right"></e-column>
            <e-column field="Freight" header-text="Freight" text-align="Right" width="75" format="{0:C}"></e-column>
            <e-column field="ShipCity" header-text="ShipCity" width="80"></e-column>
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

![](Localization_images/Globalizationandlocalization._img3.png)

I> To translate our control content from default English to any of the culture, say For example - German language, then you need to refer the **ej.culture.de-DE.min.js** file in your application, after the reference of ej.web.all.min.js file. For all culture files, please download from the [GitHub](https://github.com/syncfusion/ej-global/tree/master/i18n) location.

{% seealso %} [localization](http://helpjs.syncfusion.com/js/localization) {% endseealso %}

## Right to left - RTL

By default, grid renders its text and layout from left to right. To customize grid's direction, you can change direction from LTR to RTL by setting the `enable-rtl` as true.

{% tabs %}
{% highlight razor %}

    <ej-grid id="FlatGrid" allow-paging="true" enable-rtl="true" datasource="ViewBag.DataSource">
        <e-filter-settings filter-type="Excel"/>
         <e-columns>
            <e-column field="OrderID" is-primary-key="true" header-text="Order ID" width="120" text-align="Right"></e-column>
            <e-column field="CustomerID" header-text="Customer ID" width="120"></e-column>
            <e-column field="EmployeeID" header-text="Employee ID" width="120" text-align="Right"></e-column>
            <e-column field="Freight" header-text="Freight" text-align="Right" width="120" format="{0:C}"></e-column>
            <e-column field="ShipCity" header-text="ShipCity" width="120"></e-column>
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

![](Localization_images/Globalizationandlocalization._img4.png)