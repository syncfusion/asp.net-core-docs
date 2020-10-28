---
layout: post
title: TreeView with Multiple Selection | TreeView | ASP.NET Core | Syncfusion
description: specify multiple selection option in TreeView and its settings
platform: aspnet-core
control: TreeView
documentation: ug
---

# Multiple Selection

The tree view supports to select the multiple nodes by specifying the [allowMultiSelection](http://help.syncfusion.com/js/api/ejtreeview#members:allowmultiselection) as true. It allows you to select more than one nodes in the tree view.

In the controller page, create a data list that contains the details about the tree nodes.

{% highlight c# %}

	public partial class TreeViewController : Controller
	{
		// GET: Custom
		List<LoadData> tree1 = new List<LoadData>();
		public ActionResult Index()
		{
			tree1.Add(new LoadData { Id = 1, Parent = 0, Text = "Item 1",selected=true });
			tree1.Add(new LoadData { Id = 2, Parent = 0, Text = "Item 2" });
			tree1.Add(new LoadData { Id = 3, Parent = 0, Text = "Item 3" });
			tree1.Add(new LoadData { Id = 4, Parent = 0, Text = "Item 4" });
			tree1.Add(new LoadData { Id = 5, Parent = 1, Text = "Item 1.1", ,selected=true });
			tree1.Add(new LoadData { Id = 6, Parent = 1, Text = "Item 1.2" });
			tree1.Add(new LoadData { Id = 7, Parent = 1, Text = "Item 1.3" });
			tree1.Add(new LoadData { Id = 8, Parent = 3, Text = "Item 3.1" });
			tree1.Add(new LoadData { Id = 9, Parent = 3, Text = "Item 3.2" });
			tree1.Add(new LoadData { Id = 10, Parent = 5, Text = "Item 1.1.1" });
			ViewBag.datasource = tree1;
			return View();
		}
	}
	
	public class LoadData
	{
	        public int Id;
            public int Parent;
            public string Text;
	}


{% endhighlight %}

In the view page, add the following code and map the properties defined to the corresponding fields in data source and specify the **AllowMultiSelection** property.

{% highlight CSHTML %}

    <ej-tree-view id="treeView" allow-multi-selection="true">
	  <e-tree-view-fields datasource="ViewBag.datasource" id="Id" parent-id="Parent" text="Text">
	  </e-tree-view-fields>
	</ej-tree-view>
	
{% endhighlight %}

By running the previous code, you will get the output like the following:
![](Fullrowselection_images/multiselect.png)


## Select nodes

To select more than one nodes of tree view, use the [selectedNodes](http://help.syncfusion.com/js/api/ejtreeview#members:selectednodes) property. It will select the tree view nodes from the given indexes.

In the view page, add the following code and map the properties defined to the corresponding fields in data source and you can select the specific nodes in tree view by using the **selectedNodes** property.

{% highlight CSHTML %}

    <ej-tree-view id="treeView" allow-multi-selection="true">
	  <e-tree-view-fields datasource="ViewBag.datasource" id="Id" parent-id="Parent" text="Text">
	  </e-tree-view-fields>
	</ej-tree-view>
	
{% endhighlight %}

{% highlight js %}

	$(function () {
        // create instance for TreeView
        var treeObj = $("#treeView").data("ejTreeView");

        treeObj.option("selectedNodes", [0, 5, 6]); //select the TreeView nodes from the given indexes
    });
	
{% endhighlight %}

## Get selected nodes

To get the selected nodes of tree view, use the [getSelectedNodes](http://help.syncfusion.com/js/api/ejtreeview#methods:getselectednodes) method. It returns the collections of tree view selected nodes. You can use [getSelectedNodesIndex](https://help.syncfusion.com/api/js/ejtreeview#methods:getselectednodesindex) method to get the index positions of currently selected nodes.

In the view page, add the following code and map the properties defined to the corresponding fields in data source and you can get selected nodes from the tree view by using the **getSelectedNodes** method.

{% highlight CSHTML %}

    <ej-tree-view id="treeView" allow-multi-selection="true">
	  <e-tree-view-fields datasource="ViewBag.datasource" id="Id" parent-id="Parent" text="Text">
	  </e-tree-view-fields>
	</ej-tree-view>

{% endhighlight %}

{% highlight js %}

	$(function () {
        // create instance for TreeView
        var treeObj = $("#treeView").data("ejTreeView");

        treeObj.getSelectedNodes(); //returns the collections of TreeView selected nodes
    });
	
{% endhighlight %}