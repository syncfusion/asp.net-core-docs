---
layout: post
title: DataBinding with grid widget for Syncfusion Essential ASPNET Core
description: How to bind in-memory JSON and remote web services in grid
platform: aspnet-core
control: grid
documentation: ug
--- 
# Data Binding

The Grid `datasource` property or `e-datamanager` child tag allows to bind datasource as the instance of one of the following types.
   
*	Collection that implements IEnumerable or IEnumerable&lt;T&gt;.
*	REST Service URL as string.
*	Table – Allows to bind HTML Table and it accepts table template script "ID".
*	ORM components such as Entity Framework/Linq to SQL.

N> 1. To update the dataSource after Grid rendered, use `dataSource` method of grid.
N> 2. DateTime values, retrieved from server-end or database, will be converted based on the local time zone. To avoid the local time zone conversion, refer this knowledge base [link](https://www.syncfusion.com/kb/8613/how-to-convert-dates-to-utc-format).

## IEnumerable
 
The grid can be bound with either non-generic collection or generic collection that implements [IEnumerable](https://msdn.microsoft.com/en-us/library/system.collections.ienumerable.aspx) interface. It can be assigned to the grid’s `datasource` property.
    
N> The IEnumerable datasource can be passed as either directly to the datasource property or to the json property of the child tag.
  
The following code example describes the previous behavior.
  
{% tabs %} 
{% highlight razor %}

<ej-grid id="Grid" datasource="ViewBag.datasource">
    <e-columns>
        <e-column field="FirstName" header-text="First Name" text-align="Left" ></e-column>
        <e-column field="LastName" header-text="Last Name" text-align="Left"></e-column>
        <e-column field="Email" text-align="Left"></e-column>
    </e-columns>
</ej-grid>
{% endhighlight  %}
{% highlight c# %}
namespace samplebrowser.Controllers.Grid
{
    public class Person
    {
        public string FirstName { get; set; }
        public string LastName { get; set; }
        public string Email { get; set; }
    }

    public partial class GridController : Controller
    {
        // GET: /<controller>/
        public ActionResult DataBinding()
        {
            List<Person> Persons = new List<Person>();
            Persons.Add(new Person() { FirstName = "John", LastName = "Beckett", Email = "john@syncfusion.com" });
            Persons.Add(new Person() { FirstName = "Ben", LastName = "Beckett", Email = "ben@syncfusion.com" });
            Persons.Add(new Person() { FirstName = "Andrew", LastName = "Beckett", Email = "andrew@syncfusion.com" });
            ViewBag.datasource = Persons;
            return View();
        }
    }
}


{% endhighlight  %}
{% endtabs %} 

The following output is displayed as a result of the previous code example.

![](Data-Binding_images/Data-Binding_img1.png)

##  Complex binding

The grid can display nested or navigation properties in the column that would provide the way to display the field from another entity. The complex property can be provided in the `field` property  either as string value concatenated by dot.   

The following code example describes the previous behavior.

{% tabs %} 
{% highlight razor %}
        
<ej-grid id="Grid" datasource="ViewBag.datasource">
        <e-columns>
            <e-column field="FirstName" header-text="First Name" text-align="Left"></e-column>
            <e-column field="LastName" header-text="Last Name" text-align="Left"></e-column>
            <e-column field="Designation.Position" header-text="Designation" text-align="Left"></e-column>
            <e-column field="Email" header-text="Email" text-align="Left"></e-column>
        </e-columns>
    </ej-grid>

{% endhighlight  %}
{% highlight c# %} 
       
        namespace Grid.Controllers
        {    
          public class HomeController : Controller
           {        
           public ActionResult Index()
            {
            List<Person> Persons = new List<Person>();
            Persons.Add(new Person() { FirstName = "John", LastName = "Beckett", Email = "john@syncfusion.com", Designation = new Designation{ Position = "Manager"  } });
            Persons.Add(new Person() { FirstName = "Ben", LastName = "Beckett", Email = "ben@syncfusion.com", Designation = new Designation{ Position = "Asst. Manager" } });
            Persons.Add(new Person() { FirstName = "Andrew", LastName = "Beckett", Email = "andrew@syncfusion.com", Designation = new Designation{ Position = "Engineer"  } });
            ViewBag.datasource = Persons;
            return View();
           }
         }
       }
{% endhighlight  %}
{% endtabs %} 

The following output is displayed as a result of the previous code example.

![](Data-Binding_images/Data-Binding_img6.png)


##  WCF DataService / OData service

To consume WCF DataService in grid control, provide the service link directly to the  `url` property of grid `e-datamanager`.

There is an online OData Service `http://js.syncfusion.com/demos/ejServices/Wcf/Northwind.svc/Orders` created specifically for Syncfusion Controls

The following code example describes the previous behavior.

{% tabs %} 
{% highlight razor %}

<ej-grid id="FlatGrid" allow-paging="true">
    <e-datamanager url="http://js.syncfusion.com/demos/ejServices/Wcf/Northwind.svc/Orders"></e-datamanager>
    <e-columns>
        <e-column field="OrderID"></e-column>
        <e-column field="EmployeeID"></e-column>
        <e-column field="CustomerID"></e-column>
        <e-column field="ShipCountry"></e-column>
        <e-column field="Freight"></e-column>
    </e-columns>
</ej-grid>    

{% endhighlight  %}
{% endtabs %} 

The following output is displayed as a result of the previous code example.

![](Data-Binding_images/Data-Binding_img7.png)


##  Web API Service

The web API Adaptor is used for processing request and response messages from Web API Service.

To consume Web API service, set the service link to the `url` property of grid `e-datamanager` and you can set adaptor type as `WebApiAdaptor` to the `adaptor` Property of grid `e-datamanager`

 I> The datasource from Web API service must be returned as object that has property `result` with its value as data and another property `count` with its value as total records count.

DataOperation queries such as sorting, filtering, etc., would be sent to Web API Service corresponding to grid actions performed and they need to be handled manually as Web API Service does not process it by default.

The following code example describes the previous behavior.
    
{% tabs %} 
{% highlight razor %}
    
     <ej-grid id="FlatGrid" allow-paging="true">
    <e-datamanager url="/api/Orders" adaptor="WebApiAdaptor"></e-datamanager>
    <e-columns>
        <e-column field="OrderID"></e-column>
        <e-column field="EmployeeID"></e-column>
        <e-column field="CustomerID"></e-column>
        <e-column field="ShipCountry"></e-column>
        <e-column field="Freight"></e-column>
    </e-columns>
</ej-grid>
{% endhighlight  %}
{% highlight c# %} 
    
        public partial class GridController : Controller
        {
            // GET: /<controller>/
            private NORTHWNDContext _context;

            public GridController(NORTHWNDContext context)
            {
                _context = context;
            }
            public object Get()
            {
                var queryString = Request.Query;
                StringValues Skip;
                StringValues Take;
                int skip = (queryString.TryGetValue("$skip", out Skip)) ? Convert.ToInt32(Skip[0]) : 0;
                int top = (queryString.TryGetValue("$top", out Take)) ? Convert.ToInt32(Take[0]) : 12;
                return new { result = _context.Orders.Skip(skip).Take(top), count = _context.Orders.Count() };
            }
        }
    
{% endhighlight  %}
{% endtabs %}        

The following output is displayed as a result of the previous code example.

![](Data-Binding_images/Data-Binding_img9.png)

##  HTML Table binding

The HTML table can be set as a data source for grid. The ID of the HTML table should be assigned to the `table` property of the `DataManager`.

I> HTML table is the only valid element to use through `DataManager`.
  
The following code example describes the previous behavior.
 
{% tabs %}  
{% highlight razor %}

<ej-grid id="Grid" allow-paging="true">
    <e-datamanager table="#GridTable"></e-datamanager>
    <e-columns>
        <e-column field="Laptop" header-text="Laptop" text-align="Left"></e-column>
        <e-column field="Model" header-text="Model"></e-column>
        <e-column field="Price" header-text="Price" text-align="Right"></></e-column>
        <e-column field="OS" header-text="OS" text-align="Left"></e-column>
        <e-column field="RAM" header-text="RAM" text-align="Left"></e-column>
        <e-column field="ScreenSize" header-text="ScreenSize"></e-column>
    </e-columns>
</ej-grid>

{% endhighlight  %}
{% highlight js %}
    
      <script id="GridTable" type="text/template">
       <table>
          <thead>
               <tr>
                  <th>Laptop</th>
                  <th>Model</th>
                  <th>Price</th>
                  <th>OS</th>
                  <th>RAM</th>
                  <th>ScreenSize</th>
              </tr>
          </thead>
          <tbody>
             <tr>
                 <td>Dell Vostro</td>
                 <td>2520</td>
                 <td>39990</td>
                 <td>Windows 8</td>
                 <td>4GB</td>
                 <td>15.6</td>
             </tr>
             <tr>
                 <td>HP Pavilion Sleekbook</td>
                 <td>14-B104AU</td>
                 <td>22800</td>
                 <td>Windows 8</td>
                 <td>2GB</td>
                 <td>14</td>
             </tr>
             <tr>
                 <td>Sony Vaio</td>
                 <td>E14A15</td>
                 <td>42500</td>
                 <td>Windows 7 Home Premium</td>
                 <td>4GB DDR3 RAM</td>
                 <td>14</td>
             </tr>
             <tr>
                 <td>Lenovo</td>
                 <td>Yoga 13</td>
                 <td>57000</td>
                 <td>Windows 8 RT</td>
                 <td>2GB DDR3 RAM</td>
                 <td>11.6</td>
             </tr>
             <tr>
                 <td>Toshiba</td>
                 <td>L850-Y3110</td>
                 <td>57700</td>
                 <td>Windows 8 SL</td>
                 <td>8GB DDR3 RAM</td>
                 <td>15.6</td>
             </tr>
            </tbody>
          </table>
       </script>
{% endhighlight  %}
{% endtabs %}

The following output is displayed as a result of the previous code example.

![](Data-Binding_images/Data-Binding_img10.png)

##  Miscellaneous

###  Load on demand

By default, the grid with remote data binding will work in `On-Demand` concept for which either `Paging` or `VirtualScrolling` feature should be enabled in it. It helps in improving the performance of loading a large data set.

The following code example describes the previous behavior.

 {% tabs %}  
 {% highlight razor %} 

<ej-grid id="FlatGrid" allow-paging="true">
    <e-datamanager url="http://js.syncfusion.com/demos/ejServices/Wcf/Northwind.svc/Orders"></e-datamanager>
    <e-columns>
        <e-column field="OrderID"></e-column>
        <e-column field="EmployeeID"></e-column>
        <e-column field="CustomerID"></e-column>
        <e-column field="ShipCountry"></e-column>
        <e-column field="Freight"></e-column>
    </e-columns>
</ej-grid>

{% endhighlight  %}
{% endtabs %}

The following output is displayed as a result of the previous code example.

![](Data-Binding_images/Data-Binding_img11.png)

###  Load at once

The `Load at once` concept in grid can be used to load all data from remote service at a single request and all further grid action will be performed at client-side on the cached data.

The `offline` property of grid `DataManager` is used to enable `Load at once` in grid control

The following code example describes the previous behavior.

{% tabs %}  
{% highlight razor %} 

<ej-grid id="FlatGrid"  allow-paging="true">
    <e-datamanager url="http://js.syncfusion.com/demos/ejServices/Wcf/Northwind.svc/Orders" offline="true"></e-datamanager>
    <e-columns>
        <e-column field="OrderID"></e-column>
        <e-column field="EmployeeID"></e-column>
        <e-column field="CustomerID"></e-column>
        <e-column field="ShipCountry"></e-column>
        <e-column field="Freight"></e-column>
    </e-columns>
</ej-grid>        

{% endhighlight  %}
{% endtabs %}

The following output is displayed as a result of the previous code example.

![](Data-Binding_images/Data-Binding_img12.png)

###  Data caching

The `DataManager` can cache loaded data. The caching functionality can be enabled by setting the `enable-caching` property in `e-datamanager`.
    
The `time-till-expiration` and `caching-page-size` properties are used to control the expiration time of data and the cache page size settings respectively.

N> The window`s localStorage is used to cache the loaded data. 

The following code example describes the previous behavior.

{% tabs %}  
{% highlight razor %} 
   
<ej-grid id="Grid"  allow-paging="true">
    <e-datamanager url="DataSource" enable-caching="true" caching-page-size="4" time-till-expiration="120000" adaptor="UrlAdaptor"></e-datamanager>
    <e-columns>
        <e-column field="OrderID" header-text="Order ID"></e-column>
        <e-column field="CustomerID" header-text="Customer ID"></e-column>
        <e-column field="EmployeeID" header-text="Employee ID"></e-column>
        <e-column field="Freight" header-text="Freight" format="{0:C2}"></e-column>
    </e-columns>
</ej-grid>

{% endhighlight  %}
{% endtabs %}

The following output is displayed as a result of the previous code example.

![](Data-Binding_images/Data-Binding_img13.png)

###  Custom request parameters and HTTP header

####  Adding request parameters

The ‘addParams’ function in DataManager’s Query class is used to add additional custom parameter in data requests. The grid has an option to set default query which can be used to add custom parameter.
      
The following code example describes the previous behavior.

{% tabs %}  
{% highlight razor %} 


<ej-grid id="OrdersView"  allow-paging="true" query="ej.Query().addParams('Syncfusion', true)">
    <e-datamanager url="DataSource" adaptor="UrlAdaptor"></e-datamanager>
    <e-columns>
        <e-column field="OrderID" header-text="Order ID"></e-column>
        <e-column field="CustomerID" header-text="Customer ID"></e-column>
        <e-column field="EmployeeID" header-text="Employee ID"></e-column>
        <e-column field="Freight" header-text="Freight" format="{0:C2}"></e-column>
    </e-columns>
</ej-grid>

{% endhighlight  %}
{% endtabs %}

E> Attempting to add custom parameters with key name same as any default AJAX parameters used by the `DataManager` will results in error.

The following output is displayed as a result of the previous code example.

![](Data-Binding_images/Data-Binding_img14.png)

####  Adding custom HTTP headers

The Custom header can be added through `DataManager` `headers` options. While performing, CRUD operations, the `addParams` cannot be used to send additional parameters to the server in such cases the parameters can be send as custom header.

The following code example describes the previous behavior.

{% tabs %}  
{% highlight razor %} 
    List<Syncfusion.JavaScript.Models.KeyValue>
    str = new List<Syncfusion.JavaScript.Models.KeyValue>();
    str.Add(new Syncfusion.JavaScript.Models.KeyValue() {Key ="Syncfusion", Value = false });

                <ej-grid id="Grid" allow-paging="true">
                <e-datamanager url="DataSource" adaptor="UrlAdaptor" headers="@(str)"></e-datamanager>
                <e-columns>
                    <e-column field="OrderID" header-text="Order ID"></e-column>
                    <e-column field="CustomerID" header-text="Customer ID"></e-column>
                    <e-column field="EmployeeID" header-text="Employee ID"></e-column>
                    <e-column field="Freight" header-text="Freight" format="{0:C2}"></e-column>
                </e-columns>
            </ej-grid>        

{% endhighlight  %}
{% endtabs %}

N>  To add custom headers to the DataManager through JavaScript, refer to this [link]( https://www.syncfusion.com/kb/5963)

The following output is displayed as a result of the previous code example.

![](Data-Binding_images/Data-Binding_img15.png)

###  Handling HTTP Errors

During server interaction from the grid, there may occur some server-side exceptions and you can acquire those error messages or exception details in client-side using `action-failure` event of grid control.

The argument passed to the `action-failure` grid event contains the error details returned from server. Please refer to the following table for some error details that would be acquired in client-side event arguments.
              
<table>
<tr>
<th>Parameter</th>
<th>Description</th>
</tr>
<tr>
<td>arguments.error.status</td>
<td>It returns the response error code.</td></tr>
<tr>
<td>arguments.error.statusText</td>
<td>It returns the error message.</td>
</tr>
 </table>
              
The following code example describes the previous behavior.

{% tabs %}  
{% highlight razor %} 

    <ej-grid id="Grid" allow-paging="true" action-failure="OnActionFailure">
        <e-datamanager url="DataSource" adaptor="UrlAdaptor"></e-datamanager>
        <e-columns>
            <e-column field="OrderID" header-text="Order ID"></e-column>
            <e-column field="CustomerID" header-text="Customer ID"></e-column>
            <e-column field="EmployeeID" header-text="Employee ID"></e-column>
            <e-column field="Freight" header-text="Freight" format="{0:C2}"></e-column>
        </e-columns>
    </ej-grid>

{% endhighlight  %}
{% highlight js %}

             <script>
                 function OnActionFailure(args) {
                     alert(args.error.status + " : " + args.error.statusText);
                 }
             </script>
{% endhighlight  %}
{% endtabs %}

The following output is displayed as a result of the previous code example.

![](Data-Binding_images/Data-Binding_img16.png)