---
layout: post
title: TreeView with Full Row Selection | TreeView | ASP.NET Core | Syncfusion
description: specify full row selection option in TreeView and its settings
platform: aspnet-core
control: TreeView
documentation: ug
---

# Full Row Selection

The tree view control provides an option to highlight a full row of tree view nodes. When **FullRowSelect** is **true**, the selection highlights the entire width of the tree view node, instead of highlighting only the width of tree view node text. It makes the selection easier.

In the controller page, create a data list that contains the details about the tree nodes.

{% highlight c# %}

public partial class TreeViewController : Controller
{
    // GET: MultiSelection
    List<loadOnDemand> fullRowData = new List<loadOnDemand>();
    public ActionResult FullRowSelection()
    {
        fullRowData.Add(new loadOnDemand { id = 1, name = "Discover Music", hasChild = true, expanded = true });
        fullRowData.Add(new loadOnDemand { id = 2, parentId = 1, name = "Hot Singles", selected = true });
        fullRowData.Add(new loadOnDemand { id = 3, parentId = 1, name = "Rising Artists" });
        fullRowData.Add(new loadOnDemand { id = 4, parentId = 1, name = "Live Music" });
        fullRowData.Add(new loadOnDemand { id = 6, parentId = 1, name = "Best of 2013 So Far" });
        fullRowData.Add(new loadOnDemand { id = 7, name = "Sales and Events", hasChild = true, expanded = true });
        fullRowData.Add(new loadOnDemand { id = 8, parentId = 7, name = "100 Albums - $5 Each" });
        fullRowData.Add(new loadOnDemand { id = 9, parentId = 7, name = "Hip-Hop and R&B Sale" });
        fullRowData.Add(new loadOnDemand { id = 10, parentId = 7, name = "CD Deals" });
        fullRowData.Add(new loadOnDemand { id = 11, name = "Categories", hasChild = true });
        fullRowData.Add(new loadOnDemand { id = 12, parentId = 11, name = "Songs" });
        fullRowData.Add(new loadOnDemand { id = 13, parentId = 11, name = "Bestselling Albums" });
        fullRowData.Add(new loadOnDemand { id = 14, parentId = 11, name = "New Releases" });
        fullRowData.Add(new loadOnDemand { id = 15, parentId = 11, name = "Bestselling Songs" });
        fullRowData.Add(new loadOnDemand { id = 16, name = "MP3 Albums", hasChild = true });
        fullRowData.Add(new loadOnDemand { id = 17, parentId = 16, name = "Rock" });
        fullRowData.Add(new loadOnDemand { id = 18, parentId = 16, name = "Gospel" });
        fullRowData.Add(new loadOnDemand { id = 19, parentId = 16, name = "Latin Music" });
        fullRowData.Add(new loadOnDemand { id = 20, parentId = 16, name = "Jazz" });
        fullRowData.Add(new loadOnDemand { id = 21, name = "More in Music", hasChild = true });
        fullRowData.Add(new loadOnDemand { id = 22, parentId = 21, name = "Music Trade-In" });
        fullRowData.Add(new loadOnDemand { id = 23, parentId = 21, name = "Redeem a Gift Card" });
        fullRowData.Add(new loadOnDemand { id = 24, parentId = 21, name = "Band T-Shirts" });
        fullRowData.Add(new loadOnDemand { id = 25, parentId = 21, name = "Mobile MVC" });

        ViewBag.datasource = fullRowData;
        return View();
    }
}

public class loadOnDemand
{
    public int id { get; set; }
    public int? parentId { get; set; }
    public string name { get; set; }
    public bool? hasChild { get; set; }
    public bool? expanded { get; set; }
    public bool? selected { get; set; }
}

{% endhighlight %}

In the view page, add the following code and map the properties defined to the corresponding fields in data source and specify the **FullRowSelect** property.

{% highlight CSHTML %}

    <ej-tree-view id="treeView" full-row-select="true">
	 <e-tree-view-fields datasource="ViewBag.datasource" id="id" parent-id="parentId" text="name" has-child="hasChild" expanded="expanded">
	 </e-tree-view-fields>
	</ej-tree-view>

{% endhighlight %}

By running the previous code, you will get the output like the following:
![](Fullrowselection_images/selection1.png)

## Customization

You can customize the tree view full row selection for template support by using the **CssClass** property. Based on this custom class, you can customize the height of the highlighted tree view node.

In the controller page, create a data list that contains the details about the tree nodes.

{% highlight c# %}

public partial class TreeViewController : Controller
{
    // GET: MultiSelection
    List<loadOnDemand> fullRowData = new List<loadOnDemand>();
    public ActionResult FullRowSelection()
    {
        fullRowData.Add(new loadOnDemand { id = 1, name = "Browsers", Class = "browser", hasChild = true, expanded = true });
        fullRowData.Add(new loadOnDemand { id = 2, parentId = 1, name = "Internet Explorer", Class = "internetExplorerBrowser", selected = true });
        fullRowData.Add(new loadOnDemand { id = 3, parentId = 1, name = "Chrome", Class = "chromeBrowser" });
        fullRowData.Add(new loadOnDemand { id = 4, parentId = 1, name = "Firefox", Class = "firefoxBrowser" });
        fullRowData.Add(new loadOnDemand { id = 6, parentId = 1, name = "Bitty", Class = "bittyBrowser" });
        fullRowData.Add(new loadOnDemand { id = 7, parentId = 1, name = "Opera", Class = "operaBrowser" });
        ViewBag.datasource = fullRowData;
        return View();
    }
}

public class loadOnDemand
{
        public int id { get; set; }
        public int? parentId { get; set; }
        public string name { get; set; }
        public bool? hasChild { get; set; }
        public bool? expanded { get; set; }
        public bool? selected { get; set; }
        public string Class { get; set; }
}

{% endhighlight %}

In the view page, add the following code and map the properties defined to the corresponding fields in data source and specify the **CssClass** property.

{% highlight CSHTML %}

    <ej-tree-view id="treeView" full-row-select="true" css-class="custom" template="#treeTemplate">
	  <e-tree-view-fields datasource="ViewBag.datasource" id="id" parent-id="parentId" text="name" has-child="hasChild" expanded="expanded"> 
	  </e-tree-view-fields>
	</ej-tree-view>

<script id="treeTemplate" type="text/x-jsrender">

    {{"{{"}}if !hasChild{{}}}}
    <span class="con-img {{"{{"}}>Class{{}}}}"></span>
    {{"{{"}}/if{{}}}}
    {{"{{"}}>name{{}}}}

</script>
	
{% endhighlight %}

{% highlight css %}

<style>
	.custom .con-img {
        background-image: url("http://mvc.syncfusion.com/demos/web/images/toolbar/browserl.png");
        background-repeat: no-repeat;
        height: 32px;
        width: 32px;
        display: inline-block;
        overflow: hidden;
        background-repeat: no-repeat;
        text-align: center;
        vertical-align: middle;
    }
    
    .custom .e-li-active > .e-text-wrap .con-img {
        background-image: url("http://mvc.syncfusion.com/demos/web/images/toolbar/browserh.png");
    }
    
    .custom .e-li-hover > .e-text-wrap .con-img, .e-fullrow-wrap .e-li-focus > .e-text-wrap .con-img {
        background-image: url("http://mvc.syncfusion.com/demos/web/images/toolbar/browserl.png");
    }
    
    .custom .internetExplorerBrowser {
        background-position: -84px 0px;
    }
    
    .custom .chromeBrowser {
        background-position: -42px 0px;
    }
    
    .custom .firefoxBrowser {
        background-position: 0px 0px;
    }
    
    .custom .bittyBrowser {
        background-position: -126px 0px;
    }
    
    .custom .operaBrowser {
        background-position: -168px 0px;
    }
    
    /*customize the height of highlighting TreeView node*/
    .custom.e-fullrow-wrap .e-item ul .e-fullrow {
        margin-top: -36px;
        height: 36px;
    }

</style>

{% endhighlight %}

By running the above code, you will get the output like the following:
![](Fullrowselection_images/custom.png)