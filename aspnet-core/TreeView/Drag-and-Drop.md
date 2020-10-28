---
layout: post
title: TreeView with Drag and Drop option | TreeView | ASP.NET Core | Syncfusion
description: specify Drag and Drop option in TreeView and its settings
platform: aspnet-core
control: TreeView
documentation: ug
---

# Drag and Drop

To perform the drag and drop operation in tree view, specify the **AllowDragAndDrop** as true. It allows you to drag and drop a node in all the levels of the same tree view.
The [nodeDrag](https://help.syncfusion.com/api/js/ejtreeview#events:nodedrag), [nodeDragStart](https://help.syncfusion.com/api/js/ejtreeview#events:nodedragstart), [nodeDragStop](https://help.syncfusion.com/api/js/ejtreeview#events:nodedragstop) and 
[nodeDropped](https://help.syncfusion.com/api/js/ejtreeview#events:nodedropped) event occurs based on Treeview node drag and drop state.

    {% highlight CSHTML %}
    
      <ej-tree-view id="treeView" allow-drag-and-drop="true">
	   <e-tree-view-fields datasource="ViewBag.datasource" id="Id" parent-id="Parent" text="Text">
	   </e-tree-view-fields>
	  </ej-tree-view>
   
    {% endhighlight %}

N>**The tree view provides much easier option to drop the dragged nodes at any levels by indicator lines with icons.**

## Position indicators

The tree view provides much easier option to drop the dragged nodes at any levels by indicator lines with icons such as: in between line, plus/minus, and restrict icons. It represents the exact position of the node to be dropped as sibling or child.

<table>
<tr>
<td>
    {{'**Indicators**'| markdownify }}
</td>
<td>
    {{'**Description**'| markdownify }}
</td>
</tr>
<tr>
<td>
Plus icon
</td>
<td>
Represents the dragged node to be added as a child of targeted node.
</td>
</tr>
<tr>
<td>
Minus with restrict icon
</td>
<td>
Represents the dragged node not to be dropped at the hovered region.
</td>
</tr>
<tr>
<td>
In between icon
</td>
<td>
Represents the dragged node to be dropped in between the nodes as siblings.
</td>
</tr>
</table>

While dragged node is added as a child of targeted node, it will look like the following:
![](Drag_drop_images/plus.png) 

While dragged node is not dropped at the hovered region, it will look like the following:
![](Drag_drop_images/minus.png)

While dragged node is dropped in between the nodes as siblings, it will look like the following:
![](Drag_drop_images/sibling.png)

## Restriction

You can restrict the dragged nodes to be dropped at siblings or children’s level by using the **AllowDropSibling** and **AllowDropChild** properties.
  
    {% highlight CSHTML %}
    
      <ej-tree-view id="treeView" allow-drag-and-drop="true" allow-drop-sibling="true" allow-drop-child="false">
        <e-tree-view-fields datasource="ViewBag.datasource" id="Id" parent-id="Parent" text="Text">
        </e-tree-view-fields>
      </ej-tree-view>

    {% endhighlight %}
    
## Drag and drop between trees

You can drag and drop the tree nodes between two tree view by setting the **AllowDragAndDrop** as true along with the **AllowDragAndDropAcrossControl** as true.

In the controller page, create a data list that contains the details about the tree nodes.
    
    {% highlight c# %}
    
    public partial class TreeViewController : Controller
        {
            List<LoadData> tree1 = new List<LoadData>();
            List<LoadData> tree2 = new List<LoadData>();
            public ActionResult TreeViewFeatures()
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
        
    {% endhighlight %}       
    
In the view page, add the following code and map the properties defined to the corresponding fields in data source, and specify the drag and drop settings.
        
    {% highlight CSHTML %}
    
      <ej-tree-view id="treeview1" show-checkbox="true" allow-drag-and-drop="true" allow-drop-sibling="true" allow-drop-child="true" allow-drag-and-drop-across-control="true">
	    <e-tree-view-fields datasource="ViewBag.datasource1" id="Id" parent-id="Parent" text="Text">
		</e-tree-view-fields>
	  </ej-tree-view>
    
      <ej-tree-view id="treeview2" allow-drag-and-drop="true" allow-drop-sibling="true" allow-drop-child="true" allow-drag-and-drop-across-control="true">
	    <e-tree-view-fields datasource="ViewBag.datasource2" id="Id" parent-id="Parent" text="Text">
		</e-tree-view-fields>
	  </ej-tree-view>

    {% endhighlight %}

![](Drag_drop_images/twocontrols.png)

## Auto node structuring

You may not need to have two tree view to be in same structured node while drag and drop the nodes between them. But once the node has been dropped, it should get structured to the tree view node in which it is dropped. By default, the tree view is auto structured whenever you drop a node from different tree.
    
    {% highlight CSHTML %}
         
      <ej-tree-view id="treeview1" allow-drag-and-drop="true" allow-drop-sibling="true" allow-drop-child="true" allow-drag-and-drop-across-control="true">
	    <e-tree-view-fields datasource="ViewBag.datasource1" id="Id" parent-id="Parent" text="Text">
		</e-tree-view-fields>
	  </ej-tree-view>
    
      <ej-tree-view id="treeview2" allow-drag-and-drop="true" allow-drop-sibling="true" allow-drop-child="true" allow-drag-and-drop-across-control="true">
	    <e-tree-view-fields datasource="ViewBag.datasource2" id="Id" parent-id="Parent" text="Text">
		</e-tree-view-fields>
	  </ej-tree-view>
    
    {% endhighlight %}    
    
N>**Auto node structure is only applicable for well-structured node object.**