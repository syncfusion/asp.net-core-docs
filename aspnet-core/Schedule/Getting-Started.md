---
layout: post
title: Getting Started | ASP.NET Core | Syncfusion
description: Getting Started with Scheduler control.
platform: aspnet-core 
control: Schedule 
documentation: ug
---

# Getting Started

Refer the [Getting Started](/aspnet-core/getting-started) page of the Introduction part to know more about the basic system requirements and the steps to configure the Syncfusion components in an ASP.NET Core application.

Ensure once whether all the necessary dependency packages are included within the *bower.json* file as mentioned [here](/aspnet-core/getting-started#configure-syncfusion-components-in-aspnet-core-application), so that the required scripts and CSS to render the Schedule control gets installed and loads into the mentioned location (**wwwroot -> lib**) within your project.

Also, check whether the assembly dependency package **Syncfusion.EJ** added within the *project.json* file.

Now, refer the necessary scripts and CSS files into your *_Layout.cshtml* page from the **wwwroot -> lib -> syncfusion-javascript** folder.

{% highlight cshtml %}

<html>
<head>
    <environment names="Development">
        <link rel="stylesheet" href="~/lib/bootstrap/dist/css/bootstrap.css" />
        <link rel="stylesheet" href="~/css/site.css" />
        <link href="~/lib/syncfusion-javascript/Content/ej/web/default-theme/ej.web.all.min.css" rel="stylesheet" />
        <link href="~/lib/syncfusion-javascript/Content/ej/web/responsive-css/ej.responsive.css" rel="stylesheet" />
    </environment>
</head>
<body>

    <environment names="Development">
        <script src="~/lib/jquery/dist/jquery.js"></script>
        <script src="~/lib/bootstrap/dist/js/bootstrap.js"></script>
        <script src="~/js/site.js" asp-append-version="true"></script>
        <script src="~/lib/jquery.easing/js/jquery.easing.min.js"></script>
        <script src="~/lib/syncfusion-javascript/Scripts/jsrender.min.js"></script>
        <script src="~/lib/syncfusion-javascript/Scripts/ej/web/ej.web.all.min.js"></script>
    </environment>

</body>
</html>

{% endhighlight %}

It is necessary to define the following namespace within the *_viewImports.cshtml* page in order to make use of the Scheduler component with the tag helper support.
 
{% highlight cshtml %}
 
    @using Syncfusion.JavaScript
    @addTagHelper "*, Syncfusion.EJ"
    
{% endhighlight %}

N> Script manager must be defined at the bottom of the *_Layout.cshtml* page.

Add the Scheduler code within the View page as given below with proper field names bind to it –

{% highlight cshtml %}

    <ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2014, 6, 2)" read-only="true">
            <e-appointment-settings id='"ProgramId"' subject='"ProgramName"' start-time='"ProgramStartTime"' end-time='"ProgramEndTime"' description='"Comments"' all-day='"IsAllDay"' recurrence='"IsRecurrence"' recurrence-rule='"RecurrenceRule"'>
            </e-appointment-settings>
    </ej-schedule>

{% endhighlight %}

N> The appointment fields like id, subject, description and other required Scheduler appointment fields are needed to be mapped with the appropriate column names from the dataSource as done in the above code example.

To access and process the data back and forth the Scheduler, define it with data manager settings along with the data adaptor (url adaptor) options as given below –

 {% highlight cshtml %}
 
    <ej-schedule id="Schedule1" width="100%" height="525px" current-date="new DateTime(2014, 5, 6)" time-zone="UTC -05:00" read-only="true">
        <e-appointment-settings id='"ProgramId"' subject='"ProgramName"' start-time='"ProgramStartTime"' end-time='"ProgramEndTime"' description='"Comments"' all-day='"IsAllDay"' recurrence='"IsRecurrence"' recurrence-rule='"RecurrenceRule"'>
            <e-datamanager url="/Home/GetData" adaptor="UrlAdaptor"></e-datamanager>
        </e-appointment-settings>
    </ej-schedule>

{% endhighlight %}

N> In the above code, url adaptor has been used, where the controller action named _GetData_ is called within it.

Create a new class file namely _ScheduleData_ within the **Models** folder in order to define the data to be passed to the Scheduler as mentioned below,

{% highlight c# %}

    public class ScheduleData
    {
        public int ProgramId { get; set; }
        public string ProgramName { get; set; }
        public string Comments { get; set; }
        public DateTime ProgramStartTime { get; set; }
        public DateTime ProgramEndTime { get; set; }
        public bool IsAllDay { get; set; }
        public bool IsRecurrence { get; set; }
        public string RecurrenceRule { get; set; }
        
        // Method that passes the Scheduler appointment data
        public List<ScheduleData> getSchedulerData()
        {
           List<ScheduleData> data = new List<ScheduleData> {
             new ScheduleData {
                    ProgramName = "Turtle Walk",
                    Comments = "Night out with turtles",
                    ProgramStartTime = new DateTime(2016, 6, 2, 3, 0, 0),
                    ProgramEndTime = new DateTime(2016, 6, 2, 4, 0, 0),
                    IsAllDay = true
             },
             new ScheduleData {
                    ProgramName = "Winter Sleepers",
                    Comments = "Long sleep during winter season",
                    ProgramStartTime = new DateTime(2016, 6, 3, 1, 0, 0),
                    ProgramEndTime = new DateTime(2016, 6, 3, 2, 0, 0)
             }
           };
           return data;
        }
    }

{% endhighlight %}

Now, define the action _GetData_ within the **Home** controller page as shown below and access the model data in it (use the model namespace at the top of your controller page), which is then bind to the Scheduler.

{% highlight c# %}

    public List<ScheduleData> GetData()
    {
        ScheduleData appoint = new ScheduleData();
        return appoint.getSchedulerData(); // returns the appointment data, which gets bind to the Scheduler control
    }

{% endhighlight %}


![](Getting-Started_images/Getting-Started_img1.png)


 


 


