---
layout: post
title: Printing | TreeGrid | ASP.NET Core | Syncfusion
description: printing
platform: aspnet-core
control: TreeGrid
documentation: ug
---

# TreeGrid Printing


TreeGrid provides support to print the contents. To print the TreeGrid the print toolbar item must be added to [ToolbarSettings.ToolbarItems](/api/js/ejgantt#members:toolbarsettings-toolbaritems) property. The below code example shows how to enable print in TreeGrid.

{% highlight CSHTML %}
 
<ej-tree-grid id="TreeGrid">
    <e-tree-grid-toolbar-settings show-toolbar="true" toolbar-items="@(new List<string>() {"print"})"></e-tree-grid-toolbar-settings>
</ej-tree-grid>

{% endhighlight %}

The print preview window will be opened by clicking on this toolbar icon. 

## Print Mode

It is possible to set the printMode in [PageSettings](/api/js/ejgantt#members:pagesettings) property, to give printing preference, as to print current page alone or all the pages in case of paging enabled in TreeGrid. The following code example explains this.


{% highlight CSHTML %}
 
<ej-tree-grid id="TreeGrid" allow-paging="true">
     <e-tree-grid-page-settings print-mode="CurrentPage"></e-tree-grid-page-settings> 
     <e-tree-grid-toolbar-settings show-toolbar="true" toolbar-items="@(new List<string>() {"print"})"></e-tree-grid-toolbar-settings>
</ej-tree-grid>

{% endhighlight %}

In this case only the visible records in the current page will be send to printing.

## BeforePrint Event 

BeforePrint event will be triggered once after printing initiated in TreeGrid. This event contains the treegrid element which is going to be printing. The following code explains this.

{% highlight js %}
 
<ej-tree-grid id="TreeGrid" before-print="beforePrint">
    <e-tree-grid-toolbar-settings show-toolbar="true" toolbar-items="@(new List<string>() {"print"})"></e-tree-grid-toolbar-settings>
</ej-tree-grid>
<script>
    function beforePrint(args) {
        //will be triggered before printing the TreeGrid
    }
</script>

{% endhighlight %}
