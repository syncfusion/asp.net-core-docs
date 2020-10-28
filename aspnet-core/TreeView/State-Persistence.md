---
title: State Persistence  | TreeView | ASP.NET Core | Syncfusion
description: State Persistence option in TreeView
platform: aspnet-core
control: TreeView
documentation: UG
---

# State Persistence

The tree view state can be persisted by using the **EnablePersistence**. In which, only the user intractable model values has been persisted to maintain the performance.

The following model values are maintained through id basis of the tree node.

* selected
* checked
* expanded/collapsed state

N>**The "UL" and "li" template state has been persisted by index.**

The tree view stores its model in local storage/cookies of the browser before the page refreshes, and reinitialized with their stored model after refreshes.

In the controller page, create a data list that contains the details about the tree nodes.
    
    {% highlight c# %}
    
    public partial class TreeViewController : Controller
        {
            List<LoadData> treeData = new List<LoadData>();
            public ActionResult TreeViewFeatures()
            {
                treeData.Add(new LoadData { Id = 1, Parent = 0, Text = "Item 1" });
                treeData.Add(new LoadData { Id = 2, Parent = 0, Text = "Item 2" });
                treeData.Add(new LoadData { Id = 3, Parent = 0, Text = "Item 3" });
                treeData.Add(new LoadData { Id = 4, Parent = 0, Text = "Item 4" });
                treeData.Add(new LoadData { Id = 5, Parent = 1, Text = "Item 1.1" });
                treeData.Add(new LoadData { Id = 6, Parent = 1, Text = "Item 1.2" });
                treeData.Add(new LoadData { Id = 7, Parent = 1, Text = "Item 1.3" });
                treeData.Add(new LoadData { Id = 8, Parent = 3, Text = "Item 3.1" });
                treeData.Add(new LoadData { Id = 9, Parent = 3, Text = "Item 3.2" });
                treeData.Add(new LoadData { Id = 10, Parent = 5, Text = "Item 1.1.1" });
                ViewBag.datasource = treeData;
                return View();
            }
        }
    
    {% endhighlight %}
    
    
In the view page, add the following code with the following properties.

    
    {% highlight CSHTML %}
    
        <ej-tree-view id="treeview">
		  <e-tree-view-fields datasource="ViewBag.datasource" id="Id" parent-id="Parent" text="Text" enable-persistence="true">
		  </e-tree-view-fields>
		</ej-tree-view>
    
    {% endhighlight %} 