---
layout: post
title: Data Binding | BulletGraph | Syncfusion
description: data binding
platform: aspnet-core
control: BulletGraph	
documentation: ug
---

# Data Binding

Bullet Graph supports binding JSON data from a remote server or data created in client-side. You can use the `e-fields` property to customize the data bound with Bullet Graph.

## Local Data

Data available in client-side (local data) can be bound with Bullet Graph using `e-fields` property. This property provides option to specify data source, fields representing progress measure bar value, comparative measure value and category value. 

{% highlight C# %}

public class BulletData

{

	public double BulletValue

	{ get; set; }

	public double ComparisonValue

	{ get; set; }

	public string Category

	{ get; set; }

}


List<BulletData> data = new List<BulletData>();

data.Add(new BulletData() { BulletValue=9.5, ComparisonValue=7.5, Category="2001"  });

data.Add(new BulletData() { BulletValue = 9.5, ComparisonValue = 5, Category = "2002" });

ViewBag.DataSource = data;
			
{% endhighlight %}

{% highlight CSHTML %}

  <ej-bullet-graph id="Bullets"  qualitative-range-size="60">
  <e-quantitative-scale-settings interval="1">
  <e-location x="50" y="20"></e-location>
  </e-quantitative-scale-settings>  
  <e-fields category-field="Category" comparative-measure-field="ComparisonValue" datasource=@ViewBag.DataSource feature-measure-field="BulletValue">
  </e-fields>        
  </ej-bullet-graph>

{% endhighlight %}

The following screenshot displays Bullet Graph with local data generated using JavaScript

![](Data-Binding_images/Data-Binding_img1.png)

Bullet Graph bounded to JSON data
{:.caption}

## Remote Data

Bullet Graph provides option to bind data from a remote server using ejDataManager as data source in fields property. A query object should also be passed to query property when using data manager as data source.

{% highlight cshtml %}

<ej-bullet-graph id="Bullets"  qualitative-range-size="60">
  <e-quantitative-scale-settings interval="10" maximum="45" minimum="5">
  <e-location x="50" y="20"></e-location>
  </e-quantitative-scale-settings>
  <e-qualitative-ranges>
               <e-qualitative-range range-end="25"></e-qualitative-range>
               <e-qualitative-range range-end="37"></e-qualitative-range>
               <e-qualitative-range range-end="45"></e-qualitative-range>
           </e-qualitative-ranges>  
<e-fields category-field="ProductID" comparative-measure-field="Quantity" 
feature-measure-field="UnitPrice"
query="ej.Query().from('Order_Details').take(3).where('UnitPrice', ej.FilterOperators.greaterThan, 18, false)
.where('UnitPrice', ej.FilterOperators.lessThanOrEqual, 40, false)
.where('Quantity', ej.FilterOperators.greaterThan, 5, false)
.where('Quantity', ej.FilterOperators.lessThanOrEqual, 45, false)" >
<e-datamanager url="http://mvc.syncfusion.com/Services/Northwnd.svc/"></e-datamanager>
</e-fields>        
</ej-bullet-graph>

{% endhighlight %}

The following screenshot displays a Bullet Graph bounded with data from a remote server

![](Data-Binding_images/Data-Binding_img2.png)

Bullet Graph bounded to data from server
{:.caption}
