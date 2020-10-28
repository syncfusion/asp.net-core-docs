---
layout: post
title: Paging | TreeGrid | ASP.NET Core | Syncfusion
description: paging
platform: aspnet-core
control: TreeGrid
documentation: ug
---

# Paging

The TreeGrid control provides support for displaying records in paginated view. Paging can be enabled in TreeGrid by setting the `AllowPaging` property as `true`.

The below code snippet explains enabling paging in TreeGrid.

{% highlight CSHTML %}
 
<ej-tree-grid id="TreeGridControlPagerTemplate" allow-paging="true">            
         //...     
</ej-tree-grid>

{% endhighlight %}

The output of the TreeGrid with paging enabled is displayed below

![](Paging_images/Paging_img1.png)

## Paging settings

The paging in TreeGrid can be customized by using `PageSettings` property.
The number of records to be displayed per page can be limited by using the `PageSettings.PageSize` property. 
The number of root nodes or the 0th level records to be displayed per page can be limited by setting the `PageSettings.PageSizeMode` property as `Root`. When pageSettings.pageSizeMode property is set as `Root` the number of records to displayed per page which is defined in the `PageSettings.PageSize` property will be considered only for the root nodes or the 0th level records.
`PageSettings.PageCount` property is used to display the page number to be displayed in the pager.
`PageSettings.CurrentPage` property is used to set the active page to displayed initially.
`PageSettings.TotalRecordsCount` property is used to limit the total number of records from the data source to be displayed in TreeGrid.
 The following code example explains the properties in pageSettings. 

{% highlight CSHTML %}

<ej-tree-grid id="TreeGridControlPagingAPI" allow-paging="true">   
       <e-tree-grid-page-settings page-count="5" page-size="12" page-size-mode="All"  current-page="3" total-records-count="50"></e-tree-grid-page-settings> 
</ej-tree-grid>

{% endhighlight %}


## Pager Template

It is possible to customize the default pager in TreeGrid by using the `PageSettings.Template` property.
The below code snippet explains how to customize the default pager with template

{% highlight CSHTML %}
<script type="text/x-jsrender" id="template">
    <div class="e-pagercontainer">
        <div class="e-first e-icon e-mediaback e-firstpagedisabled e-disable" title="Go to first page"></div>
        <div class="e-prev e-icon e-arrowheadleft-2x e-prevpagedisabled e-disable" style="border-right:none" title="Go to previous page"></div>
    </div>
    <div class="e-pagercontainer e-currentPageContainer" style="border-radius:0px">
        <input id="currentPage" class="e-pagercontainer" type="text" style="text-align:center; margin:0px;border:none;width:32px;height:23px" />
    </div>
    <div id="totalPages" class="e-pagercontainer" style="margin-left: 2px;margin-bottom:5px;border: none; ">
        <span></span>
    </div>
    <div class="e-pagercontainer">
        <div class="e-nextpage e-icon e-arrowheadright-2x e-default" title="Go to next page"></div>
        <div class="e-lastpage e-icon e-mediaforward e-default" title="Go to last page"></div>
    </div>
</script> 

{% endhighlight %}

{% highlight css %}
    #currentPage {
        background-color: white;
    }

    .e-currentPageContainer {
        border-bottom: 1px solid #e0e0e0!important;
    }

    .e-pagercontainer .e-icon {
        display: inline-block;
        height: 8px;
    }

    .e-pager .e-pagercontainer {
        margin: 0px;
        margin-left: 6px;
    }
{% endhighlight %}

{% highlight CSHTML %}

<ej-tree-grid id="TreeGridControlPagerTemplate" allow-paging="true">            
    <e-tree-grid-page-settings template="#Template"></e-tree-grid-page-settings>  
</ej-tree-grid>

{% endhighlight %}

{% highlight js %}

//Code for navigating to the page 
$("#currentPage").keydown(function(e) {
    var obj = $("#TreeGridContainer").data("ejTreeGrid");
    var val = parseInt($("#currentPage").val());
    if (e.keyCode == 13) {
        if (val > obj.model.pageSettings.totalPages)
            val = obj.model.pageSettings.totalPages;
        if (val <= 0)
            val = 1;
        obj.gotoPage(val);
        return false;
    }
});

{% endhighlight %}


The below image displays TreeGrid with paging template.
![](Paging_images/Paging_img2.png)

## Paging - Touch Option

With paging and responsive mode enabled in TreeGrid, it is possible to change the current page using swipe action.

The following code example describes how to enable multiple selection in TreeGrid.	

{% highlight CSHTML %}

 <ej-tree-grid id="TreeGridControlPagerTemplate" allow-paging="true" is-responsive="true">            
       //...
 </ej-tree-grid>

{% endhighlight %}