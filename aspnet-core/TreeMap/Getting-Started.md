---
layout: post
title: Getting-Started
description: getting started
platform: aspnet-core
control: TreeMap
documentation: ug
---

# Getting Started

This section explains briefly about how to create a TreeMap in your application with ASP.NET Core .

## Configure a TreeMap

You can configure an ASP.NET Core TreeMap in simple steps. This manual provides instructions on how to configure TreeMap with grouping of populated datum based on population growth in population in each continent.  It also provides a walk-through on some of the customization feature available in TreeMap control.

![](Getting-Started_images/Getting-Started_img1.png)


## Create your TreeMap

In this tutorial, you will learn how to create a simple TreeMap. The following screen shot displays the output after completing this tutorial.

![](Getting-Started_images/Getting-Started_img4.png)

Simple TreeMap
{:.caption}

1. First, create a new ASP.NET core project; please refer [ASP.NET core 1.0-Getting Started](/aspnet-core/getting-started) documentation to create new project and add necessary DLL’s and script files.

## Add Data 

You can populate the TreeMap data inside the controller. For example, you can populate data of few countries from the following location.

~/Controller/TreeMapController.cs

{% highlight C# %}

	public class TreeMapPopulationData

	{

		public string Continent { get; set; }

		public string Region { get; set; }

		public double Growth { get; set; }

		public long Population { get; set; }

		public static List<TreeMapPopulationData> GetData()

		{

			List<TreeMapPopulationData> population = new List<TreeMapPopulationData>();

			population.Add(new TreeMapPopulationData() { 
				Continent = "Asia", Region = "Southern Asia", Growth = 1.32, Population = 1749046000
				});

			population.Add(new TreeMapPopulationData() { 
				Continent = "Asia", Region = "Eastern Asia", Growth = 0.57, Population = 1620807000
				});

			population.Add(new TreeMapPopulationData() {
				Continent = "Asia", Region = "South-Eastern Asia", Growth = 1.20, Population = 618793000
				});

			population.Add(new TreeMapPopulationData() { 
				Continent = "Asia", Region = "Western Asia", Growth = 1.98, Population = 245707000
				});

			population.Add(new TreeMapPopulationData() { 
				Continent = "Asia", Region = "Central Asia", Growth = 1.43, Population = 64370000
				});

			population.Add(new TreeMapPopulationData() { 
				Continent = "Europe", Region = "Europe", Growth = 0.10, Population = 742452000
				});

			population.Add(new TreeMapPopulationData() { 
				Continent = "America", Region = "South America", Growth = 1.06, Population = 406740000
				});

			population.Add(new TreeMapPopulationData() { 
				Continent = "America", Region = "Northern America", Growth = 0.85, Population = 355361000
				});

			population.Add(new TreeMapPopulationData() { 
				Continent = "America", Region = "Central America", Growth = 1.40, Population = 167387000
				});

			population.Add(new TreeMapPopulationData() { 
				Continent = "Africa", Region = "Eastern Africa", Growth = 2.89, Population = 373202000
				});

			population.Add(new TreeMapPopulationData() { 
				Continent = "Africa", Region = "Western Africa", Growth = 2.78, Population = 331255000
				});

			population.Add(new TreeMapPopulationData() { 
				Continent = "Africa", Region = "Northern Africa", Growth = 1.70, Population = 210002000
				});

			population.Add(new TreeMapPopulationData() {
				Continent = "Africa", Region = "Middle Africa", Growth = 2.79, Population = 135750000
				});

			population.Add(new TreeMapPopulationData() { 
				Continent = "Africa", Region = "Southern Africa", Growth = 0.91, Population = 60425000
				});

			return population;

		}

	}

{% endhighlight %}



 N> Population data is referred from [List of continents by population](http://en.wikipedia.org/wiki/List_of_continents_by_population)
 
## Initialize TreeMap

1. Create a &lt;div&gt; tag with a specific id and set the height and width to determine the TreeMap size to be rendered in “TreeMap.cshtml” file
   
{% highlight CSHTML %}

	<div style="width:700px; height:400px;"> 

	</div>            


{% endhighlight %}
  

2. Add the following code in “TreeMap.cshtml” file to create the TreeMap control in a View page.

{% highlight CSHTML %}
   
	<div style="width:700px; height:400px;"> 

		@{Html.EJ().TreeMap("treemap")                

		.Render();}

	</div>          


{% endhighlight %}
 

3. Add the TreeMap() action in “TreeMapController.cs” as illustrated in the following code sample.

{% highlight C# %}

	public IActionResult TreeMap()

	{

		ViewData["datasource"] = TreeMapPopulationData.GetData();

		return View();

	}

{% endhighlight %}
  

## Data Source

The `DataSource` property accepts the collection values as input. For example, you can provide the list of objects as input.

## Weight Value Path 

You can calculate the size of the object using `WeightValuePath` of TreeMap.

1. Populate the TreeMap by using the above properties.

{% highlight CSHTML %}

	@{

		var datasource = ViewData["datasource"];    

	}

	<div style="height:400px;width:700px;">

	@{Html.EJ().TreeMap("treemap")

			.DataSource(datasource)

			.WeightValuePath("Population")

	.Render();}

	</div>

{% endhighlight %}
  





2. Final TreeMap.cshtml file is illustrated in the following code sample.

{% highlight CSHTML %}

	@{

		var datasource = ViewData["datasource"];    

	}

	<div style="height:400px;width:700px;">

	@{Html.EJ().TreeMap("treemap")

			.DataSource(datasource)

			.WeightValuePath("Population") 

			.Render();}

		</div>   

	<ej-script-manager></ej-script-manager>

{% endhighlight %}
  

The following image displays a TreeMap with default properties using the above code. 

![](Getting-Started_images/Getting-Started_img2.png)



## GroupTreeMap Items using Levels

You can group TreeMap Items using levels in TreeMap.

### Group Path

You can use `GroupPath` property for every flat level of the TreeMap control. It is a path to a field on the source object that serves as the “Group” for the level specified. You can group the data based on the `GroupPath` in the TreeMap control. When the `GroupPath` is not specified, then the items are not grouped and the data is displayed in the order specified in the `DataSource`.

### Group Gap

You can use `GroupGap` property to separate the items from every flat level and to differentiate the levels mentioned in the TreeMap control.

The following code sample explains how to group TreeMap Items using ‘Levels’

{% highlight CSHTML %}

	@{Html.EJ().TreeMap("treemap")

		.DataSource(datasource)

		.WeightValuePath("Population")

		.Levels(level =>

		{

			level.GroupPath("Continent")

			  .GroupGap(5).Add();                            

		})   

	.Render();}

{% endhighlight %}


The following screenshot displays grouping of TreeMapItems using Levels.

![](Getting-Started_images/Getting-Started_img3.png)



## Customize TreeMap Appearance by Range

You can differentiate the nodes based on its value and color ranges using Range color. You can also define the color value range using From and To properties. 

### Color Value Path

The `ColorValuePath` of TreeMap is a path to a field on the source object. You can determine the color for the object using `ColorValuePath` of TreeMap.

The following code sample explains how to customize TreeMap Appearance by Range.

{% highlight CSHTML %}

	@{Html.EJ().TreeMap("treemap")

		.DataSource(datasource)

		.WeightValuePath("Population")                             

		.Levels(level =>

		{

			level.GroupPath("Continent")

			  .GroupGap(5).Add();                            

		})   

		.ColorValuePath("Growth")

		.TreeMapRangeColorMappings(cm => 

		{

			cm.To(1).From(0).Color("#DC562D").Add();
  			
			cm.To(1.5).From(1).Color("#FED124").Add();
  		
			cm.To(2).From(1.5).Color("#487FC1").Add();
    		
			cm.To(3).From(2).Color("#0E9F49").Add();

		})

	.Render();}   

{% endhighlight %}



The following screenshot displays customized TreeMap Appearance by Range

![](Getting-Started_images/Getting-Started_img4.png)

## Enable Tooltip

You can enable the tooltip by setting `ShowTooltip` property to ‘true’. By default, it takes the property of the bound object that is referred in the `WeightValuePath` and displays its content when the corresponding node is hovered. You can customize the template for tooltip using `TooltipTemplate` property.

### Leaf Item Settings

You can customize the Leaf level TreeMap items using `LeafItemSettings`. The Label and tooltip values take the property of bound object that is referred in the `LabelPath` when defined.

The following code sample displays how the tooltip is enabled.

{% highlight CSHTML %}

	@{Html.EJ().TreeMap("treemap")

		.DataSource(datasource)

		.WeightValuePath("Population")                             

		.Levels(level =>

		{

			level.GroupPath("Continent")

			.GroupGap(5).Add();                            

		})   

		.ColorValuePath("Growth")

		.TreeMapRangeColorMappings(cm => 

		{
  			
			cm.To(1).From(0).Color("#DC562D").Add();
  	
	  		cm.To(1.5).From(1).Color("#FED124").Add();  
  		
		  	cm.To(2).From(1.5).Color("#487FC1").Add();
  	
	  		cm.To(3).From(2).Color("#0E9F49").Add();

		})

		.ShowTooltip(true)

		.LeafItemsSetting(leaf =>

		{
   			
			leaf.LabelPath("Region");

		})

	.Render();}

{% endhighlight %}



The following screenshot displays the TreeMap when the Tooltip is enabled.

![](Getting-Started_images/Getting-Started_img5.png)

## Legend

You can set the color value of leaf nodes using TreeMap Legend. This legend is appropriate only for the TreeMap whose leaf nodes are colored using `RangeColorMapping`.

You can set ShowLegend property value to ‘_true_’ to make a Legend visible.

### Label for Legend

You can customize the labels of the legend item using `LegendLabel` property of `RangeColorMapping`. 

The following code sample displays how to add labels for legend in a TreeMap.

{% highlight CSHTML %}

	@{Html.EJ().TreeMap("treemap")

		.DataSource(datasource)

		.WeightValuePath("Population") 

		.Levels(level =>

		{

			level.GroupPath("Continent")

			  .GroupGap(5).Add();                            

		})   

		.ColorValuePath("Growth")

		.TreeMapRangeColorMappings(cm => 

		{
  		
			cm.To(1).From(0).Color("#DC562D").LegendLabel("0 - 1 % Growth").Add();
  	
	  		cm.To(1.5).From(1).Color("#FED124").LegendLabel("1 - 1.5 % Growth").Add();  
  	
	  		cm.To(2).From(1.5).Color("#487FC1").LegendLabel("1.5 - 2 % Growth").Add();
  	
	  		cm.To(3).From(2).Color("#0E9F49").LegendLabel("2 - 3 % Growth").Add();                   

		})

		.ShowTooltip(true)

		.LeafItemsSetting(leaf =>

		{
   			
			leaf.LabelPath("Region");

		})

		.ShowLegend(true)

	.Render();}



{% endhighlight %}



The following screenshot displays the TreeMap when Labels are enabled.

![](Getting-Started_images/Getting-Started_img6.png)

