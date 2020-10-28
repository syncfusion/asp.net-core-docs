---
title: Template Option  | TreeView | ASP.NET Core | Syncfusion
description: rendering TreeView using Template Option
platform: aspnet-core
control: TreeView
documentation: UG
---

# Template Option

The tree nodes can be customized by using the **Template** property. The tree view template option requires addition JS library called the **JsRender** that helps you to create the structured way of tree nodes with simple codes and increased performance. To know more about JsRender, refer to this link [http://www.jsviews.com/](http://www.jsviews.com/#).

In the controller page, create a data list that contains the details about the tree nodes.
    
    {% highlight c# %}
    
        public partial class TreeViewController : Controller
        {
            List<LoadData> treeData = new List<LoadData>();
            public ActionResult TreeViewFeatures()
            {
                treeData.Add(new LoadData { 
                    Id = 1,
                    Name = "UK",
                    Class = "UK-style",
                    HasChild = true,
                    Expanded = true
                });
                treeData.Add(new LoadData { 
                    Id = 2,
                    PId = 1,
                    ImageId = "1",
                    Name = "Steven John",
                    City = "London",
                    Phone = "555-5665-2323"
                });
                treeData.Add(new LoadData { 
                    Id = 3,
                    Name = "USA",
                    Class = "USA-style",
                    HasChild = true,
                    Expanded = true
                });
                treeData.Add(new LoadData { 
                    Id = 5,
                    PId = 3,
                    ImageId = "3",
                    Name = "Andrew",
                    City = "Capital way", 
                    Phone = "934-8374-2455"
                });
                treeData.Add(new LoadData {
                    Id = 4,
                    PId = 3,
                    ImageId = "2",
                    Name = "Angelica",
                    City = "Dayton",
                    Phone = "988-4243-0806"
                });
                ViewBag.datasource = treeData;
                return View();
            }
        }
        
    {% endhighlight %}       
    
In the view page, specify the template format and add the following code:
    
    {% highlight razor %}
    
    <script id="treeTemplate" type="text/x-jsrender">
       {{"{{"}}if HasChild{{}}}}
        <div class={{"{{"}}>Class{{}}}}>{{"{{"}}>Name{{}}}}</div>
        {{"{{"}}else{{}}}}
        <div class="cont-list">
            <img class="con-Image" src="http://mvc.syncfusion.com/demos/web/images/treeview/template-image-{{"{{"}}>ImageId{{}}}}.png" />
            <div class="cont-delete"></div>
            <b>{{"{{"}}>Name{{}}}}</b><br />
            <span>{{"{{"}}>City{{}}}}</span>
            <br />
            <span>{{"{{"}}>Phone{{}}}}</span>
        </div>
        <div class="treeFooter"></div>
        {{"{{"}}/if{{}}}}
    
    </script>
    
    <div style="width: 250px">

         <ej-tree-view id="treeview" template="#treeTemplate" create="onCreate">
		   <e-tree-view-fields datasource="ViewBag.datasource" id="Id" parent-id="PId" text="Name" has-child="HasChild" expanded="Expanded">
		   </e-tree-view-fields>
		 </ej-tree-view>

    </div>

    <style class="cssStyles">

        .e-treeview .e-node-hover, .e-treeview .e-active {
            background: transparent;
            border-color: transparent;
        }
    
        .e-treeview .e-node-hover {
            opacity: 0.8;
        }
    
        .con-Image {
            float: left;
        }
    
        .cont-list {
            background: none repeat scroll 0 0 white;
            border: 1px solid #BBBCBB;
            height: 85px;
            width: 200px;
            color: #5c5c5c;
            line-height: 17px;
        }
    
        .cont-details {
            margin-top: 12px;
            font-size: 13px;
        }
    
            background-color: #74A247 !important;
            color: #FFFFFF !important;
        }
    
            background-color: #12A99A !important;
            color: #FFFFFF !important;
        }
    
        .cont-delete {
            background-image: url("http://mvc.syncfusion.com/demos/web/images/treeview/remove-icon.png");
            background-position: -6px -10px;
            background-repeat: no-repeat;
            float: right;
            height: 16px;
            width: 16px;
            cursor: pointer;
        }
    
        .cont-list .treeFooter {
            height: 5px;
            width: 100%;
            background-color: gray;
            margin-top: 17px;
        }

    </style>

    <script>

        function onCreate(args) {
            var treeObj = $("#treeview").data("ejTreeView");
            $("#treeview").find(".cont-delete").bind("click", function (e) {
                e.preventDefault();
                treeObj.removeNode($(e.target).parents("li").first());
            });
        }

    </script>
    
    {% endhighlight %}

By running the above code, you will get the output like the following:
![](Template_images/template.png)

**Custom action in nodes**

The custom action can be performed in the tree view template node. In tree view, you can perform the node delete operation while clicking delete icon by using the [removeNode](http://help.syncfusion.com/js/api/ejtreeview#methods:removenode) method as shown in the following code example:
       
    {% highlight javascript %}
        
        function onCreate(args) {
            var treeObj = $("#treeview").data("ejTreeView");
            $("#treeview").find(".cont-delete").bind("click", function (e) {
                e.preventDefault();
                treeObj.removeNode($(e.target).parents("li").first());
            });
        }
        
    {% endhighlight %}