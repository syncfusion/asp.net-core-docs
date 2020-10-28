---
layout: post
title: Keyboard interaction | Rotator | ASP.NET Core | Syncfusion
description: keyboard interaction
platform: aspnet-core
control: Rotator
documentation: ug
---

# Keyboard interaction

The allow-keyboard-navigation property turns on keyboard interaction with the Rotator items. You must set this property to ‘true’ to access the keyboard shortcuts. The default value is ‘true’. The value set to this property is Boolean.

The entire Rotator commands are accessed through the keyboard by specifying the KeyboardShortcut in the following table.

<table>
<tr>
<th>
Keyboard Shortcut</th><th>
Function</th></tr>
<tr>
<td>
Alt + j</td><td>
Focuses the control</td></tr>
<tr>
<td>
Up/ Right</td><td>
Move to next slide</td></tr>
<tr>
<td>
Down/Left</td><td>
Move to previous slide.</td></tr>
<tr>
<td>
Space</td><td>
Move to Play/Pause slide.</td></tr>
<tr>
<td>
Alt + Right</td><td>
Move thumbnail item to right and select item.</td></tr>
<tr>
<td>
Alt + Left</td><td>
Move thumbnail item to left and select item.</td></tr>
<tr>
<td>
Enter</td><td>
Selected the thumbnail item</td></tr>
</table>

You can refer the following code example for keyboard navigation.

{% highlight CSHTML %}
// Add this code in your CSHTML page and refer local data section for binding Rotator items.

<ej-rotator id="rot" datasource="ViewBag.datasource" slide-height="350px"  is-responsive="true" allow-keyboard-navigation="true" show-play-button="true" show-thumbnail="true">
    <e-rotator-fields text="text" url="url" />
</ej-rotator>


<script type="text/JavaScript">


	$(function ()
	{

	//Control focus key

	$(document).on("keydown", function (e)
	{

		if (e.altKey && e.keyCode === 74)

		{

			// j- key code.

		    $("#rot")[0].focus();

		}

	});
	});

</script>

{% endhighlight %}

Run the above sample, we get the output like this,

![](Keyboard-interaction_images/Keyboard-interaction_img1.png)