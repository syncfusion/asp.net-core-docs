---
layout: post
title: How-to | DatePicker | ASP.NET Core | Syncfusion
description: How-to section - The frequently used options with DatePicker 
platform: aspnet-core
control: DatePicker
documentation: ug
---
# How to?

## Customizing template with range selection between two DatePicker. 

You can customize the date field to emphasize the particular dates in Essential ASP.NET Core  DatePicker calendar with help of [SpecialDates](http://help.syncfusion.com/js/api/ejdatepicker#members:specialdates) and set the date range using [MinDate](http://help.syncfusion.com/js/api/ejdatepicker#members:mindate) and [MaxDate](http://help.syncfusion.com/js/api/ejdatepicker#members:maxdate) property. 

## Validating the date value in server side
	
The Essential ASP.NET Core DatePicker control, is a form control which  allows us to validate the date value in client side and server side actions. Please refer from the [validation](https://www.syncfusion.com/kb/5433/how-to-achieve-the-required-field-validation-for-datepicker-control-in-asp-net-mvc) to know more about this with EJMVC DatePicker control.

## Localize DatePicker with browser specific culture

You can get the browser culture name at page load or document ready state. Based on the culture name, The Essential ASP.NET Core DatePicker can be initiated with that specific culture value by assigning to [Locale](http://help.syncfusion.com/js/api/ejdatepicker#members:locale) property. 

## Disable specific dates to restrict user

Essential ASP.NET Core DatePicker allows you to restrict date selection in specific range by using date range option. But you can also restrict selective date in DatePicker calendar by utilizing [BeforeDateCreate](http://help.syncfusion.com/js/api/ejdatepicker#events:beforedatecreate) event. This event will get triggered at each date creation. So you can disable the selective date in this event to restrict the user.

{% highlight cshtml %}

/*ej-Tag Helper code to render DatePicker*/

    @*handler to listen each date create*@

    <ej-date-picker id="datepick" before-date-create="restrictDate"></ej-date-picker>

    <script>   
   
    //event get triggered for each date create.
    function restrictDate(args) {
       //date to disable in calendar to restrict selection.
       var disableDate = new Date("09/22/2015"); 
       //compares two and adds the disable class.
       if (+args.date === +disableDate)                
           args.element.addClass('e-disable');  
           // args contains current date and its element.          
    }
         
    </script>


{% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render DatePicker*/

     @{Html.EJ().DatePicker("datepicker").ClientSideEvents(clientSideEvent => clientSideEvent.BeforeDateCreate("restrictDate")).Render(); }

    <script>   
   
    //event get triggered for each date create.
    function restrictDate(args) {
       //date to disable in calendar to restrict selection.
       var disableDate = new Date("09/22/2015"); 
       //compares two and adds the disable class.
       if (+args.date === +disableDate)                
           args.element.addClass('e-disable');  
           // args contains current date and its element.          
    }
         
    </script>


{% endhighlight %}

## How to add clear button with DatePicker?

Clear button can be included in the DatePicker control. In the `create` event of DatePicker, clear button element should be appended in the input element and event for clearing the value should bind with the clear button element. Refer the sample from the link [Clear button](http://jsplayground.syncfusion.com/mmdn4d0q) to know how to add the clear button with the DatePicker component. Based, on the theme loaded you can adjust the styles of the clear button.

{% highlight cshtml %}

<ej-date-picker id="date" create="Created" value="System.DateTime.Now"></ej-date-picker>

<script>
    function Created() {
        if (this.innerWrapper.find('.e-clear-date').length == 0) {
            this.innerWrapper.append("<span class='e-clear-date e-icon'></span>"); // create and append the 'div' element to the calendar
            this._on($('.e-clear-date', this.innerWrapper), "click", function () { this.option('value', null); if (!this.model.displayInline) this.hide(); }); // bind the 'Click' event to that 'div' element
        }
    }
</script>

<style>
    /*styles for clear button*/ 
    .e-clear-date {
        text-align: center;
        position: absolute;
        right: 24px;
        top: 0;
        background: #ececec;
        width: 21px !important;
        height: 100% !important;
        margin-top: -16px !important;
    }

    .e-clear-date:hover {
        background: #86cbea;
        cursor: pointer;
    }

    .e-clear-date:before {
        content: "\e605";
        font-size: 16px;
        line-height: 1.8;
    }
    /*end of styles*/ 
</style>

{% endhighlight %}


N> To render the DatePicker Control you can use either Razor or Tag helper code as given in the above code snippet.

## How to integrate with bootstrap grid system? 

Essential ASP.NET Core  DatePicker is responsive control, you have to just set the input element width as 100%. In Bootstrap grid layout use the below code example to get responsive textbox 

{% highlight cshtml %}

/*ej-Tag Helper code to render DatePicker*/

    @*sets the width to 100%*@

     <ej-date-picker id="datepick" width="100%"></ej-date-picker>


{% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render DatePicker*/

     @{Html.EJ().DatePicker("datepicker").Width("100%").Render(); }


{% endhighlight %}


