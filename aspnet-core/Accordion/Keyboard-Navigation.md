---
layout: post
title: Keyboard Navigation | Accordion  | ASP.NET Core | Syncfusion
description: keyboard navigation	
platform: aspnet-core
control: Accordion 
documentation: ug
---

# Keyboard Navigation	

You can use Keyboard shortcut keys as an alternative to the mouse on using Accordion control using AllowKeyboardNavigation property. However you will have to focus the control to enable the keyboard navigation. Accordion Control allows you to perform all kind of actions using keyboard shortcuts.

<table>
<tr>
<th>
Shortcut Key</th><th>
Description</th></tr>
<tr>
<td>
{{ '[Access key](http://en.wikipedia.org/wiki/Access_key)' | markdownify }} + j	</td><td>
Focuses into the accordion control</td></tr>
<tr>
<td>
Up</td><td>
Moves to previous panel</td></tr>
<tr>
<td>
Down</td><td>
Moves to next panel</td></tr>
<tr>
<td>
Left</td><td>
Moves to previous panel</td></tr>
<tr>
<td>
Right</td><td>
Moves to next panel</td></tr>
<tr>
<td>
Home</td><td>
Moves to the first accordion panel</td></tr>
<tr>
<td>
End</td><td>
Moves to the last accordion panel</td></tr>
</table>

## Configure keyboard interaction

The following code explains you on how to enable keyboard interaction for an Accordion widget.

{% highlight CSHTML %}

// In the View page, configure Accordion with corresponding data and configure Keyboard navigation for Accordion by setting AllowKeyboardNavigation property to true.
<div style="width: 400px; float:left;">
<ej-accordion id="basicAccordion" allow-keyboard-navigation="true">
	<e-accordion-items>
		<e-accordion-item text="ASP.NET">
			<e-content-template>
				<div>
					Essential Chart for ASP.NET MVC is a visually stunning, high-performance charting component that is easy to use.
					It includes 35 chart types ranging from simple column charts to specialized financial charts.
					The charts are highly customizable and have a powerful data model that makes data binding simple.
				</div>
			</e-content-template>
		</e-accordion-item>
		<e-accordion-item text="ASP.NET MVC">
			<e-content-template>
				<div>
					The Model-View-Controller (MVC) architectural pattern separates an application into three main components:
					the model, the view, and the controller. The ASP.NET MVC framework provides an alternative to the ASP.NET Web Forms pattern for creating Web applications. The ASP.NET MVC framework is a lightweight, highly testable presentation framework that (as with Web Forms-based applications) is integrated with existing ASP.NET features, such as master pages and membership-based authentication.
				</div>
			</e-content-template>
		</e-accordion-item>
		<e-accordion-item text="Javascript">
			<e-content-template>
				<div>
					JavaScript (JS) is an interpreted computer programming language.
					It was originally implemented as part of web browsers so that client-side scripts could interact with the user, control the browser,
					communicate asynchronously, and alter the document content that was displayed. More recently, however,
					it has become common in both game development and the creation of desktop applications.
				</div>
			</e-content-template>
		</e-accordion-item>
	</e-accordion-items>
</ej-accordion>

{% endhighlight  %}

{% highlight js %}

// Define script to focus into the Accordion control on Alt + J shortcut keys.
<script>
    $(function () {  
		$(document).on("keydown", function (e) { 
			if (e.altKey && e.keyCode === 74) { // j- key code. 
				$("#accordion").focus(); 
			}        
		});
	});
</script>

{% endhighlight %}

Output for Accordion widget focused and navigated to last item using Keyboard navigation is as follows.

![](Keyboard-Navigation_images/Keyboard-Navigation_img1.png)