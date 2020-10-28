---
layout: post
title: DatePicker Customization
description: DatePicker customization options such as dimension, highlight dates, other months, etc.
platform: aspnet-core
control: DatePicker
documentation: ug
---
# Customization

The Essential ASP.NET Core DatePicker appearance can be customized using below listed properties. 

## Set Dimension 

By default DatePicker has standard height and width (height: "30" and width: "143"). You can change this height and width by using [Height](http://help.syncfusion.com/js/api/ejdatepicker#members:height) and [Width](http://help.syncfusion.com/js/api/ejdatepicker#members:width) property respectively.


{% highlight cshtml %}

/*ej-Tag Helper code to render DatePicker*/

        @*sets height and width of the datepicker control*@

  <ej-date-picker id="datepicker" value="@DateTime.Now" height="50px" width="300px"></ej-date-picker>      
 


{% endhighlight %}


{% highlight CSHTML%}

/*Razor code to render DatePicker*/

     @{Html.EJ().DatePicker("datepicker").Value(DateTime.Now).Height("50px").Width("300px").Render(); }

{% endhighlight %}

N> To render the DatePicker Control you can use either Razor or Tag helper code as given in the above code snippet.

Since Essential ASP.NET Core DatePicker is a form control and you can make it as responsive by specifying its width as **100%**.


{% highlight cshtml %}

/*ej-Tag Helper code to render DatePicker*/

        @*sets width as 100 percentage*@

         <ej-date-picker id="datepicker" value="@DateTime.Now" width="100%"></ej-date-picker>  

{% endhighlight %}


{% highlight CSHTML%}

/*Razor code to render DatePicker*/

     @{Html.EJ().DatePicker("datepicker").Value(DateTime.Now).Width("100%").Render(); }

{% endhighlight %}


## Show Footer

You can show or hide the footer of EJMVC DatePicker calendar by using [ShowFooter](http://help.syncfusion.com/js/api/ejdatepicker#members:showfooter) property. 

{% highlight cshtml %}

/*ej-Tag Helper code to render DatePicker*/
    
    @*hides the footer in popup calendar*@

     <ej-date-picker id="datepicker" value="@DateTime.Now" show-footer="false"></ej-date-picker>      

    
{% endhighlight %}


{% highlight CSHTML%}

/*Razor code to render DatePicker*/

     @{Html.EJ().DatePicker("datepicker").Value(DateTime.Now).ShowFooter(false).Render(); }

{% endhighlight %}


N>  Footer contains the today button to quickly navigate to the current date. By turning off it, you have to select current date by manually. 


## Show Popup Button

The Essential ASP.NET Core DatePicker input textbox  contains a button to open the DatePicker calendar. You can hide this DatePicker calendar button using [ShowPopupButton](http://help.syncfusion.com/js/api/ejdatepicker#members:showpopupbutton) value as false.

By hiding this button, you can open the DatePicker by focusing the input textbox element itself.

{% highlight cshtml %}

/*ej-Tag Helper code to render DatePicker*/

    @*hides the popup calendar button*@

     <ej-date-picker id="datepicker" value="@DateTime.Now" show-popup-button="false"></ej-date-picker>      
  


{% endhighlight %}


{% highlight CSHTML%}

/*Razor code to render DatePicker*/

     @{Html.EJ().DatePicker("datepicker").Value(DateTime.Now).ShowPopupButton(false).Render(); }

{% endhighlight %}


## Show Other Months

You can show or hide the other month days from the Essential ASP.NET Core DatePicker calendar by using [ShowOtherMonths](http://help.syncfusion.com/js/api/ejdatepicker#members:showothermonths) property.

{% highlight cshtml %}

/*ej-Tag Helper code to render DatePicker*/

    @*hides the days of other months in calendar*@

     <ej-date-picker id="datepicker" value="@DateTime.Now" show-other-months="false"></ej-date-picker>      
  

{% endhighlight %}


{% highlight CSHTML%}

/*Razor code to render DatePicker*/

     @{Html.EJ().DatePicker("datepicker").Value(DateTime.Now).ShowOtherMonths(false).Render(); }

{% endhighlight %}


## Highlight Special Date

The Essential ASP.NET Core DatePicker allows you to highlight the special dates in ASP.NET Core DatePicker calendar by using [SpecialDates](http://help.syncfusion.com/js/api/ejdatepicker#members:specialdates) property. It receives the list of "dataSpecial" date fields such as, in which the data should contain the date value, icon CSS class and tooltip as field values with any names.

Special Date property has following properties,

<table>
<tr>
<th>
Members</th><th>
Description</th></tr>
<tr>
<td>
Date<br/><br/></td><td>
It specifies the mapping field of special date<br/><br/></td></tr>
<tr>
<td>
IconClass<br/><br/></td><td>
It specifies the mapping field of icon CSS class.<br/><br/></td></tr>
<tr>
<td>
Tooltip<br/><br/></td><td>
It specifies the mapping field of tool tip text.<br/><br/></td></tr>
</table>


{% highlight cshtml %}

/*ej-Tag Helper code to render DatePicker*/

    @*sets the special date in datepicker calendar*@

    
    <ej-date-picker id="datepicker" value="DateTime.Now">
        <e-special-dates><e-special-date date="28/06/2015" icon-class="birthday" tooltip="birthday" /></e-special-dates>
    </ej-date-picker>
      
{% endhighlight %}


{% highlight CSHTML%}

/*Razor code to render DatePicker*/

     @{Html.EJ().DatePicker("datepicker").SpecialDates(SpecialDate => { SpecialDate.Add().Date("28/06/2015").IconClass("birthday").Tooltip("birthday"); }).Render(); }


{% endhighlight %}


