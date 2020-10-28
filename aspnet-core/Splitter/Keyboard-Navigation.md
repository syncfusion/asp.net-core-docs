---
layout: post
title: Keyboard Navigation | Splitter | ASP.NET Core | Syncfusion
description: keyboard navigation
platform: aspnet-core
control: Splitter
documentation: ug
keywords: keyboard-navigation
---

# Keyboard Navigation

With the keyboard navigation enabled in the Splitter control, it is possible to control the actions of the Splitter with the provided shortcut keys. Almost all the Splitter actions that are done by mouse can be controlled with shortcut keys.

The various keyboard shortcuts available within the Splitter control are discussed in the following table.

_Keyboard Shortcuts_

<table>
<tr>
<th>
Shortcut Key</th><th>
Description</th></tr>
<tr>
<td>
Left</td><td>
Moves the Split bar left. </td></tr>
<tr>
<td>
Right</td><td>
Moves the Split bar right. </td></tr>
<tr>
<td>
Ctrl + Left</td><td>
Collapses the left pane.</td></tr>
<tr>
<td>
Ctrl + Right</td><td>
Collapses the right pane.</td></tr>
<tr>
<td>
Up</td><td>
Moves the Split bar up.</td></tr>
<tr>
<td>
Down</td><td>
Moves the Split bar down.</td></tr>
<tr>
<td>
Ctrl + Up</td><td>
Collapses the top pane.</td></tr>
<tr>
<td>
Ctrl + Down</td><td>
Collapses the bottom pane.</td></tr>
<tr>
<td>
Enter</td><td>
Resize the pane to the current Split bar position.</td></tr>
<tr>
<td>
Esc</td><td>
Focuses out from the Split bar.</td></tr>
</table>

## Configuring Keyboard Navigation

The following steps explain to enable keyboard interaction for Splitter widget.

1. In the View page add Splitter helper to render the control. 


{% highlight CSHTML %}
<ej-splitter id="outterSplitter" height="250" width="100%">
    <e-split-panes>
        <e-split-pane min-size="100">
            <e-content-template>

                <div>

                    <div style="padding: 0px 15px;">

                        <h3 class="h3">Tools </h3>

                        Essential Tools is a collection of user interface components used to create interactive ASP.NET MVC applications.

                    </div>

                </div>
            </e-content-template>
        </e-split-pane>
        <e-split-pane>
            <e-content-Template>
                <div>

                    <div style="padding: 0px 15px;">

                        <h3 class="h3">Grid </h3>

                        Essential MVC Grid offers full featured a Grid control with extensive support for Grouping and the display of hierarchical data.

                    </div>

                </div>
            </e-content-Template>
        </e-split-pane>
    </e-split-panes>
</ej-splitter>


<script type="text/javascript">
	//Control focus key
	$(document).on("keydown", function (e) {
	if (e.altKey && e.keyCode === 74) { // j- key code.
	$("#Splitter .e-splitbar")[0].focus();
	}
	});
</script>

{% endhighlight %}






1. Run the sample and press Alt + J to focus the Splitter widget. We can fully utilize the functionality of the splitter control by using keyboard shortcuts.



![](Keyboard-Navigation_images/Keyboard-Navigation_img1.png)



