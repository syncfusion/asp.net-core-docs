---
layout: post
title: CORS Data Fetching | DataManager | ASP.NET Core | Syncfusion
description: CORS Data Fetching
platform: aspnet-core
control: DataManager
documentation: ug
keywords: CORS Data Fetching, SAME-ORIGIN POLICY, Access-Control-Allow-Origin, Access-Control-Request-Method, Access-Control-Request-Headers

---
# CORS Data Fetching

The Cross-Origin Resource Sharing (CORS) mechanism enable secure cross-domain data transfers.

## SAME-ORIGIN POLICY

This policy defined the rule for, “how a web page can be accessed by an external resource”. Browsers wont permits a request to access the resources who origin is differ than the current page. To overcome the restriction of same-origin policy, we can use a technique called Cross-origin resource sharing

![](CORS_images/SAME-ORIGIN1.png) 

## Access-Control-Allow-Origin

First, we need to add required Packages to sample application, here we have added those packages listed below in project.json file. After putting all those packages in our project config file, they will automatically be added to our application by IDE.

{% highlight html %}

    // project.json
    // Cross Origin Resource Sharing
    "Microsoft.AspNetCore.Cors": "1.0.0"

{% endhighlight %}

Cross-domain requests require common procedure between the Web page and the server. Initiate a cross-domain request in a web page and opening a connection to the mentioned domain. The browser will request the service (i.e data) from the domain’s server by sending an Origin header with the value of the origin. It will only complete the connection if the server responds with an Access-Control-Allow-Origin header of either * or the exact URL of the requesting page.
When you set, Access-Control-Allow-Origin value as “Testing1.com”.

With this rule, only scripts that originate from http://“Testing1.com are allowed to load resources. Any other domain trying to use AJAX to load resources will be given the security error message.

By using this rule, the domain owners can restrict which domains are allowed to use the resource.

Alternatively, the  owners can grant wide-open access with the always ready to party asterisk: __Access-Control-Allow-Origin: *__.

{% highlight html %}

    Startup.cs: ConfigureServices

    services.AddCors(
        options => options.AddPolicy("AllowCors",
        builder =>
        {
            builder
            .AllowAnyOrigin() //AllowAllOrigins;
            .WithOrigins("http://localhost:4456") //AllowSpecificOrigin;
            .WithOrigins("http://localhost:4456", "http://localhost:4457") //AllowMultipleOrigins;
        })
    );

{% endhighlight %}

Now, any website that wants to load a resource using AJAX can do so without getting the security error.

## Access-Control-Request-Method

The Access-Control-Request-Method is used when issuing a preflight request to let the server know what HTTP method will be used when the  request is made.

{% highlight html %}

    Startup.cs: ConfigureServices

    services.AddCors(
        options => options.AddPolicy("AllowCors",
        builder =>
        {
            builder
            .WithMethods("GET", "PUT", "POST", "DELETE") //AllowSpecificMethods;
            .AllowAnyMethod() //AllowAllMethods;
        })
    );

{% endhighlight %}

N> 
Preflighted requests: <BR>
Setting custom headers to XHR triggers a preflight request. With simple words this mean that preflight request first sends an HTTP request by the OPTIONS method to the resource on the remote domain, to make sure that the request is safe to send. According W3C for non-same origin requests using the HTTP GET method a preflight request is made when headers other than Accept and Accept-Language are set.

## Access-Control-Request-Headers

The Access-Control-Request-Headers header is used when issuing a preflight request to let the server know what HTTP headers will be used when the  request is made.

{% highlight html %}

    Startup.cs: ConfigureServices

    services.AddCors(
        options => options.AddPolicy("AllowCors",
        builder =>
        {
            builder
            .WithHeaders("Accept", "Content-type", "Origin", "X-Custom-Header");  //AllowSpecificHeaders;
            .AllowAnyHeader(); //AllowAllHeaders;
        })
    );

{% endhighlight %}

After that, we have enabled CORS for your application using an extension method "UseCors".

{% highlight html %}

    Startup.cs: Configure

    app.UseCors("AllowCors");

{% endhighlight %}

Finally the Full Startup.cs:

{% highlight html %}

    // This method gets called by the runtime. Use this method to add services to the container
    public void ConfigureServices(IServiceCollection services)
    {
        //Add CORS services.
        //services.Configure<MvcOptions>(options =>
        //{
        //    options.Filters.Add
        //    (new CorsAuthorizationFilterFactory("AllowSpecificOrigin"));
        //});

        services.AddCors(
            options => options.AddPolicy("AllowCors",
            builder =>
            {
                builder
                //.WithOrigins("http://localhost:4456") //AllowSpecificOrigins;
                //.WithOrigins("http://localhost:4456", "http://localhost:4457") //AllowMultipleOrigins;
                .AllowAnyOrigin() //AllowAllOrigins;

                //.WithMethods("GET") //AllowSpecificMethods;
                //.WithMethods("GET", "PUT") //AllowSpecificMethods;
                //.AllowAnyMethod() //AllowAllMethods;

                //.WithHeaders("Accept", "Content-type", "Origin", "X-Custom-Header");  //AllowSpecificHeaders;
                .AllowAnyHeader(); //AllowAllHeaders;
            })
        );
    }
    / This method gets called by the runtime. 
    // Use this method to configure the HTTP request pipeline
    public void Configure (IApplicationBuilder app, IHostingEnvironment env, ILoggerFactory loggerFactory)
    {
        //Enable CORS policy "AllowCors"
        app.UseCors("AllowCors");
    }

{% endhighlight %}

**MVC WebApi**: Here are a list of required namespaces.

using Microsoft.AspNetCore.Mvc;
using Microsoft.AspNetCore.Cors;
using CrossOrigin.WebService.Models.DbEntities;

**API Controller**: Here, we are applying specific CORS policy on APiController. It can also be applied on per action based or globally for all controllers based.

{% highlight html %}

    namespace WebApplication1.Controllers
    {
        [EnableCors("AllowCors"), Route("api/[controller]")]
        public class OrdersController : Controller
        {
            public static List<OrderDetails> order = new List<OrderDetails>();
            // GET: api/values
            [HttpGet]
            public JsonResult Get()
            {
                int code = 10000;
                for (int i = 1; i < 2; i++)
                {
                    order.Add(new OrderDetails(code + 1, "ALFKI", i + 0, 2.3 * i, "Berlin"));
                    order.Add(new OrderDetails(code + 2, "ANATR", i + 2, 3.3 * i, "Madrid"));
                    order.Add(new OrderDetails(code + 3, "ANTON", i + 1, 4.3 * i, "Cholchester"));
                    order.Add(new OrderDetails(code + 4, "BLONP", i + 3, 5.3 * i, "Marseille"));
                    order.Add(new OrderDetails(code + 5, "BOLID", i + 4, 6.3 * i, "Tsawassen"));
                    code += 5;
                }
                var list = order.ToList();
                return Json(new { result = list, count = list.Count });
            }
            public class OrderDetails
            {
                public OrderDetails()
                {

                }
                public OrderDetails(int OrderID, string CustomerId, int EmployeeId, double Freight, string ShipCity)
                {
                    this.OrderID = OrderID;
                    this.CustomerID = CustomerId;
                    this.EmployeeID = EmployeeId;
                    this.Freight = Freight;
                    this.ShipCity = ShipCity;
                }

                public int? OrderID { get; set; }
                public string CustomerID { get; set; }
                public int? EmployeeID { get; set; }
                public double? Freight { get; set; }
                public string ShipCity { get; set; }
            }

            // PUT api/values/5
            [DisableCors, HttpPut("{id}")]
            public void Put(int id, [FromBody]string value)
            {
            }
        }
    }

{% endhighlight %}

We can disable CORS by using attribute "DisableCors". In this controller, we have applied on "PUT" method to disable CORS.
