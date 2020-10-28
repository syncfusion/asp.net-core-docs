---
layout: post
title: Miscellaneous | ColorPicker | ASP.NET Core | Syncfusion
description: miscellaneous
platform: aspnet-core
control: ColorPicker
documentation: ug
---

# Miscellaneous

## getValue

The getValue() method in ColorPicker returns the hexadecimal value.

1. In the View page, configure the ColorPicker widget as follows.
{% tabs %}

{% highlight CSHTML %}

/*ej-Tag Helper code to render ColorPicker*/

@*In the CSHTML page, add the Html helpers to render ColorPicker widget*@
  <ej-color-picker id="colorPicker" value="#278787"> </ej-color-picker>

{% endhighlight  %}

{% highlight js %}
<script> 
  var ColorObj;
  jQuery(function ($) { 
	ColorObj = $("#colorPicker").ejColorPicker({ value: "#278787" }).data('ejColorPicker');
	ColorObj.getValue();  
  });
</script>

{% endhighlight  %}

{% endtabs %}  

{% highlight CSHTML%}

/*Razor code to render ColorPicker*/

	@{Html.EJ().ColorPicker("colorPicker").Render();}

{% endhighlight %}

N> To render the ColorPicker Control you can use either Razor or Tag helper code as given in the above code snippet.

## setValue

The setValue() method in ColorPicker is used to set the color value. The given value is in hexadecimal form.

1. In the CSHTML page, configure the ColorPicker widget as follows.
{% tabs %}

{% highlight CSHTML %}

/*ej-Tag Helper code to render ColorPicker*/

@*In the CSHTML page, add the Html helpers to render ColorPicker widget*@
  <ej-color-picker id="colorPicker"> </ej-color-picker>

{% endhighlight  %}

{% highlight js %}

 <script>  
	 var ColorObj;
	 jQuery(function ($) {  
	 ColorObj = $("#colorPicker").ejColorPicker().data('ejColorPicker'); 
	 ColorObj.setValue("#278787"); 
	 });
</script>

{% endhighlight  %}

{% endtabs %}

{% highlight CSHTML%}

/*Razor code to render ColorPicker*/

	@{Html.EJ().ColorPicker("colorPicker").Render();}

{% endhighlight %}

## getColor

The getColor() method in ColorPicker control returns the color value in r,g,b,a form.

1. In the CSHTML page, configure the ColorPicker widget as follows.
{% tabs %}

{% highlight CSHTML%}


@*In the CSHTML page, add the Html helpers to render ColorPicker widget*@ 

/*ej-Tag Helper code to render ColorPicker*/

 <ej-color-picker id="colorPicker" value="#278787"> </ej-color-picker>

{% endhighlight  %}

{% highlight js %}
 <script> 
	 var ColorObj; 
	 jQuery(function ($) { 
	 ColorObj = $("#colorPicker").ejColorPicker({value: "#278787" }).data('ejColorPicker'); 
	 ColorObj.getColor();
	 });
</script>


{% endhighlight  %}

{% endtabs %}  

{% highlight CSHTML%}

/*Razor code to render ColorPicker*/

@{Html.EJ().ColorPicker("colorPicker").Render();}

{% endhighlight %}