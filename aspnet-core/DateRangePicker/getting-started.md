---
layout: post
title: Getting Started | DateRangePicker  | ASP.NET Core | Syncfusion
description: getting started
platform: aspnet-core
control: DateRangePicker
documentation: ug
---

# Getting Started

This section explains briefly about how to render a DateRangePicker in your application with ASP.NET Core.

## Create your first DateRangePicker in ASP.NET Core 

The Essential ASP.NET Core DateRangePicker supports to display two calendars in the webpage and allows you pick date range from the calendars. Refer the following guidelines to customize the DateRangePicker. The following screenshot illustrates the functionality of DateRangePicker.


![](getting_started_images/getting-started1.png)
    
DateRangePicker
{:.caption}

In the above screenshot, you can see the start date and end date selection of a date range in DateRangePicker. This control offers easy way to navigate and select desired date range from one month as start date to other month as end date or we can pick both the start date and end date from the same month.

## Create a DateRangePicker 

ASP.NET Core DateRangePicker widget basically renders with built-in features like navigation between two calendars in popup with animations and flexible APIs. You can easily create the DateRangePicker widget using simple DateRangePicker elements as follows.

1. Create an Core Project, add necessary assemblies and scripts.

2. Refer [ASP.NET Core-Getting Started] (https://help.syncfusion.com/aspnet-core/gettingstarted/getting-started-2-0).

3. Add the following code to the corresponding view page to render DateRangePicker.


{% highlight cshtml %}
       
	@*Add the following code example to the corresponding CSHTML page to render DateRangePicker widget*@

	<ej-date-range-picker id="DateRange" date-format="dd/MM/yyyy" width="200px"></ej-date-range-picker>

{% endhighlight %} 
   

Execute the above code to render the following output.

![](getting_started_images/getting-started2.png)

DateRangePicker
{:.caption}


## Start Date

Start Date can be selected from any calendar in the popup of DateRangePicker. The date which is selected in the calendar in any following cases will be considered as StartDate of a date range,

1. Click on any date in an calendar of date range popup where there is no selection in calendars.

2. Click on date which is lesser than existing start date

3. Click on calendar when already there is start date and end date is updated. In this case existing selection will be cleared fully and clicked date will be set as start date to form new range.

Start Date of range can be set using API called **StartDate**, please refer the below code example:


{% highlight cshtml %}
            
        @*Add the following code example to the corresponding CSHTML page to render DateRangePicker widget with start date *@

        <ej-date-range-picker id="DateRange" width="35%" start-date=DateTime.Today></ej-date-range-picker>

{% endhighlight %} 
   
And also, StartDate can be set to popup, by entering the date value into first input box in popup.


## End Date

End Date of the date range can be selected from popup directly. Else this can be also updated by using the API called EndDate.

The Selection next to the **StartDate** will be considered as end date. This selected date should be higher or equal date than the existing start date.  Else this selection will be considered **StartDate** as we have mentioned in StartDate section above.

Below code will explain to use the **EndDate** API to set the end Date in popup.

{% highlight cshtml %}
            
        @*Add the following code example to the corresponding CSHTML page to render DateRangePicker widget with customized Start Date and  End Date*@

        <ej-date-range-picker id="DateRange" width="35%" start-date=DateTime.Today  end-date=DateTime.Now.AddDays(+17)></ej-date-range-picker>

{% endhighlight %} 

Execute the above code to render the following output.

![](getting_started_images/getting-started3.png)

DateRangePicker with StartDate and EndDate 
{:.caption}

End Date can be set to popup by entering the date into the second input box in popup.



