---
layout: post
title: DataBinding of Syncfusion treeMap control
description: Learn how to bind the data in treeMap control
platform: aspnet-core
control: TreeMap
documentation: ug
---

# DataBinding

TreeMap control supports Data Binding and it can be achieved using `DataSource` property.

The `DataSource` property accepts the collection values as input. For example, you can provide the list of objects as input. The following code illustrates you on how to bind a flat collection as datasource for TreeMap.

{% tabs %}
 
{% highlight CSHTML %}
	
<div style="height:400px;width:700px;">

<ej-tree-map id="treemap" datasource="ViewBag.datasource" weight-value-path="Population" color-value-path="Population">
</ej-tree-map>

</div>

{% endhighlight %}

{% highlight C# %}

public IActionResult TreeMap()
{           
	ViewBag.datasource =TreeMapPopulationData.GetData();
	return View();
}

public class TreeMapPopulationData

{
	public string Continent { get; set; }

	public string Region { get; set; }

	public double Growth { get; set; }

	public long Population { get; set; }

	public static List<TreeMapPopulationData> GetData()

	{

		List<TreeMapPopulationData> population = new List<TreeMapPopulationData>();

		population.Add(new TreeMapPopulationData() { Continent = "Asia", Region = "Southern Asia", Growth = 1.32, Population = 1749046000});

		population.Add(new TreeMapPopulationData() { Continent = "Asia", Region = "Eastern Asia", Growth = 0.57, Population = 1620807000});

		population.Add(new TreeMapPopulationData() { Continent = "Asia", Region = "South-Eastern Asia", Growth = 1.20, Population = 618793000});

		population.Add(new TreeMapPopulationData() { Continent = "Asia", Region = "Western Asia", Growth = 1.98, Population = 245707000});

		population.Add(new TreeMapPopulationData() { Continent = "Asia", Region = "Central Asia", Growth = 1.43, Population = 64370000});

		population.Add(new TreeMapPopulationData() { Continent = "Europe", Region = "Europe", Growth = 0.10, Population = 742452000});

		population.Add(new TreeMapPopulationData() { Continent = "America", Region = "South America", Growth = 1.06, Population = 406740000});

		population.Add(new TreeMapPopulationData() { Continent = "America", Region = "Northern America", Growth = 0.85, Population = 355361000});

		population.Add(new TreeMapPopulationData() { Continent = "America", Region = "Central America", Growth = 1.40, Population = 167387000});

		population.Add(new TreeMapPopulationData() { Continent = "Africa", Region = "Eastern Africa", Growth = 2.89, Population = 373202000});

		population.Add(new TreeMapPopulationData() { Continent = "Africa", Region = "Western Africa", Growth = 2.78, Population = 331255000});

		population.Add(new TreeMapPopulationData() { Continent = "Africa", Region = "Northern Africa", Growth = 1.70, Population = 210002000});

		population.Add(new TreeMapPopulationData() { Continent = "Africa", Region = "Middle Africa", Growth = 2.79, Population = 135750000});

		population.Add(new TreeMapPopulationData() { Continent = "Africa", Region = "Southern Africa", Growth = 0.91, Population = 60425000});

		return population;

	}

}

{% endhighlight %}

{% endtabs %}