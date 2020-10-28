---
layout: post
title: Worksheets with Spreadsheet widget for Syncfusion Essential ASP.NET Core
description: How to use and customize the Spreadsheet Worksheet
platform: aspnet-core
control: Spreadsheet
documentation: ug
keywords: 
--- 

# Worksheet
Worksheet is a collection of cells organized in the form of rows and columns that allow us to store, format, manipulate and display data in grid format. You can create multiple sheets in Spreadsheet and use sheet tab for switching between those worksheets. By default, Spreadsheet creates single worksheet since default `sheet-count` value is `1`.

## List of Sheet Operations 
You can perform following operations in worksheet,
 
* Add
* Remove
* Rename
* Move and Copy

### Add
The Spreadsheet has support for inserting new sheet. You can insert sheet in two ways.

* Add a new sheet as last sheet.
* Insert a new sheet before the active sheet.

### Add Sheet
You can dynamically add a sheet by one of the following ways,

* Click the new sheet button in the Spreadsheet sheet tab.
* Using [`addNewSheet`](http://help.syncfusion.com/api/js/ejspreadsheet#methods:addnewsheet "addNewSheet") method.

### Insert Sheet
You can dynamically insert a sheet by one of the following ways,

* Right clicking on the worksheet in the sheet tab and then click Insert option in the context menu.
* Click OTHERS tab in the ribbon and select Insert Sheet option in Insert dropdown button.
* Using [`insertSheet`](http://help.syncfusion.com/api/js/ejspreadsheet#methods:insertsheet "insertSheet") method.

The following code example describes the above behavior

{% highlight cshtml %}

<ej-spread-sheet id="Spreadsheet" load-complete="loadComplete">
</ej-spread-sheet>
    
{% endhighlight %}

{% highlight js %}
<script type="text/javascript">
    function loadComplete(args) {
        if (!this.isImport) {
            this.addNewSheet(); //To add as a last sheet.
            //this.insertSheet(); // To insert a sheet before the active sheet.		
        }
    }
</script>
{% endhighlight %}

The following output is displayed as a result of the above code example.
![](Worksheet_images/Worksheet_img1.png)

### Copy
The Spreadsheet provides support to create a copy of an existing worksheet. You can dynamically copy a worksheet by using one of the following ways,

* Right clicking on the worksheet in the sheet tab and then click Move or Copy in the context menu. Check the “Create a copy” checkbox in the “Move or Copy” dialog.
* Copy an existing worksheet using [`copySheet`](http://help.syncfusion.com/api/js/ejspreadsheet#methods:copysheet "copySheet") method.

The following code example describes the above behavior

{% highlight cshtml %}

<ej-spread-sheet id="Spreadsheet" sheet-count="3" load-complete="loadComplete">
</ej-spread-sheet>
    
<script type="text/javascript">
    function loadComplete(args) {
        if (!this.isImport) 
            this.copySheet(1, 3, true); //arg1- from index, arg2 -to index, arg3 - isCopySheet
    }
</script>
    
{% endhighlight %}

The following output is displayed as a result of the above code example.
![](Worksheet_images/Worksheet_img2.png)

### Move
The Spreadsheet provides support to move an existing worksheet. You can dynamically move a worksheet by using one of the following ways,

* Right clicking on the worksheet in the sheet tab and then click Move or Copy in the context menu. Select the sheet that you have to move in the “Move or Copy” dialog.
* Move an existing worksheet using [`copySheet`](http://help.syncfusion.com/api/js/ejspreadsheet#methods:copysheet "copySheet") method.

The following code example describes the above behavior

{% highlight cshtml %}

<ej-spread-sheet id="Spreadsheet" sheet-count="3" load-complete="loadComplete">
</ej-spread-sheet>
    
<script type="text/javascript">
    function loadComplete(args) {
        if (!this.isImport) 
            this.copySheet(1, 3, false); //arg1- from index, arg2 -to index, arg3 - isCopySheet
    }
</script>
    
{% endhighlight %}

The following output is displayed as a result of the above code example.
![](Worksheet_images/Worksheet_img3.png)

### Remove
The Spreadsheet has support for removing an existing worksheet. You can dynamically remove the existing sheet by following ways,

* Right click on the worksheet in the sheet tab and then click Delete option in the context menu.
* Select the existing worksheet, click OTHERS tab in the ribbon and select Delete dropdown button. Then click Delete Sheet.

You can also remove an active worksheet using [`deleteSheet`](http://help.syncfusion.com/api/js/ejspreadsheet#methods:deletesheet "deleteSheet") method.

The following code example describes the above behavior

{% highlight cshtml %}

<ej-spread-sheet id="Spreadsheet" sheet-count="2" load-complete="loadComplete">
</ej-spread-sheet>
    
<script type="text/javascript">
    function loadComplete(args) {
        if (!this.isImport) 
            this.deleteSheet();
    }
</script>
    
{% endhighlight %}

The following output is displayed as a result of the above code example.
![](Worksheet_images/Worksheet_img4.png)

### Rename
The Spreadsheet has support for renaming an existing worksheet. You can dynamically rename worksheet by using one of the following ways,

* Right clicking on the worksheet in the sheet tab and then click Rename option in the context menu.
* Rename an active worksheet using [`sheetRename`](http://help.syncfusion.com/api/js/ejspreadsheet#methods:sheetrename "sheetRename") method.

The following code example describes the above behavior

{% highlight cshtml %}

<ej-spread-sheet id="Spreadsheet" sheet-count="2" load-complete="loadComplete">
</ej-spread-sheet>
    
<script type="text/javascript">
    function loadComplete(args) {
        if (!this.isImport) 
            this.sheetRename("RenameSheet")
        
    }
</script>

{% endhighlight %}

The following output is displayed as a result of the above code example.
![](Worksheet_images/Worksheet_img5.png)

## Headers
Headers in the Spreadsheet are numbered rows and lettered columns in worksheets. It makes ease of view and reference to your data. You can dynamically show/hide worksheet header by using one of the following ways,

* Select PAGE LAYOUT tab in the ribbon and then check or uncheck Headings in the Show group.
* Show/Hide the worksheet headers using `show-headings` property and [`showHeadings`](http://help.syncfusion.com/api/js/ejspreadsheet#methods:showheadings "showHeadings") method.

The following code example describes the above behavior

{% highlight cshtml %}

<ej-spread-sheet id="Spreadsheet" >
    <e-sheets>
        <e-sheet show-headings="false"></e-sheet>
    </e-sheets>
</ej-spread-sheet>
    
{% endhighlight %}

The following output is displayed as a result of the above code example.
![](Worksheet_images/Worksheet_img6.png)

## Show / Hide Sheets
You can dynamically show/hide worksheet by using one of the following ways,

* Right clicking on the worksheet in the sheet tab and then click Hide or Unhide in the context menu
* Hide the sheet using [`hideSheet`](http://help.syncfusion.com/api/js/ejspreadsheet#methods:hidesheet "hideSheet") method.
* Show the hidden sheet using [`unhideSheet`](http://help.syncfusion.com/api/js/ejspreadsheet#methods:unhidesheet "unhideSheet") method.

The following code example describes the above behavior

{% highlight cshtml %}

<ej-spread-sheet id="Spreadsheet" sheet-count="3" load-complete="loadComplete">
</ej-spread-sheet>

<script type="text/javascript">
    function loadComplete(args) {
        if (!this.isImport) {
            this.hideSheet(1);
            this.hideSheet(2);
            this.unhideSheet(1);
        }
    }
</script>

{% endhighlight %}

The following output is displayed as a result of the above code example.
![](Worksheet_images/Worksheet_img7.png)

## Show / Hide Gridlines
Gridlines act as a border like appearance of cells. They are used to distinguish cells on the worksheet. You can dynamically show/hide gridlines by using one of the following ways,

* Select PAGE LAYOUT tab in the ribbon and then check or uncheck Gridlines in the Show group.
* Show/Hide gridlines in a worksheet using `show-gridlines` property and [`showGridlines`](http://help.syncfusion.com/api/js/ejspreadsheet#methods:showgridlines "showGridlines") method.

The following code example describes the above behavior

{% highlight cshtml %}

<ej-spread-sheet id="Spreadsheet" >
    <e-sheets>
        <e-sheet show-gridlines="false"></e-sheet>
    </e-sheets>
</ej-spread-sheet>

{% endhighlight %}

The following output is displayed as a result of the above code example.
![](Worksheet_images/Worksheet_img8.png)

