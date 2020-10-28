---
layout: post
title: Getting Started for Essential JavaScript SunburstChart
description: How to create a SunburstChart.
platform: aspnet-core
control: SunburstChart
documentation: ug
---

# Getting Started

This section explains you the steps required to populate the SunburstChart , add data labels, tooltips and title to the SunburstChart. This section covers only the minimal features that you need to know to get started with the SunburstChart.


## Create Sunburst Chart

1. First, create a new ASP.NET core project. please refer [ASP.NET core 1.0-Getting Started](/aspnet-core/getting-started) documentation to create new project and add necessary DLL’s and script files.

2.Add the following code in the index.cshtml file to create the SunburstChart control in View page.

{% highlight cshtml %}
<div>
<ej-sunburstchart id="SunburstChart" >
</ej-sunburstchart>
   
</div>
{% endhighlight %}

## Populate Data source:

Now, let’s see how to plot data source to the SunburstChart. First, let us generate a data source containing following fields in controller.

{% highlight cs %}

 public class DefaultData
    {
        public string Category { get; set; }
        public string Country { get; set; }
        public string JobDescription { get; set; }
        public string JobGroup { get; set; }
        public string JobRole { get; set; }
        public int EmployeesCount { get; set; }

        public static List<DefaultData> GetDefaultData()
        {
            List<DefaultData> data = new List<DefaultData>();
           data.Add(new DefaultData() { Category = "Employees", Country = "USA", JobDescription = "Sales",         JobGroup ="Executive",                         EmployeesCount= 50});
           data.Add(new DefaultData() { Category = "Employees", Country = "USA", JobDescription = "Sales",         JobGroup = "Analyst",                         EmployeesCount =40 });
           data.Add(new DefaultData() { Category = "Employees", Country = "USA", JobDescription = "Marketing",                                                  EmployeesCount =40 });
           data.Add(new DefaultData() { Category = "Employees", Country = "USA", JobDescription = "Technical",     JobGroup = "Testers",                         EmployeesCount =55 });
           data.Add(new DefaultData() { Category = "Employees", Country = "USA", JobDescription = "Technical",     JobGroup = "Developers", JobRole = "Windows", EmployeesCount =175});
           data.Add(new DefaultData() { Category = "Employees", Country = "USA", JobDescription = "Technical",     JobGroup = "Developers", JobRole = "Web",     EmployeesCount =70 });
           data.Add(new DefaultData() { Category = "Employees", Country = "USA", JobDescription = "Management",                                                  EmployeesCount =40 });
           data.Add(new DefaultData() { Category = "Employees", Country = "USA", JobDescription = "Accounts",                                                    EmployeesCount =60 });
           
           data.Add(new DefaultData() { Category = "Employees", Country = "India",   JobDescription = "Technical",     JobGroup = "Testers",                         EmployeesCount = 43 });
           data.Add(new DefaultData() { Category = "Employees", Country = "India",   JobDescription = "Technical",     JobGroup = "Developers", JobRole = "Windows", EmployeesCount = 125});
           data.Add(new DefaultData() { Category = "Employees", Country = "India",   JobDescription = "Technical",     JobGroup = "Developers", JobRole = "Web",     EmployeesCount = 60 });
           data.Add(new DefaultData() { Category = "Employees", Country = "India",   JobDescription = "HR Executives",                                              EmployeesCount = 70 });
           data.Add(new DefaultData() { Category = "Employees", Country = "India",   JobDescription = "Accounts",                                                   EmployeesCount = 45 });
          
           data.Add(new DefaultData() { Category = "Employees", Country = "Germany", JobDescription = "Sales",         JobGroup = "Executive",                       EmployeesCount = 30 });
           data.Add(new DefaultData() { Category = "Employees", Country = "Germany", JobDescription = "Sales",         JobGroup = "Analyst",                         EmployeesCount = 40 });
           data.Add(new DefaultData() { Category = "Employees", Country = "Germany", JobDescription = "Marketing",                                                  EmployeesCount = 50  });
           data.Add(new DefaultData() { Category = "Employees", Country = "Germany", JobDescription = "Technical",     JobGroup = "Testers",                         EmployeesCount = 40 });
           data.Add(new DefaultData() { Category = "Employees", Country = "Germany", JobDescription = "Technical",     JobGroup = "Developers", JobRole = "Windows", EmployeesCount = 65 });
           data.Add(new DefaultData() { Category = "Employees", Country = "Germany", JobDescription = "Technical",     JobGroup = "Developers", JobRole = "Web",     EmployeesCount = 27 });
           data.Add(new DefaultData() { Category = "Employees", Country = "Germany", JobDescription = "Management",                                                 EmployeesCount = 33  });
           data.Add(new DefaultData() { Category = "Employees", Country = "Germany", JobDescription = "Accounts",                                                   EmployeesCount = 55  });
           
           data.Add(new DefaultData() { Category = "Employees", Country = "UK",      JobDescription = "Technical",     JobGroup = "Testers",                         EmployeesCount = 45 });
           data.Add(new DefaultData() { Category = "Employees", Country = "UK",      JobDescription = "Technical",     JobGroup = "Developers", JobRole = "Windows", EmployeesCount = 96 });
           data.Add(new DefaultData() { Category = "Employees", Country = "UK",      JobDescription = "Technical",     JobGroup = "Developers", JobRole = "Web",     EmployeesCount = 55 });
           data.Add(new DefaultData() { Category = "Employees", Country = "UK",      JobDescription = "HR Executives",                                               EmployeesCount = 60 });
           data.Add(new DefaultData() { Category = "Employees", Country = "UK",      JobDescription= "Accounts",                                                     EmployeesCount=30   });
           
           data.Add(new DefaultData() { Category = "Employees", Country = "France", JobDescription= "Technical",     JobGroup = "Testers",                         EmployeesCount = 40 });
           data.Add(new DefaultData() { Category = "Employees", Country = "France", JobDescription= "Technical",     JobGroup = "Developers", JobRole = "Windows", EmployeesCount = 65 });
           data.Add(new DefaultData() { Category = "Employees", Country = "France", JobDescription= "Technical",     JobGroup = "Developers", JobRole = "Web",     EmployeesCount = 27 });
           data.Add(new DefaultData() { Category = "Employees", Country = "France", JobDescription="Marketing",                                                     EmployeesCount= 50 });
           return data; 
        }
    }



{% endhighlight %}

### Initialize Sunburst Chart with data

Now, bind the DefaultData to `datasource` property of the Sunburst Chart. The`e-sunburstchart-levels`property determines the number of hierarchical levels. Each hierarchy level is formed based on the property specified in `group-member-path` property, and each arc segment size is calculated using `value-member-path`.

2. Add SunburstChart() action in SunburstChartController and add the following code.

{% highlight C# %}

public ActionResult SunburstChart()
        {
            ViewData["defaultData"] = DefaultData.GetDefaultData();            
            return View();
        }

{% endhighlight %}

3.Render the SunburstChart with the Datasource and Levels,the following code snippet is used in the index.cshtml


{% highlight CSHTML %}

<ej-sunburstchart id="SunburstChart" datasource=@ViewData["defaultData"] value-member-path="EmployeesCount">
  <e-sunburstchart-levels>
                <e-sunburstchart-level group-member-path="Country"></e-sunburstchart-level>
                <e-sunburstchart-level group-member-path="JobDescription"></e-sunburstchart-level>
                <e-sunburstchart-level group-member-path="JobGroup"></e-sunburstchart-level>
                <e-sunburstchart-level group-member-path="JobRole"></e-sunburstchart-level>
            </e-sunburstchart-levels>
</ej-sunburstchart>


{% endhighlight %}



## Add Title to the Sunburst Chart

The title of the Sunburst chart is used to provide quick information to the user about the data being plotted in the Sunburst Chart. You can add it by using the `text` property of the **e-sunburstchart-title** 

{% highlight cshtml %}

<ej-sunburstchart id="SunburstChart" >
<e-sunburstchart-title text="Employees Count"></e-sunburstchart-title>
</ej-sunburstchart>

{% endhighlight %}

## Enable Legend

You can enable or disable the legend by using the `visible` property present inside the **e-sunburstchart-legend**

{% highlight cshtml %}

<ej-sunburstchart id="SunburstChart" > 
<e-sunburstchart-legend visible="true" ></e-sunburstchart-legend>
</ej-sunburstchart>

{% endhighlight %}

## Add Data Labels

The data labels are used to improve the readability of the Sunburst chart. This can be achieved by enabling the `visible` property in the **e-sunburstchart-data-label-settings**

{% highlight cshtml %}

<ej-sunburstchart id="SunburstChart" >
 <e-sunburstchart-data-label-settings visible="true"></e-sunburstchart-data-label-settings>
</ej-sunburstchart>



{% endhighlight %}

Now the Sunburst Chart is rendered along with the specified customizations

![](Getting-Started_images/Getting-Started_img1.png)

[Click](http://aspnetcore.syncfusion.com/sunburst/default) here to view the default sample of the Sunburst Chart.
