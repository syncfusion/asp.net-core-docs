---
layout: post
title: Trendlines | Chart  | ASP.NET Core | Syncfusion
description: What are the different types of trendlines available in chart.
platform: aspnet-core
control: Chart
documentation: ug
---

# Trendlines

Chart can generate trendlines for Cartesian type series such as line, column, scatter, area, candle, HiLo, etc., except bar type series. You can add more than one trendline object to the **Trendlines** option.

{% highlight cshtml %}

<ej-chart id="chartContainer">
// ...
<e-chart-series>
    <e-series>
        <e-trend-lines>
            <e-trend-line visibility="Visible"></e-trend-line>
        </e-trend-lines>
    </e-series>
</e-chart-series>
// ...
</ej-chart>

{% endhighlight %}

![](Trendlines_images/Trendlines_img1.png)

## Customize the trendline styles

A trendline can be customized by using the properties such as **Fill**, **Width**, **DashArray**, and **Opacity**. The default type of trendline is **Linear**.

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
    <e-chart-series>
        <e-series>
            <e-trend-lines>
                <e-trend-line fill="#99CCFF" width="3" opacity="1" dash-array="2,3"></e-trend-line>
            </e-trend-lines>
        </e-series>
    </e-chart-series>
    // ...
</ej-chart>

{% endhighlight %}

![](Trendlines_images/Trendlines_img2.png)


## Types of trendline

Chart supports the following types of Trendline:

* Linear
* Exponential
* Logarithmic
* Power 
* Polynomial
* MovingAverage

### Linear

To render linear trendline, set the type to **Linear**. 

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
    <e-chart-series>
        <e-series>
            <e-trend-lines>
                <e-trend-line type="Linear"></e-trend-line>
            </e-trend-lines>
        </e-series>
    </e-chart-series>
    // ...
</ej-chart>

{% endhighlight %}

![](Trendlines_images/Trendlines_img3.png)

### Exponential

Exponential trendline can be rendered by setting the type to **Exponential**. 

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
    <e-chart-series>
        <e-series>
            <e-trend-lines>
                <e-trend-line type="Exponential"></e-trend-line>
            </e-trend-lines>
        </e-series>
    </e-chart-series>
    // ...
</ej-chart>

{% endhighlight %}

![](Trendlines_images/Trendlines_img4.png)

### Logarithmic

Logarithmic trendline can be rendered by setting the type to **Logarithmic**.

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
    <e-chart-series>
        <e-series>
            <e-trend-lines>
                <e-trend-line type="Logarithmic"></e-trend-line>
            </e-trend-lines>
        </e-series>
    </e-chart-series>
    // ...
</ej-chart>

{% endhighlight %}

![](Trendlines_images/Trendlines_img5.png)


### Power

Power trendline can be rendered by setting the type to **Power**. 

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
    <e-chart-series>
        <e-series>
            <e-trend-lines>
                <e-trend-line type="Power"></e-trend-line>
            </e-trend-lines>
        </e-series>
    </e-chart-series>
    // ...
</ej-chart>

{% endhighlight %}

![](Trendlines_images/Trendlines_img6.png)


### Polynomial

Polynomial trendline can be rendered by setting the type to **Polynomial**. You can change the polynomial order by using the **PolynomialOrder** property of the trendlines. It ranges from 2 to 6.

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
    <e-chart-series>
        <e-series>
            <e-trend-lines>
                <e-trend-line type="Polynomial"></e-trend-line>
            </e-trend-lines>
        </e-series>
    </e-chart-series>
    // ...
</ej-chart>

{% endhighlight %}

![](Trendlines_images/Trendlines_img7.png)


### MovingAverage

Moving average trendline can be rendered by setting the type to **MovingAverage**.

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
    <e-chart-series>
        <e-series>
            <e-trend-lines>
                <e-trend-line type="MovingAverage"></e-trend-line>
            </e-trend-lines>
        </e-series>
    </e-chart-series>
    // ...
</ej-chart>

{% endhighlight %}

![](Trendlines_images/Trendlines_img8.png)


## Forecasting

**Trendline forecasting** is the prediction of future/past situations. **Forecasting** can be classified as the following two types:

  * Forward Forecasting
  * Backward Forecasting

### Forward forecasting

The value set for **ForwardForecast** is used to determine the distance moving towards the future trend.

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
    <e-chart-series>
        <e-series>
            <e-trend-lines>
                <e-trend-line forward-forecast="5"></e-trend-line>
            </e-trend-lines>
        </e-series>
    </e-chart-series>
    // ...
</ej-chart>

{% endhighlight %}

![](Trendlines_images/Trendlines_img9.png)


### Backward forecasting

The value set for the **BackwardForecast** is used to determine the past trends.

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
    <e-chart-series>
        <e-series>
            <e-trend-lines>
                <e-trend-line backward-forecast="5"></e-trend-line>
            </e-trend-lines>
        </e-series>
    </e-chart-series>
    // ...
</ej-chart>

{% endhighlight %}

![](Trendlines_images/Trendlines_img10.png)


## Trendlines legend

To display the legend item for trendline, use the **Name** property. You can interact with the trendline legends similar to the series legends, i.e. show/hide trendlines on legend click.  

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
    <e-chart-series>
        <e-series>
            <e-trend-lines>
                <e-trend-line name="Linear"></e-trend-line>
            </e-trend-lines>
        </e-series>
    </e-chart-series>
    // ...
</ej-chart>

{% endhighlight %}

![](Trendlines_images/Trendlines_img11.png)