---
layout: post
title: Selection
description: Selection
platform: aspnet-core
control: Gantt
documentation: ug
---
# Selection

## Row selection

You can enable or disable the row selection in Gantt, by using `allow-selection` property. And you can able to get the selected row object using selectedItem property from the Gantt model. The following code example shows how to disable the row selection in Gantt.

{% highlight cshtml %}

<ej-gantt id="ganttSample" datasource="ViewBag.datasource"
    //...
    allow-selection="false">
</ej-gantt>  

{% endhighlight %}

### Selecting a row on initial load

You can select a row on load time by setting the index of the row to `selected-row-index` property. Find the following code example for details.

{% highlight cshtml %}

<ej-gantt id="ganttSample" datasource="ViewBag.datasource"
    //...
    selected-row-index=3>
</ej-gantt>  

{% endhighlight %}

![](Selection_images/Selection_img1.png)

### Selecting a row programmatically 

You can also select a row programmatically by setting index of the row value to `selected-row-index` property. The following code shows to select a row programmatically with a custom button click action,

{% highlight cshtml %}
    <button id="selectRow">SelectRow</button>
    <ej-gantt id="ganttSample" datasource="ViewBag.datasource"
        //...>
    </ej-gantt>  
{% endhighlight %}

{% highlight javascript %}

$("#selectRow").click(function(args) {
    $("#ganttSample ").ejGantt("option", "selectedRowIndex", 4);
})

{% endhighlight %}

### Multiple row selection

It is also possible to select multiple rows by setting `selection-type` as `Multiple`. You can select more than one row by holding down `CTRL` key while selecting multiple rows.
The following code example explains how to enable multiple selection in Gantt.

{% highlight cshtml %}

<ej-gantt id="ganttSample" datasource="ViewBag.datasource"
    //...
    selection-mode="Row"
    selection-type="Multiple">
</ej-gantt> 

{% endhighlight %}

The output of the Gantt with multiple row selection is as follows.

![](Selection_images/Selection_img5.png)


### Selecting multiple rows programmatically 

You can also select multiple rows programmatically  by using `selectMultipleRows` public method. The following code example explains how to enable multiple selection in Gantt.

{% highlight cshtml %}

<button id="selectMultipleRows">selectMultipleRows</button>
<ej-gantt id="ganttSample" datasource="ViewBag.datasource"
    //...
    selection-mode="Row"
    selection-type="Multiple">
</ej-gantt> 
{% endhighlight %}

{% highlight javascript %}

$("#selectMultipleRows").click(function(args) {
     var ganttObj = $("#ganttSample").data("ejGantt"),
     multipleRowIndex = [1,0,5,7];   
     ganttObj.selectMultipleRows(multipleRowIndex);
})
{% endhighlight %}

## Cell selection

You can select a cell in Gantt by setting `selection-mode` property as `Cell`. And you can able to get the selected cell information using `selected-cell-indexes` property from the Gantt object. `selected-cell-indexes` is an object collection, which has the cell index and row index information of the selected cells.

Find the code example below to enable the cell selection in Gantt. 

{% highlight cshtml %}

<ej-gantt id="ganttSample" datasource="ViewBag.datasource"
    //...
    selection-mode="Cell">
</ej-gantt>  

{% endhighlight %}

The following screen shots shows you cell selection.

![](Selection_images/Selection_img2.png)

### Selecting multiple cells

You can also select multiple cells by setting `selection-type` property as `Multiple` while `selection-mode` property is set to `Cell`. Multiple cells can be selected by holding the ctrl key and to click on the cells. The following code example shows you to select multiple cells.

{% highlight cshtml %}

<ej-gantt id="ganttSample" datasource="ViewBag.datasource"
    //...
    selection-mode="Cell"
    selection-type="Multiple">
</ej-gantt>  

{% endhighlight %}

![](Selection_images/Selection_img3.png)

### Select cells programmatically 

You can select the cells programmatically using `selectCells` public method. Find the code example below for details.

{% highlight cshtml %}

<button id="selectMultiple">SelectMultipleCells</button>

<ej-gantt id="ganttSample" datasource="ViewBag.datasource"
    //...
    selection-mode="Cell"
    selection-type="Multiple">
</ej-gantt> 
{% endhighlight %}

{% highlight javascript %}


$("#selectMultiple").click(function(args) {

    //create Gantt object

    var ganttObj = $("#ganttSample").data("ejGantt");

    cellIndex = [{
        rowIndex: 2,
        cellIndex: 1
    }, {
        rowIndex: 3,
        cellIndex: 1
    }];

    ganttObj.selectCells(cellIndex);

})
{% endhighlight %}

![](Selection_images/Selection_img4.png)

## MultiSelection - Touch Option

It is possible to select rows using touch action in Gantt. Gantt provides support for both single selection and multiple row selection using touch action. For multiple row selection, when we tap on a cell, a helper icon will be displayed using which we can select multiple rows.

The following code example describes how to enable multiple selection in Gantt.

{% highlight cshtml %}

<ej-gantt id="ganttSample" datasource="ViewBag.datasource"
    //...
    selection-mode="Row"
    selection-type="Multiple">
</ej-gantt>  

{% endhighlight %}

The following output is displayed the result of multiple selection in touch device environment.

![](Selection_images/Selection_img6.png)