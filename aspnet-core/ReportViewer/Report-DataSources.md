---
layout: post
title: Report DataSources | Syncfusion
description: report datasources
platform: aspnet-core
control: ReportViewer
documentation: ug
---

## Report DataSources

The ReportViewer has support to add data sources to ReportViewer for RDLC reports at runtime. You can add SQL Server DataSources to ReportViewer. The ReportViewer has `dataSources` property that is the list of ReportDataSource type to add collection of DataSources to it. You can add DataSources through Web API.


The following code example illustrates how to add DataSource in Web API.

{% highlight c# %}

public class ReportsController : ApiController, IReportController
{
    /// <summary>
    /// Report loaded method that is triggered when report and sub report are loaded.
    /// </summary>
    /// <param name="reportOptions">The ReportViewer options.</param>
    public void OnReportLoaded(ReportViewerOptions reportOptions)
    {
        //Adds data sources to report model.
        reportOptions.ReportModel.DataSources.Clear();
        ProductList productList = new ProductList();
        reportOptions.ReportModel.DataSources.Add(new ReportDataSource { Name = "list", Value = productList.GetData() });            
    }
}

public class ProductList
{
    public string ProductName { get; set; }
    public string OrderId { get; set; }
    public double Price { get; set; }
    public string Category { get; set; }
    public string Ingredients { get; set; }
    public string ProductImage { get; set; }
    
    public IList GetData()
    {
        List<ProductList> dataList = new List<ProductList>();
        ProductList data = null;
        data = new ProductList() { ProductName = "Baked Chicken and Cheese", OrderId = "323B60", Price = 55, Category = "Non-Veg", Ingredients = "grilled chicken, corn and olives.", ProductImage = "" };
        dataList.Add(data);
        data = new ProductList() { ProductName = "Chicken Delite", OrderId = "323B61", Price = 100, Category = "Non-Veg", Ingredients = "cheese, chicken chunks, onions & pineapple chunks.", ProductImage = "" };
        dataList.Add(data);
        data = new ProductList() { ProductName = "Chicken Tikka", OrderId = "323B62", Price = 64, Category = "Non-Veg", Ingredients = "onions, grilled chicken, chicken salami & tomatoes.", ProductImage = "" };
        dataList.Add(data);
        return dataList;
    }
}
{% endhighlight %}

## DataSource Credentials

The DataSource credentials can be given at Web API Controller to connect data source from SQL server.

{% highlight c# %}
 // Method will be called to initialize the report information to load the report for processing.
public void OnInitReportOptions(ReportViewerOptions reportOptions)
{
   //Adds Database Credentials here.   
    reportOptions.ReportModel.DataSourceCredentials.Add(new DataSourceCredentials("AdventureWorks", "ssrs1", "RDLReport1"));
}
{% endhighlight %}



