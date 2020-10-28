---
layout: post
title: Getting Started | ASP.NET Core | Syncfusion
description: Getting started walk through to create your first Heat map.
platform: aspnet-core
control: HeatMap
documentation: ug
---

# Getting Started

## Initialize the HeatMap

Initialize `HeatMap` to the Html Page as shown in the following code sample.

{% highlight razor %}

@*Initializes heat map control*@




     <ej-heatmap is-responsive="true" id="heatmap" width="830" items-source="ViewBag.itemsource" items-mapping="ViewBag.itemsmapping" legend-collection="ViewBag.legendcollection">
     </ej:heatMap>

    
{% endhighlight %}
 

## Prepare data

Populate product information in a collection

{% highlight c# %}

[Serializable]

     public class SampleTableData
      {
            private string productName;
            [JsonProperty("ProductName")]
            [DefaultValue("")]
            public string ProductName
            {
                get { return productName; }
                set { productName = value; }
            }

            private double y2010;
            [JsonProperty("Y2010")]
            [DefaultValue("")]
            public double Y2010
            {
                get { return y2010; }
                set { y2010 = value; }
            }

            private double y2011;
            [JsonProperty("Y2011")]
            [DefaultValue("")]
            public double Y2011
            {
                get { return y2011; }
                set { y2011 = value; }
            }

            private double y2012;
            [JsonProperty("Y2012")]
            [DefaultValue("")]
            public double Y2012
            {
                get { return y2012; }
                set { y2012 = value; }
            }

            private double y2013;
            [JsonProperty("Y2013")]
            [DefaultValue("")]
            public double Y2013
            {
                get { return y2013; }
                set { y2013 = value; }
            }

            private double y2014;
            [JsonProperty("Y2014")]
            [DefaultValue("")]
            public double Y2014
            {
                get { return y2014; }
                set { y2014 = value; }
            }

            private double y2015;
            [JsonProperty("Y2015")]
            [DefaultValue("")]
            public double Y2015
            {
                get { return y2015; }
                set { y2015 = value; }
            }
  }
 
{% endhighlight %}

## Populate data

Populate product information in a collection.

{% highlight c# %} 
       
     public void CreateTableHeatmap()
     {
     List<string> collection = new List<string>();
     collection.Add("heatmapLegend");
     ViewBag.legendcollection = collection;
     ViewBag.itemsource = GetTableSource();
     return View();
     }

       public Collection GetTableSource()
       {
            Collection collection = new Collection();
            Random random = new Random();
            string[] rows = { "Vegie-spread", "Tofuaa", "Alice Mutton", "Konbu", "Fløtemysost", "Perth Pasties", "Boston Crab Meat", "Raclette Courdavault" };
            for (int i = 0; i < 8; i++)
            {
                collection.Add(new SampleTableData()
                {
                    ProductName = rows[i],
                    Y2010 = random.Next(0, 100),
                    Y2011 = random.Next(0, 100),
                    Y2012 = random.Next(0, 100),
                    Y2013 = random.Next(0, 100),
                    Y2014 = random.Next(0, 100),
                    Y2015 = random.Next(0, 100)
                });
            }
            return collection;
         }

{% endhighlight %}

## Map data into HeatMap

Now data is ready, next we need to configure data source and map rows and columns to visualize.

* Prepare `ItemsMapping` add it in resource.

{% highlight c# %}

     TableMapping TableMapping = new TableMapping();
     TableMapping.HeaderMapping = new HeaderMapping() { PropertyName = "ProductName", DisplayName = "Product Name", ColumnStyle = new ColumnStyle() { Width = 140, TextAlign = HeatMapTextAlign.Right } };
     TableMapping.ColumnMapping.Add(new HeaderMapping() { PropertyName = "Y2010", DisplayName = "Y2010" });
     TableMapping.ColumnMapping.Add(new HeaderMapping() { PropertyName = "Y2011", DisplayName = "Y2011" });
     TableMapping.ColumnMapping.Add(new HeaderMapping() { PropertyName = "Y2012", DisplayName = "Y2012" });
     TableMapping.ColumnMapping.Add(new HeaderMapping() { PropertyName = "Y2013", DisplayName = "Y2013" });
     TableMapping.ColumnMapping.Add(new HeaderMapping() { PropertyName = "Y2014", DisplayName = "Y2014" });
     TableMapping.ColumnMapping.Add(new HeaderMapping() { PropertyName = "Y2015", DisplayName = "Y2015" });
     ViewBag.itemsmapping = TableMapping;

{% endhighlight %}

 
![](Getting-Started_images/Getting-Started_img1.png)
 
##Color Mapping
  
Next we can configure color range for these values using color mapping
 
* Configure items mapping based on items source.
 
{% highlight razor %}  
        
    <ej-heatmap is-responsive="true" id="heatmap" width="830" items-source="ViewBag.itemsource" items-mapping="ViewBag.itemsmapping" legend-collection="ViewBag.legendcollection">
    <e-colorMappingCollection>
    <e-color-mapping value="0" color="#8ec8f8">
    <e-label text="0"></e-label>
    </e-color-mapping>
    <e-color-mapping value="100" color="#0d47a1">
    <e-label text="100"></e-label>
    </e-color-mapping>
    </e-colorMappingCollection>
    </ej-heatmap>
            
{% endhighlight %} 
 

* This will show the grid data with color based on the range given.
 
![](Getting-Started_images/Getting-Started_img2.png)
 
 
## Legend
 
A legend control is used to represent range value in a gradient, create a legend with the same color mapping as shown below.
  
{% highlight razor %}
   
@*Initializes heat map control*@
      
        <ej-heatmaplegend is-responsive="true" id="heatmapLegend" width="75%" height="50px" legend-mode="Gradient" orientation="Horizontal">
            <e-colorMappingCollection>
                <e-color-mapping value="0" color="#8ec8f8">
                    <e-label text="0"></e-label>
                </e-color-mapping>
                <e-color-mapping value="100" color="#0d47a1">
                    <e-label text="100"></e-label>
                </e-color-mapping>
            </e-colorMappingCollection>
        </ej-heatmaplegend>

    
{% endhighlight %}

Final script file looks like this.

{% tabs %}
{% highlight razor %}

    <div style="width: 950px; margin: 0 auto; text-align: center;">
        <ej-heatmap is-responsive="true" id="heatmap" width="830" items-source="ViewBag.itemsource" items-mapping="ViewBag.itemsmapping" legend-collection="ViewBag.legendcollection">
            <e-colorMappingCollection>
                <e-color-mapping value="0" color="#8ec8f8">
                    <e-label text="0"></e-label>
                </e-color-mapping>
                <e-color-mapping value="100" color="#0d47a1">
                    <e-label text="100"></e-label>
                </e-color-mapping>
            </e-colorMappingCollection>
        </ej-heatmap>
    <div style="height: 15px; width: 100%;"></div>
        <ej-heatmaplegend is-responsive="true" id="heatmapLegend" width="75%" height="50px" legend-mode="Gradient" orientation="Horizontal">
            <e-colorMappingCollection>
                <e-color-mapping value="0" color="#8ec8f8">
                    <e-label text="0"></e-label>
                </e-color-mapping>
                <e-color-mapping value="100" color="#0d47a1">
                    <e-label text="100"></e-label>
                </e-color-mapping>
            </e-colorMappingCollection>
        </ej-heatmaplegend>
    </div>

    
        
{% endhighlight %}

{% highlight c# %}

public class TableMapBinding : System.Web.UI.Page
{

    protected void Page_Load(object sender, EventArgs e)
    {
        if (!IsPostBack)
        {
            
            CellMapping CellMapping = new CellMapping();
            CellMapping.Column = new PropertyMapping() { PropertyName = "ProductName", DisplayName = "Product Name" };
            CellMapping.Row = new PropertyMapping() { PropertyName = "Year", DisplayName = "Year" };
            CellMapping.Value = new PropertyMapping() { PropertyName = "Value" };
            Collection columnMapping = new Collection();
            columnMapping.Add(new HeaderMapping() { PropertyName = "Vegie-spread", DisplayName = "Vegie-spread" });
            columnMapping.Add(new HeaderMapping() { PropertyName = "Tofuaa", DisplayName = "Tofuaa" });
            columnMapping.Add(new HeaderMapping() { PropertyName = "Alice Mutton", DisplayName = "Alice Mutton" });
            columnMapping.Add(new HeaderMapping() { PropertyName = "Konbu", DisplayName = "Konbu" });
            columnMapping.Add(new HeaderMapping() { PropertyName = "Fløtemysost", DisplayName = "Fløtemysost" });
            columnMapping.Add(new HeaderMapping() { PropertyName = "Perth Pasties", DisplayName = "Perth Pasties" });
            CellMapping.ColumnMapping = columnMapping;
            HeaderMapping headerMapping = new HeaderMapping() { PropertyName = "Year", DisplayName = "Year", ColumnStyle = new ColumnStyle() { Width = 105, TextAlign = HeatMapTextAlign.Right } };
            CellMapping.HeaderMapping = headerMapping;
            ViewBag.itemsource = GetCellSource();
            ViewBag.itemsmapping = CellMapping;
            List<string> collection = new List<string>();
            collection.Add("heatmapLegend");
            ViewBag.legendcollection = collection;
            return View();

        }
    }

    public Collection GetCellSource()
    {
        Collection collection = new Collection();
            string[] name = { "Vegie-spread", "Tofuaa", "Alice Mutton", "Konbu", "Fløtemysost", "Perth Pasties" };
            Random random = new Random();

            foreach (string item in name)
            {
                for (int i = 0; i < 6; i++)
                {
                    double value = random.Next(0, random.Next(0, 100));
                    collection.Add(new SampleCellData() { ProductName = item, Year = "Y" + (2011 + i), Value = value });
                }
            }
            return collection;
         }
     }

[Serializable]

        public class SampleCellData
        {
            private string productName;

            [JsonProperty("ProductName")]
            [DefaultValue("")]
            public string ProductName
            {
                get { return productName; }
                set { productName = value; }
            }

            private string year;
            [JsonProperty("Year")]
            [DefaultValue("")]
            public string Year
            {
                get { return year; }
                set { year = value; }
            }

            private Double valuex;
            [JsonProperty("Value")]
            [DefaultValue("")]
            public Double Value
            {
                get { return valuex; }
                set { valuex = value; }
            }
         }

{% endhighlight %}
{% endtabs %}

![](Getting-Started_images/Getting-Started_img3.png)