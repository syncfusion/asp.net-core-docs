---
layout: post
title: Behaviour Settings
description: Configure the DatePicker behavior settings
platform: aspnet-core
control: DatePicker
documentation: ug
---
# Behavior Settings

The Essential ASP.NET Core DatePicker has some default behavior settings which helps to perform more operation by built-in.

## Selected Date

The Essential ASP.NET Core DatePicker value can be selected through picking date from DatePicker calendar or you can set it by using “Value” property.


The Essential ASP.NET Core DatePicker allows only the valid date to be entered and it should be within the specified range. By default, strict mode is enabled in DatePicker, so it will restrict invalid date and resets to previous date if it’s not valid. Also the valid date should be defined in specified range or else it resets to min or maximum date when the entered date is out of range. To know more about strict mode refer [Strict Mode](#strict-mode)

## Date Range

EJMVC DatePicker provides an option to restrict the user to pick the date from specified range of value. You can utilize this option by make use of ‘MinDate’ and ‘MaxDate’ property.

**MinDate** - specifies the minimum date to be picked in DatePicker calendar by disabling below date of minDate.

**MaxDate** -  specifies the maximum date to be picked in DatePicker calendar by disabling above date of maxDate. 
Refer below example to set min and max date range in DatePicker at initialization (You can change the **‘MinDate’** and **‘MaxDate’** value dynamical as like ‘Value’ property)

{% highlight cshtml %}

/*ej-Tag Helper code to render DatePicker*/
   
    @*sets min and max date to be pick able in datepicker*@
      <ej-date-picker id="datepicker" value="@DateTime.Now" min-date="2014/06/03" max-date="2014/06/19"></ej-date-picker>        
        
{% endhighlight %}


{% highlight CSHTML%}

/*Razor code to render DatePicker*/

    @{Html.EJ().DatePicker("datePicker").Value(DateTime.Now).MinDate("2014/06/03").MaxDate("2014/06/19").Render(); }

{% endhighlight %}

N> To render the DatePicker  Control you can use either Razor or Tag helper code as given in the above code snippet.

N> You can change the **MinDate** and **MaxDate** value dynamically like **Value** property

## Start and Depth Level

Start and depth represents the view of Essential ASP.NET Core DatePicker calendar. DatePicker calendar has four different level of views, which are month, year, decade and century. It allows you to quick pick date from different months and years by navigating through different views.

By default DatePicker starts with month view and can be drill down into year, decade and century. You can also change the start and depth level view by using [StartLevel](http://help.syncfusion.com/js/api/ejdatepicker#members:startlevel) and [DepthLevel](http://help.syncfusion.com/js/api/ejdatepicker#members:depthlevel) property. So that you can initiate DatePicker calendar to view at any level and control the navigation.

* "Month"   - shows the days in month to pick.
* "Year"    - shows the months in year to pick.
* "Decade"  - shows the years in decade to pick.
* "Century" - shows the decades in century to pick.

{% highlight cshtml %}

/*ej-Tag Helper code to render DatePicker*/

        @*sets the start view and defines when the DatePicker calendar to return date*@
         <ej-date-picker id="datepicker" value="@DateTime.Now" start-level="Year" depth-level="Year" date-format="MMMM yyyy"></ej-date-picker>      
  
{% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render DatePicker*/

      @{ Html.EJ().DatePicker("datepicker").Value(DateTime.Now).StartLevel(Period.Year).DepthLevel(Period.Year).DateFormat("MMMM yyyy").Render(); }

{% endhighlight %}


## Display Inline Mode

The Essential ASP.NET Core DatePicker provides an option to act as calendar by setting the [DisplayInline](http://help.syncfusion.com/js/api/ejdatepicker#members:displayinline) property as true. In this mode the DatePicker calendar has been placed open state constantly to pick the date. 
Refer below code example to represent DatePicker as calendar.

{% highlight cshtml %}

/*ej-Tag Helper code to render DatePicker*/

    @*sets inline to represent datePicker as DatePicker calendar*@
  <ej-date-picker id="datepicker" value="@DateTime.Now" display-inline="true"></ej-date-picker>      
  

{% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render DatePicker*/

     @{ Html.EJ().DatePicker("datepicker").Value(DateTime.Now).DisplayInline(true).Render(); }

{% endhighlight %}


## Strict Mode

Strict mode in Essential ASP.NET Core DatePicker allows you to enter valid or invalid date in input textbox, but an error class will get added to exhibit if it is an invalid date. When you set [EnableStrictMode](http://help.syncfusion.com/js/api/ejdatepicker#members:enablestrictmode) to false, DatePicker allows you to enter only the valid date or else it will resets with previous value. 

Also the valid date should be defined in specified range or else it resets to min or maximum date when the entered date is out of range

By default **EnableStrictMode** is true, so you can enter any value other than date too, but an **error** class ("**e** **-** **error**") will get added to wrapper to highlight the invalid date.

{% highlight cshtml %}

/*ej-Tag Helper code to render DatePicker*/

    @*sets active strict mode*@

    <ej-date-picker id="datepicker" value="@DateTime.Now" enable-strict-mode="false"></ej-date-picker>      
   

{% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render DatePicker*/

     @{ Html.EJ().DatePicker("datepicker").Value(DateTime.Now).EnableStrictMode(false).Render(); }


{% endhighlight %}


You can also override the  **error** class to highlight when invalid date is entered.

{% highlight cshtml %}

/*ej-Tag Helper code to render DatePicker*/

    @*sets inactive strict mode*@

    <ej-date-picker id="datepicker" value="@DateTime.Now" enable-strict-mode="true"></ej-date-picker>      
   
 
{% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render DatePicker*/

     @{ Html.EJ().DatePicker("datepicker").Value(DateTime.Now).EnableStrictMode(true).Render(); }

{% endhighlight %}


{% highlight css %}

    <style>
        /* error class to highlight invalid date */

        .e-error .e-input {
            color: Red; /* highlights invalid date font color in input */
        }
    </style>

{% endhighlight %}
