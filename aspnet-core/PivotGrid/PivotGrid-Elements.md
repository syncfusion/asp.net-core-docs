---
layout: post
title: PivotGrid Elements | PivotGrid | ASP.NET Core | Syncfusion
description: This document illustrates that how to customize cells with an interactive way in ASP.NET Core PivotGrid control
platform: aspnet-core
control: PivotGrid
documentation: ug
---

# Pivot grid: Elements

## Hyperlink
The pivot grid control supports hyperlink option to link the data for each individual cell. The hyperlink can be enabled separately for row header, column header, value, and summary cells. Following are the respective properties:

* **enable-column-header-hyperlink**: Enables hyperlink for column headers.
* **enable-row-header-hyperlink**: Enables hyperlink for row headers.
* **enable-summary-cell-hyperlink**: Enables hyperlink for the summary cell.
* **enable-value-cell-hyperlink**: Enables hyperlink for the value cell.

Also, hyperlink option provides separate events for row header, column header, value, and summary cells as mentioned below:

* **column-header-hyperlink-click**: Returns column header information through the event by clicking the hyperlink.
* **row-header-hyperlink-click**: Returns row header information through the event by clicking the hyperlink.
* **summary-cell-hyperlink-click**: Returns summary cell information through the event by clicking the hyperlink.
* **value-cell-hyperlink-click**: Returns value cell information through the event by clicking the hyperlink.

{% highlight CSHTML %}

<ej-pivot-grid id="PivotGrid1" value-cell-hyperlink-click="CellClickEvent" row-header-hyperlink-click="CellClickEvent" column-header-hyperlink-click="CellClickEvent" summary-cell-hyperlink-click="CellClickEvent">
    <e-hyperlink enable-column-header-hyperlink="true" enable-value-cell-hyperlink="true" enable-row-header-hyperlink="true" enable-summary-cell-hyperlink="true"></e-hyperlink>
</ej-pivot-grid>

<script type="text/javascript">
    CellClickEvent = function (evt) {
        alert("Cell Click event is fired");
    }
</script>

{% endhighlight %}

![Hyperlink in ASP NET Core pivot grid control](PivotGrid-Elements_images/hyperlink.png)

## Selection
You can select a particular range of value cells from the pivot grid and manipulate/display them. The cell selection is applicable only for value cells and you can enable this functionality by setting the `EnableCellSelection` property to true.

The **"CellSelection"** event will be triggered as soon as the selection process is over, i.e., the event will be triggered when you release the mouse left-click. The event argument contains a collection of JSON records, and header values contains information about the selected cells.

{% highlight CSHTML %}

<ej:PivotGrid ID="PivotGrid1" runat="server" EnableCellSelection="true" >
    <ClientSideEvents CellSelection="valueCellClick"/>
</ej:PivotGrid>

<ej-pivot-grid id="PivotGrid1" enable-cell-selection="true" cell-selection="valueCellClick">
</ej-pivot-grid>

<script type="text/javascript">
    valueCellClick = function(evt) {
        // The event lets you to perform required operation with the selected set of cells. The details of the selected range can be obtained in the parameter of the event.
        cellvalue = evt.JSONRecords;
        rowheaders = evt.rowHeader;
        colheaders = evt.columnHeader;
    }
</script>

{% endhighlight %}

![Cell selection in ASP NET Core pivot grid control](PivotGrid-Elements_images/cellselection.png)

## Cell context
The cell context allows you to perform any custom operation by right-clicking the cell. For example, you can create and display the context menu by right-clicking the cell.

The cell context is enabled by setting the `enable-cell-context` property to true. The **"cell-context"** event will be raised as soon as the right-click is done to provide cell information through the event argument.

{% highlight CSHTML %}

<ej-pivot-grid id="PivotGrid1" enable-cell-context="true" cell-context="cell_RightClick">
</ej-pivot-grid>

<script type="text/javascript">
    cell_RightClick = function(evt) {
        //Write your Cell Context code here
    }
</script>

{% endhighlight %}

## Conditional formatting
The conditional formatting allows you to highlight the particular cells with certain color, font-style, font-family etc., based on the condition they have met. It is enabled by setting the `enable-conditional-formatting` property to true, and the formatting dialog will be launched when the **"createConditionalDialog"** method is invoked.

{% highlight CSHTML %}

<ej-pivot-grid id="PivotGrid1" enable-conditional-formatting="true"></ej-pivot-grid>
<ej-button id="button" text="Conditional" size="@ButtonSize.Normal" show-rounded-corner="true" click="btnClick" />

<script type="text/javascript">
    function btnClick(e) {
        var pivotGridObj = $('#PivotGrid1').data("ejPivotGrid");
        if (pivotGridObj.model.enableConditionalFormatting) {
            pivotGridObj.createConditionalDialog();
        }
    }
</script>

{% endhighlight %}

![ASP NET Core pivot grid control with conditional formatting](PivotGrid-Elements_images/conditional.png)

### Export

You can export the pivot grid with highlighted particular cells along with its formatting styles.

Limitations for Word:

The following border styles are not supported:

* Solid
* Groove
* Ridge

Limitations for PDF:

Border styles are not applicable.

Limitations for Excel:

The following border styles are alone supported:

* Dashed
* Dotted
* Double

Also, the border size is not supported.

![Excel exporting with conditional formatting in ASP NET Core pivot grid control](PivotGrid-Elements_images/conditional_export.png)