---
layout: post
title: Chart Striplines| Chart  | ASP.NET CORE | Syncfusion
description: Learn how to add horizontal or vertical lines in Chart.                                                  
platform: aspnet-core
control: Chart
documentation: ug
---

# Striplines

Chart supports horizontal and vertical striplines. 

## Horizontal Stripline

You can create horizontal stripline by adding the **Stripline** in the vertical axis and setting **Visible** option to true. Striplines are rendered in the specified **Start** to **End** range, and you can add more than one stripline for an axis.


{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
    <e-primary-y-axis>
        <e-strip-lines><e-strip-line visible="true" start="30" end="40"></e-strip-line></e-strip-lines>
    </e-primary-y-axis>
    // ...
</ej-chart>

{% endhighlight %}

![](Striplines_images/Striplines_img1.png)

## Vertical Stripline

You can create vertical stripline by adding the **Stripline** in the horizontal axis and setting **Visible** option to true.  

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
    <e-primary-x-axis>
        <e-strip-lines><e-strip-line visible="true" start="3" end="7"></e-strip-line></e-strip-lines>
    </e-primary-x-axis>
    // ...
</ej-chart>

{% endhighlight %}

![](Striplines_images/Striplines_img2.png)

## Customize the text

To customize the text of the stripline, use **Text** and **Font** options. 

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
    <e-primary-y-axis>
        <e-strip-lines>
            <e-strip-line text="High Temperature">
                <e-Font font-size="18px" color="white"></e-Font>
            </e-strip-line>
        </e-strip-lines>
    </e-primary-y-axis>
    // ...
</ej-chart>

{% endhighlight %}

![](Striplines_images/Striplines_img3.png)


**Text alignment**

Stripline's text can be aligned by using the **TextAlignment** property.  

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
    <e-primary-y-axis>
        <e-strip-lines>
            <e-strip-line text-alignment="MiddleTop">
            </e-strip-line>
        </e-strip-lines>
    </e-primary-y-axis>
    // ...
</ej-chart>

{% endhighlight %}

![](Striplines_images/Striplines_img4.png)

## Customize the stripline

To customize the styles of the stripline, use the **Color**, **Opacity**, **BorderWidth** and **BorderColor** properties. 

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
    <e-primary-y-axis>
        <e-strip-lines>
            <e-strip-line color="#33CCFF" border-width="2" opacity="0.5" border-color="red">
            </e-strip-line>
        </e-strip-lines>
    </e-primary-y-axis>
    // ...
</ej-chart>

{% endhighlight %}

![](Striplines_images/Striplines_img5.png)


## Change the Z-order of the stripline

Stripline's **ZIndex** property is used to display the stripline either behind or over the series.  

{% highlight cshtml %}

<ej-chart id="chartContainer">
    // ...
    <e-primary-y-axis>
        <e-strip-lines>
            <e-strip-line z-index="Over">
            </e-strip-line>
        </e-strip-lines>
    </e-primary-y-axis>
    // ...
</ej-chart>

{% endhighlight %}

![](Striplines_images/Striplines_img6.png)