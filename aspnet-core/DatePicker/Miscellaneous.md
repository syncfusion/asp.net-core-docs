---
layout: post
title: Miscellaneous
description: Configure start day of week, step month, and enabled/disabled state of DatePicker
platform: aspnet-core
control: DatePicker
documentation: ug
---
# Miscellaneous 

## Start Day

By default EJMVC DatePicker calendar starts with "Sunday" and ends with "Monday". You can redefine this start day by using [StartDay](http://help.syncfusion.com/js/api/ejdatepicker#members:startday) property.

Refer below code to start Wednesday as start day. 


{% highlight cshtml %}

/*ej-Tag Helper code to render DatePicker*/

        @*sets start day as Wednesday in calendar*@

     <ej-date-picker id="datepick" start-day="3"></ej-date-picker>

{% endhighlight %}


{% highlight CSHTML%}

/*Razor code to render DatePicker*/

         @{Html.EJ().DatePicker("datepick").StartDay(3).Render(); }

{% endhighlight %}

N> To render the DatePicker Control you can use either Razor or Tag helper code as given in the above code snippet.


## Step Months

The EJMVC DatePicker calendar allows you to quick navigate back and forth from one month to previous or next month by clicking the arrow button. By default it is navigate one by one month. You can also navigate by skipping months in odd or even or any count by using [StepMonths](http://help.syncfusion.com/js/api/ejdatepicker#members:stepmonths) property. 


{% highlight cshtml %}

/*ej-Tag Helper code to render DatePicker*/

        @*skips the one months from current month(July to Sept to Nov)*@

         <ej-date-picker id="datepick" step-months="2"></ej-date-picker>

{% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render DatePicker*/

         @{Html.EJ().DatePicker("datepick").StepMonths(2).Render(); }

{% endhighlight %}


## Read Only

You can make EJMVC DatePicker as read only by setting [ReadOnly](http://help.syncfusion.com/js/api/ejdatepicker#members:readonly) property as true. It allows only to read the value and it cannot be changed by interaction.


{% highlight cshtml %}

/*ej-Tag Helper code to render DatePicker*/

        @*sets DatePicker as read only*@

        <ej-date-picker id="datepick" read-only="true"></ej-date-picker>

{% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render DatePicker*/

         @{Html.EJ().DatePicker("datepick").ReadOnly(true).Render(); }

{% endhighlight %}


## Enable or Disable

You can enable or disable the EJMVC DatePicker textbox by using [Enabled](http://help.syncfusion.com/js/api/ejdatepicker#members:enabled) property. In inline mode DatePicker calendar also gets enabled or disabled. 


{% highlight cshtml %}

/*ej-Tag Helper code to render DatePicker*/

        @*disables the DatePicker textbox*@

         <ej-date-picker id="datepick" enabled="false"></ej-date-picker>    

{% endhighlight %}


{% highlight CSHTML%}

/*Razor code to render DatePicker*/

        @{Html.EJ().DatePicker("datepick").Enabled(false).Render(); }


{% endhighlight %}


