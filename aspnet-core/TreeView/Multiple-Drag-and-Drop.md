---
layout: post
title: TreeView with Multiple Drag and Drop option | TreeView | ASP.NET Core | Syncfusion
description: specify multiple drag and drop option in TreeView and its settings
platform: aspnet-core
control: TreeView
documentation: ug
---


# Drag and Drop Multiple Nodes

The tree view supports to drag and drop multiple nodes by specifying the [allowMultiSelection](http://help.syncfusion.com/js/api/ejtreeview#members:allowmultiselection) as true along with the [allowDragAndDrop](https://help.syncfusion.com/js/api/ejtreeview#members:allowdraganddrop) as true. It allows you to drag and drop multiple nodes in the tree view.

In the controller page, create a data list that contains the details about the tree nodes.

{% highlight c# %}

	public partial class TreeViewController : Controller
	{
		List<LoadData> tree1 = new List<LoadData>();
		List<LoadData> tree2 = new List<LoadData>();
		public ActionResult Index()
		{
			tree1.Add(new LoadData { Id = 1, Parent = 0, Text = "Item 1" });
			tree1.Add(new LoadData { Id = 2, Parent = 0, Text = "Item 2" });
			tree1.Add(new LoadData { Id = 3, Parent = 0, Text = "Item 3" });
			tree1.Add(new LoadData { Id = 4, Parent = 0, Text = "Item 4" });
			tree1.Add(new LoadData { Id = 5, Parent = 1, Text = "Item 1.1" });
			tree1.Add(new LoadData { Id = 6, Parent = 1, Text = "Item 1.2" });
			tree1.Add(new LoadData { Id = 7, Parent = 1, Text = "Item 1.3" });
			tree1.Add(new LoadData { Id = 8, Parent = 3, Text = "Item 3.1" });
			tree1.Add(new LoadData { Id = 9, Parent = 3, Text = "Item 3.2" });
			tree1.Add(new LoadData { Id = 10, Parent = 5, Text = "Item 1.1.1" });
			ViewBag.datasource1 = tree1;
	
			tree2.Add(new LoadData { Id = 11, Parent = 0, Text = "Item 5" });
			tree2.Add(new LoadData { Id = 12, Parent = 0, Text = "Item 6" });
			tree2.Add(new LoadData { Id = 13, Parent = 0, Text = "Item 7" });
			tree2.Add(new LoadData { Id = 14, Parent = 0, Text = "Item 4" });
			tree2.Add(new LoadData { Id = 15, Parent = 11, Text = "Item 5.1" });
			tree2.Add(new LoadData { Id = 16, Parent = 11, Text = "Item 5.2" });
			tree2.Add(new LoadData { Id = 17, Parent = 11, Text = "Item 5.3" });
			tree2.Add(new LoadData { Id = 18, Parent = 13, Text = "Item 7.1" });
			tree2.Add(new LoadData { Id = 19, Parent = 13, Text = "Item 7.2" });
			tree2.Add(new LoadData { Id = 10, Parent = 15, Text = "Item 5.1.1" });
			ViewBag.datasource2 = tree2;
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

In the view page, add the following code and map the properties defined to the corresponding fields in data source, and specify the multiple drag and drop settings.

{% highlight CSHTML %}

	 <ej-tree-view id="treeview1" allow-multi-selection="true" allow-drag-and-drop="true">
	   <e-tree-view-fields datasource="ViewBag.datasource1" id="Id" parent-id="Parent" text="Text">
	   </e-tree-view-fields>
	 </ej-tree-view>

    <ej-tree-view id="treeview2" allow-multi-selection="true" allow-drag-and-drop="true">
	  <e-tree-view-fields datasource="ViewBag.datasource2" id="Id" parent-id="Parent" text="Text">
	  </e-tree-view-fields>
	</ej-tree-view>

{% endhighlight %}