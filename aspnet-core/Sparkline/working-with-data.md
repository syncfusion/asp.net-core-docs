---
layout: post
title: Data binding
description: Learn how to bind Sparkline with local data.
platform: aspnet-core
control: Sparkline
documentation: ug
---

# Working with Data

## Local Data

1. You can bind the data to the Sparkline by using `datasource`property and then you need to map the **X** and **Y** value with **x-name** and **y-name** properties respectively.

{% highlight C# %}

public class HomeController : Controller
    {
         public IActionResult Index()

        {    
            //// Create dataSource to Sparkline
            List<SparklineData> data = new List<SparklineData>();
            data.Add(new SparklineData(0, 35));
            data.Add(new SparklineData(1, 28));
            data.Add(new SparklineData(2, 34));
            data.Add(new SparklineData(3, 32));
            data.Add(new SparklineData(4, 40));
            data.Add(new SparklineData(5, 32));
            data.Add(new SparklineData(6, 35));
            data.Add(new SparklineData(7, 55));
            data.Add(new SparklineData(8, 38));
            data.Add(new SparklineData(9, 30));
            data.Add(new SparklineData(10, 25));
            data.Add(new SparklineData(11, 32));
            ///...
            ViewBag.SparklineData = data;
            return View();
        }
    }

    public class SparklineData
    {
        public double Month;
        public double Sales;
        public SparklineData(double month, double sales)
        {
            this.Month = month;
            this.Sales = sales;
        }
    }

{% endhighlight %}

{% highlight cshtml %}

<ej-spark-line id="sparkline" datasource="ViewBag.SparklineData" x-name="Month" 
y-name="Sales">
</ej-spark-line>

{% endhighlight %}

![](Working-with-Data_images/Working-with-Data_img1.png); 

2. You can also bind an array of data to Sparkline by using `datasource` property.  

{% highlight cshtml %}

public class HomeController : Controller
    {
         public IActionResult Index()

        {    
            Double[] y1 = { 2, 6, -1, 1, 12, 5, -2, 7, -3, 5, 8, 10};
            ViewBag.SparklineData = y1;
            return View();
        }
    }

{% endhighlight %}

{% highlight cshtml %}

<ej-spark-line id="sparkline" datasource="ViewBag.SparklineData">
</ej-spark-line>

{% endhighlight %}


![](Working-with-Data_images/Working-with-Data_img2.png); 


