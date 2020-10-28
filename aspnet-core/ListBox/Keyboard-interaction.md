---
layout: post
title: Keyboard interaction | ListBox | ASP.NET Core | Syncfusion
description: keyboard interaction
platform: aspnet-core
control: ListBox
documentation: ug
---

# Keyboard interaction

You can use Keyboard shortcut keys as an alternative to the mouse on using ListBox widget. ListBox Widget allows you to perform all kind of actions using keyboard shortcuts.

_Keyboard shortcut keys_

<table>
<tr>
<th>
Shortcut Key</th><th>
Description</th></tr>
<tr>
<td>
{{ '[Access key](http://en.wikipedia.org/wiki/Access_key)' | markdownify }} + j	</td><td>
Focuses into the ListBox text box</td></tr>
<tr>
<td>
Up</td><td>
Moves to previous item in the ListBox</td></tr>
<tr>
<td>
Down</td><td>
Moves to next item in the ListBox</td></tr>
<tr>
<td>
Enter</td><td>
Selects the focused item</td></tr>
<tr>
<td>
Left </td><td>
Moves to previous item in the ListBox</td></tr>
<tr>
<td>
Right </td><td>
Moves to next item in the ListBox</td></tr>
<tr>
<td>
Home</td><td>
Navigates to the starting item </td></tr>
<tr>
<td>
End</td><td>
Navigates to the end item </td></tr>
</table>
Configure keyboard interaction

The following steps explains you to enable keyboard interaction for a ListBox.

1. Add the below code in your page to render the ListBox


 {% highlight CSHTML %}

	// Add the following code in View page to configure ListBox widget
	<div id="control">  
		<h5 class="ctrllabel"> 
			Select a skill 
		</h5>
   <ej-list-box id="listboxsample" datasource="ViewBag.datasource" >
    <e-list-box-fields id="empid" text="text"/>
   </ej-list-box>  
	</div>
	
{% endhighlight %}
   

 {% highlight JS %}
   
	// Render ListBox control
	<script type="text/javascript">
		$(document).on("keydown", function (e) {
			if (e.altKey && e.keyCode === 74) { // j- key code. 
				var target = $('#listboxsample').data("ejListBox");
				target.selectItemByIndex(1);  
				$("#listboxsample_container").focus(); 
			}  
		});
	</script>


{% endhighlight %}
   


2. Run the sample, press Alt + J to focus in the ListBox widget that enables it and you can navigate using arrow keys.


![](Keyboard-interaction_images/Keyboard-interaction_img1.png)


