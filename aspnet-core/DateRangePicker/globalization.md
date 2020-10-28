---
layout: post
title: Globalization | DateRangePicker | ASP.NET Core | Syncfusion
description: globalization
platform: aspnet-core
control: DateRangePicker
documentation: ug
---

# Localization

DateRangePicker, has built in support with Localization. so, it allows users to use culture specified DateRangePicker component with their application using locale API.
Essential ASP.NET Core DateRangePicker has been provided with built-in localization support, so that it can adapt based on culture specific locale defined for it. 

More than 350 culture specific files are available to localize the DateRangePicker. To know more about EJ globalize support, please refer the below link      
 [http://help.syncfusion.com/js/localization](http://help.syncfusion.com/js/localization) 


N> Seven culture-specific script files are available in the below specified location. For all other culture files, please download from the [GitHub](https://github.com/syncfusion/ej-global/tree/master/i18n) location.

<table>
<tr>
<td>

    (installed location)\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets\scripts\i18n

    For example, If you have installed the Essential Studio package within C:\Program Files (x86), then navigate to the below location, 
    C:\Program Files (x86)\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets\scripts\i18n

</td></tr>
</table>
To translate our control content from default English to any of the culture, say For example - French language, then you need to refer the ej.culture.fr-FR.min.js file in your application,

The **en-US** locale is currently being used as default culture in **DateRangePicker**. You can set any other culture to DateRangePicker using **Locale** property. Below code example shows French cultured DateRangePicker.

Refer the below French culture file in head section of HTML page after the reference of **ej.web.all.min.js** file.

 {% highlight javascript %}
   
           <script src="https://cdn.syncfusion.com/js/assets/i18n/ej.culture.fr-FR.min.js"></script>
                
 {% endhighlight %}

If you want to change month names to your culture month just replace month names with your culture month names or your customized format.

The following example is used to set DateRangePicker in French language.

{% highlight javascript %}

    calendars: {
            standard: {
                '/': '/',
                ':': ':',
                firstDay: 1,
                days: {
                    names: ["dimanche","lundi","mardi","mercredi","jeudi","vendredi","samedi"],
                    namesAbbr: ["dim.","lun.","mar.","mer.","jeu.","ven.","sam."],
                    namesShort: ["di","lu","ma","me","je","ve","sa"]
                },
                months: {
                    names: ["janvier","février","mars","avril","mai","juin","juillet","août","septembre","octobre","novembre","décembre",""],
                    namesAbbr: ["janv.","févr.","mars","avr.","mai","juin","juil.","août","sept.","oct.","nov.","déc.",""]
                },
                AM: null,
                PM: null,
                eras: [{"name":"ap. J.-C.","start":null,"offset":0}],
                patterns: {
                    d: "dd/MM/yyyy",
                    D: "dddd d MMMM yyyy",
                    t: "HH:mm",
                    T: "HH:mm:ss",
                    f: "dddd d MMMM yyyy HH:mm",
                    F: "dddd d MMMM yyyy HH:mm:ss",
                    M: "d MMMM"
                }
            }
        }

{% endhighlight%}   

Add the following code in your CSHTML page to render DateRangePicker widget.

{% highlight cshtml %}

    @Html.EJ().DateRangePicker("DateRange").Locale("fr-FR").Width("25%")
    
{% endhighlight %}  

The following screenshot displays the output for the above code.

![](Globalization_images/globalization.png)

    Showcase for DateRangePicker with French culture
    {:.caption}
