---
layout: post
title: Keyboard Interaction | TimePicker | ASP.NET Core | Syncfusion
description: keyboard interaction
platform: aspnet-core
control: TimePicker
documentation: ug
---

# Keyboard Interaction

You can use Keyboard shortcut keys as an alternative to the mouse on using TimePicker widget. TimePicker widget allows you to perform all kinds of actions using keyboard shortcuts. For enabling the keyboard navigation, we need to set the access key to TimePicker control by using HtmlAttributes property. The HtmlAttributes receives the IDictionary object. The IDictionary represents a generic collection of key/value pairs.

The various keyboard shortcuts available within the TimePicker widget are discussed in the following table.

_List of keyboard shortcuts_

<table>
<tr>
<th>
Shortcut Key</th><th>
Description</th></tr>
<tr>
<td>
{{ '[Access key](http://en.wikipedia.org/wiki/Access_key)' | markdownify }} + j</td><td>
Focuses into Timepicker widget</td></tr>
<tr>
<td>
Alt + Down</td><td>
Opens/Hides the popup</td></tr>
<tr>
<td>
Right/Left</td><td>
Moves to adjacent part</td></tr>
<tr>
<td>
Up</td><td>
Increments the value</td></tr>
<tr>
<td>
Down</td><td>
Decrements the value</td></tr>
</table>


## When popup is open

_List of keyboard shortcuts_

<table>
<tr>
<th>
Shortcut Key</th><th>
Description</th></tr>
<tr>
<td>
Up</td><td>
Selects the previous time </td></tr>
<tr>
<td>
Down </td><td>
Selects the next time.</td></tr>
<tr>
<td>
Home/End</td><td>
Moves to the first / last item</td></tr>
<tr>
<td>
Esc</td><td>
Closes the popup</td></tr>
</table>


## Configure Keyboard Interaction

The following steps explains you on how to enable keyboard interaction for the TimePicker widget with access key as “j”. We can set the any other key as access key in TimePicker control.

1. Add the following code to the corresponding view page to render the TimePicker.


   ~~~ cshtml

   /*ej-Tag Helper code to render TimePicker*/

	@*Add the following code example to the corresponding CSHTML page to render TimePicker widget*@

	@{IDictionary<string, object> parameters = new Dictionary<string, object>();

		parameters.Add("accesskey", "j");

	}

	 <ej-time-picker id="time" html-attributes="parameters"></ej-time-picker>

   ~~~
   
{% highlight CSHTML%}

/*Razor code to render TimePicker*/

	@{Html.EJ().TimePicker("time").HtmlAttributes(parameters).Render(); }

{% endhighlight %}

N> To render the TimePicker Control you can use either Razor or Tag helper code as given in the above code snippet.


2. Run the code sample, press [Access key](http://en.wikipedia.org/wiki/Access_key) + J to focus in the TimePicker widget that enables it and you can navigate using arrow keys and Esc key to close the popup.



![](Keyboard-Interaction_images/Keyboard-Interaction_img1.png)

TimePicker focused with keyboard shortcut
{:.caption}



