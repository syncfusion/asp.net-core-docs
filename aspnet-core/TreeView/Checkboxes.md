---
title: Checkboxes in TreeView | TreeView | ASP.NET Core | Syncfusion
description: specify checkboxes in TreeView and its settings
platform: aspnet-core
control: TreeView
documentation: UG
---
    
# Checkboxes

The tree view consists of built-in checkbox option and it is displayed to the left of the tree node by setting the **ShowCheckbox** property as true. It allows you to select more than one node at a time.
 
## Indeterminate checkboxes
 
The tree view supports tri-state checkboxes in addition to the standard two-state checkboxes. By default, the tree view is enabled with tri-state in checkboxes. You can enable the two-state checkboxes by setting the **AutoCheckParentNode** as false.
    
    {% highlight CSHTML %}
    
       <ej-tree-view id="treeView" show-checkbox="true" auto-check-parent-node="false">
	     <e-tree-view-fields datasource="ViewBag.datasource" id="Id" parent-id="Parent" text="Text">
	     </e-tree-view-fields> 
	   </ej-tree-view>

    {% endhighlight %}
    
By running the above code, you will get the output like the following image.
![](Checkboxes_images/checkbox_images_img1.png)

## Auto checkable

By default, checkbox state of child nodes depends on the parent node checkbox state and also the parent node state gets updated based on the child nodes state. You can turn off this option by setting **AutoCheck** as false to make independent parent and child nodes checkboxes.
    
    {% highlight CSHTML %}
    
        <ej-tree-view id="treeView" show-checkbox="true" auto-check="false">
		 <e-tree-view-fields datasource="ViewBag.datasource" id="Id" parent-id="Parent" text="Text">
		 </e-tree-view-fields>
	   </ej-tree-view>
   
    {% endhighlight %}
    
## Check or uncheck node

Tree node can be checked or unchecked using [checkNode](https://help.syncfusion.com/api/js/ejtreeview#methods:checknode) and [uncheckNode](https://help.syncfusion.com/api/js/ejtreeview#methods:unchecknode) methods while [showCheckbox](https://help.syncfusion.com/api/js/ejtreeview#members:showcheckbox) property is enabled in TreeView. Also you can get or set the checked nodes of TreeView using [checkedNodes](https://help.syncfusion.com/api/js/ejtreeview#members:checkednodes) property, which indicates the checked nodes index collection as array. The [nodeCheck](https://help.syncfusion.com/api/js/ejtreeview#events:nodecheck) and [nodeUncheck](https://help.syncfusion.com/api/js/ejtreeview#events:nodeuncheck) event occurs based on checkbox state.
You can use [isNodeChecked](https://help.syncfusion.com/api/js/ejtreeview#methods:isnodechecked) method to check the particular TreeView node is checked or unchecked. Also you can use [checkAll](https://help.syncfusion.com/api/js/ejtreeview#methods:checkall) method to check all the nodes in TreeView.

    {% highlight javascript %}
    
        //create an instance from an existing TreeView.
        // only after control creation you can get treeObj otherwise it throws exception.
        treeObj = $("#treeView").ejTreeView('instance');
                
        //to check node
        treeObj.checkNode("2");
    
        //to uncheck node
        treeObj.uncheckNode("2");
    
    
    {% endhighlight %}

## Get checked nodes

To get the checked nodes of tree view, use the [getCheckedNodes](http://help.syncfusion.com/js/api/ejtreeview#methods:getcheckednodes) method. It returns the collection of checked tree nodes.  Also you can get currently checked nodes indexes in TreeView by using [getCheckedNodesIndex](https://help.syncfusion.com/api/js/ejtreeview#methods:getcheckednodesindex) method.

    {% highlight CSHTML %}
    
    <script type="text/javascript">
        function onClick() {
            //create an instance from an existing TreeView.
            // only after control creation you can get treeObj otherwise it throws exception.
            treeObj = $("#treeView").ejTreeView('instance');
    
            //to get checked nodes
            treeObj.getCheckedNodes();
        }        
    </script>
    
    {% endhighlight %}