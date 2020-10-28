---
layout: post
title: Keyboard Navigation | Tab  | ASP.NET Core | Syncfusion
description: keyboard navigation
platform: aspnet-core
control: Tab 
documentation: ug
---

# Keyboard Navigation

The tab control provides support for keyboard interaction. Using this keyboard functionality you can interact with the control. It is achieved by enabling the **AllowKeyboardNavigation** to true. By default, this property value is set to true.

The following table illustrates the accessible keys and their usage:

<table>
<tr>
<th>
Keys</th><th>
Behavior</th></tr>
<tr>
<td>
Up</td><td>
Selects previous item.</td></tr>
<tr>
<td>
Right</td><td>
Selects previous item.</td></tr>
<tr>
<td>
Down</td><td>
Selects next item.</td></tr>
<tr>
<td>
Left</td><td>
Selects next item.</td></tr>
<tr>
<td>
Home</td><td>
Selects first item.</td></tr>
<tr>
<td>
End</td><td>
Selects last item.</td></tr>
</table>
The following code example is used to render the tab element with keyboard navigation.

1. Add the following code in your view page to render the tab with keyboard navigation.

{% highlight CSHTML %}

<div style="width: 500px">

	<ej-tab id="tab1" allow-keyboard-navigation="true">
		<e-tab-items>
			<e-tab-item id="pizzatype" text="Pizza Type">
				<e-content-template>
					<div>
						Pizza cooked to perfection tossed with milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.
					</div>
				</e-content-template>
			</e-tab-item>
			<e-tab-item id="sandwichtype" text="Sandwich Type">
				<e-content-template>
					<div>
						Sandwich cooked to perfection tossed with bread, milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.
					</div>
				</e-content-template>
			</e-tab-item>
		</e-tab-items>
	</ej-tab>

</div>

// Add the following script to render the tab with keyboard navigation.
	
<script type="text/javascript">
$(function () {
	//Control focus key
	$(document).on("keydown", function (e) {
		if (e.altKey && e.keyCode === 74) {
			// j- key code.
			$("#tab1 ul a").focus();
		}
	});
});
</script>

{% endhighlight %}

2. The following screenshot illustrates the tab with keyboard navigation.

![](Keyboard-Navigation_images/Keyboard-Navigation_img1.png)