---
layout: post
title: Keyboard Interaction | ColorPicker | ASP.NET Core | Syncfusion
description: keyboard interaction
platform: aspnet-core
control: ColorPicker
documentation: ug
---

# Keyboard Interaction

You can use keyboard shortcut keys as an alternative to the mouse while using the ColorPicker widget. The ColorPicker widget allows you to perform all kinds of actions using keyboard shortcuts.

_Keyboard shortcut keys_

<table>
<tr>
<th>
Shortcut Key</th><th>
Description</th></tr>
<tr>
<td>
Alt + j               </td><td>
Focuses into the ColorPicker control</td></tr>
<tr>
<td>
Alt + Down</td><td>
Open / Close the Popup</td></tr>
<tr>
<td>
Up</td><td>
Increase the brightness value</td></tr>
<tr>
<td>
Down</td><td>
Decrease the brightness value</td></tr>
<tr>
<td>
Right</td><td>
Increase the saturation value</td></tr>
<tr>
<td>
Left</td><td>
Decrease the saturation value</td></tr>
<tr>
<td>
Enter</td><td>
Choose the current color</td></tr>
<tr>
<td>
Esc</td><td>
Closes the popup</td></tr>
<tr>
<td>
Tab</td><td>
Choose the next element</td></tr>
<tr>
<td>
Home</td><td>
Downwards to value 0</td></tr>
<tr>
<td>
End</td><td>
Upwards to value 100</td></tr>
</table>

## Configure Keyboard Interaction

The following steps explain how you can enable keyboard interaction for ColorPicker textbox.

1. In the CSHTML page, configure the ColorPicker widget and enable keyboard interaction by the access key property.
{% tabs %}

{% highlight CSHTML %}

/*ej-Tag Helper code to render ColorPicker*/

@*In the CSHTML page, add the Html helpers to render ColorPicker widget and enable keyboard interaction by the accesskey property*@
 <ej-color-picker id="colorPicker" value="#278787"> </ej-color-picker>

{% endhighlight  %}
{% highlight js %}
<script> 
   jQuery(function ($) {
   $(document).on("keydown", function (e) { 
		if (e.altKey && e.keyCode === 74) { // j- key code.    
			$("#colorPickerWrapper").focus();       
		}   
	});
  });
</script>

{% endhighlight  %}
{% endtabs %}  

{% highlight CSHTML %}

/*Razor code to render ColorPicker*/

	@{Html.EJ().ColorPicker("colorPicker).Value("#278787").Render();}

{% endhighlight  %}


N> To render the ColorPicker Control you can use either Razor or Tag helper code as given in the above code snippet.

The following screenshot displays the output of the above code example.



![](Keyboard-Interaction_images/Keyboard-Interaction_img1.png)

ColorPicker with Keyboard Navigation
{:.caption}
