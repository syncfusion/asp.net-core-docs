---
layout: post
title: Markers and data labels in Essential ASP.NET Core Chart
description: Learn how to add markers and data point labels to a Chart series.
platform: aspnet-core
control: Chart
documentation: ug
---

# Data Markers

Data markers are used to provide information about the data point to the user. You can add shapes and labels to adorn the data points.

## Add Shapes

You can add shapes to any chart types but they are often used with line, area, and spline series to indicate each data point. It is highlighted when you hover the mouse on the shape.

Shapes can be added to the chart by enabling the **Visible** option of the **Marker** property. There are different shapes can be added to the chart by using the **Shape** option such as rectangle, circle, diamond etc.

The following code example explains how to add shapes and enable series marker,

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
    <e-chart-series>
        <e-series>
            <e-marker visible="true" shape="Diamond"></e-marker>
        </e-series>
        <e-series>
            <e-marker visible="true" shape="Triangle"></e-marker>
        </e-series>
        <e-series>
            <e-marker visible="true" shape="Hexagon"></e-marker>
        </e-series>
    </e-chart-series>
    // ...
</ej-chart>

{% endhighlight %}

![](Data-Markers_images/Data-Markers_img1.png)


## Add image to marker

Apart from the shapes, you can also add images to mark the data point by using the **ImageUrl** option.

The following code example illustrates this,

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
    <e-chart-series>
        <e-series>
            <e-marker visible="true" shape="Image" image-url="sun_annotation.png">
                <e-Size height="20" width="20"></e-Size>
            </e-marker>
        </e-series>
    </e-chart-series>
    // ...
</ej-chart>

{% endhighlight %}

![](Data-Markers_images/Data-Markers_img2.png)


## Add labels

Data label can be added to a chart series by enabling the **Visible** property in the **DataLabel** option. The labels appear at the top of the data point, by default.

The following code example illustrates how to enable data label and set its horizontal and vertical texts alignment. 

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
    <e-chart-series>
        <e-series>
            <e-marker><e-data-label visible="true" horizontal-text-alignment="Center" vertical-text-alignment="Far"></e-data-label>
            </e-marker>
        </e-series>
    </e-chart-series>
    // ...
</ej-chart>

{% endhighlight %}

![](Data-Markers_images/Data-Markers_img3.png)

Label content can be formatted by using the **template** option. Inside the template, you can add the placeholder text *"point.x"* and *"point.y"* to display the x & y values of corresponding data points.

You can adorn the labels with background shapes by setting *Shape* option.

The following code example illustrates how to add background shapes and set template to data label.

{% highlight cshtml %}

<div id="template">
     <div id="left">
	<img src="../images/chart/icon_investments.png"/>
     </div>
     <div id="right">
          <div id="point">#point.y#%</div>
     </div>
</div>

<ej-chart id="chartContainer">
// ...
<e-chart-series>
    <e-series>
        <e-marker><e-data-label visible="true" template="template"></e-data-label>
        </e-marker>
    </e-series>
    <e-series>
        <e-marker>
            <e-data-label visible="true" shape="Rectangle"><e-border width="1" color="red"></e-border></e-data-label>
        </e-marker>
    </e-series>
    <e-series>
        <e-marker>
            <e-data-label visible="true"></e-data-label>
        </e-marker>
    </e-series>
</e-chart-series>
// ...
</ej-chart>

{% endhighlight %}

![](Data-Markers_images/Data-Markers_img4.png)

The appearance of the labels can be customized by using the **Font** and **Offset** options. The Offset option is used to move the labels vertically. Also, labels can be rotated by using the **Rotate** option.

The following code example illustrates how to rotate data label text and customize the font.

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
    <e-chart-series>
        <e-series>
            <e-marker><e-data-label visible="true" angle="300" offset="15"><e-font color="Black" font-size="13px"></e-font></e-data-label>
            </e-marker>
        </e-series>
    </e-chart-series>
    // ...
</ej-chart>

{% endhighlight %}

![](Data-Markers_images/Data-Markers_img5.png)


You can position the label at top, center, or bottom position of the segment by using the **TextPosition** option for the chart types such as column, bar, stacked bar, stacked column, 100% stacked bar, 100% stacked column, Candle, and OHLC.

The following code example illustrates how to set TextPosition to display data label in the middle of the column rectangle.

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
    <e-chart-series>
        <e-series>
            <e-marker><e-data-label visible="true" text-position="Middle"></e-data-label>
            </e-marker>
        </e-series>
    </e-chart-series>
    // ...
</ej-chart>

{% endhighlight %}

![](Data-Markers_images/Data-Markers_img6.png)

The label can be positioned inside or outside the perimeter of the series by using the **LabelPosition** option for the chart types such as Pie and Doughnut.

The following code example illustrates how to set the LabelPosition.

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
    <e-chart-series>
        <e-series type="Doughnut" label-position="Outside">
            <e-points>
                <e-point x="India" y="24" text="India 24%"></e-point>
                <e-point x="Japan" y="25" text="Japan 25%"></e-point>
                <e-point x="Australia" y="20" text="Australia 20%"></e-point>
                <e-point x="USA" y="35" text="USA 35%"></e-point>
                <e-point x="China" y="23" text="China 23%"></e-point>
                <e-point x="Germany" y="27" text="Germany 27%"></e-point>
                <e-point x="France" y="22" text="France 22%"></e-point>
           </e-points>
           <e-marker><e-data-label visible="true" shape="Rectangle"><e-font color="white"></e-font></e-data-label></e-marker>
        </e-series>
    </e-chart-series>
    // ...
</ej-chart>

{% endhighlight %} 

![](Data-Markers_images/Data-Markers_img7.png)


The following screenshot illustrates the labels when the LabelPosition is set to **Inside**.

![](/js/Chart/Data-Markers_images/Data-Markers_img8.png)


The following screenshot illustrates the labels when the LabelPosition is set as **OutsideExtended**.

![](Data-Markers_images/Data-Markers_img9.png)


The label can be wrapped for pie, doughnut, funnel, and pyramid series by setting the **enableWrap** property. 

{% highlight javascript %} 

<ej-chart id="chartContainer">
    // ...
    <e-chart-series>
        <e-series>            
           <e-marker><e-data-label visible="true" enable-wrap="true" maximum-label-width="32"></e-data-label></e-marker>
        </e-series>
    </e-chart-series>
    // ...
</ej-chart>

{% endhighlight %} 

![](Data-Markers_images/Data-Markers_img13.png)


## Contrast color for the data label

 
To change the contrast color for the data label, set the **EnableContrastColor** to **true** in the **dataLabel** property of the chart series.

When you enable this property, the data label text will be rendered in contrast color based on the segment on which it is placed.

If you place the data label inside the data points segment, that particular point's color will be taken. Else the chart area or chart background color will be considered for deriving the contrast color.
 
{% highlight javascript %} 

<ej-chart id="chartContainer">
    // ...
    <e-chart-series>
        <e-series>            
           <e-marker><e-data-label visible="true" enable-contrast-color="true"></e-data-label></e-marker>
        </e-series>
    </e-chart-series>
    // ...
</ej-chart>

{% endhighlight %} 


## Binding label from the datasource

Bind the text value to the data label from the datasource, and then map the text value field with the [`TextMappingName`](../api/ejchart#members:commonseriesoptions-marker-datalabel-textmappingname) property.


{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
    <e-chart-series>
        <e-series type="Column" load="onChartLoad"> 
            //Mapping the text name 
            <e-marker><e-data-label visible="true" text-mapping-name="text"></e-data-label></e-marker>           
        </e-series>
    </e-chart-series>
    // ...
</ej-chart>    

{% endhighlight %}

{% highlight js %}

var chartData = [
          { month: 'Jan', sales: 35, text: 'January' },
          { month: 'Feb', sales: 28, text: 'February' }
          //..
];
          
function onChartLoad(sender) {
    sender.model.series[0].dataSource = chartData;
    sender.model.series[0].xName = "month";
    sender.model.series[0].yName = "sales";
}
   
{% endhighlight %}

## Binding fill color to the points from the datasource

Bind the color value to the points from the datasource, and then map the color value field to the [`PointColorMappingName`](../api/ejchart#members:commonseriesoptions-pointcolormappingname) property.


{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
    <e-chart-series>
        <e-series type="Column" load="onChartLoad" point-color-mapping-name="color">            
        </e-series>
    </e-chart-series>
    // ...
</ej-chart>    

{% endhighlight %}

{% highlight js %}

var chartData = [
          { month: 'Jan', sales: 35, color: 'red' },
          { month: 'Feb', sales: 28: color: 'blue' }
          //..
];
          
function onChartLoad(sender) {
    sender.model.series[0].dataSource = chartData;
    sender.model.series[0].xName = "month";
    sender.model.series[0].yName = "sales";
}
   
{% endhighlight %}

## Connect Line

This feature is used to connect label and data point by using a line. It can be enabled only for pie, doughnut, pyramid and funnel chart types. **ConnectorLine** can be set as *Bezier* or *Line* by using the **Type** option.

The following code example illustrates this,

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
    <e-chart-series>
        <e-series label-position="OutsideExtended" type="Doughnut">
            <e-marker>
                <e-data-label>
                    <e-connector-line color="black" type="Bezier"></e-connector-line>
                </e-data-label>
            </e-marker>
        </e-series>
    </e-chart-series>
    // ...
</ej-chart>

{% endhighlight %}

![](Data-Markers_images/Data-Markers_img11.png)


## Smart labels

Overlapping of the labels can be avoided by enabling the **EnableSmartLabels** property. The default value is true for Accumulation type series and false for other series types.

The following code example illustrates how to enable smart labels,

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
    <e-chart-series>
        <e-series enable-smart-labels="true" start-angle="145" name="Expenses" type="Pie">
            <e-marker>
                <e-data-label>
                    <e-connector-line color="black" type="Bezier" height="60"></e-connector-line>
                    <e-font font-size="14px"></e-font>
                </e-data-label>
            </e-marker>
        </e-series>
    </e-chart-series>
    // ...
</ej-chart>

{% endhighlight %}

![](Data-Markers_images/Data-Markers_img12.png)