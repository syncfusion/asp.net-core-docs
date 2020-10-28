---
layout: post
title: Miscellaneous | DateRangePicker | ASP.NET Core | Syncfusion
description: miscellaneous
platform: aspnet-core
control: DateRangePicker
documentation: ug
---

# Allow Editing

Editing in input box can be disabled by setting the false value to **AllowEdit** API. By default this property will be true and we can edit the value in input box.

{% highlight cshtml %}
        
    <ej-date-range-picker id="DateRange" width="35%" allow-edit=true></ej-date-range-picker>

{% endhighlight %}
   

# Enable/Disable

The control can be enabled / disabled using public methods, **enable** or **disable**.

{% highlight cshtml %}
	
    <ej-date-range-picker id="DateRange" width="35%" create=Create></ej-date-range-picker>

    <script>
    //Create event triggers after DateRangePicker created successfully.
        function Create() {
            $("#DateRange").ejDateRangePicker('disable');
            } 
    </script>
    
{% endhighlight %} 

## Clear Ranges

To clear the all selection and ranges in a popup we can make use of **clearRanges** method.

{% highlight cshtml %}
    
    <ej-date-range-picker id="DateRange" width="35%" before-close=Clear></ej-date-range-picker>

    <script>
    //BeforeClose event triggers before closing DateRangePicker popup
    function Clear() {
                $("#DateRange").ejDateRangePicker('clearRanges');
            }

    </script>

{% endhighlight %} 

The following screenshot displays the output for the above code.

![](Miscellaneous_images/Miscellaneous.png)

BeforeClose Event of DateRangePicker
{:.caption}
