---
layout: post
title: Data Binding | TreeGrid | ASP.NET Core | Syncfusion
description: data binding
platform: aspnet-core
control: TreeGrid
documentation: ug
---

# Data Binding

Data Binding is the process that establishes a connection between the application and different kinds of data sources such as business objects.

## Local Data Binding

In Local Data Binding, datasource for rendering the TreeGrid control is retrieved from the same application locally.

Two types of Data Binding are possible with TreeGrid control, 

* Hierarchical Datasource Binding
* Self-Referential Data Binding (Flat Data)

## Hierarchy Datasource Binding

The following code example shows you how to bind the Hierarchical local data into the TreeGrid control.

{% tabs %}


{% highlight C# %}

 public partial class TreeGridController : Controller
    {
        //
        // GET: /Default/

        public ActionResult Default()
        {
            var data = this.GetDefaultData();
            ViewBag.datasource = data;
            return View();
        }



        private List<BusinessObject> GetDefaultData()
        {
            List<BusinessObject> BusinessObjectCollection = new List<BusinessObject>();

            BusinessObject Record1 = null;

            Record1 = new BusinessObject()
            {
                TaskId = 1,
                TaskName = "Planning",
                StartDate = "02/03/2014",
                EndDate = "02/07/2014",
                Progress = 100,
                Duration = 5,
                Children = new List<BusinessObject>(),
            };

            BusinessObject Child1 = new BusinessObject()
            {
                TaskId = 2,
                TaskName = "Plan timeline",
                StartDate = "02/03/2014",
                EndDate = "02/07/2014",
                Duration = 5,
                Progress = 100
            };

            BusinessObject Child2 = new BusinessObject()
            {
                TaskId = 3,
                TaskName = "Plan budget",
                StartDate = "02/03/2014",
                EndDate = "02/07/2014",
                Duration = 5,
                Progress = 100
            };

            BusinessObject Child3 = new BusinessObject()
            {
                TaskId = 4,
                TaskName = "Allocate resources",
                StartDate = "02/03/2014",
                EndDate = "02/07/2014",
                Duration = 5,
                Progress = 100
            };

            BusinessObject Child4 = new BusinessObject()
            {
                TaskId = 5,
                TaskName = "Planning complete",
                StartDate = "02/07/2014",
                EndDate = "02/07/2014",
                Duration = 0,
                Progress = 0
            };

            Record1.Children.Add(Child1);
            Record1.Children.Add(Child2);
            BusinessObject Record2 = new BusinessObject()
            {
                TaskId = 6,
                TaskName = "Design",
                StartDate = "02/10/2014",
                EndDate = "02/14/2014",
                Progress = 86,
                Duration = 3,
                Children = new List<BusinessObject>(),
            };

            BusinessObject Child5 = new BusinessObject()
            {
                TaskId = 7,
                TaskName = "Software Specification",
                StartDate = "02/10/2014",
                EndDate = "02/12/2014",
                Duration = 3,
                Progress = 60
            };

            BusinessObject Child6 = new BusinessObject()
            {
                TaskId = 8,
                TaskName = "Develop prototype",
                StartDate = "02/10/2014",
                EndDate = "02/12/2014",
                Duration = 3,
                Progress = 100
            };

            BusinessObject Child7 = new BusinessObject()
            {
                TaskId = 9,
                TaskName = "Get approval from customer",
                StartDate = "02/13/2014",
                EndDate = "02/14/2014",
                Duration = 2,
                Progress = 100
            };

            BusinessObject Child8 = new BusinessObject()
            {
                TaskId = 10,
                TaskName = "Design complete",
                StartDate = "02/14/2014",
                EndDate = "02/14/2014",
                Duration = 0,
                Progress = 0
            };

            Record2.Children.Add(Child5);
            Record2.Children.Add(Child6);
            Record2.Children.Add(Child7);
            Record2.Children.Add(Child8);
            BusinessObjectCollection.Add(Record1);
            BusinessObjectCollection.Add(Record2);
            return BusinessObjectCollection;
        }


        public class BusinessObject
        {
            public int TaskId
            {
                get;
                set;
            }

            public string TaskName
            {
                get;
                set;
            }

            public string StartDate
            {
                get;
                set;
            }

            public string EndDate
            {
                get;
                set;
            }

            public int Duration
            {
                get;
                set;
            }

            public int Progress
            {
                get;
                set;
            }
            public string Priority
            {
                get;
                set;
            }
            public bool InProgress
            {
                get;
                set;
            }
            public DateTime FilterStartDate
            {
                get;
                set;
            }
            public DateTime FilterEndDate
            {
                get;
                set;
            }
            public List<BusinessObject> Children
            {
                get;
                set;
            }

        }
    }

{% endhighlight  %}
{% highlight CSHTML %}


@using Syncfusion.JavaScript

@using Syncfusion.JavaScript.Models

@using Syncfusion.MVC.EJ 



<!DOCTYPE html>     



<html>



<head>



         @*Add script reference and style reference here*@



</head>



<body>


  <ej-tree-grid id="TreeGridContainer" datasource="ViewBag.datasource" child-mapping="Children" tree-column-index="1">
        <e-tree-grid-columns>
            <e-tree-grid-column field="TaskId" header-text="Task Id" width=45 />
            <e-tree-grid-column field="TaskName" header-text="Task Name" />
            <e-tree-grid-column field="StartDate" header-text="Start Date" />
            <e-tree-grid-column field="EndDate" header-text="End Date" />
            <e-tree-grid-column field="Duration" header-text="Duration" />
            <e-tree-grid-column field="Progress" header-text="Progress" />
        </e-tree-grid-columns>
    </ej-tree-grid>                           

      


</body>

</html>



{% endhighlight %}
{% endtabs %}  


The output of the above steps is as follows:

![](Data-Binding_images/Data-Binding_img1.png)



## Self-Referential Data Binding (Flat Data)

TreeGrid is rendered from Self-Referential data structures by providing two fields: ID field and parent ID field.

•ID Field- This field contains unique values used to identify nodes. Its name is assigned to the id-mapping property.

•Parent ID Field- This field contains values that indicate parent nodes. Its name is assigned to the parent-id-mapping property.


{% tabs %}

{% highlight C# %}

    public partial class TreeGridController : Controller
    {


        public ActionResult Default()
        {
            var data = this.GetDefaultData();
            ViewBag.datasource = data;
            return View();
        }


        #region Create DataSource for Self TreeGrid control
        private List<BusinessObject> GetDefaultData()
        {
            List<BusinessObject> BusinessObjectCollection = new List<BusinessObject>();
            BusinessObjectCollection.Add(new BusinessObject()
            {
                TaskId = 1,
                TaskName = "Parent Task 1",
                StartDate = "10/23/2013",
                Duration = 10,
                Progress = 70,
                ParentId = 1
            });
            BusinessObjectCollection.Add(new BusinessObject()
            {
                TaskId = 2,
                TaskName = "Child task 1",
                StartDate = "10/23/2013",
                Duration = 4,
                Progress = 80,
                ParentId = 1
            });
            BusinessObjectCollection.Add(new BusinessObject()
            {
                TaskId = 3,
                TaskName = "Child Task 2",
                StartDate = "10/24/2013",
                Duration = 5,
                Progress = 65,
                ParentId = 1
            });
            BusinessObjectCollection.Add(new BusinessObject()
            {
                TaskId = 4,
                TaskName = "Child task 3",
                StartDate = "10/25/2013",
                Duration = 6,
                Progress = 77,
                ParentId = 1
            });
            BusinessObjectCollection.Add(new BusinessObject()
            {
                TaskId = 5,
                TaskName = "Parent Task 2",
                StartDate = "10/23/2013",
                Duration = 10,
                Progress = 70,
                ParentId = 1
            });
            BusinessObjectCollection.Add(new BusinessObject()
            {
                TaskId = 6,
                TaskName = "Child task 1",
                StartDate = "10/23/2013",
                Duration = 4,
                Progress = 80,
                ParentId = 5
            });
            BusinessObjectCollection.Add(new BusinessObject()
            {
                TaskId = 7,
                TaskName = "Child Task 2",
                StartDate = "10/24/2013",
                Duration = 5,
                Progress = 65,
                ParentId = 5
            });
            BusinessObjectCollection.Add(new BusinessObject()
            {
                TaskId = 8,
                TaskName = "Child task 3",
                StartDate = "10/25/2013",
                Duration = 6,
                Progress = 77,
                ParentId = 5
            });
            BusinessObjectCollection.Add(new BusinessObject()
            {
                TaskId = 9,
                TaskName = "Child task 4",
                StartDate = "10/25/2013",
                Duration = 6,
                Progress = 77,
                ParentId = 5
            });
            BusinessObjectCollection.Add(new BusinessObject()
            {
                TaskId = 10,
                TaskName = "Parent Task 3",
                StartDate = "10/23/2013",
                Duration = 10,
                Progress = 70,
                ParentId = 5
            });
            BusinessObjectCollection.Add(new BusinessObject()
            {
                TaskId = 11,
                TaskName = "Child task 1",
                StartDate = "10/23/2013",
                Duration = 4,
                Progress = 80,
                ParentId = 10
            });
            BusinessObjectCollection.Add(new BusinessObject()
            {
                TaskId = 12,
                TaskName = "Child Task 2",
                StartDate = "10/24/2013",
                Duration = 5,
                Progress = 65,
                ParentId = 10
            });
            BusinessObjectCollection.Add(new BusinessObject()
            {
                TaskId = 13,
                TaskName = "Child task 3",
                StartDate = "10/25/2013",
                Duration = 6,
                Progress = 77,
                ParentId = 10
            });
            BusinessObjectCollection.Add(new BusinessObject()
            {
                TaskId = 14,
                TaskName = "Child task 4",
                StartDate = "10/25/2013",
                Duration = 6,
                Progress = 77,
                ParentId = 10
            });
            BusinessObjectCollection.Add(new BusinessObject()
            {
                TaskId = 15,
                TaskName = "Child task 5",
                StartDate = "10/25/2013",
                Duration = 6,
                Progress = 77,
                ParentId = 10
            });

            return BusinessObjectCollection;
        }
        #endregion

    }


{% endhighlight  %}
{% highlight CSHTML %}

<ej-tree-grid id="TreeGridContainer" datasource="ViewBag.datasource" tree-column-index="1" allow-column-resize="true" is-responsive="true" id-mapping="Id" parent-id-mapping="ParentId">
    <e-tree-grid-columns>
        <e-tree-grid-column field="TaskId" header-text="Task Id" width=45 />
        <e-tree-grid-column field="TaskName" header-text="Task Name" />
        <e-tree-grid-column field="StartDate" header-text="Start Date" />   
        <e-tree-grid-column field="Duration" header-text="Duration" />
        <e-tree-grid-column field="Progress" header-text="Progress" />
    </e-tree-grid-columns>
</ej-tree-grid> 

{% endhighlight %}
{% endtabs %}  

The following screenshot shows the output of the above steps,

![](Data-Binding_images/Data-Binding_img2.png)

## Remote data binding

### Load on demand

TreeGrid provides `Load on Demand` support for rendering remote data. Load on demand is considered in TreeGrid for the following actions, 

* Expanding root nodes.
* Navigating pages, with paging enabled in TreeGrid.

When load on demand is enabled, all the root nodes are rendered in collapsed state at initial load.

When load on demand support is enabled in TreeGrid with paging, the current or active page’s root node alone will be rendered in collapsed state. On expanding the root node, the child nodes will be loaded from the remote server. 

When a root node is expanded, its child nodes are rendered and are cached locally, such that on consecutive expand/collapse actions on root node, the child nodes are loaded from the cache instead from the remote server.

Similarly, if the user navigates to a new page, the root nodes of that specific page, will be rendered with request to the remote server.

N> 1. Load on demand support in TreeGrid can be enabled only for remote data.
N> 2. For better initial load time performance, we need to define the “HasChildMapping” property.

Load on demand support in TreeGrid can be enabled by the following ways,

1. By enabling [`EnableLoadOnDemand`](https://help.syncfusion.com/api/js/ejtreegrid#members:enableLoadOnDemand "enableLoadOnDemand") property of TreeGrid control
2. By enabling **CrossDomain** property while binding data source using ejDataManager control.

The following code explains how to use Load on Demand in TreeGrid Control,

{% highlight CSHTML %}

 <ej-tree-grid id="TreeGridLoadonDemand" id-mapping="TaskID" parent-id-mapping="ParentID" has-child-mapping="isParent" enable-virtualization="true">
    <e-tree-grid-data-manager URL="http://js.syncfusion.com/demos/ejServices/Wcf/TreeGridGantt/TreeGantt.svc/SelfReferenceDatas" cross-domain="true"></e-tree-grid-data-manager>
    <e-tree-grid-columns>
        <e-tree-grid-column headerText="Task Id" field="TaskID" width="45" />
        <e-tree-grid-column headerText="Task Name" field="TaskName" />
        <e-tree-grid-column headerText="Start Date" field="StartDate" editType="datetimepicker" />
        <e-tree-grid-column headerText="End Date" field="EndDate" editType="datetimepicker" />
        <e-tree-grid-column headerText="Progress" field="Progress" />
    </e-tree-grid-columns>
</ej-tree-grid>

{% endhighlight %}

The output for load on demand support in TreeGrid:

![](Data-Binding_images/Data-Binding_img3.png)
![](Data-Binding_images/Data-Binding_img4.png)

The following code snippet shows on how to enable load on demand support using  [`EnableLoadOnDemand`](https://help.syncfusion.com/api/js/ejtreegrid#members:enableLoadOnDemand "enableLoadOnDemand") property.

{% highlight CSHTML %}

 <ej-tree-grid id="TreeGridLoadonDemand"
     //...
    enable-load-on-demand="true">
    <e-tree-grid-data-manager url="http://js.syncfusion.com/demos/ejServices/Wcf/TreeGridGantt/TreeGantt.svc/SelfReferenceDatas" cross-domain="true"></e-tree-grid-data-manager>  
</ej-tree-grid>

{% endhighlight %}

The following output shows how load on demand works for expanding action

![](Data-Binding_images/Data-Binding_img5.png)

### Load at once:

On remote data binding, for every action such as paging, sorting, filtering, the data will be fetched from remote server each time. To avoid requesting the data from the remote server for each action, we can set TreeGrid to load all the data on initialization and make all the data operations in client side. To enable this, we can use Offline property of `ej.DataManager`. the following code example explains this.

{% highlight CSHTML %}

 <ej-tree-grid id="TreeGridLoadonDemand" id-mapping="TaskID" parent-id-mapping="ParentID" has-child-mapping="isParent" enable-virtualization="true">
    <e-tree-grid-data-manager url="http://js.syncfusion.com/demos/ejServices/Wcf/TreeGridGantt/TreeGantt.svc/SelfReferenceDatas" Offline="true"></e-tree-grid-data-manager>
    <e-tree-grid-columns>
        <e-tree-grid-column headerText="Task Id" field="TaskID" width="45" />
        <e-tree-grid-column headerText="Task Name" field="TaskName" />
        <e-tree-grid-column headerText="Start Date" field="StartDate" edit-type="datetimepicker" />
        <e-tree-grid-column headerText="End Date" field="EndDate" edit-type="datetimepicker" />
        <e-tree-grid-column headerText="Progress" field="Progress" />
    </e-tree-grid-columns>
</ej-tree-grid>

{% endhighlight %}

Please refer the [link](https://help.syncfusion.com/js/datamanager/data-binding#offline-mode "offline") for further reference on offline property

**Limitations**:

1. Mapping the expand state of a record using `ExpandStateMapping` property is not supported in load on demand feature.
2. If a root or parent node is in collapsed state (child nodes not yet loaded), then that parent node will not be expanded while inserting new child to that parent node using toolbar icon or drag and drop actions.




