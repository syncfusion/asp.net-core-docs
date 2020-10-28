---
layout: post
title: Chart legend| Chart  | ASP.NET CORE | Syncfusion
description: How to cutomize the legend in Essential JavaScript Chart.
platform: aspnet-core
control: Chart
documentation: ug
---

# Legend

The legend contains the list of chart series and trendlines that appear in a chart. 

## Legend visibility

By default, the legend is enabled in the chart. You can enable or disable this by using the **Visible** option of the **Legend**.

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
   <e-legend visible="true"></e-legend>
    // ...
</ej-chart>

{% endhighlight %}

![](Legend_images/Legend_img1.png)

## Legend title

To add title to the legend, specify the **Legend.Title.Text** option.

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
   <e-legend><e-title text="Countries"></e-title></e-legend>
    // ...
</ej-chart>

{% endhighlight %}

![](Legend_images/Legend_img2.png)


## Position and align the legend

By using the **Position** option, you can position the legend at left, right, top, or bottom of the chart. The legend is positioned at the **Bottom** of the chart, by default.

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
   <e-legend position="Top"></e-legend>
    // ...
</ej-chart>

{% endhighlight %}

![](Legend_images/Legend_img3.png)

**Legend alignment**

You can align the legend to center, far, or near based on its position by using the **Alignment** option.

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
   <e-legend position="Top" alignment="Far"></e-legend>
    // ...
</ej-chart>

{% endhighlight %}

![](Legend_images/Legend_img4.png)

## Arrange legend items in the rows and columns

You can arrange the legend items horizontally and vertically by using the **RowCount** and **ColumnCount** options of the legend.

* When only the RowCount is specified, the legend items are arranged according to the row count, and number of columns may vary based on the number of legend items.

* When only the ColumnCount is specified, the legend items are arranged according to the column count, and number of rows may vary based on the number of legend items.

* When both options are specified, then the preference will be given for the one which has higher. For example, when the RowCount is 4 and ColumnCount is 3, legend items are arranged in 4 rows.

* When both the options are specified and have the same value, the preference will be given to the ColumnCount when it is positioned at the top/bottom position. The preference will be given to the RowCount when it is positioned at the left/right position.
 

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
   <e-legend row-count="4" column-count="4"></e-legend>
    // ...
</ej-chart>

{% endhighlight %}

![](Legend_images/Legend_img5.png)

## Customization

### Legend shape

To change the legend icon shape, specify the shape in the **Shape** property of the legend. When you want the legend icon to display the prototype of the series, set the **SeriesType** to shape.

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
   <e-legend shape="SeriesType"></e-legend>
    // ...
</ej-chart>

{% endhighlight %}

![](Legend_images/Legend_img6.png)

### Legend items size and border

You can change the size of the legend items by using the **ItemStyle.Width** and **ItemStyle.Height** options. To change the legend item border, use **Border** option of the legend's **ItemStyle** option.

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
   <e-legend><e-item-style width="13" height="13"></e-item-style><e-border width="1" color="#FF0000"></e-border></e-legend>
    // ...
</ej-chart>

{% endhighlight %}

![](Legend_images/Legend_img7.png)

### Legend size

By default, legend takes 20% of the **Height** horizontally when it is placed on the top or bottom position and 20% of the **Width** vertically while placing on the left or right position of the chart. You can change this default legend size by using the **Size** option of the legend.

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
   <e-legend><e-size height="100" width="550"></e-size></e-legend>
    // ...
</ej-chart>

{% endhighlight %}

![](Legend_images/Legend_img8.png)

### Legend item padding

You can control the spacing between the legend items by using the **ItemPadding** option of the legend.  The default value is 10. 

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
   <e-legend item-padding="15"></e-legend>
    // ...
</ej-chart>

{% endhighlight %}

![](Legend_images/Legend_img9.png)

### Legend border

You can customize the legend border by using the **Border** option in the legend. 

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
   <e-legend><e-border color="#FFC342" width="2"></e-border></e-legend>
    // ...
</ej-chart>

{% endhighlight %}

![](Legend_images/Legend_img10.png)

### Scrollbar for legend

You can enable or disable the legend scrollbar by using the **EnableScrollbar** option of the legend. When you disable the scrollbar option, the legend does not consider the default size, and chart will be rendered in the remaining space. If you have specified the **size** to the legend with the scrollbar disabled, then the legends beyond this limit will get clipped. The default value of **EnableScrollbar** option is true.  

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
   <e-legend enable-scrollbar="true"><e-size height="80" width="430"></e-size></e-legend>
    // ...
</ej-chart>

{% endhighlight %}

![](Legend_images/Legend_img11.png)

### Customize the legend text

To customize the text and title of the legend item, use the **Legend.Font** and **Legend.Title** options. You can change the legend title alignment by using the **TextAlignment** option of the legend title.

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
    <e-legend>
        <e-font font-family="Segoe UI" font-style="Normal" font-weight="Bold" font-size="15px"></e-font>
        <e-title text-alignment="Center"></e-title>
        <e-font font-family="Segoe UI" font-style="Italic" font-weight="Bold" font-size="12px"></e-font>
    </e-legend>
    // ...
</ej-chart>

{% endhighlight %}

![](Legend_images/Legend_img12.png)

### Legend items text overflow

**Trim**

You can trim the text of the legend item when its width exceeds the **Legend.TextWidth** by specifying **TextOverflow** to **Trim**. The original text will be displayed on mouse hover.

{% highlight cshtml %}

<ej-chart id="chartContainer">
// ...
<e-legend visible="true" text-overflow="Trim" text-width="34">        
</e-legend>
// ...
</ej-chart>

{% endhighlight %}

![](Legend_images/Legend_img13.png)

**Wrap**

By specifying **TextOverflow** to **Wrap**, you can wrap the legend text by word.

![](Legend_images/Legend_img14.png)

**WrapAndTrim**

You can wrap and trim the legend text by specifying **TextOverflow** as **WrapAndTrim**. The original text will be displayed on mouse hover.

![](Legend_images/Legend_img15.png)


## Handle the legend item click

You can get the legend item details such as index, bounds, shape, and series by subscribing the **LegendItemClick** event on the chart. When the legend item is clicked, it triggers the event and returns the Legend information. 

{% highlight cshtml %}

<ej-chart id="chartContainer" legend-item-click="onLegendClicked">
    // ...
    <e-legend visible="true">        
    </e-legend>
    // ...
</ej-chart>

function onLegendClicked(sender) {
//Get legend item details on legend item click.
var legendItem = sender.data;
}

{% endhighlight %}

## Series selection on legend item click

You can select a specific series or point while clicking the corresponding legend item through disabling the **ToggleSeriesVisibility** option of the legend. The default value of **toggleSeriesVisibility** option is true. To customize the series selection, refer to the series selection.

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
    <e-legend toggle-series-visibility="false">        
    </e-legend>
    // ...
</ej-chart>
      
{% endhighlight %}

![](Legend_images/Legend_img16.png)


## Collapsing legend item

You can collapse the legend item of the specific series/point, which is displayed in the chart by setting the **VisibleOnLegend** to Hidden in the point or series.

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
    <e-chart-series>
        <e-series>
            <e-points>
                <e-point x="Albania" y="60.1"></e-point>
                <e-point x="New Zealand" y="82.8" visible-on-legend="Hidden"></e-point>
            </e-points>
            <e-empty-point-settings visible="true"></e-empty-point-settings>
        </e-series>
    </e-chart-series>
    <e-legend visible="true"></e-legend>
    // ...
</ej-chart>
      
{% endhighlight %}

![](Legend_images/Legend_img17.png)