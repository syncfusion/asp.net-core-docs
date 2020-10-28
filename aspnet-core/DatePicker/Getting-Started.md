---
layout: post
title: Getting-Started | DatePicker | ASP.NET Core | Syncfusion
description: getting started
platform: aspnet-core
control: DatePicker
documentation: ug
---

# Getting Started

This section explains the essential steps required to render a DatePicker control in an ASP.net Core application.

## DatePicker Initialization

1. [Getting Started](/aspnet-core/getting-started) section explains about basic system requirements and the steps to configure the Syncfusion Components in an ASP.net core application.

    After successfully adding the necessary dependencies in your solution, make sure to build the solution, so that the necessary assembly files are compiled properly before using it in your project.

2. The Essential DatePicker can be created using EJTag helper as given below.

    {% highlight CSHTML %}

/*ej-Tag Helper code to render DatePicker*/

        <ej-date-picker id="startDate" value="DateTime.Now"></ej-date-picker>
               
    {% endhighlight %}

N>  DatePicker is a form control, so in form submission its value can be retrieved as a name value pair. By default, ID will be set as name attribute to achieve uniqueness. If you want to set the name manually you can use our HtmlAttributes API as given in the below code.
    
{% highlight CSHTML%}

/*Razor code to render DatePicker*/

    @{Html.EJ().DatePicker("startDate1").Value(DateTime.Now).Render();}

{% endhighlight %}

N> To render the DatePicker Control you can use either Razor or Tag helper code as given in the above code snippet.

    {% highlight CSHTML %}

    @{
            Dictionary<string, object> htmlAttr = new Dictionary<string, object>();
            htmlAttr.Add("name", "datepicker_start");
    }

/*ej-Tag Helper code to render DatePicker*/

    <ej-date-picker id="startDate" value="DateTime.Now" html-attributes="htmlAttr"></ej-date-picker>

    {% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render DatePicker*/

@{
     Dictionary<string, object> htmlAttr = new Dictionary<string, object>();
     htmlAttr.Add("name", "datepicker_start");
}

    @{Html.EJ().DatePicker("startDate1").Value(DateTime.Now).HtmlAttributes(htmlAttr).Render(); }


{% endhighlight %}

## Get / Set value

The Essential DatePicker provides an options to configure all its properties and to get its value. DatePicker value can be assigned during initialization or at run time. Below code shows how to assign values at initialization.

    {% highlight CSHTML %}

/*ej-Tag Helper code to render DatePicker*/

    <ej-date-picker id="startDate" value="DateTime.Now"  date-format="yyyy/MM/dd"></ej-date-picker>

    {% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render DatePicker*/

    @{Html.EJ().DatePicker("startDate1").Value(DateTime.Now).DateFormat("yyyy/MM/dd").Render(); }

{% endhighlight %}

You can assign values to existing DatePicker using its instance. Consider that you going to set date value at button click, refer the below code example.

~~~ javascript

        <script type="text/javascript">

        //bind below onClick action to button
        function onClick() {

            //create instance for datePicker.
            // only after control creation we can get dateObj otherwise it throws exception.
            var dateObj = $("#startDate").ejDatePicker('instance');

            //set value using date object
            dateObj.option('value', new Date());

            //get value using date object and displays in alert box
            alert(dateObj.option('value'));
        }
  
    </script>

~~~
    

N> Existing DatePicker instance can be created by jQuery.data() and you can control the API`s of DatePicker behavior.

## Client Side Events

You can handle the all available client side events in Essential JavaScript DatePicker. Refer the below code example to use the client side event in DatePicker.

    {% highlight CSHTML %}

/*ej-Tag Helper code to render DatePicker*/

    <ej-date-picker id="startDate" value="DateTime.Now" change="onChange"></ej-date-picker>
	
    <script>    
    
    function onChange(args) {
        //args contains entire model of DatePicker to get the value of all properties.

        //alert popup shows the previous date and selected date.
        alert(" previous date is : " + args.prevDate + " \n selected date is : " + args.value);
    }     
    </script>

    {% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render DatePicker*/

    @{ Html.EJ().DatePicker("startDate").Value(DateTime.Now).ClientSideEvents(e => e.Change("onChange")).Render(); } 
      <script>    
    
    function onChange(args) {
        //args contains entire model of DatePicker to get the value of all properties.

        //alert popup shows the previous date and selected date.
        alert(" previous date is : " + args.prevDate + " \n selected date is : " + args.value);
    }     
    </script>

{% endhighlight %}

## Strongly Typed Tag Helper

Essential DatePicker can be created using DatePickerFor extension, which behaves like strongly typed HTML helper. This reduces the run time issues while using model values in DatePickerFor, since it will find the issues, if any in compilation phase itself.
Please refer the below code to create the DatePickerFor control in your application.

    {% highlight CSHTML %}

/*ej-Tag Helper code to render DatePicker*/

    @* bind the "date" property in model to strongly typed Datepicker *@
    <ej-date-picker id="datepicker" ej-for="date" min-date="DateTime.Now"></ej-date-picker>
    @Html.ValidationMessageFor(model => model.date)

    {% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render DatePicker*/

    @{Html.EJ().DatePickerFor(model => model.datepicker, (Syncfusion.JavaScript.Models.DatePickerProperties)ViewData["date"]).Render(); }

{% endhighlight %}
