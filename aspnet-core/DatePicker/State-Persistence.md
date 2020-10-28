---
layout: post
title: State Persistence
description: DatePicker - State persistence support 
platform: aspnet-core
control: DatePicker
documentation: ug
---
# State Persistence

You can sustain the entire widget model of EJMVC DatePicker even after form post or browser refresh by using [EnablePersistence](http://help.syncfusion.com/js/api/ejdatepicker#members:enablepersistence) property. So the entire model values such as 

* Selected date
* Highlighted date
* Start and depth level 

are stored in local storage / cookies of browser before page refreshes and reinitialized with the restored model after refresh.


{% highlight cshtml %}

/*ej-Tag Helper code to render DatePicker*/

    @*persists the DatePicker model*@

    <ej-date-picker id="datepick" enable-persistence="true"></ej-date-picker>


{% endhighlight %}


{% highlight CSHTML%}

/*Razor code to render DatePicker*/

     @{Html.EJ().DatePicker("datepick").EnablePersistence(true).Render(); }

{% endhighlight %}

N> To render the DatePicker Control you can use either Razor or Tag helper code as given in the above code snippet.



