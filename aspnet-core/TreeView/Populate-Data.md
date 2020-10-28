---
title: Populate Data | TreeView | ASP.NET Core | Syncfusion
description: To populate the data for TreeView
platform: aspnet-core
control: TreeView
documentation: UG
---


# Populate Data

Tree view can be populated with local or remote data source by using the `DataSource` property that is the member of **TreeViewFields** property.

In Tree view, you should use the **TreeViewFields** property to go with data source. It specifies the mapping fields for the data source to receive the data, query to process the data, and field mappers to map the data members.

## Fields

The following table list out the field members with description.
  
<table>
<tr>
<td>
    {{'**Properties**'| markdownify }}
</td>
<td>
    {{'**Description**'| markdownify }}
</td>
</tr>
<tr>
<td>
DataSource
</td>
<td>
The data source contains the list of data for generating the tree view list. Also, it contains properties to load data from remote data source.
</td>
</tr>
<tr>
<td>
Query
</td>
<td>
Specifies the query to retrieve data from the online server.
</td>
</tr>
<tr>
<td>
TableName
</td>
<td>
Specifies the name of the table from which the data to be processed from given data source.
</td>
</tr>
<tr>
<td>
Id
</td>
<td>
Specifies the ID of the node.
</td>
</tr>
<tr>
<td>
ParentId
</td>
<td>
Specifies the parent id of the node.
</td>
</tr>
<tr>
<td>
Text
</td>
<td>
Specifies the text content of the node.
</td>
</tr>
<tr>
<td>
HasChild
</td>
<td>
Specifies the node has child (nested or inner level of nodes). Also it is used in load on demand of tree data.
</td>
</tr>
<tr>
<td>
Expanded
</td>
<td>
Specifies the tree node to be in expanded state.
</td>
</tr>
<tr>
<td>
Selected
</td>
<td>
Specifies the selected node at initial rendering. (note: only one node get selected)
</td>
</tr>
<tr>
<td>
IsChecked
</td>
<td>
Specifies the node to be in checked state, if tree node is represented with checkboxes.
</td>
</tr>
<tr>
<td>
ImageUrl
</td>
<td>
Defines the image location.
</td>
</tr>
<tr>
<td>
ImageAttribute
</td>
<td>
Defines the image attributes such as height, width, styles, etc.
</td>
</tr>
<tr>
<td>
SpriteCssClass
</td>
<td>
Defines the sprite CSS for the image tag.
</td>
</tr>
<tr>
<td>
HtmlAttribute
</td>
<td>
Defines the HTML attributes such as class and styles for a node ("li" tag).
</td>
</tr>
<tr>
<td>
LinkAttribute
</td>
<td>
Defines the HTML attributes such as class and styles for a link tag that is the child of node.
</td>
</tr>
<tr>
<td>
Child
</td>
<td>
Specifies the properties of child nodes in tree view.
</td>
</tr>
</table>

Mapping all fields with data source.

In the model page, specify the tree view node properties as shown in the following:
        
    {% highlight c# %}
    
        public class LoadData
        {
            public int Id { get; set; }
            public int Parent { get; set; }
            public string Text { get; set; }
            public string SpriteImage { get; set; }
            public string ImageURL { get; set; }
            public bool HasChild { get; set; }
            public bool Expanded { get; set; }
            public bool Selected { get; set; }
            public bool NodeChecked { get; set; }
            public object NodeProperty { get; set; }
            public object LinkProperty { get; set; }
            public object ImageProperty { get; set; }
        }
        
    {% endhighlight %}
    
In the controller page, create a data list that contains details about the tree nodes.
      
    {% highlight c# %}
    
        public partial class TreeViewController : Controller
        {
            List<LoadData> treeData = new List<LoadData>();
            public ActionResult TreeViewFeatures()
            {
                treeData.Add(new LoadData
                {
                    Id = 1,
                    Parent = 0,
                    Text = "Item 1",
                    Expanded = true,
                    NodeProperty = new Dictionary<string, string>() {
                    { "class", "text-blue" },
                    { "value", "Item 1" }
                    }
                });
                treeData.Add(new LoadData
                {
                    Id = 2,
                    Parent = 0,
                    Text = "Item 2",
                    LinkProperty = new Dictionary<string, string>() {
                    { "class", "text-underline" },
                    { "href", "http://www.syncfusion.com" },
                    { "target", "_blank"}
                    }
                });
                treeData.Add(new LoadData
                {
                    Id = 3,
                    Parent = 0,
                    Text = "Item 3",
                    Selected = true,
                    SpriteImage = "mail-icon sprite-calendar"
                });
                treeData.Add(new LoadData
                {
                    Id = 4,
                    Parent = 0,
                    Text = "Item 4",
                    NodeChecked = true,
                    ImageProperty = new Dictionary<string, string>() {
                    { "width", "20px" },
                    { "height", "20px" }
                    },
                    ImageURL = "http://cdn.syncfusion.com/13.3.0.7/js/web/flat-azure/images/ajax-loader.gif"
                });
                treeData.Add(new LoadData
                {
                    Id = 5,
                    Parent = 1,
                    Text = "Item 1.1"
                });
                treeData.Add(new LoadData
                {
                    Id = 6,
                    Parent = 1,
                    Text = "Item 1.2"
                });
                treeData.Add(new LoadData
                {
                    Id = 7,
                    Parent = 1,
                    Text = "Item 1.3"
                });
                treeData.Add(new LoadData
                {
                    Id = 8,
                    Parent = 3,
                    Text = "Item 3.1"
                });
                treeData.Add(new LoadData
                {
                    Id = 9,
                    Parent = 3,
                    Text = "Item 3.2"
                });
                treeData.Add(new LoadData
                {
                    Id = 10,
                    Parent = 5,
                    Text = "Item 1.1.1"
                });
                ViewBag.datasource = treeData;
                return View();
            }
        }
        
    {% endhighlight %}
      
    
In the view page, add the following code and map the properties defined to the corresponding fields in a data source.
  
   {% highlight CSHTML %}

    <div style="width: 250px">
   
    <ej-tree-view id="treeview" show-checkbox="true">
	  <e-tree-view-fields datasource="ViewBag.datasource" id="Id" parent-id="Parent" text="Text" expanded="Expanded" is-checked="NodeChecked" selected="Selected" sprite-css-class="SpriteImage" image-url="ImageURL" link-attribute="LinkProperty" html-attribute="NodeProperty" image-attribute="ImageProperty">
	  </e-tree-view-fields>
	</ej-tree-view>

    </div>
    
    {% endhighlight %}    
       
N>**If you want to display nodes in root level, exclude parent attribute or specify “0” in the corresponding value.**

## Local data

The tree view can be rendered from a self-referential data by providing the two required fields **id**and **parent**.

In the controller page, create a data list that contains details about the tree nodes.
    
    {% highlight c# %}
    
        public partial class TreeViewController : Controller
        {
            List<LoadData> load = new List<LoadData>();
            public ActionResult TreeViewFeatures()
            {
                load.Add(new LoadData { Id = 1, Parent = 0, Text = "Item 1" });
                load.Add(new LoadData { Id = 2, Parent = 0, Text = "Item 2" });
                load.Add(new LoadData { Id = 3, Parent = 0, Text = "Item 3" });
                load.Add(new LoadData { Id = 4, Parent = 1, Text = "Item 1.1" });
                load.Add(new LoadData { Id = 5, Parent = 1, Text = "Item 1.2" });
                load.Add(new LoadData { Id = 6, Parent = 3, Text = "Item 3.1" });
                ViewBag.datasource = load;
                return View();
            }
            public class LoadData {
                public int Id;
                public int Parent;
                public string Text;
            }
        }
        
    {% endhighlight %}  
    
    
Previous data can be directly assigned to the `DataSource` property and you can map data fields with respect to the mapper field in order to form the tree view.
           
    {% highlight CSHTML %}
    
    <ej-tree-view id="treeview">
	  <e-tree-view-fields datasource="ViewBag.datasource" id="Id" parent-id="Parent" text="Text">
	  </e-tree-view-fields>
	</ej-tree-view>
    
    {% endhighlight %}   

### Nested object support

The nested object support is provided for the tree view component.

In the controller page, create a data list that contains details about the tree nodes.
    
    {% highlight c# %}
    
        public partial class TreeViewController : Controller
        {
            List<LoadData> load = new List<LoadData>();
            public ActionResult TreeViewFeatures()
            {
                load.Add(new LoadData { Id = 1, Parent = 0, Text = new InnerData { nodeName = "Item 1" } });
                load.Add(new LoadData { Id = 2, Parent = 0, Text = new InnerData { nodeName = "Item 2" } });
                load.Add(new LoadData { Id = 3, Parent = 0, Text = new InnerData { nodeName = "Item 3" } });
                load.Add(new LoadData { Id = 4, Parent = 1, Text = new InnerData { nodeName = "Item 1.1" } });
                load.Add(new LoadData { Id = 5, Parent = 1, Text = new InnerData { nodeName = "Item 1.2" } });
                load.Add(new LoadData { Id = 6, Parent = 3, Text = new InnerData { nodeName = "Item 3.1" } });
                ViewBag.datasource = load;
                return View();
            }
            public class LoadData
            {
                public int Id { get; set; }
                public int Parent { get; set; }
                public InnerData Text { get; set; }
            }
            public class InnerData
            {
                public string nodeName { get; set; }
            }

        }
        
    {% endhighlight %}  
    
    
Previous data can be directly assigned to the `DataSource` property and you can map data fields with respect to the mapper field in order to form the tree view.
           
    {% highlight CSHTML %}
    
    <ej-tree-view id="treeview">
		<e-tree-view-fields datasource="ViewBag.datasource" id="Id" parent-id="Parent" text="Text.nodeName">
		</e-tree-view-fields>
	</ej-tree-view>
    
    {% endhighlight %}   
    
    
## Remote data

When using remote data binding, the adaptor of [ej.DataManager](http://helpjs.syncfusion.com/js/api/ejdatamanager#) plays a vital role in processing queries to make them suitable to send along with data request, and also process the response data from the server.

The following steps explain you to bind remote data to the tree view control.

* In the view page, add the following code to configure the tree view.

* In the DataSource field, assign remote data source. Here, DataManager gets the remote web service and filters the data using Query API. The select property of ej.Query is used to retrieve the specified columns from the data source.

* Assign the DataSource and Query property values to bind the remote data. Map the corresponding fields in tree view control.

### OData

**OData** is a standardized protocol for creating and consuming data. Bind the [OData service](http://www.odata.org/#) data to tree view in two ways by using `DataSource` API of tree view control.
    
   **Using Datasource(DataSource) API**
    
   Create an object for `DataSource` class by using OData service URL and then assign it to the `DataSource` API of tree view.
       
    
    {% highlight CSHTML %}
    
    @{
        DataSource treeData = new DataSource();
        treeData.URL = "http://js.syncfusion.com/demos/ejServices/Wcf/Northwind.svc/";
    }
     <ej-tree-view id="treeview">
       <e-tree-view-fields datasource="treeData" query="ej.Query().from('Categories').select('CategoryID,CategoryName').take(3)" id="CategoryID" text="CategoryName">
         <e-child datasource="treeData" table-name="Products" id="ProductID" parent-id="CategoryID" text="ProductName"></e-child>
       </e-tree-view-fields>
     </ej-tree-view>
   
    {% endhighlight %}
    
   **Using Datasource(Action&lt;DataSourceBuilder&gt;) API**
    
   Here, directly you can specify the OData service URL.
    {% highlight CSHTML %}
    
       <ej-tree-view id="treeview">
	     <e-tree-view-fields query="ej.Query().from('Categories').select('CategoryID,CategoryName').take(3)" id="CategoryID" text="CategoryName">
	       <e-datamanager url="//js.syncfusion.com/demos/ejServices/Wcf/Northwind.svc/"></e-datamanager>
		  <e-child table-name="Products" id="ProductID" parent-id="CategoryID" text="ProductName">
		   <e-datamanager url="//js.syncfusion.com/demos/ejServices/Wcf/Northwind.svc/"></e-datamanager>
		  </e-child>
	     </e-tree-view-fields>
	   </ej-tree-view>
   
    {% endhighlight %}
    
    
In the previous methods, you may also specify the **adaptor** as [ODataAdaptor](http://helpjs.syncfusion.com/js/datamanager/data-adaptors#odata-adaptor) and it is optional to specify.

Provide the adaptor value either as string value (“ODataAdaptor”) or Enum type (AdaptorType.ODataAdaptor).
    
    {% highlight CSHTML %}
    
         <ej-tree-view id="treeview">
		   <e-tree-view-fields query="ej.Query().from('Categories').select('CategoryID,CategoryName').take(3)" id="CategoryID" text="CategoryName">
		    <e-datamanager url="//js.syncfusion.com/demos/ejServices/Wcf/Northwind.svc/" adaptor="@AdaptorType.ODataAdaptor"></e-datamanager>
		   <e-child table-name="Products" id="ProductID" parent-id="CategoryID" text="ProductName">
		    <e-datamanager url="//js.syncfusion.com/demos/ejServices/Wcf/Northwind.svc/" adaptor="@AdaptorType.ODataAdaptor"></e-datamanager>
		   </e-child>
		  </e-tree-view-fields>
		 </ej-tree-view>
    
    {% endhighlight %}   
    
    
N>**You can use the previous code until OData service version 3. For OData Service version 4 End Point, a separate adaptor [ej.ODataV4Adaptor](http://helpjs.syncfusion.com/js/datamanager/data-binding#odata-v4) is created for data binding.**
    
    {% highlight CSHTML %}
    
       <ej-tree-view id="treeview">
	     <e-tree-view-fields query="ej.Query().from('Categories').select('CategoryID,CategoryName').take(3)" id="CategoryID" text="CategoryName">
	       <e-datamanager url="//js.syncfusion.com/demos/ejServices/Wcf/Northwind.svc/" adaptor="@AdaptorType.ODataV4Adaptor"></e-datamanager>
	     <e-child table-name="Products" id="ProductID" parent-id="CategoryID" text="ProductName">
	       <e-datamanager url="//js.syncfusion.com/demos/ejServices/Wcf/Northwind.svc/" adaptor="@AdaptorType.ODataV4Adaptor"></e-datamanager>
		 </e-child>
		</e-tree-view-fields>
	   </ej-tree-view>

    {% endhighlight %}
    
    
    
### Web API

Using the [ej.WebApiAdaptor](http://helpjs.syncfusion.com/js/datamanager/data-adaptors#webapi-adaptor), you can bind Web API service data to the tree view as shown in the following code example.
    
    
    {% highlight CSHTML %}

          <ej-tree-view id="treeview">
		   <e-tree-view-fields id="id" text="name" parent-id="pid">
		   <e-datamanager url= "http://js.syncfusion.com/demos/ejServices/api/TreeViewData/GetAllData" adaptor="@AdaptorType.WebApiAdaptor" cross-domain="true"></e-datamanager>
		   </e-tree-view-fields>
		  </ej-tree-view>
  
    {% endhighlight %}   
    
    
### Other restful web services

The Custom Adaptor concept of the [ej.DataManager](http://helpjs.syncfusion.com/js/api/ejdatamanager#) allows you to customize or generate your own adaptor which is used to process query and result data.

[http://helpjs.syncfusion.com/js/datamanager/data-adaptors#custom-adaptor](http://helpjs.syncfusion.com/js/datamanager/data-adaptors#custom-adaptor)

When using remote data binding, the adaptor of [ej.DataManager](http://helpjs.syncfusion.com/js/api/ejdatamanager#) plays a vital role in processing queries to make them suitable to send along with the data request, and also process the response data from the server.

In the controller page, create a data list that contains the details about the tree nodes.
    
    {% highlight c# %}
    
        public partial class TreeViewController : Controller
        {
            List<LoadData> load = new List<LoadData>();
            public ActionResult TreeViewFeatures()
            {
                load.Add(new LoadData { Id = 1, Parent = 0, Text = "Item 1" });
                load.Add(new LoadData { Id = 2, Parent = 0, Text = "Item 2" });
                load.Add(new LoadData { Id = 3, Parent = 0, Text = "Item 3" });
                load.Add(new LoadData { Id = 4, Parent = 1, Text = "Item 1.1" });
                load.Add(new LoadData { Id = 5, Parent = 1, Text = "Item 1.2" });
                load.Add(new LoadData { Id = 6, Parent = 3, Text = "Item 3.1" });
                ViewBag.datasource = load;
                return View();
            }
            public class LoadData {
                public int Id;
                public int Parent;
                public string Text;
            }
        }
        
    {% endhighlight %}
    
    
In the view page, add the following code and specify the custom adaptor as shown in the following:
    
    {% highlight CSHTML %}
    
    <ej-tree-view id="treeview" create="onCreate">
	 <e-tree-view-fields datasource="ViewBag.datasource" id="Id" text="Text" parent-id="Parent">
	 </e-tree-view-fields>
	</ej-tree-view>
    
    <script type="text/javascript">
        function onCreate() {
            var treeObj = $("#tree").ejTreeView("instance");
            var treeData = treeObj.model.fields.dataSource;
            var customAdaptor = new ej.Adaptor().extend({
                insert: function (dataManager, data) {
                    return dataManager.dataSource.json.push(data);
                },
                processQuery: ej.JsonAdaptor.prototype.processQuery
            });
            var dataManager = new ej.DataManager(treeData);
            dataManager.adaptor = new customAdaptor();
            dataManager.insert({ Id: 7, Text: "CustomData", Parent: 0 });
            treeObj.option("fields", { dataSource: dataManager });
        }
    </script>
    
    {% endhighlight %}
        
## Load on demand

Load on demand is a technique (Lazy load) used to reduce the bandwidth size of consuming huge data. When you are going to use huge data, load data on demand in the tree view by using the “**LoadOnDemand**” property.

For a local data source, tree view loads the first level nodes initially. While expanding a parent node, the tree view loads its child nodes from the data source based on the parentId member. It reduces the time to render the tree view with huge data.

In the controller page, create a data list that contains the details about the tree nodes.

{% highlight c# %}
    
public class HomeController : Controller
{
    List<load> data = new List<load>();
    public ActionResult Index()
    {
        data.Add(new load { id = 1, name = "Local Disk(C:)", hasChild = true });
        data.Add(new load { id = 2, name = "Local Disk(D:)", hasChild = true });
        data.Add(new load { id = 3, name = "Local Disk(E:)", hasChild = true });
        data.Add(new load { id = 4, parentId = 1, name = "Folder 1", hasChild = true });
        data.Add(new load { id = 5, parentId = 1, name = "Folder 2" });
        data.Add(new load { id = 6, parentId = 1, name = "Folder 3" });
        data.Add(new load { id = 7, parentId = 2, name = "Folder 4" });
        data.Add(new load { id = 8, parentId = 2, name = "Folder 5", hasChild = true });
        data.Add(new load { id = 9, parentId = 2, name = "Folder 6" });
        data.Add(new load { id = 10, parentId = 3, name = "Folder 7" });
        data.Add(new load { id = 11, parentId = 3, name = "Folder 8" });
        data.Add(new load { id = 12, parentId = 3, name = "Folder 9", hasChild = true });
        data.Add(new load { id = 13, parentId = 4, name = "File 1" });
        data.Add(new load { id = 14, parentId = 4, name = "File 2" });
        data.Add(new load { id = 15, parentId = 4, name = "File 3" });
        data.Add(new load { id = 16, parentId = 8, name = "File 4" });
        data.Add(new load { id = 17, parentId = 8, name = "File 5" });
        data.Add(new load { id = 18, parentId = 8, name = "File 6" });
        data.Add(new load { id = 19, parentId = 12, name = "File 7" });
        data.Add(new load { id = 20, parentId = 12, name = "File 8" });
        data.Add(new load { id = 21, parentId = 12, name = "File 9" });
        ViewBag.datasource = data;
        return View();
    }
}

public class load
{
    public int id { get; set; }
    public int? parentId { get; set; }
    public string name { get; set; }
    public bool? hasChild { get; set; }
    public bool? expanded { get; set; }
    public bool? ischecked { get; set; }
    public bool? selected { get; set; }
    public string spriteCss { get; set; }
}
        
{% endhighlight %}
    
In the view page, add the following code and map the properties defined to the corresponding fields in Datasource. This enables the load on demand option.
   
{% highlight CSHTML %}
    
   <ej-tree-view id="treeview" load-on-demand="true">
    <e-tree-view-fields datasource="ViewBag.datasource" id="id" text="name" parent-id="parentId" has-child="hasChild">
	</e-tree-view-fields>
   </ej-tree-view>
    
{% endhighlight %}

The following screenshot displays the load on demand for a local data source in the tree view control.

![](Populate-Data_images/Populate-Data_img1.png)

While expanding the parent node
{:.caption}

![](Populate-Data_images/Populate-Data_img2.png)

After expanding the parent node
{:.caption}

For remote data source, the tree view loads the first level nodes initially. While expanding the node from tree view, the data manager passes the query to the controller. Based on this query, you can filter the data from table and return it to the tree view.
   
Refer the following code example to load data on demand from remote data source.
    
{% highlight CSHTML %}
    
    <ej-tree-view id="treeview" load-on-demand="true">
	  <e-tree-view-fields id="CategoryID" text="CategoryName" query="ej.Query().from('Categories').select('CategoryID,CategoryName').take(3)" has-child="CategoryName">
	    <e-datamanager url="//js.syncfusion.com/demos/ejServices/Wcf/Northwind.svc/"></e-datamanager>
		<e-child url="//js.syncfusion.com/demos/ejServices/Wcf/Northwind.svc/" table-name="Products" parent-id="CategoryID" text="ProductName"></e-child>
	  </e-tree-view-fields>
	</ej-tree-view>
    
{% endhighlight %}