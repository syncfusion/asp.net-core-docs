---
layout: post
title: Keyboard Interaction | AutoComplete | ASP.NET Core | Syncfusion
description: keyboard interaction
platform: aspnet-core
control: AutoComplete
documentation: ug
---

# Keyboard Interaction

You can use keyboard shortcut keys as an alternative to the mouse while using the AutoComplete widget. The AutoComplete widget allows you to perform all kinds of actions using keyboard shortcuts.

_Keyboard shortcut keys_

<table>
<tr>
<th>
Shortcut Key</th><th>
Description</th></tr>
<tr>
<td>
{{ '[Access key](http://en.wikipedia.org/wiki/Access_key)' | markdownify }} + j	</td><td>
Focuses into the AutoComplete text box</td></tr>
<tr>
<td>
Up</td><td>
Moves to previous item in pop up</td></tr>
<tr>
<td>
Down</td><td>
Moves to next item in pop up</td></tr>
<tr>
<td>
Enter</td><td>
Selects the focused item</td></tr>
<tr>
<td>
Esc</td><td>
Closes the popup</td></tr>
</table>


## Configure Keyboard Interaction

The following steps explain how you can enable keyboard interaction for an AutoComplete textbox.



1. In the View page, define the AutoComplete control.


{% highlight CSHTML %}

  <ej-autocomplete id="autocomplete" datasource="ViewBag.datasource">
                <e-autocomplete-fields text="Text" key="UniqueKey" />
 </ej-autocomplete>

 <script type="text/javascript" class="jsScript">
        $(function () {
            $(document).on("keydown", function (e) {
                if (e.altKey && e.keyCode === 74) { // j- key code.
                    $("#autocomplete").focus();
                }
            });
        });
</script>

{% endhighlight %}
   

2. Run the sample, press AccessKey + J to focus in the AutoComplete widget and you can navigate using the arrow keys. Use the Escape key to close the popup.



   ![](Keyboard-Interaction_images/Keyboard-Interaction_img1.png)

	AutoComplete focused with keyboard shortcut
	{:.caption}

