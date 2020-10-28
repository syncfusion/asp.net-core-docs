---
layout: post
title:  Drill Through | PivotClient | ASP.NET Core | Syncfusion
description:  This document explains that how to define drill through feature with respective to the modes in ASP.NET Core PivotClient control
platform: aspnet-core
control: PivotClient
documentation: ug
---

# Drill through

The drill-through retrieves raw items that are used to create a specified cell. To enable drill-through support, set [`enable-drill-through`] property to true. Raw items are obtained through the [`drill-through`] event, using which you can bind them to an external widget for a precise view.

N> The drill-through is supported in the pivot grid only when you configure and enable the drill-through action at the cube.

![DrillThrough support in ASP NET Core pivot client control](DrillThrough_images/pivotclient.png)

When any value cell is clicked, the Drill Through Information dialog will open. It consists of a grid with the data associated with the measure values of the clicked value cell. In this example, the measure behind the respective cell is “Sales Amount” and the values of the dimensions associated with this measure are displayed in the grid.

![DrillThrough data in ASP NET Core pivot client control](DrillThrough_images/DrillThroughData.png)

When the Hierarchy Selector displayed below the grid is clicked, the Hierarchy Selector dialog will open. It consists of dimensions associated with the measure of a clicked value cell. In this example, the measure behind the respective cell is “Sales Amount” and the dimensions associated with this measure are alone displayed in the dialog.

![Hierarchy selector in ASP NET Core pivot client control](DrillThrough_images/hierarchy_selector.png)

Drag and drop the respective hierarchies and click OK. The drill-through MDX query will be framed and executed internally and provides back raw items through the "drill-through" event. In this example, the obtained raw items are bound to the ejGrid widget. Refer to the following code sample and screenshot:

{% highlight cshtml %}

<ej-pivot-client id="PivotClient1" title="OLAP Browser" enable-drill-through="true" drill-through="drilledData" load="onLoad">
//..
</ej-pivot-client>

<script type="text/javascript">
    function onLoad(args) {
        this.model.analysisMode = "pivot";
    }

    function drilledData(args) {
        gridData = args.selectedData;
        var dialogContent = ej.buildTag("div#Grid", { })[0].outerHTML;
        ejDialog = ej.buildTag("div#clientDialog.e-clientDialog", dialogContent, { "opacity": "1" }).attr("title", "Drill Through Information")[0].outerHTML;
        $(ejDialog).appendTo("#" + this._id);
        this.element.find(".e-clientDialog").ejDialog({ width: "70%", content: "#" + this._id, enableResize: false, close: ej.proxy(ej.Pivot.closePreventPanel, this) });

        $("#Grid").ejGrid({
            dataSource: gridData,
            allowScrolling: true,
            scrollSettings: { width: "85%" },
            allowPaging: true,
            allowResizing: true,
            allowResizeToFit: true,
            pageSettings: {pageSize: 8}
        });
    }
</script>

{% endhighlight %}

![DrillThrough data in ASP NET Core pivot client relational](DrillThrough_images/drill_data.png)
