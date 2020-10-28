---
layout: post
title:  Drill Through | PivotGrid | ASP.NET Core | Syncfusion
description:  This document explains that how to define drill through feature with respective to the modes in ASP.NET Core PivotGrid control
platform: aspnet-core
control: PivotGrid
documentation: ug
---

# Drill through

Drill-through retrieves the raw items that are used to create a specific cell. To enable drill-through support, set the [`enable-drill-through`] property to true. Raw items are obtained through the [`drill-through`] event, using which you can bind them to an external widget for a precise view.

## Relational

{% highlight html %}

<ej-pivot-grid id="PivotGrid1" enable-drill-through="true" drill-through="drilledData"></ej-pivot-grid>

<script type="text/javascript">
    function drilledData(args) {
    gridData = args.selectedData;
    var dialogContent = ej.buildTag("div#Grid", {height:"50px"})[0].outerHTML;
    ejDialog = ej.buildTag("div#clientDialog.e-clientDialog", dialogContent, { "opacity": "1" }).attr("title", "Drill Through Information")[0].outerHTML;
    $(ejDialog).appendTo("#" + this._id);
    this.element.find(".e-clientDialog").ejDialog({ width: "70%", height: "100%", content: "#" + this._id, enableResize: false, close: ej.proxy(ej.Pivot.closePreventPanel, this) });

    $("#Grid").ejGrid({
        dataSource: gridData,
        });
}
</script>

{% endhighlight %}

![Drill through data in ASP NET Core pivot grid relational mode](DrillThrough_images/DrillThroughRelational.png)

## OLAP

N> Drill-through is supported in the pivot grid only when you configure and enable the drill-through action at the cube.

![Drill through support in ASP NET Core pivot grid control](DrillThrough_images/pivotgrid.png)

By clicking any value cell, the "Drill Through Information" dialog will be opened. It consists of a grid with data that are associated with the measure values of clicked value cell. In this example, the measure behind the respective cell is “Sales Amount” and the values of the dimensions that are associated with this measure are alone displayed in the grid.

![Drill through data in ASP NET Core pivot grid control](DrillThrough_images/DrillThroughData.png)

By clicking the "Hierarchy Selector" button which is displayed below the grid, the "Hierarchy Selector" dialog will be opened. It consists of dimensions that are associated with the measure of the clicked value cell. In this example, the measure behind the respective cell is “Sales Amount” and dimensions associated with this measure are alone displayed in the dialog.

![Hierarchy selector in ASP NET Core pivot grid control](DrillThrough_images/hierarchy_selector.png)

By dragging and dropping the respective hierarchies and finally clicking OK, the drill through MDX query will be framed and executed internally, and then it will provide the raw items through the [`drill-Through`] event. In this example, the obtained raw items are bounded to the ejGrid widget. Refer to the following code sample and screenshot:

{% highlight cshtml %}

<ej-pivot-grid id="PivotGrid1" enable-drill-through="true" drill-through="drilledData"></ej-pivot-grid>

<script type="text/javascript">
    function drilledData(args) {
        $(".e-dialog, .e-clientDialog, .e-tableDlg").remove();
        gridData = JSON.parse(args.data);
        var dialogContent = ej.buildTag("div#" + this._id + "_tableDlg.e-tableDlg", $("<div id=\"Grid1\"></div>"))[0].outerHTML;
        var dialogFooter = ej.buildTag("div", ej.buildTag("button#btnOK.e-dialogBtnOK", "Hierarchy Selector")[0].outerHTML, { "float": "right", "margin": "-5px 0 6px" })[0].outerHTML
        ejDialog = ej.buildTag("div#clientDialog.e-clientDialog", dialogContent + dialogFooter, { "opacity": "1" }).attr("title", "Drill Through Information")[0].outerHTML;
        $(ejDialog).appendTo("#" + this._id);
        $("#btnOK").ejButton().css({ margin: "30px 0 20px 0" });
        $("#Grid1").ejGrid({
            dataSource: gridData,
            allowPaging: true,
            allowTextWrap: true,
            pageSettings: { pageSize: 8 }
        });
        this.element.find(".e-clientDialog").ejDialog({ width: "70%", content: "#" + this._id, enableResize: false, close: ej.proxy(ej.Pivot.closePreventPanel, this) });
        var pivotGrid = $("#" + this._id).data("ejPivotGrid");
        $("#btnOK").click(function () {
            ej.Pivot.createHierarchySelector(pivotGrid);
        });
    }
</script>

{% endhighlight %}

![Drill through data in ASP NET Core pivot grid OLAP client mode](DrillThrough_images/drill_data.png)